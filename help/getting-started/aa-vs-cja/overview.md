---
title: Vergleich mit Adobe Analytics
description: Übersicht über den Vergleich von Customer Journey Analytics mit Adobe Analytics.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: cb81422ed08420fe9a16c32ddd748c9569197b17
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 8%

---

# Vergleich mit Adobe Analytics

In diesem Abschnitt der Dokumentation wird erläutert, wie Sie die Unterschiede zwischen Customer Journey Analytics und Adobe Analytics vergleichen und verstehen können.

Der grundlegende Unterschied zwischen den beiden Lösungen besteht in der Datenbreite, die Sie bei der Erstellung Ihrer Berichte und Analysen berücksichtigen können.

Customer Journey Analytics: *any* -Datenquelle kann Teil der Daten sein, die Sie für die Berichterstellung und Analyse verwenden. Adobe Analytics richtet sich in erster Linie an Online-Daten, die über Websites und mobile Apps erfasst werden. Adobe Analytics bietet Funktionen zum Importieren von Daten aus anderen Quellen. Der Hauptzweck besteht darin, den zuvor erwähnten Online-Daten mehr Kontext zu geben.

## Datenerfassung

Customer Journey Analytics beruht auf Daten, die in Experience Platform-Datensätzen gespeichert sind. Sie haben mehrere Möglichkeiten, Daten in diesen Datensätzen zu erfassen und in Experience Platform zu erfassen. Diese Optionen werden im Abschnitt [Datenerfassung - Übersicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/data-ingestion.html?lang=en).

Adobe Analytics erfasst letztendlich Daten innerhalb der Lösung selbst. Auch hier haben Sie mehrere Möglichkeiten, diese Daten zu erfassen, die im Abschnitt [Adobe Analytics-Implementierungshandbuch](https://experienceleague.adobe.com/docs/analytics/implementation/home.html?lang=de).

Sie können Ihre Adobe Analytics Report Suite-Daten in Customer Journey Analytics mit dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de). Dieser Connector verwendet die in Adobe Analytics erfassten Daten zur Aufnahme in Experience Platform und zur anschließenden Verwendung in Customer Journey Analytics. Siehe [Verwenden von Adobe Analytics Report Suite-Daten in Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=de) für weitere Informationen.


## Datenverarbeitung

Bevor Sie Berichte zu Daten erstellen können, müssen Sie diese Daten häufig verarbeiten, um sicherzustellen, dass die Daten zu diesem Zweck ordnungsgemäß verwendet werden können. Diese Datenverarbeitung kann zur Erfassungszeit und zur Berichtszeit erfolgen.

Im Allgemeinen kann Customer Journey Analytics mit den erfassten und gespeicherten Daten im Experience Platform-Datensatz zur Berichtszeit verwendet werden. Customer Journey Analytics bietet eine leistungsstarke Berichtszeitverarbeitungsfunktion, um sicherzustellen, dass die Daten für Berichte und Analysen bereit sind. Wenn Sie Daten vor der Erfassung in Experience Platform zuordnen, transformieren und validieren müssen, können Sie die [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) Funktionalität von Experience Platform.

In Adobe Analytics erfolgt der Großteil der Datenverarbeitung unmittelbar nach der Datenerfassung.

Siehe [Datenverarbeitung in Adobe Analytics und Customer Journey Analytics vergleichen](data-processing-comparisons.md) und [Verarbeitungsregeln, VISTA und Klassifizierungen im Vergleich zur Datenvorbereitung](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=de) für weitere Informationen.


## Terminologie

Customer Journey Analytics bietet Flexibilität bei der Definition von Dimensionen und Metriken, was durch die Flexibilität ermöglicht wird, die die zugrunde liegenden Experience-Datenmodell (XDM)-basierten Schemas bieten. Wenn Adobe Analytics beispielsweise Besucher, Besuche und Treffer verwendet, verwendet Customer Journey Analytics Personen, Sitzungen und Ereignisse als gleichwertige Konzepte, aber Sie können die Benennung nach Bedarf ändern.

Siehe [Vergleich der Terminologie für Analytics-Daten, die über den Analytics-Quell-Connector übergeben werden](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/terminology.html?lang=en) für weitere Informationen zu den Unterschieden in der Terminologie.


## Virtual Reporting-Umgebungen und Sandboxes

Adobe Analytics basiert auf dem Konzept von Virtual Report Suites, mit denen Sie Ihre erfassten Daten segmentieren und den Zugriff auf diese segmentierten Daten steuern können.

Customer Journey Analytics hat ein ähnliches Konzept, Datenansichten genannt. Datenansichten sind Container, mit denen Sie bestimmen können, wie Daten aus einer Verbindung interpretiert werden. Es bietet ultimative Flexibilität bei der Spezifizierung und Konfiguration von Dimensionen und Metriken zur Vorbereitung auf Ihre Berichterstellung und Analyse.

Experience Platform bietet Sandboxes, die als Container mit Daten und Anwendungen für eine bestimmte Umgebung betrachtet werden können. Die Funktionalität einer Sandbox ist nicht mit einer Virtual Report Suite in Adobe Analytics oder einer Customer Journey Analytics-Datenansicht verbunden. Adobe Analytics selbst hat überhaupt keine Abhängigkeit oder Beziehung zu Experience Platform-Sandboxes. Customer Journey Analytics unterstützt zwar Experience Platform-Sandboxes, es gibt jedoch einige wichtige Aspekte.

Siehe [Virtual Report Suites, Datenansichten, Adobe Experience Platform-Sandboxes und der Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=de) für weitere Informationen.


## Identitäten

Customer Journey Analytics unterstützt die Identitäten, die Sie als Teil der Schemas definieren, denen die Datensätze, die Ihre Daten enthalten, entsprechen. Identitäten sind also ein grundlegendes Konzept der Experience Platform, das Customer Journey Analytics beim Einrichten eines [connection](../../connections/overview.md) (durch Definition der Personen-ID für jeden Datensatz) und beim Anwenden der [Stitching](../../stitching/overview.md) für die kanalübergreifende Analyse. Eine wichtige Identität, die von den Experience Platform-SDKs und der API verwendet wird, ist die Experience Cloud-ID (ECID).

Adobe Analytics verwendet einen definitiveren Satz von Identitätsfeldern, z. B. die Adobe Analytics ID (AAID). Bei Verwendung des Analytics-Quell-Connectors werden diese Adobe Analytics-Identifizierungsfelder besonders behandelt. Siehe [AAID, ECID, AACUSTOMID und der Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=en) für weitere Informationen.


## Funktionen

Eine Übersicht über die Adobe Analytics-Funktionen und die Unterstützung dieser Funktionen durch Customer Journey Analytics finden Sie unter [Customer Journey Analytics-Funktionsunterstützung](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/cja-aa.html?lang=en).





