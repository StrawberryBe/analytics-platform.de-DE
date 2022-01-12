---
title: AA-Daten mit CJA-Daten vergleichen
description: Erfahren Sie, wie Sie Ihre Adobe Analytics-Daten mit Daten in Customer Journey Analytics vergleichen.
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
source-git-commit: b22592a13a6b60144d2021a08060e9929c7f619a
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 4%

---


# Adobe Analytics-Daten mit CJA-Daten vergleichen

Nehmen wir an, Sie haben Adobe Analytics-Daten über Analytics Source Connector in AEP aufgenommen und dann eine CJA-Verbindung mit diesem Datensatz erstellt.

![Datenfluss](assets/compare.png)

Als Nächstes haben Sie eine Datenansicht erstellt und anschließend über diese Daten in Customer Journey Analytics berichtet. Es wurden Abweichungen bei den Berichtsergebnissen in Adobe Analytics festgestellt.

Im Folgenden finden Sie einige Schritte zum Vergleich Ihrer ursprünglichen Adobe Analytics-Daten mit den Adobe Analytics-Daten, die sich jetzt im Customer Journey Analytics befinden.

## Voraussetzungen

* Stellen Sie sicher, dass der Analytics-Datensatz in AEP Daten für den zu untersuchenden Datumsbereich enthält.

* Stellen Sie sicher, dass die in Analytics ausgewählte Report Suite mit der in Adobe Experience Platform erfassten Report Suite übereinstimmt.


## Schritt 1: Metrik &quot;Vorfälle&quot;in Adobe Analytics ausführen

Die [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de) zeigt die Anzahl der Treffer an, bei denen eine bestimmte Dimension festgelegt oder beibehalten wurde.

1. In Analytics > [!UICONTROL Arbeitsbereich], ziehen Sie den Datumsbereich, für den Sie einen Bericht erstellen möchten, als Dimension in eine [!UICONTROL Freiform] Tabelle.

1. Die [!UICONTROL Vorfälle] wird automatisch auf diesen Datumsbereich angewendet.

1. Speichern Sie dieses Projekt, damit Sie es im Vergleich verwenden können.

## Schritt 2: Ergebnisse vergleichen mit [!UICONTROL Datensätze insgesamt nach Zeitstempeln] in CJA

Vergleichen Sie nun die [!UICONTROL Vorfälle] in Analytics in die Gesamtzahl der Datensätze nach Zeitstempeln in Customer Journey Analytics.

Datensätze insgesamt nach Zeitstempeln sollten mit Vorfällen übereinstimmen, sofern keine Datensätze vom Analytics Source Connector abgelegt wurden - siehe folgenden Abschnitt.

>[!NOTE]
>
>Dies funktioniert nur für normale Mid-Werte-Datensätze, nicht für zugeordnete Datensätze (über [Kanalübergreifende Analyse](\help/connections/cca/overview.md)). Beachten Sie, dass die Berücksichtigung der in CJA verwendeten Personen-ID für die Durchführung des Vergleichs von entscheidender Bedeutung ist. Dies ist möglicherweise nicht immer einfach in AA zu replizieren, insbesondere wenn die kanalübergreifende Analyse aktiviert ist.

1. In Adobe Experience Platform [Query Services](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html)führen Sie die folgenden Datensätze insgesamt nach Zeitstempelabfrage aus:

```
SELECT Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) as Day, \ 
        Count(_id) AS Records 
        FROM  {dataset} \ 
        WHERE timestamp>=from_utc_timestamp('{fromDate}','UTC') \ 
        AND timestamp<from_utc_timestamp('{toDate}','UTC') \ 
        AND timestamp IS NOT NULL \ 
        AND enduserids._experience.aaid.id IS NOT NULL  \ 
        GROUP BY Day \ 
        ORDER BY Day; 
```

1. In [Analytics-Daten-Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de)anhand der Rohdaten erkennen, ob einige Zeilen vom Analytics-Quell-Connector möglicherweise gelöscht werden.

   Die [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) kann beim Konvertieren in das XDM-Schema Zeilen löschen. Es kann mehrere Gründe dafür geben, dass die gesamte Zeile für die Umwandlung nicht geeignet ist. Wenn eines der folgenden Analytics-Felder diese Werte aufweist, wird die gesamte Zeile abgelegt.

   | Analytics-Feld | Werte, die dazu führen, dass sie gelöscht werden |
   | --- | --- |
   | Opt_out | `y, Y` |
   | In_data_only | not 0 |
   | Exclude_hit | not 0 |
   | Bot_id | not 0 |
   | Hit_source | 0,3,5,7,8,9,10 |
   | Page_event | 53,63 |

1. Wenn der Connector Zeilen abgelegt hat, ziehen Sie diese Zeilen von der Metrik Vorfälle ab. Die resultierende Zahl sollte mit der Anzahl der Ereignisse in den AEP-Datensätzen übereinstimmen.

## Warum Datensätze während der Aufnahme aus AEP möglicherweise gelöscht oder übersprungen werden

CJA [Verbindungen](\help/connections/create-connection.md) ermöglichen es Ihnen, mehrere Datensätze zusammenzuführen und miteinander zu verbinden, basierend auf einer gemeinsamen Personen-ID über die Datensätze hinweg. Im Backend wird Deduplizierung angewendet: vollständiger äußere Join oder Vereinigung für Ereignis-Datensätze basierend auf Zeitstempeln und dann innerer Join in Profil- und Lookup-Datensatz, basierend auf der Personen-ID.

Im Folgenden finden Sie einige Gründe, warum Datensätze bei der Aufnahme von Daten aus AEP übersprungen werden können.

* **Fehlende Zeitstempel** - Wenn Zeitstempel in Ereignis-Datensätzen fehlen, werden diese Datensätze bei der Erfassung vollständig ignoriert oder übersprungen. weil sie eine Vereinigung des Datensatzes ermöglichen würden.

* **Fehlende Personen-IDs** - Fehlende Personen-IDs (aus dem Ereignis-Datensatz und/oder aus Profil-/Lookup-Datensatz) führen dazu, dass diese Datensätze ignoriert oder übersprungen werden. Der Grund dafür ist, dass es keine gemeinsamen IDs oder übereinstimmenden Schlüssel zum Verbinden der Datensätze gibt.

* **Ungültige Personen-IDs** - Bei ungültigen IDs kann das System keine gültige gemeinsame ID unter den Datensätzen finden, die hinzugefügt werden sollen. In einigen Fällen weist die Spalte mit der Personen-ID ungültige Personen-IDs auf, z. B. &quot;undefiniert&quot;oder &quot;0000000&quot;.

* **Große Personen-ID** - Eine Personen-ID mit einer beliebigen Kombination von Zahlen und Buchstaben, die in einem Ereignis angezeigt wird, das mehr als eine Million Mal pro Monat stattfindet, kann keinem bestimmten Benutzer oder einer bestimmten Person zugeordnet werden. Sie wird als ungültig kategorisiert. Diese Datensätze können nicht in das System aufgenommen werden und führen zu fehleranfälliger Erfassung und Berichterstellung.


