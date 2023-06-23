---
title: FAQ zu Customer Journey Analytics
description: Customer Journey Analytics – häufig gestellte Fragen.
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
source-git-commit: cf11fa76503e700c07de7872b5f6c8a73b1d94d1
workflow-type: tm+mt
source-wordcount: '2210'
ht-degree: 72%

---

# Häufig gestellte Fragen

Adobe Customer Journey Analytics ist ein Analytics-Produkt der nächsten Generation. Im Folgenden finden Sie Antworten auf häufig gestellte Fragen zum Customer Journey Analytics. Weitere Informationen finden Sie unter [Customer Journey Analytics-Funktionsunterstützung](/help/getting-started/aa-vs-cja/cja-aa.md).

## 1. Voraussetzungen {#prerequisites}

+++**Benötige ich [!UICONTROL Private Device Graph] oder [!UICONTROL Device Coop] für [!UICONTROL Customer Journey Analytics]?**

Nein, [!UICONTROL Private Device Graph] oder [!UICONTROL Device Coop] sind für [!UICONTROL Customer Journey Analytics] nicht erforderlich. Sie werden aktuell noch nicht unterstützt.

+++


+++**Benötige ich eine [!UICONTROL Experience Cloud ID] (ECID) für [!UICONTROL Customer Journey Analytics]?**

Nein, [!UICONTROL Customer Journey Analytics] unterstützt alle IDs in einem Datensatz, unabhängig davon, ob es sich um eine [!UICONTROL ECID] oder eine andere ID handelt.

+++


+++**Wie gehe ich vor, wenn ich meine Daten vor [!UICONTROL Customer Journey Analytics] einem ETL-Prozess (Extract, Transform, Load) unterziehen muss?**

