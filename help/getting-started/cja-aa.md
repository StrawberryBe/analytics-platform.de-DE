---
title: Customer Journey Analytics-Funktionen
description: Customer Journey Analytics-Funktionen im Vergleich zu Adobe Analytics-Funktionen.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
translation-type: tm+mt
source-git-commit: 4b543a1566580a8f3060c2387928148d55be70f2
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 99%

---

# Customer Journey Analytics-Funktionen

In den folgenden Tabellen ist aufgeführt, welche Funktionen in Adobe Analytics in Customer Journey Analytics (CJA) unterstützt, teilweise unterstützt oder nicht unterstützt werden. Diese Listen ändern sich im Laufe der Zeit, wenn CJA Funktionen hinzugefügt werden.

## Vollständig unterstützte Funktionen/Komponenten

| Adobe Analytics-Funktion | Hinweise zur Unterstützung |
| --- | --- |
| Metriken | CJA nutzt das Experience-Datenmodell (XDM) und unterstützt unbegrenzte Metriken und ist nicht an die benutzerspezifischen Erfolgsereignisse traditioneller Analytics gebunden. Beachten Sie, dass einige Standardmetriken aus der traditionellen Analytics umbenannt wurden: Besucher = Personen, Besuche = Sitzungen, Treffer = Ereignisse. |
| Dimensionen | Customer Journey Analytics nutzt XDM, unterstützt unbegrenzte Dimensionen und ist nicht an die benutzerdefinierten eVars oder Props des herkömmlichen Analytics gebunden. |
| Listenvariablen/Listen-Props | Customer Journey Analytics (CJA) nutzt XDM und unterstützt unbegrenzte Zeichenfolgen-Arrays, die ähnlich wie listVars verwendet werden können. |
| Datumsbereiche | Die Unterstützung benutzerdefinierter Kalender ist geplant. |
| Berechnete Metriken | Beachten Sie, dass vorhandene Berechnungsmetriken im herkömmlichen Analysis Workspace nicht auf CJA portiert werden. |
| Segmente | Jetzt „Filter“ genannt. Beachten Sie, dass keine vorhandenen Segmente im traditionellen Analysis Workspace auf CJA portiert werden. |
| Anomalieerkennung | Vollständige Unterstützung. |
| Attribution IQ | Vollständige Unterstützung. |
| Projektkuration | Vollständige Unterstützung. |
| Projektverknüpfung | Vollständige Unterstützung. |
| Datumsvergleiche | Vollständige Unterstützung. |
| Virtual Report Suites | Jetzt [Datenansichten](/help/data-views/create-dataview.md) genannt. |
| Kuration von VRS-Komponenten | Jetzt Teil der Datenansichten. |
| Berichtszeitverarbeitung | CJA basiert ausschließlich auf der Berichtszeitverarbeitung. |
| DSGVO-Löschung | Beachten Sie, dass die DSGVO jetzt in Abstimmung mit [!UICONTROL Adobe Experience Platform] gehandhabt wird. Customer Journey Analytics übernimmt alle Datenänderungen, die [!UICONTROL Experience Platform] an den zugrunde liegenden Datensätzen vornimmt. |
| Benutzerberechtigungen/Datenzugangssteuerung | CJA unterscheidet zwischen Produktadministratoren und Anwendern von Adobe Admin Console. Nur Produktadministratoren können 1) Verbindungen oder Datenansichten erstellen/aktualisieren/löschen, 2) Projekte, Filter oder Berechnungsmetriken, die von anderen Benutzern erstellt wurden, aktualisieren/löschen und 3) ein Workspace-Projekt für alle Benutzer freigeben. |
| Geräteübergreifende/kanalübergreifende Zuordnung | Siehe [Cross-Channel-Analysen](/help/connections/cca/overview.md). |
| Vorkonfigurierte Analysis Workspace-Dimensionen (Browser-Typ, Typ der verweisenden Stelle, Betriebssystem usw.) | Customer Journey Analytics stellt diese Dimensionen nativ bereit, solange die grundlegenden XDM-Felder (z. B. Benutzeragent oder Geräte-ID) ausgefüllt sind. Für Kunden, der Data Connector von Analytics (ADC) verwenden, sind einige dieser Dimensionen verfügbar, jedoch nicht alle. Bitte lesen Sie in unserer [Dokumentation, welche Analytics-Variablen über ADC unterstützt werden](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Zugriff auf Reporting-API | Jetzt mit der [CJA API](https://www.adobe.io/cja-apis/docs/) verfügbar. |
| Terminierte Berichte/Projekte | Vollständige Unterstützung. |
| PDF-Export | Vollständige Unterstützung. |

## Mit Einschränkungen unterstützt

| Funktion | Hinweise |
| --- | --- |
| Produktvariable | In Experience Platform können Benutzer ein Array mit Objekttypfeldern in einem Datensatzschema verwenden, um die Anforderungen dieses Anwendungsfalls zu erfüllen. In Customer Journey Analytics können Kunden beliebige Produktvariablen verwenden und sind nicht wie in Adobe Analytics auf einzelne Variablen beschränkt. |
| Marketing-Kanäle | Daten von Marketing-Kanälen werden jetzt über Analytics Data Connector an Customer Journey Analytics weitergeleitet. Die Regeln für den Marketing-Kanal müssen weiterhin im herkömmlichen Adobe Analytics konfiguriert werden. Einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie in der [Customer Journey Analytics Marketing-Kanal-Dokumentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=de#cja-usecases). |
| Visualisierungen | Alle Visualisierungen mit Ausnahme der Zuordnungsvisualisierung werden unterstützt. |
| Projektfreigabe | Die Projektfreigabe wird nur von zwischen CJA-Anwendern unterstützt. Es gibt keine Projektfreigabe zwischen CJA und dem traditionellen Analysis Workspace. |
| Benutzerdefinierte Sitzungen | Unterstützung aller benutzerdefinierten Sitzungsfunktionen außer mobilen Hintergrundtreffern. |
| eVar-Persistenzeinstellungen | eVars sind nicht mehr Teil von CJA. Die Persistenzeinstellungen sind jetzt jedoch Teil der Datenansichten und für alle Dimensionen verfügbar. Beachten Sie, dass die Persistenz auf der Berichtszeitverarbeitung und nicht auf der Datenerfassungsverarbeitung basiert. Dimensionen, die innerhalb von Datenansichten festgelegt werden, sind auf eine maximale Persistenz von 90 Tagen beschränkt und unterstützen keine unbegrenzte Persistenz. |
| Classifications | Jetzt „Lookup-Datensätze“ genannt. In Analytics verwendete Klassifizierungen können mit Data Connector für Analytics-Klassifizierungen in Experience Platform und in Customer Journey Analytics importiert werden. Lookup-Datensätze können auch direkt in Adobe Experience Platform hochgeladen und in Customer Journey Analytics verfügbar gemacht werden. |
| Kundenattribute | Jetzt als „Profildatensätze“ bezeichnet, werden sie nicht automatisch aus Experience Cloud importiert, sondern müssen in AEP hochgeladen werden, bevor sie in CJA verfügbar sind. |
| Geräte-, Browser- und Technologie-Dimensionen | Diese Dimensionen werden automatisch eingeschlossen, wenn ein Adobe Experience Platform-Datensatz bestimmte XDM-Schema-Felder enthält und der XDM-Erlebnisereignis-Klasse entspricht. |
| Eintritte, Ausstiege und Besuchszeit-Dimensionen und -Metriken | Unterstützt (Eintritte und Ausstiege werden jetzt als Sitzungsanfang und Sitzungsende bezeichnet) und etwas anders berechnet. |

## Teilweise Unterstützung

| Funktion | Hinweise |
| --- | --- |
| Bedienfelder | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. Die Bedienfelder „Segmentvergleich“, „Analytics for Target (A4T)“ und „Gleichzeitige Medienbesucher“ werden nicht unterstützt. |
| Merchandising-eVars | Das Verhalten von Merchandising-eVars kann mithilfe von Dimensionen innerhalb eines Objectarrays erreicht werden, sofern eine Merchandising-eVar nicht für die Verwendung von Persistenz konfiguriert ist. Derzeit ist die Persistenz für die Merchandising-Dimension nicht verfügbar. |
| Bot-Filterung | Bei Data Connector von Analytics (ADC)-basierten Datensätzen wird die Bot-Filterung angewendet. Die allgemeine Bot-Filterlogik für andere Datensätze wird weder von [!UICONTROL Experience Platform] noch von CJA ausgeführt. |
| Verarbeitungsregeln | Auf Analytics Data Connector-basierte Datensätze werden weiterhin Verarbeitungsregeln angewendet. |
| Media Analytics | Mediendaten stehen als Teil von Analytics Data Connector zur Verfügung. |

## Derzeit nicht unterstützt, aber geplant

| Funktion | Hinweise |
| --- | --- |
| Beitragsanalyse | Unterstützung ist geplant. |
| Segment IQ | Unterstützung ist geplant. |
| Segmentveröffentlichung (Senden von Segmenten aus Workspace an Experience Cloud) | Unterstützung ist geplant. |
| CSV-Download | Unterstützung ist geplant. |
| Benutzerdefinierte Kalender | Unterstützung ist geplant. |
| Deduplizierung der Metrik | Unterstützung ist geplant. |
| Persistenz von Merchandising-Variablen | Unterstützung ist geplant. |
| Warnhinweise | Unterstützung ist geplant. |
| ID-Zuordnung über Gerätediagramm | Unterstützung ist geplant. |
| Report Builder (Excel-Plug-in) | Unterstützung ist geplant. |
| Echtzeitberichterstellung | Unterstützung ist geplant. |
| Data Warehouse-Berichte (100 % Zeilenexport) | Die Unterstützung über die Analysis Workspace-Oberfläche ist geplant. Der [!UICONTROL Abfrage-Service von Experience Platform] bietet auch eine Schnittstelle für diese Anwendungsfälle in CJA. |

## Unterstützung ist noch nicht geplant

| Funktion | Hinweise |
| --- | --- |
| A4T | Unterstützung ist noch nicht geplant. |
| Advertising Cloud | Unterstützung ist noch nicht geplant. |
| Activity Map | Unterstützung ist noch nicht geplant. |
| Classification Rule Builder | Unterstützung ist noch nicht geplant. |
| Zusammenfassungs-Data Sources | Unterstützung ist noch nicht geplant. |
| Daten-Feeds | Unterstützung ist noch nicht geplant. |

## Keine Unterstützung geplant

* Benutzermetriken mit Cross-Device Coop
* Reports &amp; Analytics-Dashboards
* Reports &amp; Analytics-Lesezeichen
* Reports &amp; Analytics-Zielgruppen
* Reports &amp; Analytics-Kalenderereignisse
* Mobile Services
