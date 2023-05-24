---
title: Vergleich der Datenverarbeitung zwischen Reporting-Funktionen von Adobe Analytics und CJA
description: Verstehen der Unterschiede bei der Datenverarbeitung für die verschiedenen Reporting-Funktionen
exl-id: e3deedb2-0171-4fc2-9127-b9543603d4f0
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 71%

---

# Vergleichen Sie die Datenverarbeitung in Adobe Analytics und Customer Journey Analytics.

Sie benötigen häufig die Möglichkeit, Daten zu verarbeiten, bevor sie für die Berichterstellung nützlich sind. Sie können diese Daten in verschiedenen Phasen der Journey verarbeiten, von der Datenerfassung bis zur Erstellung Ihres Berichts oder Ihrer Visualisierung.

In Adobe Analytics erfolgt der Großteil dieser Datenverarbeitung unmittelbar nach der Datenerfassung. Funktionen wie VISTA-Regeln, Verarbeitungsregeln und Verarbeitungsregeln für Marketing-Kanäle stehen zur Unterstützung dieser Funktion zur Verfügung **Sammlungszeitverarbeitung**.
Die Daten werden dann gespeichert und zum Zeitpunkt des Berichts können Sie eine zusätzliche Verarbeitung vornehmen. Beispielsweise können Sie Dimensionen aufschlüsseln, eine Segmentierung anwenden oder ein anderes Attributionsmodell auswählen. Diese **Berichtszeitverarbeitung** passiert von vorn.

In Adobe Analytics ist die Berichtszeitverarbeitung normalerweise kleiner als die Verarbeitung zur Erfassungszeit.

![Verarbeitung der Erfassungszeit von Adobe Analytics](../assets/aa-processing.png)

Im Gegensatz dazu ist Customer Journey Analytics (CJA) so konzipiert, dass eine minimale Vorabverarbeitung während der Erfassung erforderlich ist, bevor Daten organisiert und gespeichert werden. Die zugrunde liegende Architektur von CJA wurde für die Arbeit mit den gespeicherten Daten zur Berichtszeit konzipiert und bietet seine leistungsstarke Berichtszeitverarbeitungsfunktion nicht nur in Workspace, sondern auch, noch wichtiger, durch die Definition von [Komponenten](/help/data-views/component-settings/overview.md) und [abgeleitete Felder](/help/data-views/derived-fields/derived-fields.md) in Ihren Datenansichten.

![CJA-Berichtszeitverarbeitung](../assets/cja-processing.png)

Das Verständnis der Unterschiede bei der Datenverarbeitung für die verschiedenen Reporting-Funktionen kann hilfreich sein, um zu verstehen, welche Metriken wo verfügbar sind und warum sie sich unterscheiden können.

Da beispielsweise „Besuche“ als Metrik in Adobe Analytics zur Datenverarbeitungszeit definiert wird und „Sitzungen“ als Metrik in CJA zur Berichtszeit berechnet wird, können die beiden Metriken je nach den Regeln, die für die Sitzungsdefinition in der CJA-Datenansicht verwendet werden, unterschiedlich sein.

Außerdem sind weder Besuche noch Sitzungen als Metrik in Datensätzen verfügbar, die vom Analytics-Quell-Connector erstellt wurden. Daher müssten Sie die Sitzung in Ihrer Abfragelogik definieren, um Vergleiche durchzuführen.

## Terminologie {#terms}

In der folgenden Tabelle wird die Terminologie für die verschiedenen Arten von Verarbeitungslogik definiert, die auf Adobe Analytics und CJA angewendet werden:

