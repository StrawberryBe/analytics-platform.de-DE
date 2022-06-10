---
title: Vergleichen von Adobe Analytics-Daten mit Customer Journey Analytics-Daten
description: Erfahren Sie, wie Sie Ihre Adobe Analytics-Daten mit Daten in Customer Journey Analytics vergleichen
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: ht
source-wordcount: '782'
ht-degree: 100%

---

# Vergleichen von Adobe Analytics-Daten mit Customer Journey Analytics-Daten

Wenn Ihr Unternehmen Customer Journey Analytics einsetzt, kann es bei den Daten zwischen Adobe Analytics und Customer Journey Analytics zu Unterschieden kommen. Dies ist normal und kann aus verschiedenen Gründen auftreten. CJA soll es Ihnen ermöglichen, einige Einschränkungen bei Daten in AA zu verbessern. Es können jedoch unerwartete/unbeabsichtigte Diskrepanzen auftreten. Dieser Artikel soll Ihnen dabei helfen, diese Unterschiede zu diagnostizieren und zu beheben, damit Sie und Ihr Team CJA ohne Beeinträchtigung der Datenintegrität verwenden können.

Nehmen wir an, Sie haben Adobe Analytics-Daten über den [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) in AEP aufgenommen und dann mit diesem Datensatz eine CJA-Verbindung erstellt.

![Datenfluss](assets/compare.png)

Als Nächstes haben Sie eine Datenansicht erstellt und anschließend Reporting zu diesen Daten in Customer Journey Analytics durchgeführt. Dabei wurden Abweichungen bei den Berichtsergebnissen in Adobe Analytics festgestellt.

Im Folgenden finden Sie einige Schritte zum Vergleich Ihrer ursprünglichen Adobe Analytics-Daten mit den Adobe Analytics-Daten, die sich jetzt in Customer Journey Analytics befinden.

## Voraussetzungen

* Stellen Sie sicher, dass der Analytics-Datensatz in AEP Daten für den zu untersuchenden Datumsbereich enthält.

* Stellen Sie sicher, dass die in Analytics ausgewählte Report Suite mit der in Adobe Experience Platform aufgenommenen Report Suite übereinstimmt.

## Schritt 1: Metrik „Vorfälle“ in Adobe Analytics ausführen

Die Metrik [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de) zeigt die Anzahl der Treffer an, bei denen eine bestimmte Dimension festgelegt oder beibehalten wurde.

1. Ziehen Sie in Analytics unter [!UICONTROL Arbeitsbereich] den Datumsbereich, für den Sie einen Bericht erstellen möchten, als Dimension in eine [!UICONTROL Freiform]-Tabelle.

1. Die Metrik [!UICONTROL Vorfälle] wird automatisch auf diesen Datumsbereich angewendet.

1. Speichern Sie dieses Projekt, damit Sie es im Vergleich verwenden können.

## Schritt 2: Ergebnisse in CJA mit den [!UICONTROL Datensätzen insgesamt nach Zeitstempeln] vergleichen

Vergleichen Sie nun die [!UICONTROL Vorfälle] in Analytics mit der Gesamtzahl der Datensätze nach Zeitstempeln in Customer Journey Analytics.

Die Gesamtzahl der Datensätze nach Zeitstempeln sollten mit der der Vorfälle übereinstimmen, sofern keine Datensätze vom Analytics-Quell-Connector ignoriert wurden (siehe folgenden Abschnitt).

>[!NOTE]
>
>Dies funktioniert nur für normale Mittelwert-Datensätze, nicht für zugeordnete Datensätze (über [Cross-Channel Analytics](/help/connections/cca/overview.md)). Beachten Sie, dass die Berücksichtigung der in CJA verwendeten Personen-ID für die Durchführung des Vergleichs von entscheidender Bedeutung ist. Dies ist möglicherweise nicht immer einfach in AA zu replizieren, insbesondere wenn Cross-Channel Analytics aktiviert ist.

1. Führen Sie in [Abfrage-Services](https://experienceleague.adobe.com/docs/experience-platform/query/best-practices/adobe-analytics.html?lang=de) von Adobe Experience Platform die folgende Abfrage zu [!UICONTROL Datensätzen insgesamt nach Zeitstempeln] aus:

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

1. Stellen Sie in den [Analytics-Daten-Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de) anhand der Rohdaten fest, ob einige Zeilen möglicherweise vom Analytics-Quell-Connector gelöscht wurden.

   Der [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) kann beim Konvertieren in das XDM-Schema Zeilen ignorieren. Es kann mehrere Gründe dafür geben, dass die gesamte Zeile nicht für eine Umwandlung geeignet ist. Wenn eines der folgenden Analytics-Felder diese Werte aufweist, wird die gesamte Zeile ignoriert.

   | Analytics-Feld | Werte, die zum Ignorieren führen |
   | --- | --- |
   | Opt_out | `y, Y` |
   | In_data_only | Nicht 0 |
   | Exclude_hit | Nicht 0 |
   | Bot_id | Nicht 0 |
   | Hit_source | 0,3,5,7,8,9,10 |
   | Page_event | 53,63 |

1. Wenn der Connector Zeilen ignoriert hat, ziehen Sie diese Zeilen von der Metrik [!UICONTROL Vorfälle] ab. Die resultierende Zahl sollte mit der Anzahl der Ereignisse in den Adobe Experience Platform-Datensätzen übereinstimmen.

## Warum Datensätze während der Aufnahme aus AEP möglicherweise ignoriert oder übersprungen werden

[Verbindungen](/help/connections/create-connection.md) in CJA ermöglichen es Ihnen, mehrere Datensätze zusammenzuführen und miteinander zu verbinden, basierend auf einer gemeinsamen Personen-ID über die Datensätze hinweg. Im Backend wird Deduplizierung angewendet: ein vollständiger äußerer Join oder eine Vereinigung für Ereignis-Datensätze basierend auf Zeitstempeln und dann ein innerer Join in Profil- und Lookup-Datensatz basierend auf der Personen-ID.

Im Folgenden finden Sie einige Gründe, warum Datensätze bei der Aufnahme von Daten aus AEP übersprungen werden können.

* **Fehlende Zeitstempel** – Wenn Zeitstempel in Ereignis-Datensätzen fehlen, werden diese Datensätze bei der Aufnahme vollständig ignoriert oder übersprungen.

* **Fehlende Personen-IDs** – Fehlende Personen-IDs (aus dem Ereignis-Datensatz und/oder aus dem Profil-/Lookup-Datensatz) führen dazu, dass diese Datensätze ignoriert oder übersprungen werden. Der Grund dafür ist, dass es keine gemeinsamen IDs oder übereinstimmenden Schlüssel zum Verbinden der Datensätze gibt.

* **Ungültige oder zu große Personen-IDs** – Bei ungültigen IDs kann das System keine gültige gemeinsame ID unter den Datensätzen finden, die verbunden werden sollen. In einigen Fällen weist die Spalte mit der Personen-ID ungültige Personen-IDs auf, z. B. „undefiniert“ oder „00000000“. Eine Personen-ID (mit beliebiger Kombination aus Zahlen und Buchstaben), die in einem Ereignis angezeigt wird, das mehr als eine Million Mal pro Monat stattfindet, kann keinem bestimmten Benutzer bzw. keiner bestimmten Person zugeordnet werden. Sie wird als ungültig kategorisiert. Solche Datensätze können nicht in das System aufgenommen werden und würden zu Fehlern bei Datenaufnahme und Reporting führen.
