---
title: CJA-Benutzerhandbuch für Adobe Analytics-Benutzer
description: Was aus der Sicht eines Benutzers zu beachten ist, wenn Ihr Unternehmen Daten von Adobe Analytics in Customer Journey Analytics verschiebt
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 755e554e3eb362d6e7149e5d3a4fbbcddebdd14d
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 25%

---


# CJA-Benutzerhandbuch für Adobe Analytics-Benutzer

>[!NOTE]
>
>Diese Seite befindet sich im Aufbau.

Herzlichen Glückwunsch, Ihr Unternehmen beginnt mit der Arbeit mit Customer Journey Analytics! Als Anwender, der mit Adobe Analytics vertraut ist, haben Sie bereits einen tollen Vorsprung. Beim Arbeiten mit Customer Journey Analytics werden Sie einige große Unterschiede und Ähnlichkeiten bemerken. Auf dieser Seite werden die Dinge erläutert, die sich nicht geändert haben, sowie einige der wichtigsten Unterschiede. Wir erklären Ihnen auch, wie Sie weitere Informationen zu neuen Konzepten erhalten und weitere Schritte unternehmen können, um IHRE Journey zu vereinfachen und erfolgreicher zu gestalten.

## Was sich nicht geändert hat

Vieles, was Sie auf der Berichtsseite kennen, hat sich nicht geändert.

* Sie können weiterhin die [Analysis Workspace](/help/analysis-workspace/home.md) um Ihre Daten zu analysieren.
* Sie haben auch dieselbe Version von [Adobe Analytics-Dashboards](/help/mobile-app/home.md) zur Verfügung. Workspace und Dashboards funktionieren genauso wie im herkömmlichen Adobe Analytics.
* [Report Builder](/help/report-builder/report-buider-overview.md) hat eine neue Schnittstelle und läuft jetzt auf PCs, Macs und der Web-Version von Excel.

Was die Berichterstellung angeht, ist, dass Sie Zugriff auf viel mehr kanalübergreifende Daten haben, die analysiert werden können. Im Folgenden finden Sie ein Beispiel für einige kanalübergreifende Visualisierungen, die eine Reihe kanalübergreifender Datenquellen enthalten:

![Mehrkanal-Visualisierungen](assets/cross-channel.png)

## Neue Architektur

Customer Journey Analytics erhält seine Daten von Adobe Experience Platform. Mit Experience Platform können Sie Kundendaten und -inhalte aus beliebigen Systemen oder Kanälen zentralisieren und standardisieren sowie mithilfe von Datenwissenschaft und maschinellem Lernen die Gestaltung und Bereitstellung personalisierter Erlebnisse verbessern.

Kundendaten in Platform werden als Datensätze gespeichert, die aus einem Schema und Datenstapeln bestehen. Weitere Informationen zu Platform finden Sie unter [Übersicht über die Adobe Experience Platform-Architektur](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Ihr CJA-Administrator hat [Verbindungen](/help/connections/create-connection.md) auf Datensätze in Platform. Sie haben dann [Datenansichten](/help/data-views/data-views.md) innerhalb dieser Verbindungen. Stellen Sie sich Datenansichten ähnlich wie Virtual Report Suites vor. Datenansichten sind die Grundlage für die Berichterstellung in Customer Journey Analytics.

## Neue Konzepte und Terminologie

Verschiedene Funktionen in CJA wurden im Vergleich zum herkömmlichen Adobe Analytics umbenannt und neu gestaltet, um sie an Branchenstandards anzupassen. Einige aktualisierte Begriffe umfassen Segmente, Virtual Report Suites, Klassifizierungen, Kundenattribute und Container-Namen. Vertraute Konzepte wie eVars und Props existieren nicht mehr, zusammen mit den Einschränkungen, die sie auferlegten.

### eVars und Props

[!UICONTROL eVars], [!UICONTROL Props] und [!UICONTROL Ereignisse] im herkömmlichen Sinne von Adobe Analytics existieren in [!UICONTROL Customer Journey Analytics] nicht mehr. Es gibt unbegrenzte Schemaelemente (Dimensionen, Metriken, Listenfelder). Alle Zuordnungseinstellungen, die Sie bisher während des Datenerfassungsprozesses angewendet haben, werden jetzt bei der Abfrage angewendet.

### Segmente sind jetzt &quot;Filter&quot;

[!UICONTROL Customer Journey Analytics] verwendet keine eVars, Props oder Ereignisse mehr und verwendet stattdessen ein AEP-Schema. Das bedeutet, dass keines der vorhandenen Segmente mit [!UICONTROL Customer Journey Analytics]. Außerdem wurden &quot;Segmente&quot;in &quot;Filter&quot;umbenannt.

Derzeit können Sie keine Inhalte freigeben/veröffentlichen [!UICONTROL Filter] ([!UICONTROL Segmente]) von [!DNL Customer Journey Analytics] zur Experience Platform von Unified Profile oder anderen Experience Cloud-Anwendungen. Diese Funktion wird derzeit entwickelt.

### Berechnete Metriken

[!UICONTROL Customer Journey Analytics] verwendet keine eVars, Props oder Ereignisse mehr und verwendet stattdessen ein AEP-Schema. Das bedeutet, dass keine der vorhandenen berechneten Metriken mit [!UICONTROL Customer Journey Analytics].

### Sitzungs- und Variablenpersistenzeinstellungen

[!UICONTROL Customer Journey Analytics] verwendet alle diese Einstellungen zur Berichtszeit. Diese Einstellungen sind jetzt in Datenansichten verfügbar. Änderungen an diesen Einstellungen sind jetzt rückwirkend. Jetzt sind mehrere Versionen verfügbar, indem Sie mehrere Datenansichten verwenden.

### Virtual Report Suites sind jetzt &quot;Datenansichten&quot;.



### Classifications sind jetzt &quot;Lookup-Datensätze&quot;

### Kundenattribute sind jetzt &quot;Profil-Datensätze&quot;.


### Trefferbehälter sind jetzt &#39;Ereignis&#39;-Container

### Besuchebehälter sind jetzt Sitzungs-Container

### Besuchercontainer sind jetzt &quot;Personen&quot;-Container

### `Uniques Exceeded`Einschränkungen

[!UICONTROL In Customer Journey Analytics] gibt es keine Beschränkungen hinsichtlich eindeutiger Werte, sodass Sie sie nicht beachten müssen.
