---
title: Unterstützung der Customer Journey Analytics-Funktion
description: Customer Journey Analytics-Funktionen im Vergleich zu Adobe Analytics-Funktionen.
exl-id: be19aa27-58aa-438d-806c-e27c9a289797
solution: Customer Journey Analytics
feature: Basics
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '2053'
ht-degree: 38%

---

# Adobe Customer Journey Analytics-Funktionsunterstützung

In den folgenden Tabellen ist aufgeführt, welche Funktionen in Adobe Analytics in Customer Journey Analytics unterstützt, teilweise unterstützt oder nicht unterstützt werden und welche Funktionen von Customer Journey Analytics in Adobe Analytics nicht unterstützt oder nicht verfügbar sind. Diese Listen ändern sich im Laufe der Zeit, wenn Funktionen zu Customer Journey Analytics hinzugefügt werden.

## Vollständig unterstützte Funktionen/Komponenten {#full-support}

| Adobe Analytics-Funktion | Hinweise zur Unterstützung |
| --- | --- |
| Anomalieerkennung | Vollständige Unterstützung. |
| Attribution IQ | Vollständige Unterstützung. |
| Berechnete Metriken | Vollständige Unterstützung. Vorhandene berechnete Metriken im herkömmlichen Analysis Workspace werden nicht auf Customer Journey Analytics portiert. |
| Kalenderereignisse | Vollständige Unterstützung. Kalenderereignisse wurden bisher als [Anmerkungen](/help/components/annotations/overview.md) in Workspace implementiert. |
| CSV-Download | Vollständige Unterstützung. |
| Benutzerdefinierte Kalender | Vollständige Unterstützung. |
| Datumsvergleiche | Vollständige Unterstützung. |
| Datumsbereiche | Alle Datumsbereichsfunktionen werden unterstützt. |
| Dimensionen | Vollständige Unterstützung. Customer Journey Analytics verwendet XDM und unterstützt unbegrenzte Dimensionen. Customer Journey Analytics ist nicht an benutzerdefinierte eVars oder Eigenschaften des herkömmlichen Adobe Analytics gebunden. |
| Löschung gemäß der DSGVO | Vollständige Unterstützung; beachten Sie, dass die DSGVO jetzt in Abstimmung mit [!UICONTROL Adobe Experience Platform] gehandhabt wird. Customer Journey Analytics übernimmt alle Datenänderungen [!UICONTROL Experience Platform] führt zu zugrunde liegenden Datensätzen aus. |
| Reporting über Anstieg und Konfidenz | Vollständige Unterstützung über das [Experimentier-Bedienfeld](/help/analysis-workspace/c-panels/experimentation.md) |
| Listenvariablen/Listen-Props | Vollständige Unterstützung. Customer Journey Analytics verwendet XDM und unterstützt unbegrenzte Zeichenfolgen-Arrays, die ähnlich wie listVars verwendet werden können. |
| Merchandising-eVars | Vollständige Unterstützung über [Binding-Dimensionen und Binding-Metriken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=de#binding-dimension) |
| Metriken | volle Unterstützung; Customer Journey Analytics verwendet das Experience-Datenmodell (XDM) und unterstützt unbegrenzte Metriken und ist nicht an die benutzerdefinierten Erfolgsereignisse von Adobe Analytics gebunden. Einige Standardmetriken wurden aus Adobe Analytics umbenannt: Besucher = Personen, Besuche = Sitzungen, Treffer = Ereignisse. |
| Mobile Scorecard/Dashboards | Vollständige Unterstützung. |
| Bedienfelder | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. |
| PDF-Export | Vollständige Unterstützung. |
| Projektkuration | Vollständige Unterstützung. |
| Projektverknüpfung | Vollständige Unterstützung. |
| Berichtszeitverarbeitung | volle Unterstützung; Customer Journey Analytics verlassen sich ausschließlich auf die Berichtszeitverarbeitung. |
| Zugriff auf die Reporting-API | volle Unterstützung; Verfügbar über [Customer Journey Analytics-API](https://developer.adobe.com/cja-apis/docs/). |
| Terminierte Berichte/Projekte | Vollständige Unterstützung. |
| Segmente | Vollständige Unterstützung. Jetzt als &quot;Filter&quot;bezeichnet - Beachten Sie, dass vorhandene Segmente im herkömmlichen Analysis Workspace nicht auf Customer Journey Analytics portiert werden. |
| Virtual Report Suites | Vollständige Unterstützung. Jetzt genannt [Datenansichten](/help/data-views/create-dataview.md). |
| Zusammenstellung der Virtual Report Suite-Komponenten | Vollständige Unterstützung. Jetzt Teil der Datenansichten. |
| Streamen von Media Analytics | Mediendaten sind über den Analytics-Quell-Connector als Teil des Bedienfelds &quot;Gleichzeitige Medienbetrachter&quot;und des Bedienfelds &quot;Besuchszeit für Medienwiedergabe&quot;in Workspace verfügbar. |

{style="table-layout:auto"}

## Auf neue Art unterstützt {#new-support}

| Funktion | Hinweise |
| --- | --- |
| Zielgruppenveröffentlichung (Segment-Publishing) | Wird unterstützt, sofern diese Funktion mit den Adobe-Produkten Customer Data Platform oder Journey Optimizer lizenziert wurde. [Zielgruppenveröffentlichung](/help/components/audiences/audiences-overview.md) sendet Zielgruppen an das Echtzeit-Kundenprofil in Experience Platform. |
| Classifications | Jetzt „Lookup-Datensätze“ genannt. In Analytics verwendete Classifications können mithilfe des Analytics Classifications Source Connector in die Experience Platform und den Customer Journey Analytics importiert werden. Lookup-Datensätze können auch direkt in Experience Platform hochgeladen und in Customer Journey Analytics verfügbar gemacht werden. |
| Classification Rule Builder | Unterstützt mit [Teilzeichenfolgen](/help/data-views/component-settings/substring.md) in Customer Journey Analytics. Verwendet zum Zeitpunkt der Berichtserstellung Zeichenfolgenmanipulationen anstelle von Lookup-Datensätzen. |
| Benutzerdefinierte Sitzungen | Unterstützung für alle benutzerdefinierten Sitzungsfunktionen außer mobilen Hintergrundereignissen. |
| Währungsumrechnung | Unterstützt als Teil von [Formatieren einer Metrikkomponente](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/format.html?lang=en#currency) in einer Datenansicht. |
| Persistenz von Merchandising-Variablen | Vollständige Unterstützung über [Binding-Dimensionen und Binding-Metriken](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=de#binding-dimension) |
| Kundenattribute | Jetzt als &quot;Profildatensätze&quot;bezeichnet, werden sie nicht automatisch aus Experience Cloud importiert, sondern müssen in Experience Platform hochgeladen werden, bevor sie in Customer Journey Analytics verfügbar sind. |
| Daten-Feeds | Der Datenexport der ersten Generation von Datensätzen ist über das [Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html?lang=en) und [Experience Platform-Ziele](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=de). Diese Optionen bieten den Export aller erfassten oder in den Experience Platform Data Lake erfassten Daten auf Ereignis-/Zeilenebene. Nachbearbeitungs-Datenspalten sind nicht verfügbar, da Post-Spalten zur Abfragezeit berechnet werden. Der Export von Post-Spalten ist über Berichte verfügbar. |
| Deduplizierung von Metriken | Nun für Metriken in Datenansichten konfiguriert. Die Metrik-Deduplizierung erfolgt auf Personen- oder Sitzungsebene und nicht auf Datensatz-, Datenansichts- oder Verbindungsebene. |
| Dimensionen und Metriken zu Eintritten, Austritten und aufgewendeter Zeit | Unterstützt (Eintritte und Austritte werden jetzt als Sitzungsanfang und Sitzungsende bezeichnet) und etwas anders berechnet. |
| eVar-Persistenzeinstellungen | eVars sind nicht mehr Teil von Customer Journey Analytics. Die Persistenzeinstellungen sind jetzt jedoch Teil der Datenansichten und für alle Dimensionen verfügbar. Beachten Sie, dass die Persistenz auf der Berichtszeitverarbeitung und nicht auf der Datenerfassungsverarbeitung basiert. In Datenansichten festgelegte Dimensionen sind auf eine maximale Persistenz von 90 Tagen beschränkt und unterstützen keine unbegrenzte Persistenz. |
| IP-Verschleierung | Für Customer Journey Analytics, die den Analytics-Quell-Connector verwenden, um Daten aus Adobe Analytics in Customer Journey Analytics zu füllen: Die in Adobe Analytics angewendeten IP-Verschleierungseinstellungen fließen durch Ihre Customer Journey Analytics-Daten. Sie können diese Einstellungen nach Bedarf in Adobe Analytics steuern.<p>Für Customer Journey Analytics, die das Experience Platform Web SDK verwenden, um Daten direkt in Platform und Customer Journey Analytics zu füllen. Sie können die Datenvorbereitung für die Datenerfassung in Platform verwenden, um Regeln zu konfigurieren, die die IP-Adresse basierend auf den Anforderungen Ihres Unternehmens verschleiern. |
| Reporting über neue und wiederholte Sitzungen | Erfolgte bislang über die Dimension „Anzahl der Besuche“. Neue und wiederholte Sitzungen werden [mit einem 13-monatigen Lookback-Fenster](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/data-views/data-views-usecases.html?lang=de) unterstützt. |
| Produktvariable | In Experience Platform können Benutzer ein Array mit Objekttypfeldern in einem Datensatzschema verwenden, um die Anforderungen dieses Anwendungsfalls zu erfüllen. In Customer Journey Analytics können Kunden eine beliebige Anzahl von Produktvariablen verwenden und sind nicht wie in Adobe Analytics auf eine einzelne Variable beschränkt. |
| Projektfreigabe | Die Projektfreigabe wird nur zwischen Anwendern von Customer Journey Analytics unterstützt. Es gibt keine Projektfreigabe zwischen Customer Journey Analytics und dem herkömmlichen Analysis Workspace. |
| Visualisierungen | Alle Visualisierungen mit Ausnahme der Zuordnungsvisualisierung werden unterstützt. |
| Report Builder (Excel-Plug-in) | Unterstützt mit einem neuen Office 365-Plug-in für Excel. |
| Benutzerberechtigungen/Datenzugriffssteuerung | Customer Journey Analytics unterscheidet zwischen [Adobe Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=de) Produktadministratoren, Produktprofiladministratoren und Benutzer. Nur Produktadministrierende können von anderen Benutzenden erstellte Verbindungen, Projekte, Filter oder berechnete Metriken erstellen/aktualisieren/löschen, während Produktadministrierende und Produktprofiladministrierende Datenansichten bearbeiten können. Zusätzliche Benutzerberechtigungen sind für Dinge wie das Erstellen berechneter Metriken, Filter oder Anmerkungen verfügbar. |
| Verarbeitungsregeln, VISTA-Regeln, Verarbeitungsregeln für Marketing-Kanäle | Wird sowohl für WebSDK-basierte Datensätze als auch für Daten aus dem Analytics-Quell-Connector mit der Adobe Experience Platform-Datenvorgangsfunktion unterstützt. |
| Marketing-Kanäle | Bei Verwendung des Analytics-Quell-Connectors fließen Daten von Marketing-Kanälen über diesen Connector in Customer Journey Analytics. Marketingkanalregeln werden im herkömmlichen Adobe Analytics konfiguriert und einige Regeln werden nicht unterstützt. Weitere Informationen finden Sie unter [Dokumentation zu Customer Journey Analytics Marketing Channels](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/aa-data/marketing-channels.html). <br/>Bei WebSDK-Implementierungen werden Verarbeitungsregeln für Berichtszeitmarketingkanäle über unterstützt. [Abgeleitete Felder](../../data-views/derived-fields/derived-fields.md). |

{style="table-layout:auto"}

## Teilweise Unterstützung {#partial}

| Funktion | Hinweise |
| --- | --- |
| Geräteübergreifendes/kanalübergreifendes Stitching | Unterstützt bei Datensätzen, die direkt Identitätsinformationen enthalten (auch als „feldbasiertes“ Stitching bezeichnet). Diagrammbasiertes Stitching wird noch nicht unterstützt, ist aber in Planung. Siehe [Stitching](../../stitching/overview.md). |
| Bot-Filterung | Für [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de)-basierte Datensätze verwenden, wird die Bot-Filterung angewendet. Die allgemeine Bot-Filterlogik für andere Datensätze wird nicht von der [!UICONTROL Experience Platform] oder Customer Journey Analytics. |
| Dimensionen Gerät, Browser, Referrer, Technologie | Unterstützt für [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de)-basierte Datensätze. Siehe [Dokumentation darüber, welche Analytics-Variablen über ADC unterstützt werden](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics.html?lang=de).<p>Wenn Sie die Experience Platform Web SDK-Datenerfassung verwenden, werden Gerät und Dimensionen, die auf der Gerätesuche basieren, derzeit nicht unterstützt. Eine künftige Unterstützung ist geplant. |
| GeoSegmentation-Dimensionen | Alle in Adobe Analytics erfassten GeoSegmentation/Geografie fließen über die [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de). Implementierungen, die nicht den Analytics-Quell-Connector verwenden, aber für die digitale Datenerfassung auf das Experience Platform Web SDK angewiesen sind, können die [Experience Edge Geo Lookup-Dienst](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=de). |
| Bedienfelder | Leeres Bedienfeld, Attributions-Bedienfeld, Freiform-Bedienfeld und Quick Insights werden vollständig unterstützt. Die Bedienfelder „Segmentvergleich“ und „Analytics for Target“ (A4T) werden nicht unterstützt. |
| Verarbeitungsregeln | Für Analytics-Quell-Connector-basierte Datensätze werden weiterhin Verarbeitungsregeln angewendet. [Datenvorbereitungsfunktionen in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) können auch als Ersatz für Verarbeitungsregeln für Daten verwendet werden, die direkt an Platform übermittelt werden. |
| A4T | Teilweise wird die Unterstützung über Felder im [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de). Die Unterstützung von A4T-gerechten Namen für die Zielgruppenaktivitäten und -erfahrungen ist geplant. |

{style="table-layout:auto"}

## Keine Unterstützung, aber geplant {#planned}

| Funktion | Hinweise |
| --- | --- |
| Warnhinweise | Unterstützung ist geplant. |
| Beitragsanalyse | Unterstützung ist geplant. |
| Data Warehouse Reporting | Die Unterstützung über die Analysis Workspace-Oberfläche ist geplant. Adobe Experience Platform [[!UICONTROL Query Service]](<https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de>) bietet außerdem eine Schnittstelle für diese Anwendungsfälle in Customer Journey Analytics. |
| ID-Zuordnung über Gerätediagramm | Unterstützung ist geplant. |
| Projektvorlagen | Unterstützung ist geplant. |
| Echtzeitberichterstellung | Unterstützung ist geplant. |
| Segment IQ | Unterstützung ist geplant. |
| Transaktions-ID-Datenquellen | Unterstützung ist geplant. |
| Migrieren von Projekten/Filtern/berechneten Metriken von Adobe Analytics zu Customer Journey Analytics | Unterstützung ist geplant. |
| Datenquellen auf Zusammenfassungsebene | Unterstützung ist geplant. |

{style="table-layout:auto"}

## Keine Unterstützung, noch nicht geplant {#not-planned}

| Funktion | Hinweise |
| --- | --- |
| Activity Map | Unterstützung ist noch nicht geplant. |
| Advertising Cloud | Unterstützung ist noch nicht geplant. |

{style="table-layout:auto"}

## Nie unterstützt {#never}

* Benutzermetriken mit Cross-Device Coop
* Reports &amp; Analytics-Dashboards
* Reports &amp; Analytics-Lesezeichen
* Reports &amp; Analytics-Zielgruppen

## Adobe Customer Journey Analytics-Funktionen sind in Adobe Analytics nicht verfügbar {#cja-not-aa}

In der folgenden Tabelle sind Funktionen aufgeführt, die in Customer Journey Analytics verfügbar sind, in Adobe Analytics jedoch nicht unterstützt werden.

| Funktion | Mehr Infos |
| --- | --- |
| Unterkunft für jede Art von Daten | Customer Journey Analytics wird mit der Fähigkeit der Experience Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Verwenden [Experience-Datenmodell (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de), können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und untersucht werden können. Adobe Analytics konzentriert sich hauptsächlich auf Web- und mobile Analysedaten mit einigen Funktionen für [Daten importieren](https://experienceleague.adobe.com/docs/analytics/import/home.html?lang=de). |
| Unbegrenzte Dimensionen und Metriken für Kunden | Customer Journey Analytics-Dimensionen sind unbegrenzt. -Werte können numerisch, Text, Objekte, Listen oder Mischungen von allen sein. Dimensionen können verschachtelt oder hierarchisch aufgebaut sein. Analytics unterstützt maximal 75 Props und 250 eVars. |
| Unbegrenzte Kardinalität/eindeutige Werte | Customer Journey Analytics unterstützt unbegrenzte eindeutige Werte oder Dimensionselemente, über die innerhalb einer Dimension berichtet werden kann. Adobe Analytics ist auf 500.000 eindeutige Werte begrenzt. Durch die unbegrenzten eindeutigen Werte oder Dimensionen werden die Berichterstellungs- und Analysebeschränkungen aufgehoben, die derzeit bei einer umfangreichen Analytics-Implementierung bestehen. |
| Berichtszeitumwandlungen | Mit Berichtszeitumwandlungen (besser als Datenansichten bezeichnet) in Customer Journey Analytics können Sie Daten aus einer Verbindung weiter interpretieren. Sie können Daten ohne erneute Implementierung ändern oder entfernen. Verwenden von Unterzeichenfolgen zum Bearbeiten von Dimensionen; Metriken aus einem beliebigen Wert erstellen; Filterereignisse. Und die Transformation erfolgt alle zerstörungsfrei. Adobe Analytics bietet eingeschränkte Funktionen durch Virtual Report Suites und die Sitzungserstellung. |
| Experimentanalyse | Customer Journey Analytics können die Steigerung und Konfidenz jedes Experiments aus jeder Datenquelle bewerten, die als Teil einer Verbindung definiert wurde. Diese Auswertung ermöglicht Ihnen, die Ursache-Wirkungs-Beziehungen zwischen Kundeninteraktionen zu verstehen, die sich über einen beliebigen Kanal erstrecken. Analytics ist auf die experimentelle Analyse über die Integration von Analytics for Target (A4T) beschränkt. |
| Cross-Device Analytics | Customer Journey Analytics unterstützt die nahtlose Kombination gerätespezifischer Datensätze aus nicht authentifizierten und authentifizierten Sitzungen. Customer Journey Analytics bietet die Möglichkeit, historische Daten auf bekannte Geräte aufzustocken. In Analytics ist diese Funktion auf eine einzige Report Suite und die Verwendung eines Gerätediagramms beschränkt. |
| SQL-Zugriff | Mit der Option Data Distiller können Customer Journey Analytics die Einschränkungen von Daten beseitigen, die bei der Backend-Verarbeitung der Adobe erfasst wurden. Sie können Ihre Daten mit SQL ändern, unternehmensspezifische Werte und Datensätze erstellen und die Erforschung fortsetzen. Analytics unterstützt keinen SQL-Zugriff auf seine Daten. |
| Verbesserte Sicherheits- und Datenschutzoptionen - HIPAA-Bereitschaft | Customer Journey Analytics ist bereit für HIPAA und bietet zusätzliche Sicherheitsoptionen für die Einhaltung von Vorschriften. Adobe Analytics ist nicht bereit für HIPAA. |

{style="table-layout:auto"}