| Begriff | Definition | Hinweise |
| --- | --- | --- |
| Verarbeitung der Sammlungszeit | Logik, die ausgeführt wird, wenn Daten erfasst und verarbeitet werden, bevor sie zu Berichts- und Analysezwecken gespeichert werden. | Diese Logik wird in historische Daten aufgenommen und kann im Allgemeinen nicht einfach geändert werden. |
| Berichtszeitverarbeitung | Logik, die zum Zeitpunkt der Berichtsausführung ausgeführt wird. | Diese Logik kann zur Berichtslaufzeit auf zerstörungsfreie Weise auf zukünftige und historische Daten angewendet werden. |
| Logik auf Trefferebene | Logik, die Zeile für Zeile angewendet wird. | Beispiele: Verarbeitungsregeln, VISTA, bestimmte Regeln von Marketing-Kanälen. |
| Logik auf Besuchsebene | Logik, die auf Besuchsebene angewendet wird. | Beispiele: Besuchs- und Sitzungsdefinition. |
| Logik auf Besucherebene | Logik, die auf der Personenebene angewendet wird. | Beispiel: Geräteübergreifende/kanalübergreifende Personenzuordnung. |
| Segmentlogik (Filterlogik) | Auswertung der Segmentregeln für Ereignis/Besuch/Person (Ereignis/Sitzung/Person) (Filter). | Beispiel: Personen, die rote Schuhe gekauft haben. |
| Berechnete Metriken | Auswertung benutzerdefinierter Metriken, die von Kunden erstellt wurden und auf komplexen Formeln, einschließlich Segmenten und Filtern, basieren können. | Beispiel: Anzahl der Personen, die rote Schuhe gekauft haben. |
| Attributionslogik | Logik zur Berechnung der Attribution. | Beispiel: eVar-Persistenz. |
| Komponenteneinstellungen | Anwenden von Anpassungen auf Metriken oder Dimensionen, wie Attribution, Verhalten, Format und andere | Beispiel: Wertesammlung zum Kombinieren numerischer Werte basierend auf einem Bereich |
| Benutzerdefinierte Felder | Logik gilt für Schema- oder Standardfelder bei der Definition von Komponenten in einer Datenansicht. | Beispiel: Erstellen einer neuen Marketing-Kanal-Dimension |

{style="table-layout:auto"}

Im Laufe der Zeit haben Adobe Analytics und jetzt Customer Journey Analytics ihre Flexibilität verbessert, indem sie die Ausführung der Datendlogik auf Besuchs- und Personenebene zur Berichtslaufzeit ermöglichen.

## Typen von Datenverarbeitung {#types}

Die für Adobe und CJA durchgeführten Datenverarbeitungsschritte und der Zeitpunkt dieser Schritte sind je nach Analytics-Funktion unterschiedlich. Die nachstehende Tabelle bietet eine Zusammenfassung der Typen von Datenverarbeitung für jede Analytics-Funktion und gibt an, wann die Datenverarbeitung angewendet wird.

