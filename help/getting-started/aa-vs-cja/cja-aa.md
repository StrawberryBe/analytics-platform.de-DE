---
title: Unterstützung der Customer Journey Analytics-Funktion
description: Customer Journey Analytics-Funktionen im Vergleich zu Adobe Analytics-Funktionen.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: c87d7428a2ddca35297225314e97171fe8b129fb
workflow-type: tm+mt
source-wordcount: '1525'
ht-degree: 98%

---

# Unterstützung der Customer Journey Analytics-Funktion

In den folgenden Tabellen ist aufgeführt, welche Funktionen in Adobe Analytics in Customer Journey Analytics (CJA) unterstützt, teilweise unterstützt oder nicht unterstützt werden. Diese Listen ändern sich im Laufe der Zeit, wenn CJA Funktionen hinzugefügt werden.

## Vollständig unterstützte Funktionen/Komponenten

| Adobe Analytics-Funktion | Hinweise zur Unterstützung |
| --- | --- |
| Anomalieerkennung | Vollständige Unterstützung. |
| Attribution IQ | Vollständige Unterstützung. |
| Berechnete Metriken | Vollständige Unterstützung; beachten Sie, dass vorhandene berechnete Metriken in herkömmlichem Analysis Workspace nicht in CJA portiert werden. |
| Kalenderereignisse | Vollständige Unterstützung. Kalenderereignisse wurden bisher als [Anmerkungen](/help/components/annotations/overview.md) in Workspace implementiert. |
| CSV-Download | Vollständige Unterstützung. |
| Benutzerdefinierte Kalender | Vollständige Unterstützung. |
| Datumsvergleiche | Vollständige Unterstützung. |
| Datumsbereiche | Alle Datumsbereichsfunktionen werden unterstützt. |
| Dimensionen | Vollständige Unterstützung; CJA nutzt XDM und unterstützt unbegrenzte Dimensionen. CJA ist nicht an benutzerdefinierte eVars oder Props von herkömmlichem Adobe Analytics gebunden. |
| Löschung gemäß der DSGVO | Vollständige Unterstützung; beachten Sie, dass die DSGVO jetzt in Abstimmung mit [!UICONTROL Adobe Experience Platform] gehandhabt wird. CJA übernimmt alle Datenänderungen, die [!UICONTROL Experience Platform] an den zugrunde liegenden Datensätzen vornimmt. |
| Reporting über Anstieg und Konfidenz | Vollständige Unterstützung über das [Experimentier-Bedienfeld](/help/analysis-workspace/c-panels/experimentation.md) |
| Listenvariablen/Listen-Props | Vollständige Unterstützung; CJA nutzt XDM und unterstützt unbegrenzte Zeichenfolgen-Arrays, die ähnlich wie listVars verwendet werden können. |
| Merchandising-eVars | Vollständige Unterstützung über [Binding-Dimensionen und Binding-Metriken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=de#binding-dimension) |
| Metriken | Vollständige Unterstützung; CJA nutzt das Experience-Datenmodell (XDM), unterstützt unbegrenzte Metriken und ist nicht an die benutzerspezifischen Erfolgsereignisse von traditionellem Analytics gebunden. Beachten Sie, dass einige Standardmetriken in traditionellem Analytics umbenannt wurden: Besucher = Personen, Besuche = Sitzungen, Treffer = Ereignisse. |
| Mobile Scorecard/Dashboards | Vollständige Unterstützung. |
| Bedienfelder | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. |
| PDF-Export | Vollständige Unterstützung. |
| Projektkuration | Vollständige Unterstützung. |
| Projektverknüpfung | Vollständige Unterstützung. |
| Berichtszeitverarbeitung | Vollständige Unterstützung; CJA basiert ausschließlich auf der Berichtszeitverarbeitung. |
| Zugriff auf die Reporting-API | Vollständige Unterstützung; verfügbar über die [CJA-API](https://www.adobe.io/cja-apis/docs/). |
| Terminierte Berichte/Projekte | Vollständige Unterstützung. |
| Segmente | Vollständige Unterstützung; jetzt „Filter“ genannt. Beachten Sie, dass keine in traditionellem Analysis Workspace vorhandenen Segmente in CJA portiert werden. |
| Virtual Report Suites | Vollständige Unterstützung; jetzt [Datenansichten](/help/data-views/create-dataview.md) genannt. |
| Kuratierung von VRS-Komponenten | Vollständige Unterstützung; jetzt Teil der Datenansichten. |
| Streamen von Media Analytics | Mediendaten sind über den Analytics Data Connector als Teil des Bedienfelds „Gleichzeitige Medienbetrachter“ und des Bedienfelds „Bei Medienwiedergabe verbrachte Zeit“ in Workspace verfügbar. |

{style=&quot;table-layout:auto&quot;}

## Auf neue Art unterstützt

| Funktion | Hinweise |
| --- | --- |
| Zielgruppenveröffentlichung (Segment-Publishing) | Wird unterstützt, sofern diese Funktion mit den Adobe-Produkten Customer Data Platform oder Journey Optimizer lizenziert wurde. [Zielgruppenveröffentlichung](/help/components/audiences/audiences-overview.md) sendet Zielgruppen an das Echtzeit-Kundenprofil in Experience Platform. |
| Classifications | Jetzt „Lookup-Datensätze“ genannt. In Analytics verwendete Klassifizierungen können mit dem Analytics Classifications Source Connector in Experience Platform und Customer Journey Analytics importiert werden. Lookup-Datensätze können auch direkt in Adobe Experience Platform hochgeladen und in Customer Journey Analytics verfügbar gemacht werden. |
| Classification Rule Builder | Unterstützt mit [Teilzeichenfolgen](/help/data-views/component-settings/substring.md) in CJA. Verwendet zum Zeitpunkt der Berichtserstellung Zeichenfolgenmanipulationen anstelle von Lookup-Datensätzen. |
| Benutzerdefinierte Sitzungen | Unterstützung aller benutzerdefinierten Sitzungsfunktionen außer mobiler Hintergrundtreffer. |
| Persistenz von Merchandising-Variablen | Vollständige Unterstützung über [Binding-Dimensionen und Binding-Metriken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=de#binding-dimension) |
| Kundenattribute | Sie werden jetzt als „Profildatensätze“ bezeichnet und nicht automatisch aus Experience Cloud importiert, sondern müssen erst in AEP hochgeladen werden, bevor sie in CJA verfügbar sind. |
| Deduplizierung von Metriken | Nun für Metriken in Datenansichten konfiguriert. Die Metrik-Deduplizierung erfolgt auf Personen- oder Sitzungsebene und nicht auf Datensatz-, Datenansichts- oder Verbindungsebene. |
| Dimensionen und Metriken zu Eintritten, Austritten und aufgewendeter Zeit | Unterstützt (Eintritte und Austritte werden jetzt als Sitzungsanfang und Sitzungsende bezeichnet) und etwas anders berechnet. |
| eVar-Persistenzeinstellungen | eVars sind nicht mehr Teil von CJA. Die Persistenzeinstellungen sind jetzt jedoch Teil der Datenansichten und für alle Dimensionen verfügbar. Beachten Sie, dass die Persistenz auf der Berichtszeitverarbeitung und nicht auf der Datenerfassungsverarbeitung basiert. Dimensionen, die innerhalb von Datenansichten festgelegt werden, sind auf eine maximale Persistenz von 90 Tagen beschränkt und unterstützen keine unbegrenzte Persistenz. |
| IP-Verschleierung | Für CJA-Kunden, die den Analytics Source Connector verwenden, um Daten aus Adobe Analytics in CJA einzupflegen: Die in Adobe Analytics vorgenommenen Einstellungen zur IP-Verschleierung fließen in Ihre CJA-Daten ein. Sie können diese Einstellungen nach Bedarf in Adobe Analytics steuern.<p>Für CJA-Kunden, die das Adobe Experience Platform Web SDK verwenden, um Daten direkt in Platform und CJA einzugeben: Sie können die Data Prep für die Datenerfassung in Platform verwenden, um Regeln zu konfigurieren, die die IP-Adresse basierend auf den Anforderungen Ihres Unternehmens verschleiern. |
| Reporting über neue und wiederholte Sitzungen | Erfolgte bislang über die Dimension „Anzahl der Besuche“. Neue und wiederholte Sitzungen werden [mit einem 13-monatigen Lookback-Fenster](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=de#new-repeat) unterstützt. |
| Produktvariable | In Experience Platform können Benutzer ein Array mit Objekttypfeldern in einem Datensatzschema verwenden, um die Anforderungen dieses Anwendungsfalls zu erfüllen. In Customer Journey Analytics können Kunden beliebige Produktvariablen verwenden und sind nicht wie in Adobe Analytics auf eine einzelne Variable beschränkt. |
| Projektfreigabe | Die Projektfreigabe wird nur von zwischen CJA-Anwendern unterstützt. Es gibt keine Projektfreigabe zwischen CJA und dem traditionellen Analysis Workspace. |
| Visualisierungen | Alle Visualisierungen mit Ausnahme der Zuordnungsvisualisierung werden unterstützt. |
| Report Builder (Excel-Plug-in) | Unterstützt mit einem neuen Office 365-Plug-in für Excel. |
| Benutzerberechtigungen/Datenzugriffssteuerung | CJA unterscheidet zwischen [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=de)-Produktadministrierenden, -Produktprofiladministrierenden und -Benutzenden. Nur Produktadministrierende können von anderen Benutzenden erstellte Verbindungen, Projekte, Filter oder berechnete Metriken erstellen/aktualisieren/löschen, während Produktadministrierende und Produktprofiladministrierende Datenansichten bearbeiten können. Zusätzliche Benutzerberechtigungen sind für Vorgänge wie das Erstellen von berechneten Metriken, Filtern oder Anmerkungen verfügbar. |
| Verarbeitungsregeln, VISTA-Regeln, Verarbeitungsregeln für Marketing-Kanäle | Wird sowohl für WebSDK-basierte Datensätze als auch für Daten vom Analytics Data Connector über die Adobe Experience Platform-Datenvorbereitungsfunktion unterstützt. |

{style=&quot;table-layout:auto&quot;}

## Teilweise Unterstützung

| Funktion | Hinweise |
| --- | --- |
| Marketing-Kanäle | Daten von Marketing-Kanälen werden über den Analytics-Quell-Connector an CJA weitergeleitet. Marketing-Kanalregeln müssen weiterhin im herkömmlichen Adobe Analytics-Tool konfiguriert werden, und einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie in der [Dokumentation zu Marketing-Kanälen von Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=de#cja-usecases). Darüber hinaus stehen für WebSDK-Implementierungen Plug-ins zur Client-seitigen Definition von Marketing-Kanälen zur Verfügung. Zukünftig sollen auch berichtszeitbezogene Verarbeitungsregeln für Marketing-Kanäle unterstützt werden. |
| Geräteübergreifendes/kanalübergreifendes Stitching | Unterstützt bei Datensätzen, die direkt Identitätsinformationen enthalten (auch als „feldbasiertes“ Stitching bezeichnet). Diagrammbasiertes Stitching wird noch nicht unterstützt, ist aber in Planung. Siehe die [Cross-Channel-Analyse](/help/cca/overview.md). |
| Bot-Filterung | Bei Datensätzen, die auf dem [Adobe Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) basieren, wird die Bot-Filterung angewendet. Die allgemeine Bot-Filterlogik für andere Datensätze wird weder von [!UICONTROL Experience Platform] noch von CJA ausgeführt. |
| Dimensionen Gerät, Browser, Referrer, Technologie | Unterstützt für [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de)-basierte Datensätze. Bitte lesen Sie in unserer [Dokumentation, welche Analytics-Variablen über ADC unterstützt werden](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=de).<p>Wenn Sie Adobe Source Connector nicht zum Übertragen von Daten von Adobe Analytics nach Customer Journey Analytics verwenden, sondern stattdessen die Experience Platform Web SDK-Datenerfassung nutzen, werden das Gerät und die Dimensionen, die auf der Gerätesuche basieren, derzeit nicht unterstützt. Eine künftige Unterstützung ist geplant. |
| GeoSegmentation-Dimensionen | Alle in Adobe Analytics erfassten Daten zu GeoSegmentation/Geografie fließen über den [Analytics Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) in CJA. Bei Implementierungen, die nicht den Analytics-Quell-Connector verwenden, z. B. solche, die für die digitale Datenerfassung das AEP-Web-SDK nutzen, werden nicht alle geografischen Suchvorgänge automatisch durchgeführt (so werden etwa Land und US-Bundesstaat unterstützt, Stadt und Postleitzahl dagegen nicht). |
| Bedienfelder | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. Die Bedienfelder „Segmentvergleich“ und „Analytics for Target“ (A4T) werden nicht unterstützt. |
| Verarbeitungsregeln | Auf Datensätze, die auf dem Analytics-Quell-Connector basieren, werden weiterhin Verarbeitungsregeln angewendet. [Datenvorbereitungsfunktionen in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) können auch als Ersatz für Verarbeitungsregeln für Daten verwendet werden, die direkt an Platform übermittelt werden. |
| A4T | Teilweise Unterstützung wird über Felder im [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) bereitgestellt. Unterstützung für A4T-freundliche Namen für Target-Aktivitäten und -Erlebnisse ist geplant. |

{style=&quot;table-layout:auto&quot;}

## Derzeit nicht unterstützt, aber geplant

| Funktion | Hinweise |
| --- | --- |
| Warnhinweise | Unterstützung ist geplant. |
| Beitragsanalyse | Unterstützung ist geplant. |
| Data Warehouse Reporting | Die Unterstützung über die Analysis Workspace-Oberfläche ist geplant. Der [[!UICONTROL Abfrage-Service]](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de) von Adobe Experience Platform bietet auch eine Schnittstelle für diese Anwendungsfälle in CJA. |
| ID-Zuordnung über Gerätediagramm | Unterstützung ist geplant. |
| Projektvorlagen | Unterstützung ist geplant. |
| Echtzeitberichterstellung | Unterstützung ist geplant. |
| Segment IQ | Unterstützung ist geplant. |
| Währungsumrechnung | Unterstützung ist geplant. |
| Daten-Feeds | Unterstützung ist über AEP-Ziele geplant. |
| Transaktions-ID-Datenquellen | Unterstützung ist geplant. |
| Migrieren von Projekten/Filtern/berechneten Metriken von AA zu CJA | Unterstützung ist geplant. |
| Datenquellen auf Zusammenfassungsebene | Unterstützung ist geplant. |

{style=&quot;table-layout:auto&quot;}

## Unterstützung ist noch nicht geplant

| Funktion | Hinweise |
| --- | --- |
| Activity Map | Unterstützung ist noch nicht geplant. |
| Advertising Cloud | Unterstützung ist noch nicht geplant. |

{style=&quot;table-layout:auto&quot;}

## Keine Unterstützung geplant

* Benutzermetriken mit Cross-Device Coop
* Reports &amp; Analytics-Dashboards
* Reports &amp; Analytics-Lesezeichen
* Reports &amp; Analytics-Zielgruppen
* Mobile Services
