---
title: FAQ zu Customer Journey Analytics
description: Customer Journey Analytics – häufig gestellte Fragen
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
translation-type: tm+mt
source-git-commit: 6de1907e74eb0323bde921f4400e27bcdf06cdd1
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 65%

---

# Häufig gestellte Fragen

[!UICONTROL Customer Journey Analytics]  (CJA) ist unser Analyseprodukt der nächsten Generation. Im Folgenden finden Sie Antworten auf häufig gestellte Fragen zu CJA. Weitere Informationen finden Sie unter [Customer Journey Analytics-Funktionsunterstützung](/help/getting-started/cja-aa.md).

## 1. Voraussetzungen

| # | Frage | Antwort |
| --- | --- | --- |
| a | Benötige ich [!UICONTROL Private Device Graph] oder [!UICONTROL Device Coop] für [!UICONTROL Customer Journey Analytics]? | Nein, [!UICONTROL Private Device Graph] oder [!UICONTROL Device Coop] sind für [!UICONTROL Customer Journey Analytics] nicht erforderlich. Sie werden aktuell noch nicht unterstützt. |
| b | Benötige ich eine [!UICONTROL Experience Cloud ID] (ECID) für [!UICONTROL Customer Journey Analytics]? | Nein, [!UICONTROL Customer Journey Analytics] unterstützt alle IDs in einem Datensatz, unabhängig davon, ob es sich um eine [!UICONTROL ECID] oder eine andere ID handelt. |
| c | Wie gehe ich vor, wenn ich meine Daten vor [!UICONTROL Customer Journey Analytics] einem ETL-Prozess (Extract, Transform, Load) unterziehen muss? | Customer Journey Analytics enthält die Funktionen [Datenvorgabe](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html), mit denen Sie Ihre Daten umwandeln können, bevor Sie sie in den Adobe Experience Platform Data Lake übernehmen. Wenn Sie ETL benötigen, nachdem die Daten bereits erfasst wurden, stehen Ihnen für [Adobe Experience Platform Abfrage Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=en#queries) einige begrenzte Optionen zur Verfügung, auch wenn zusätzliche Gebühren anfallen können. |

## 2. Stitching-Daten (Cross-Kanal Analytics)

| # | Frage | Antwort |
| --- | --- | --- |
| a | Kann [!UICONTROL Customer Journey Analytics] Daten über Geräte oder über Datensätze hinweg zusammenfügen? | Ja. [!UICONTROL Customer Journey ] Analytics ist eine Heftlösung mit dem Namen  [Cross-Kanal Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html)  (CCA). Damit können Sie die Personen-ID eines Datasets neu eingeben, was eine nahtlose Kombination mehrerer Datensätze ermöglicht. |
| b | Wird das Stitching vom anonymen Verhalten zum authentifizierten Verhalten unterstützt? | Ja. [Cross-Kanal ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html) Analytics untersucht Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen, um eine zugewiesene ID zu generieren. |
| c | Wie funktioniert &quot;Replay&quot;in CCA? | CCA &quot;wiederholt&quot;Daten basierend auf eindeutigen Bezeichnern, die sie gelernt hat. Bei einer erneuten Wiedergabe werden neue Geräte an der Verbindung angeheftet. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=en#step-1%3A-live-stitching) |
| d | Wie funktioniert das Verbinden von historischen Daten (Aufstockung) in CCA? | Bei Aktivierung stellt die Adobe eine Aufstockung der gehefteten Daten bereit, die bis zum Beginn des Vormonats (bis zu 60 Tage) zurückreicht. Um diese Aufstockung durchführen zu können, muss die transiente ID in den nicht zugewiesenen Daten vorhanden sein, die weit zurück in der Zeit liegen. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=en#enable-cross-channel-analytics) |

## 3. Daten in [!UICONTROL Customer Journey Analytics]

| # | Frage | Antwort |
| --- | --- | --- |
| a | Kann ich Daten aus verschiedenen [!UICONTROL Adobe Experience Platform]-Sandboxen in einer [!UICONTROL Customer Journey Analytics]-Verbindung kombinieren? | Nein, Sie können nicht über Sandboxes hinweg auf Daten zugreifen. Sie können nur Datensätze kombinieren, die sich innerhalb derselben Sandbox befinden. [Weitere Infos](https://docs.adobe.com/content/help/de-DE/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| b | Wie hoch ist die erwartete Latenz für [!UICONTROL Customer Journey Analytics] auf [!UICONTROL Adobe Experience Platform]? | <ul><li>Unter normaler Belastung: &lt; 60 Minuten <br>**Hinweis:** Bei ungewöhnlich hohem Datenfluss durch die Pipeline kann es bis zu 24 Stunden dauern.</li><li>Aufstockungsdaten (bis zu 13 Monate Daten, unabhängig von der Größe): &lt; 4 Wochen</li></ul> |
| c | Wie werden in [!UICONTROL Customer Journey Analytics] Online-Daten mit Offline-Daten verbunden? | Solange die Personen-ID zwischen den Datensätzen übereinstimmt, kann [!UICONTROL Customer Journey Analytics] Filter, Zuordnung, Fluss, Trichteranalyse usw. verbinden. über Datensätze hinweg miteinander verbinden. |
| d | Wie integriere ich meine Offline-Daten in [!UICONTROL Customer Journey Analytics]? | Mit Ihrer Berechtigung zum Customer Journey Analytics können Sie Daten in die Experience Platform aufnehmen. Sie können dann Verbindungen zu diesen Daten- und Datenverbindungen in [!UICONTROL Customer Journey Analytics] erstellen, um in Analysis Workspace Berichte zu erhalten. Das Datenerfassungs-Team der Experience Platform bietet bei Bedarf Empfehlungen oder eine Beratung für Sie an. |
| e | Wie integriere ich [!UICONTROL Adobe Analytics]-Daten in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics]-Daten können über [Adobe Analytics Source Connector](https://docs.adobe.com/content/help/de-DE/experience-platform/sources/connectors/adobe-applications/analytics.html) mit Experience Platform verbunden werden. Die meisten [!UICONTROL Adobe Analytics]-Felder werden im XDM-Format übermittelt, andere Felder (wie beispielsweise [!UICONTROL Marketing Channels]-Dimensionen) sind jedoch noch nicht verfügbar. |
| f | Wie lange dauert es, bis Datensatzelemente in einer Datenansicht zusammengefasst werden? | Ein paar Stunden für eine erste Ansicht und ein paar Tage, um die Daten der letzten 13 Monate einzufügen. |
| g | Sind PII-Daten notwendig, um Verbindungen zwischen den Daten herzustellen? | Nein, Sie können eine beliebige ID verwenden, einschließlich eines Hash einer Kunden-ID, bei der es sich nicht um personenbezogene Daten handelt. |

## 4. Traditionelle Komponenten [!UICONTROL Adobe Analytics]

| # | Frage | Antwort |
| --- | --- | --- |
| a | Kann ich Filter (Segmente) von Customer Journey Analytics zu Experience Platform Unified Profil oder anderen Experience Cloud-Anwendungen freigeben/veröffentlichen? | Noch nicht, aber wir arbeiten aktiv daran, diese Fähigkeit zu erreichen. |
| b | Was ist mit meiner alten eVar-Einstellung passiert? | eVars, Props und Ereignisse im Sinne vom herkömmlichen Adobe Analytics gibt es in [!UICONTROL Customer Journey Analytics] nicht mehr. Es gibt unbegrenzte Schemaelemente (Dimensionen, Metriken, Listenfelder). Alle Zuordnungseinstellungen, die Sie bisher während des Datenerfassungsprozesses angewendet haben, werden jetzt bei der Abfrage angewendet. |
| c | Wo sind jetzt meine Einstellungen für die Sitzungs- und Variablenpersistenz? | [!UICONTROL Customer Journey Analytics] verwendet alle diese Einstellungen zur Berichtszeit. Diese Einstellungen sind jetzt in Datenansichten verfügbar. Änderungen an diesen Einstellungen sind jetzt rückwirkend. Jetzt sind mehrere Versionen verfügbar, indem Sie mehrere Datenansichten verwenden. |
| d | Was passiert mit den bereits vorhandenen Segmenten/berechneten Metriken? | [!UICONTROL Customer Journey Analytics] verwendet keine eVars, Props oder Ereignisse mehr und verwendet stattdessen ein AEP-Schema. Das bedeutet, dass keine der vorhandenen Segmente oder Berechnungsmetriken mit [!UICONTROL Customer Journey Analytics] kompatibel sind. |
| e | Wie werden in [!UICONTROL Customer Journey Analytics] `Uniques Exceeded`-Einschränkungen behandelt? | [!UICONTROL In Customer Journey Analytics] gibt es keine Beschränkungen hinsichtlich eindeutiger Werte, sodass Sie sie nicht beachten müssen. |
| f | Kann ich als bestehender [!DNL Data Workbench]-Kunde jetzt zu [!UICONTROL Customer Journey Analytics] wechseln? | Es hängt von Ihrem Anwendungsfall ab. Bitte wenden Sie sich an Ihr Adobe Account Team. Ihre aktuellen Anwendungsfälle sind möglicherweise bereits gut für den Customer Journey Analytics geeignet. |

## 5. Auswirkungen des Löschens von Datenkomponenten

Beim Löschen von Daten geht es um sechs Arten von Komponenten: Sandbox-, Schema-, Dataset-, Verbindungs-, Daten-Ansicht- und Workspace-Projekt. Im Folgenden sind einige Szenarien für das Löschen der jeweiligen Komponenten aufgeführt:

| Wenn Sie... | Dies geschieht... |
| --- | --- |
| eine Sandbox in [!UICONTROL Adobe Experience Platform] lösche | Durch das Löschen einer Sandbox wird der Datenfluss aller [!UICONTROL Customer Journey Analytics]-Verbindungen zu Datensätzen in dieser Sandbox angehalten. Derzeit werden Verbindungen in CJA, die an die gelöschte Sandbox gebunden sind, nicht automatisch gelöscht. |
| ein Schema in [!UICONTROL Adobe Experience Platform] lösche, aber nicht den Datensatz bzw. die Datensätze, die diesem Schema zugeordnet sind | [!UICONTROL Adobe Experience Platform] ermöglicht nicht das Löschen von Schemata, denen ein oder mehrere Datensätze zugeordnet sind. Ein Administrator mit den entsprechenden Berechtigungen kann jedoch zuerst die Datensätze und dann das Schema löschen. |
| Löschen eines Datensatzes im Datensee [!UICONTROL Adobe Experience Platform] | Durch das Löschen eines Datensatzes im AEP-Datensee wird der Datenfluss von diesem Datensatz zu allen CJA-Verbindungen, die diesen Datensatz enthalten, gestoppt. Daten aus diesem Datensatz werden nicht automatisch aus zugehörigen Customer Journey Analytics-Verbindungen gelöscht. |
| einen Datensatz in [!UICONTROL Customer Journey Analytics] lösche | Derzeit ist es nicht möglich, einen Datensatz in einer gespeicherten Verbindung zu löschen. Dazu müssten Sie die gesamte Verbindung löschen und von Neuem beginnen. (Kunden, die die CJA-SKU erworben haben, können jedoch einen Datensatz in der Benutzeroberfläche [!UICONTROL Adobe Experience Platform] löschen.) |
| Stapel aus einem Datensatz löschen (in [!UICONTROL Adobe Experience Platform]) | Wenn ein Batch in einem [!UICONTROL Adobe Experience Platform]-Datensatz gelöscht wird, wird er auch aus allen Customer Journey Analytics-Verbindungen entfernt, die diesen Batch enthalten.  Customer Journey Analytics wird über das Löschen von Batches in [!UICONTROL Adobe Experience Platform] benachrichtigt. |
| einen Batch lösche, **während er** in [!UICONTROL Customer Journey Analytics] aufgenommen wird | Wenn in dem Datensatz nur ein Batch vorhanden ist, erscheinen keine Daten oder nur teilweise Daten aus diesem Batch in [!UICONTROL Customer Journey Analytics]. Die Aufnahme wird zurückgesetzt. Wenn es in dem Datensatz beispielsweise 5 Batches gibt und 3 davon bereits aufgenommen wurden, als der Datensatz gelöscht wurde, erscheinen die Daten dieser 3 Batches in [!UICONTROL Customer Journey Analytics]. |
| eine Verbindung in [!UICONTROL Customer Journey Analytics] lösche | Eine Fehlermeldung weist darauf hin, dass<ul><li>für die gelöschte Verbindung erstellte Datenansichten nicht mehr funktionieren.</li><li> Ebenso funktionieren alle Workspace-Projekte nicht mehr, die von den Datenansichten der gelöschten Verbindung abhängig sind.</li></ul> |
| eine Datenansicht in [!UICONTROL Customer Journey Analytics] lösche | Eine Fehlermeldung weist darauf hin, dass alle Workspace-Projekte, die von dieser gelöschten Datenansicht abhängen, nicht mehr funktionieren. |