| Funktion | Zur Verarbeitungszeit angewendet | Zur Berichtszeit angewendet | Nicht verfügbar | Hinweise |
| --- | --- | --- | --- | --- |
| [Core AA](https://experienceleague.adobe.com/docs/analytics.html?lang=de)-Reporting<br/>(ohne Attribution IQ oder Virtual Report Suites mit Verarbeitung zur Berichtszeit) | <ul><li>[Verarbeitungsregeln](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules.html?lang=de)</li><li>[VISTA-Regeln](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=de)</li><li>Trefferebene [Regeln von Marketing-Kanälen](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=de)</li><li>Regeln von Marketing-Kanälen auf Besuchsebene (siehe Hinweis)</li><li>Besuchsdefinition</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li><li>Berechnete Metriken</li></ul> | <ul><li>Cross-Device Analytics (siehe Hinweis)</li></ul> | <ul><li>CDA erfordert die Verwendung von Virtual Report Suites mit Berichtszeitverarbeitung.</li><li>Die „Regeln für Marketing-Kanäle auf Besuchsebene“ umfassen Folgendes: **Ist erste Seite des Besuchs**, **Last Touch-Kanal überschreiben** und **Marketing-Kanalgültigkeit**. (Siehe die [Dokumentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=de).)</li></ul> |
| Core AA [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=de) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li><li>Besuchsdefinition</li><li>Attributionslogik</li></ul> | <ul><li>Segmentlogik</li></ul> | <ul><li>Berechnete Metriken</li><li>Cross-Device Analytics</li></ul> |  |
| Core AA [Daten-Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=de) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li><li>Besuchsdefinition (visitnum-Feld)</li><li>Attributionslogik (in Post-Spalten)</li></ul> |  | <ul><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Cross-Device Analytics</li></ul> | <ul><li>ID-Zuordnungen für bestimmte Spalten, die mit Marketing-Kanälen in Daten-Feeds in Verbindung stehen, sind nicht in den Daten-Feeds enthalten. (Siehe [Daten-Feed-Dokumentation](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de).)</li></ul> |
| Core AA [Livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md) | <ul><li> Verarbeitungsregeln</li><li>VISTA-Regeln</li><ul> |  | <ul><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li><li>Besuchslogik</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Cross-Device Analytics</li></ul> |  |
| Core AA [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html?lang=de) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Besuchsdefinition (siehe Hinweis)</li><li>Cross-Device Analytics (siehe Hinweis)</li></ul> | <ul><li>Regeln für Marketing-Kanäle auf Trefferebene (siehe Hinweis)</li><li>Regeln für Marketing-Kanäle auf Besuchsebene (siehe Hinweis) Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li></ul> |  | <ul><li>CDA erfordert die Verwendung von Virtual Report Suites mit Berichtszeitverarbeitung.</li><li>Attribution IQ in Core Analytics verwendet Marketing-Kanäle, die vollständig zur Berichtszeit abgeleitet wurden (d. h. abgeleitete Mittelwerte).</li><li>Attribution IQ verwendet eine Besuchsdefinition für Verarbeitungszeiten, es sei denn, diese wird in einer VRS zur Berichtszeitverarbeitung verwendet.</li></ul> |
| Core AA Virtual Report Suites mit [Berichtszeitverarbeitung](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=de) (VRS RTP) | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de)</li></ul> | <ul><li>Besuchsdefinition</li><li>Attributionslogik</li><li>Segmentlogik</li><li>Berechnete Metriken</li><li>Andere VRS-RTP-Einstellungen</li></ul> | <ul><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Regeln für Marketing-Kanäle auf Besuchsebene</li></ul> | <ul><li>Siehe VRS-RTP-[Dokumentation](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=de).</li></ul> |
| Auf dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) basierender Datensatz im Data Lake von AEP | <ul><li>Verarbeitungsregeln</li><li>VISTA-Regeln</li><li>Regeln für Marketing-Kanäle auf Trefferebene</li><li>Feldbasierte Zuordnung (siehe Hinweis)</li></ul> |  | <ul><li>[Regeln für Marketing-Kanäle auf Besuchsebene](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=de)</li><li>Besuchslogik</li><li>Attributionslogik</li><li>Filterlogik</li></ul> | <ul><li>Muss Ihre eigene Filterlogik und berechnete Metriken anwenden</li><li>Bei der feldbasierten Zuordnung wird zusätzlich zu dem vom Analytics-Quell-Connector erstellten Datensatz ein separater zugeordneter Datensatz erstellt.</li></ul> |
| Reporting in [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=de) | <ul><li>Implementiert als Teil der Adobe Experience Platform-Datenerfassung</li></ul> | <ul><li>Sitzungsdefinition</li><li>[Datenansichtseinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de)<li>Attributionslogik</li><li>Berechnete Metriken</li><li>Filterlogik</li></ul> | <ul><li>Regeln für Marketing-Kanäle auf Besuchsebene</li></ul> | <ul><li>Muss zugeordnete Datensätze verwenden, um kanalübergreifende Analysen nutzen zu können.</li></ul> |

{style="table-layout:auto"}
