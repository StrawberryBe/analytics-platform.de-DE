---
title: Customer Journey Analytics-Funktionen
description: Customer Journey Analytics-Funktionen im Vergleich zu Adobe Analytics-Funktionen.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
source-git-commit: 8efb8da477b2680a44294553fdca944461ba0f0c
workflow-type: ht
source-wordcount: '1195'
ht-degree: 100%

---

# Customer Journey Analytics-Funktionen

In den folgenden Tabellen ist aufgeführt, welche Funktionen in Adobe Analytics in Customer Journey Analytics (CJA) unterstützt, teilweise unterstützt oder nicht unterstützt werden. Diese Listen ändern sich im Laufe der Zeit, wenn CJA Funktionen hinzugefügt werden.

## Vollständig unterstützte Funktionen/Komponenten

| Adobe Analytics-Funktion | Hinweise zur Unterstützung |
| --- | --- |
| Anomalieerkennung | Vollständige Unterstützung. |
| Attribution IQ | Vollständige Unterstützung. |
| Berechnete Metriken | Vollständige Unterstützung; beachten Sie, dass vorhandene berechnete Metriken in herkömmlichem Analysis Workspace nicht in CJA portiert werden. |
| Geräteübergreifende/kanalübergreifende Zuordnung | Vollständige Unterstützung; siehe [kanalübergreifende Analyse](/help/connections/cca/overview.md). |
| CSV-Download | Vollständige Unterstützung. |
| Benutzerdefinierte Kalender | Vollständige Unterstützung. |
| Datumsvergleiche | Vollständige Unterstützung. |
| Datumsbereiche | Alle Datumsbereichsfunktionen werden unterstützt. |
| Sommerzeit | Vollständige Unterstützung. |
| Dimensionen | Vollständige Unterstützung; CJA nutzt XDM und unterstützt unbegrenzte Dimensionen. CJA ist nicht an benutzerdefinierte eVars oder Props von herkömmlichem Adobe Analytics gebunden. |
| Vorkonfigurierte Analysis Workspace-Dimensionen (Browser-Typ, Typ der verweisenden Stelle, Betriebssystem usw.) | Customer Journey Analytics stellt diese Dimensionen nativ bereit, solange die grundlegenden XDM-Felder (z. B. Benutzeragent oder Geräte-ID) ausgefüllt sind. Für Kunden, der Data Connector von Analytics (ADC) verwenden, sind einige dieser Dimensionen verfügbar, jedoch nicht alle. Bitte lesen Sie in unserer [Dokumentation, welche Analytics-Variablen über ADC unterstützt werden](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| DSGVO-Löschung | Vollständige Unterstützung; beachten Sie, dass die DSGVO jetzt in Abstimmung mit [!UICONTROL Adobe Experience Platform] gehandhabt wird. CJA übernimmt alle Datenänderungen, die [!UICONTROL Experience Platform] an den zugrunde liegenden Datensätzen vornimmt. |
| Listenvariablen/Listen-Props | Vollständige Unterstützung; CJA nutzt XDM und unterstützt unbegrenzte Zeichenfolgen-Arrays, die ähnlich wie listVars verwendet werden können. |
| Metriken | Vollständige Unterstützung; CJA nutzt das Experience-Datenmodell (XDM), unterstützt unbegrenzte Metriken und ist nicht an die benutzerspezifischen Erfolgsereignisse von traditionellem Analytics gebunden. Beachten Sie, dass einige Standardmetriken in traditionellem Analytics umbenannt wurden: Besucher = Personen, Besuche = Sitzungen, Treffer = Ereignisse. |
| Deduplizierung der Metrik | Vollständige Unterstützung. |
| Bedienfelder | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. |
| PDF-Export | Vollständige Unterstützung. |
| Projektkuration | Vollständige Unterstützung. |
| Projektverknüpfung | Vollständige Unterstützung. |
| Report Builder (Excel-Plug-in) | Vollständige Unterstützung (Oktober 2021) |
| Berichtszeitverarbeitung | Vollständige Unterstützung; CJA basiert ausschließlich auf der Berichtszeitverarbeitung. |
| Zugriff auf die Reporting-API | Vollständige Unterstützung; verfügbar über die [CJA-API](https://www.adobe.io/cja-apis/docs/). |
| Terminierte Berichte/Projekte | Vollständige Unterstützung. |
| Segmente | Vollständige Unterstützung; jetzt „Filter“ genannt. Beachten Sie, dass keine in traditionellem Analysis Workspace vorhandenen Segmente in CJA portiert werden. |
| Benutzerberechtigungen/Datenzugangssteuerung | Vollständige Unterstützung; CJA unterscheidet zwischen Produktadministratoren von [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=de) und Anwendern. Nur Produktadministratoren können <ul><li>Verbindungen oder Datenansichten erstellen/aktualisieren/löschen</li><li>Projekte, Filter oder berechnete Metriken, die von anderen Benutzern erstellt wurden, aktualisieren/löschen</li><li>ein Arbeitsbereich-Projekt für alle Anwender freigeben</li></ul> |
| Virtual Report Suites | Vollständige Unterstützung; jetzt [Datenansichten](/help/data-views/create-dataview.md) genannt. |
| Kuratierung von VRS-Komponenten | Vollständige Unterstützung; jetzt Teil der Datenansichten. |

## Mit Einschränkungen unterstützt

| Funktion | Hinweise |
| --- | --- |
| A4T | Unterstützung wird über Felder im [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) bereitgestellt. |
| Classifications | Jetzt „Lookup-Datensätze“ genannt. In Analytics verwendete Klassifizierungen können in Experience Platform und Customer Journey Analytics mit dem Analytics Classifications Data Connector importiert werden. Lookup-Datensätze können auch direkt in Adobe Experience Platform hochgeladen und in Customer Journey Analytics verfügbar gemacht werden. |
| Benutzerdefinierte Sitzungen | Unterstützung aller benutzerdefinierten Sitzungsfunktionen außer mobilen Hintergrundtreffern. |
| Kundenattribute | Sie werden jetzt als „Profildatensätze“ bezeichnet und nicht automatisch aus Experience Cloud importiert, sondern müssen erst in AEP hochgeladen werden, bevor sie in CJA verfügbar sind. |
| Geräte-, Browser- und Technologie-Dimensionen | Diese Dimensionen werden automatisch eingeschlossen, wenn ein Adobe Experience Platform-Datensatz bestimmte XDM-Schema-Felder enthält und der XDM-Erlebnisereignis-Klasse entspricht. |
| Dimensionen und Metriken zu Eintritten, Austritten und aufgewendeter Zeit | Unterstützt (Eintritte und Austritte werden jetzt als Sitzungsanfang und Sitzungsende bezeichnet) und etwas anders berechnet. |
| eVar-Persistenzeinstellungen | eVars sind nicht mehr Teil von CJA. Die Persistenzeinstellungen sind jetzt jedoch Teil der Datenansichten und für alle Dimensionen verfügbar. Beachten Sie, dass die Persistenz auf der Berichtszeitverarbeitung und nicht auf der Datenerfassungsverarbeitung basiert. Dimensionen, die innerhalb von Datenansichten festgelegt werden, sind auf eine maximale Persistenz von 90 Tagen beschränkt und unterstützen keine unbegrenzte Persistenz. |
| GeoSegmentation-Dimensionen | Alle in Adobe Analytics erfassten Daten zu GeoSegmentation/Geografie strömen über den Analytics Data Connector in CJA. Bei Implementierungen, die nicht den Analytics Data Connector verwenden, z. B. solche, die für die digitale Datenerfassung das AEP-Web-SDK nutzen, werden nicht alle geografischen Suchvorgänge automatisch durchgeführt (Land und Bundesland werden unterstützt, Stadt und Postleitzahl nicht). |
| Marketing-Kanäle | Daten von Marketing-Kanälen werden jetzt über Analytics Data Connector an Customer Journey Analytics weitergeleitet. Die Regeln für den Marketing-Kanal müssen weiterhin im herkömmlichen Adobe Analytics konfiguriert werden. Einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie in der [Customer Journey Analytics Marketing-Kanal-Dokumentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=de#cja-usecases). |
| Produktvariable | In Experience Platform können Benutzer ein Array mit Objekttypfeldern in einem Datensatzschema verwenden, um die Anforderungen dieses Anwendungsfalls zu erfüllen. In Customer Journey Analytics können Kunden beliebige Produktvariablen verwenden und sind nicht wie in Adobe Analytics auf einzelne Variablen beschränkt. |
| Projektfreigabe | Die Projektfreigabe wird nur von zwischen CJA-Anwendern unterstützt. Es gibt keine Projektfreigabe zwischen CJA und dem traditionellen Analysis Workspace. |
| Visualisierungen | Alle Visualisierungen mit Ausnahme der Zuordnungsvisualisierung werden unterstützt. |

## Teilweise Unterstützung

| Funktion | Hinweise |
| --- | --- |
| Bot-Filterung | Bei Data Connector von Analytics (ADC)-basierten Datensätzen wird die Bot-Filterung angewendet. Die allgemeine Bot-Filterlogik für andere Datensätze wird weder von [!UICONTROL Experience Platform] noch von CJA ausgeführt. |
| Media Analytics | Mediendaten stehen als Teil von Analytics Data Connector zur Verfügung. |
| Merchandising-eVars | Das Verhalten von Merchandising-eVars kann mithilfe von Dimensionen innerhalb eines Objectarrays erreicht werden, sofern eine Merchandising-eVar nicht für die Verwendung von Persistenz konfiguriert ist. Derzeit ist die Persistenz für die Merchandising-Dimension nicht verfügbar. |
| Bedienfelder | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. Die Bedienfelder „Segmentvergleich“, „Analytics for Target (A4T)“ und „Gleichzeitige Medienbesucher“ werden nicht unterstützt. |
| Verarbeitungsregeln | Auf Analytics Data Connector-basierte Datensätze werden weiterhin Verarbeitungsregeln angewendet. [Datenvorbereitungsfunktionen in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) können auch als Ersatz für Verarbeitungsregeln für Daten verwendet werden, die direkt an Platform übermittelt werden. |

## Derzeit nicht unterstützt, aber geplant

| Funktion | Hinweise |
| --- | --- |
| Warnhinweise | Unterstützung ist geplant. |
| Beitragsanalyse | Unterstützung ist geplant. |
| Data Warehouse-Berichte (100 % Zeilenexport) | Die Unterstützung über die Analysis Workspace-Oberfläche ist geplant. Der [!UICONTROL Abfrage-Service von Experience Platform] bietet auch eine Schnittstelle für diese Anwendungsfälle in CJA. |
| ID-Zuordnung über Gerätediagramm | Unterstützung ist geplant. |
| Persistenz von Merchandising-Variablen | Unterstützung ist geplant. |
| Echtzeitberichterstellung | Unterstützung ist geplant. |
| Segment IQ | Unterstützung ist geplant. |
| Segmentveröffentlichung (Senden von Segmenten aus Arbeitsbereich an Experience Cloud) | Unterstützung ist geplant. |

## Unterstützung ist noch nicht geplant

| Funktion | Hinweise |
| --- | --- |
| Activity Map | Unterstützung ist noch nicht geplant. |
| Advertising Cloud | Unterstützung ist noch nicht geplant. |
| Classification Rule Builder | Unterstützung ist noch nicht geplant. |
| Daten-Feeds | Unterstützung ist noch nicht geplant. |
| Zusammenfassungs-Data Sources | Unterstützung ist noch nicht geplant. |

## Keine Unterstützung geplant

* Benutzermetriken mit Cross-Device Coop
* Reports &amp; Analytics-Dashboards
* Reports &amp; Analytics-Lesezeichen
* Reports &amp; Analytics-Zielgruppen
* Reports &amp; Analytics-Kalenderereignisse
* Mobile Services
