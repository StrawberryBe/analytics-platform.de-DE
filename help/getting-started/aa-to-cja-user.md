---
title: CJA-Benutzerhandbuch für Adobe Analytics-Benutzer
description: Was aus der Sicht eines Benutzers zu beachten ist, wenn Ihr Unternehmen Daten von Adobe Analytics in Customer Journey Analytics verschiebt
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: eeb56599c81dd9cd20bf91c864aa57a783ef13fd
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 40%

---


# CJA-Benutzerhandbuch für Adobe Analytics-Benutzer

Herzlichen Glückwunsch! Ihr Unternehmen hat zumindest einige seiner Daten in den Customer Journey Analytics verschoben! Beim Arbeiten mit Customer Journey Analytics werden Sie einige große Unterschiede und einige Ähnlichkeiten bemerken. Auf dieser Seite werden die Dinge erläutert, die sich nicht geändert haben, sowie einige der wichtigsten Unterschiede.

Wir erklären Ihnen auch, wie Sie weitere Informationen zu neuen Konzepten erhalten und weitere Schritte unternehmen können, um IHRE Journey zu vereinfachen und erfolgreicher zu gestalten.

## Was sich nicht geändert hat

Vieles, was Sie auf der Berichtsseite kennen, hat sich nicht geändert. Sie können weiterhin die Leistungsfähigkeit von Analysis Workspace nutzen, um Ihre Daten sowie Adobe Analytics-Dashboards und eine neue Version von Report Builder zu analysieren. Workspace und Dashboards funktionieren im Wesentlichen genauso wie im herkömmlichen Adobe Analytics. Report Builder verfügt über eine neue Benutzeroberfläche und läuft jetzt auf PCs, Mac-Computern und der Webversion von Excel. Berichterstattungsorientiert ist es anders, dass Sie Zugriff auf viel mehr kanalübergreifende Daten haben, die analysiert werden können. Im Folgenden finden Sie ein Workspace-Beispiel für

## Neue Architektur

Architektonisch erhält Customer Journey Analytics seine Daten von Adobe Experience Platform. Mit Experience Platform können Sie Kundendaten und -inhalte aus beliebigen Systemen oder Kanälen zentralisieren und standardisieren sowie mithilfe von Datenwissenschaft und maschinellem Lernen die Gestaltung und Bereitstellung personalisierter Erlebnisse verbessern.

Kundendaten in Platform werden als Datensätze gespeichert, die aus einem Schema und Datenstapeln bestehen. Weitere Informationen zu Platform finden Sie unter [Übersicht über die Adobe Experience Platform-Architektur](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Ihr CJA-Administrator stellt Verbindungen zu den Daten in Platform her und erstellt Datenansichten innerhalb dieser Verbindungen. Stellen Sie sich Datenansichten ähnlich wie Virtual Report Suites vor. Datenansichten sind die Grundlage für die Berichterstellung in Customer Journey Analytics.

## Neue Konzepte und Terminologie

Verschiedene Funktionen in CJA wurden im Vergleich zum herkömmlichen Adobe Analytics umbenannt und neu gestaltet, um sie an Branchenstandards anzupassen. Einige aktualisierte Begriffe umfassen Segmente, Virtual Report Suites, Klassifizierungen, Kundenattribute und Container-Namen. Vertraute Konzepte wie eVars und Props existieren nicht mehr, zusammen mit den Einschränkungen, die sie auferlegten.

### Segmente sind jetzt &quot;Filter&quot;


### Virtual Report Suites sind jetzt &quot;Datenansichten&quot;.


### Classifications sind jetzt &quot;Lookup-Datensätze&quot;

### Kundenattribute sind jetzt &quot;Profil-Datensätze&quot;.


### Trefferbehälter sind jetzt &#39;Ereignis&#39;-Container

### Besuchebehälter sind jetzt Sitzungs-Container

### Besuchercontainer sind jetzt &quot;Personen&quot;-Container

## Häufig gestellte Fragen zu Adobe Analytics-Komponenten

| Frage | Antwort |
| --- | --- |
| Kann ich [!UICONTROL Filter] ([!UICONTROL Segmente]) von [!DNL Customer Journey Analytics] für Experience Platform Unified Profile oder andere Experience Cloud-Programme freigeben/veröffentlichen? | Noch nicht, wir arbeiten aber aktuell daran, diese Funktion bald bereitstellen zu können. |
| Was ist mit meiner alten [!UICONTROL eVar]-Einstellung passiert? | [!UICONTROL eVars], [!UICONTROL Props] und [!UICONTROL Ereignisse] im herkömmlichen Sinne von Adobe Analytics existieren in [!UICONTROL Customer Journey Analytics] nicht mehr. Es gibt unbegrenzte Schemaelemente (Dimensionen, Metriken, Listenfelder). Alle Zuordnungseinstellungen, die Sie bisher während des Datenerfassungsprozesses angewendet haben, werden jetzt bei der Abfrage angewendet. |
| Wo sind jetzt meine Einstellungen für die Sitzungs- und Variablenpersistenz? | [!UICONTROL Customer Journey Analytics] verwendet alle diese Einstellungen zur Berichtszeit. Diese Einstellungen sind jetzt in Datenansichten verfügbar. Änderungen an diesen Einstellungen sind jetzt rückwirkend. Jetzt sind mehrere Versionen verfügbar, indem Sie mehrere Datenansichten verwenden. |
| Was passiert mit den bereits vorhandenen Segmenten/berechneten Metriken? | [!UICONTROL Customer Journey Analytics] verwendet keine eVars, Props oder Ereignisse mehr und verwendet stattdessen ein AEP-Schema. Das bedeutet, dass keine der vorhandenen Segmente oder Berechnungsmetriken mit [!UICONTROL Customer Journey Analytics] kompatibel sind. |
| Wie werden in [!UICONTROL Customer Journey Analytics] `Uniques Exceeded`-Einschränkungen behandelt? | [!UICONTROL In Customer Journey Analytics] gibt es keine Beschränkungen hinsichtlich eindeutiger Werte, sodass Sie sie nicht beachten müssen. |
| Kann ich als bestehender [!DNL Data Workbench]-Kunde jetzt zu [!UICONTROL Customer Journey Analytics] wechseln? | Das hängt von Ihrem Anwendungsfall ab. Bitte wenden Sie sich an Ihr Adobe Account Team. Möglicherweise eignen sich Ihre aktuellen Anwendungsfälle gut für Customer Journey Analytics. |