Customer Journey Analytics enthält Funktionen zur [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=de), mit denen Ihre Daten transformiert werden, bevor Sie in den Data Lake von Adobe Experience Platform überschrieben werden. Wenn Sie einen ETL-Prozess benötigen, nachdem die Daten aufgenommen wurden, stehen Ihnen über den [Abfrage-Service von Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=de#queries) einige begrenzte Optionen zur Verfügung. Hierfür könnten jedoch zusätzliche Gebühren anfallen.

+++


## 2. Daten zusammenfügen (Cross-Channel-Analyse) {#stitching}

+++**Kann [!UICONTROL Customer Journey Analytics] Daten über Geräte oder über Datensätze hinweg zusammenfügen?**

Ja. [!UICONTROL Customer Journey Analytics] verfügt über eine Lösung zum Zusammenfügen (Stitching) von Daten namens [Cross-Channel-Analyse](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=de) (CCA). Damit können Sie die Personen-ID eines Datensatzes neu eingeben, was eine nahtlose Kombination mehrerer Datensätze ermöglicht.

+++


+++**Wird das Zusammenfügen von anonymen Verhaltens- mit authentifizierten Verhaltensdaten unterstützt?**

Ja. Die [Cross-Channel-Analyse](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=de) untersucht Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen und generiert eine zusammengefügte ID.

+++


+++**Wie funktioniert „Replay“ in CCA?**

CCA gibt Daten basierend auf eindeutigen Kennungen wieder, die CCA gelernt hat. Bei einem Replay werden zu einer Verbindung neu hinzugefügte Geräte per Stitching zusammengefügt. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=de#step-1%3A-live-stitching)

+++


+++**Wie funktioniert das Zusammenfügen historischer Daten (Aufstockung) in CCA?**

Bei der erstmaligen Aktivierung stellt Adobe eine Aufstockung der zusammengefügten Daten bereit, die bis zum Beginn des Vormonats zurückreicht (bis zu 60 Tage). Um diese Aufstockung durchführen zu können, muss die vorübergehende ID in den nicht zusammengefügten Daten aus dem so weit zurückreichenden Zeitfenster vorhanden sein. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=de#enable-cross-channel-analytics)

+++


+++**Welches Verhalten wird für nicht zugeordnete Profil-Datensatzdatensätze erwartet?**

**Beispielszenario**: Sie fügen zwei Datensätze in einer Customer Journey Analytics-Verbindung ein, indem Sie `CRMid` als Personen-ID. Einer ist ein Web-Ereignis-Datensatz mit `CRMid` in allen Datensätzen. Der andere Datensatz ist ein CRM-Profildatensatz. 40 % des CRM-Datensatzes verfügen über `CRMid` im Webereignis-Datensatz vorhanden. Für die anderen 60 % ist es nicht im CRM-Datensatz vorhanden. Werden diese Datensätze im Reporting in Analysis Workspace angezeigt?<p> **Antwort**: Profilzeilen, für die keine Ereignisse verknüpft sind, werden in Customer Journey Analytics gespeichert. Sie können sie jedoch erst dann in Analysis Workspace sehen, wenn ein mit dieser ID verknüpftes Ereignis angezeigt wird.

+++

## 3. Daten in [!UICONTROL Customer Journey Analytics] einbringen {#ingest}

+++**Kann ich Daten aus verschiedenen [!UICONTROL Adobe Experience Platform]-Sandboxen in einer [!UICONTROL Customer Journey Analytics]-Verbindung kombinieren?**

Nein, Sie können nicht über Sandboxes hinweg auf Daten zugreifen. Sie können nur Datensätze kombinieren, die sich innerhalb derselben Sandbox befinden. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de#select-sandbox-and-datasets)

+++


+++**Wie werden in [!UICONTROL Customer Journey Analytics] Online-Daten mit Offline-Daten verbunden?**

Solange die Personen-ID zwischen Datensätzen übereinstimmt, kann [!UICONTROL Customer Journey Analytics] Filter, Attributionen, Flüsse, Fallout usw. verbinden. über Datensätze hinweg miteinander verbinden.

+++


+++**Wie integriere ich meine Offline-Daten in [!UICONTROL Customer Journey Analytics]?**

Mit Ihrer Berechtigung zur Nutzung von Customer Journey Analytics können Sie Daten in Experience Platform aufnehmen. Sie können dann zu diesen Daten und Datenansichten in [!UICONTROL Customer Journey Analytics] Verbindungen herstellen, um in Analysis Workspace Berichte zu generieren. Das Datenerfassungs-Team von Experience Platform bietet bei Bedarf Empfehlungen oder eine Beratung für Sie an.

+++


+++**Wie integriere ich [!UICONTROL Adobe Analytics]-Daten in [!UICONTROL Customer Journey Analytics]?**

[!UICONTROL Adobe Analytics]-Daten können über [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) mit Experience Platform verbunden werden. Die meisten [!UICONTROL Adobe Analytics]-Felder werden im XDM-Format übermittelt, andere Felder sind aber noch nicht verfügbar.

+++


+++**Wie lange dauert es, bis Datensatzelemente in einer Datenansicht zusammengefasst sind?**

Ein paar Stunden für eine erste Ansicht und ein paar Tage, um die Daten der letzten 13 Monate aufzustocken.

+++


+++**Sind PII-Daten notwendig, um Verbindungen zwischen den Daten herzustellen?**

Nein, Sie können eine beliebige ID verwenden, einschließlich eines Hash einer Kunden-ID, bei der es sich nicht um personenbezogene Daten handelt.

+++


+++**Welche Beschränkungen gibt es für die Aufnahme vergangener oder künftiger Daten/Zeitstempel in Customer Journey Analytics-Ereignisdatensätze?**

<ul><li>Für vergangene Daten/Zeitstempel: bis zu 10 Jahre alte Ereignisdaten.</li><li>Für zukünftige Daten/Zeitstempel: Ereignisdaten (prädiktiv) bis zu einem Monat in der Zukunft.</li></ul>

+++


## 4. Latenzaspekte {#latency}

>[!NOTE]
>Es gibt keine feste Datengröße im Customer Journey Analytics und daher kann die Adobe nicht auf eine standardmäßige Erfassungszeit übertragen werden. Wir arbeiten aktiv daran, diese Latenzen durch neue Updates und Aufnahmeoptimierung zu reduzieren.

+++**Wie hoch ist die erwartete Latenz? [!UICONTROL Customer Journey Analytics] Daten zu [!UICONTROL Adobe Experience Platform]?**

Wir haben kürzlich die Verarbeitung von Daten in Customer Journey Analytics geändert:

<ul><li>Alle Ereignisdaten mit einem Zeitstempel unter 24 Stunden werden gestreamt.</li><li>Alle Ereignisdaten mit einem Zeitstempel, der älter als 24 Stunden ist (auch wenn sie sich im gleichen Batch wie neuere Daten befinden) werden als Aufstockung betrachtet und mit einer niedrigeren Priorität erfasst.</li></ul>

<ul><li>Live-Daten oder -Ereignisse: Wird innerhalb von 90 Minuten verarbeitet und erfasst, sobald Daten in Adobe Experience Platform verfügbar sind. (Batch-Größe &gt; 50 Millionen Zeilen: länger als 90 Minuten.)</li><li>Kleine Aufstockungen – z. B. ein Lookup-Datensatz mit 10 Millionen Zeilen: innerhalb von 7 Tagen<li>Große Aufstockungen – z. B. 500 Milliarden Zeilen: 30 Tage</li></ul>


+++

## 5. Festlegen eines rollierenden Fensters für die [!UICONTROL Verbindungs]-Datenspeicherung {#data-retention}

Die [**[!UICONTROL Rollierendes Datenfenster aktivieren ]**Einstellung](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de#create-connection) ermöglicht die Definition der Aufbewahrung von Customer Journey Analytics-Daten als rollierendes Fenster in Monaten (3 Monate, 6 Monate usw.). Sie wird auf einer [!UICONTROL Verbindungs]-Ebene, nicht auf einer [!UICONTROL Datensatz]-Ebene festgelegt. Die Datenaufbewahrung basiert auf Zeitstempeln für Ereignis-Datensätze und gilt nur für Ereignis-Datensätze. Für Profil- oder Lookup-Datensätze gibt es keine Datenspeicherungseinstellung, da keine entsprechenden Zeitstempel vorhanden sind.

Der Hauptvorteil besteht darin, dass Sie nur Daten speichern oder Berichte dazu erstellen, die anwendbar und nützlich sind, und ältere Daten löschen, die nicht mehr nützlich sind. Dies hilft Ihnen, Ihre vertraglichen Beschränkungen einzuhalten und das Risiko bezüglich Kostendeckung zu reduzieren.

## 6. Auswirkungen des Löschens von Datenkomponenten {#deletion}

In Bezug auf das Löschen von Daten sollten folgende sechs Komponenten beachtet werden: Sandbox, Schema, Datensatz, Verbindung, Datenansicht und Arbeitsbereich-Projekte. Im Folgenden sind einige Szenarien für das Löschen der jeweiligen Komponenten aufgeführt:

| Aktion | Auswirkung |
| --- | --- |
| Löschen einer Sandbox in [!UICONTROL Adobe Experience Platform] | Durch das Löschen einer Sandbox wird der Datenfluss aller [!UICONTROL Customer Journey Analytics]-Verbindungen zu Datensätzen in dieser Sandbox angehalten. Zurzeit [!UICONTROL Verbindungen] im Customer Journey Analytics, der mit der gelöschten Sandbox verknüpft ist, werden nicht automatisch gelöscht. |
| Löschen eines Schemas in [!UICONTROL Adobe Experience Platform], aber nicht der mit diesem Schema verbundenen Datensätze | [!UICONTROL Adobe Experience Platform] erlaubt nicht das Löschen von [!UICONTROL Schemata], denen ein oder mehrere [!UICONTROL Datensätze] zugeordnet sind. Ein Administrator mit den entsprechenden Berechtigungen kann jedoch zuerst die Datensätze und dann das Schema löschen. |
| Löschen eines Datensatzes im Data Lake von [!UICONTROL Adobe Experience Platform] | Durch das Löschen eines Datensatzes in Adobe Experience Platform Data Lake wird der Datenfluss von diesem Datensatz zu allen Customer Journey Analytics-Verbindungen, die diesen Datensatz enthalten, angehalten. Alle Daten aus diesem Datensatz werden automatisch aus den verknüpften Customer Journey Analytics-Verbindungen gelöscht. |
| Löschen eines Datensatzes in [!UICONTROL Customer Journey Analytics] | Wenden Sie sich an Ihr Adobe-Kundenbetreuungsteam, um den Prozess zum Löschen eines Datensatzes innerhalb einer gespeicherten Verbindung in Gang zu setzen. |
| Löschen von einem Batch aus einem Datensatz (in [!UICONTROL Adobe Experience Platform]) | Wenn ein Batch aus einem [!UICONTROL Adobe Experience Platform] Datensatz, wird derselbe Batch aus allen Customer Journey Analytics-Verbindungen entfernt, die diesen Batch enthalten.  Customer Journey Analytics wird über das Löschen von Batches in [!UICONTROL Adobe Experience Platform]. |
| Löschen von einem Batch, **während er** in [!UICONTROL Customer Journey Analytics] aufgenommen wird | Wenn in dem Datensatz nur ein Batch vorhanden ist, erscheinen keine Daten oder nur teilweise Daten aus diesem Batch in [!UICONTROL Customer Journey Analytics]. Die Aufnahme wird zurückgesetzt. Wenn beispielsweise 5 Batches im Datensatz vorhanden sind und 3 davon bereits erfasst wurden, als der Datensatz gelöscht wurde, werden Daten aus diesen 3 Batches in [!UICONTROL Customer Journey Analytics]. |
| Löschen einer Verbindung in [!UICONTROL Customer Journey Analytics] | Eine Fehlermeldung weist darauf hin, dass<ul><li>für die gelöschte Verbindung erstellte Datenansichten nicht mehr funktionieren.</li><li> Ebenso funktionieren alle Arbeitsbereich-Projekte nicht mehr, die von den Datenansichten der gelöschten Verbindung abhängig sind.</li></ul> |
| Löschen einer Datenansicht in [!UICONTROL Customer Journey Analytics] | Eine Fehlermeldung weist darauf hin, dass alle Workspace-Projekte, die von dieser gelöschten Datenansicht abhängig sind, nicht mehr funktionieren. |

## 7. Überlegungen beim Zusammenführen von Report Suites in Customer Journey Analytics {#merge-reportsuite}

Wenn Sie planen, Adobe Analytics-Daten über den [Adobe Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) zu erfassen, sollten Sie diese Auswirkungen beim Zusammenführen von 2 oder mehr Adobe Analytics-Report Suites berücksichtigen.

| Problem | Hinweis |
| --- | --- |
| Variablen | Variablen wie [!UICONTROL eVars] werden möglicherweise nicht in allen Report Suites angezeigt. Beispielsweise kann eVar1 in Report Suite 1 auf **[!UICONTROL Seite]** verweisen. In Report Suite 2 kann eVar1 auf **[!UICONTROL Interne Kampagne]** verweisen, was zu gemischten und ungenauen Berichten führt. |
| Zahlen für [!UICONTROL Sitzungen] und [!UICONTROL Personen] | Sie werden über Report Suites hinweg dedupliziert. Daher stimmen die Zahlen möglicherweise nicht überein. |
| Deduplizierung von Metriken | Dedupliziert Instanzen einer Metrik (z. B. [!UICONTROL Bestellungen]), wenn mehrere Zeilen dieselbe Transaktions-ID aufweisen (z. B. [!UICONTROL Kauf-ID]). Dadurch wird verhindert, dass Schlüsselmetriken zu häufig gezählt werden. Daher sind die Summen von Metriken wie [!UICONTROL Bestellungen] möglicherweise nicht über Report Suites hinweg korrekt. |
| Währung | Die Währungsumrechnung wird in Customer Journey Analytics noch nicht unterstützt. Wenn die Report Suites, die Sie zusammenführen möchten, unterschiedliche Basiswährungen verwenden, können Probleme auftreten. |
| [!UICONTROL Persistenz] | [Persistenz](../data-views/component-settings/persistence.md) erstreckt sich über Report Suites hinweg, was sich auf [!UICONTROL Filter], [!UICONTROL Attribution] usw. auswirkt. Zahlen werden möglicherweise nicht richtig addiert. |
| [!UICONTROL Klassifizierungen] | [!UICONTROL Klassifizierungen] werden beim Zusammenführen von Report Suites nicht automatisch dedupliziert. Beim Kombinieren mehrerer Klassifizierungsdateien zu einer [!UICONTROL Nachschlagen] -Datensatz, können Probleme auftreten. |

## 8. [!UICONTROL Adobe Analytics] Komponenten

+++**Kann ich freigeben/veröffentlichen? [!UICONTROL Filter] von [!DNL Customer Journey Analytics] Experience Platform Real-Time CDP oder anderen Experience Cloud-Applikationen?**

Noch nicht, wir arbeiten aber aktuell daran, diese Funktion bald bereitstellen zu können.

+++

+++**Was ist mit meiner alten [!UICONTROL eVar]-Einstellung passiert?**

[!UICONTROL eVars], [!UICONTROL props]und [!UICONTROL events] im Sinne von Adobe Analytics gibt es in [!UICONTROL Customer Journey Analytics]. Es gibt unbegrenzte Schemaelemente (Dimensionen, Metriken, Listenfelder). Alle Zuordnungseinstellungen, die Sie bisher während des Datenerfassungsprozesses angewendet haben, werden jetzt bei der Abfrage angewendet.

+++

+++**Wo sind jetzt meine Einstellungen für die Sitzungs- und Variablenpersistenz?**

[!UICONTROL Customer Journey Analytics] wendet alle diese Einstellungen zur Berichtszeit an, und diese Einstellungen sind jetzt in Datenansichten verfügbar. Änderungen an diesen Einstellungen sind jetzt rückwirkend. Sie können mehrere Versionen verwenden, indem Sie mehrere Datenansichten verwenden!

+++

+++**Was passiert mit den bereits vorhandenen Segmenten/berechneten Metriken?**

[!UICONTROL Customer Journey Analytics] verwendet keine eVars, Props oder Ereignisse mehr und verwendet stattdessen ein Adobe Experience Platform-Schema. Das bedeutet, dass keine der vorhandenen Segmente oder Berechnungsmetriken mit [!UICONTROL Customer Journey Analytics] kompatibel sind.

+++

+++**Wie werden in [!UICONTROL Customer Journey Analytics] `Uniques Exceeded`-Einschränkungen behandelt?**

In [!UICONTROL Customer Journey Analytics] gibt es keine Beschränkungen hinsichtlich eindeutiger Werte, sodass Sie sie nicht beachten müssen.

+++

+++**Kann ich als bestehender [!DNL Data Workbench]-Kunde jetzt zu [!UICONTROL Customer Journey Analytics] wechseln?**

Das hängt von Ihrem Anwendungsfall ab. Bitte wenden Sie sich an Ihr Adobe Account Team. Möglicherweise eignen sich Ihre aktuellen Anwendungsfälle gut für Customer Journey Analytics.

+++

## 9. Verbindungsgröße schätzen {#estimate-size}

Siehe [Schätzen und Verwalten der Nutzung](/help/admin/estimate-usage.md).

## 10. Über die Limits bei der Verwendung {#overage}

Nutzungsbeschränkungen werden von Adobe regelmäßig überwacht und durchgesetzt. „Datenzeilen“ sind die täglichen durchschnittlichen Datenzeilen, die innerhalb von Customer Journey Analytics für die Analyse verfügbar sind.

Nehmen wir beispielsweise an, Ihr Vertrag berechtigt Sie zu einer Million Datenzeilen. Angenommen, Sie laden am 1. Tag der Verwendung von Customer Journey Analytics zwei Millionen Datenzeilen hoch. Am Tag 2 löschen Sie 1 Million Zeilen und behalten diese Nutzung für den Rest Ihrer Lizenzvereinbarung bei (d. h. maximal eine Million Datenzeilen). Abhängig von Ihren Vertragsbedingungen können Ihnen für Tag 1 anteilige zusätzliche Nutzungsgebühren entstehen, da Sie die Lizenzberechtigung für „Datenzeilen“ überschritten haben.

## 11. Diskrepanzen bei Daten erkennen {#discrepancies}

In einigen Fällen kann es vorkommen, dass die Gesamtanzahl der von Ihrer Verbindung erfassten Ereignisse sich von der Anzahl der Zeilen im Datensatz in [!UICONTROL Adobe Experience Platform] unterscheidet. In diesem Beispiel enthält der Datensatz „B2B Impression“ 7650 Zeilen, der Datensatz enthält jedoch 3830 Zeilen in [!UICONTROL Adobe Experience Platform]. Es kann mehrere Gründe für Diskrepanzen geben. Die folgenden Schritte können für die Diagnose hilfreich sein:

1. Schlüsseln Sie diese Dimension nach **[!UICONTROL Platform-Datensatz-ID]** und Sie werden zwei Datensätze mit derselben Größe, aber unterschiedlichen **[!UICONTROL Platform-Datensatz-IDs]**. Jeder Datensatz enthält 3.825 Aufzeichnungen. Das bedeutet, dass [!UICONTROL Customer Journey Analytics] fünf Datensätze aufgrund fehlender Personen-IDs oder fehlender Zeitstempel ignoriert hat:

   ![Aufschlüsselung](assets/data-size2.png)

2. Wenn wir außerdem einchecken [!UICONTROL Adobe Experience Platform], gibt es keinen Datensatz mit der ID &quot;5f21c12b732044194bffc1d0&quot;, daher hat jemand diesen bestimmten Datensatz aus [!UICONTROL Adobe Experience Platform] bei der Erstellung der ersten Verbindung. Später wurde es wieder zum Customer Journey Analytics hinzugefügt, aber eine andere [!UICONTROL Platform-Datensatz-ID] wurde von [!UICONTROL Adobe Experience Platform].

Weitere Informationen über die [Implikationen beim Löschen von Datensätzen und Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components) erhalten Sie in [!UICONTROL Customer Journey Analytics] und [!UICONTROL Adobe Experience Platform].
