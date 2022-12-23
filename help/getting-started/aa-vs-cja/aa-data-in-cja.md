---
title: Verwenden von Daten aus Report Suites von Adobe Analytics in Customer Journey Analytics
description: Konfigurieren von Report Suites aus Adobe Analytics für die Aufnahme in AEP und CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: ht
source-wordcount: '767'
ht-degree: 100%

---

# Verwenden von Daten aus Report Suites von Adobe Analytics in Customer Journey Analytics

Adobe Analytics-Kunden können ihre Report Suites aus Adobe Experience Platform und Customer Journey Analytics einfach mit dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) nutzen. Im Folgenden wird erörtert, wie man dazu vorgehen kann.

## Vorbereitung

Bei der Vorbereitung auf die Verwendung von Report Suites aus Adobe Analytics in AEP und CJA sollten Sie verschiedene Maßnahmen ergreifen, um Ihre Daten für einen nahtlosen Wechsel zu Customer Journey Analytics vorzubereiten. Weitere Informationen finden Sie auf der folgenden Seite:

* [Umstieg von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Einrichten von Report Suites für die Aufnahme in Adobe Experience Platform und CJA

Sobald Sie Ihre Daten vorbereitet haben, können Sie mit der Konfiguration von Report Suites für die Verwendung in AEP und CJA beginnen.

1. **Erstellen Sie einen Datenfluss für jede Report Suite, die Sie in AEP und CJA verwenden möchten.** Der [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) ist das Tool, das Ihnen das [Erstellen einer Verbindung](/help/connections/create-connection.md) (auch als Datenfluss bezeichnet) zwischen Adobe Analytics und AEP ermöglicht. Zum Herstellen eines Datenflusses für jede Report Suite, die Sie in AEP verwenden möchten, sollten Sie den Quell-Connector verwenden. Durch den Datenfluss wird eine Kopie Ihrer Report Suite-Daten hergestellt, wobei das Schema in [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=de) konvertiert wurde, damit die Daten von AEP-Programmen einschließlich CJA verwendet werden können. Jede Report Suite, die mittels des Quell-Connectors mit einem Datenfluss konfiguriert wurde, wird als separater Datensatz im AEP Data Lake gespeichert. In jeden Datenfluss werden automatisch 13 Monate historischer Report Suite-Daten eingeschlossen. Neue Daten werden laufend zu AEP übertragen. Mit dem Analytics-Quell-Connector müssen Sie sich nicht im Voraus um die Erstellung des Schemas kümmern. Für Adobe Analytics wird automatisch ein standardisiertes Schema erstellt. Das AEP-Tool zur [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) kann jedoch verwendet werden, um dieses Schema zu erweitern, bevor die Daten im Data Lake gespeichert und CJA zur Verfügung gestellt werden. Beachten Sie, dass bestimmte Datentypen vom Quell-Connector herausgefiltert werden und nicht in dem Datensatz im AEP Data Lake vorhanden sein werden. Zwischen Data Lake und CJA können andere Zeilen herausgefiltert werden. Weitere Details finden Sie unter [Vergleichen von Adobe Analytics-Daten mit Customer Journey Analytics-Daten](/help/troubleshooting/compare.md).
1. **Verwenden Sie die Datenvorbereitung, um Report Suites in CJA zu kombinieren.** Die Datenvorbereitung kann für viele Arten der Datenumwandlung verwendet werden. Eine gängige Verwendung von Adobe Analytics-Daten ist die Beseitigung von Unterschieden bei den Eigenschafts- und/oder eVar-Zuordnungen über mehrere Report Suites hinweg, sodass Report Suites innerhalb von Customer Journey Analytics einfach kombiniert werden können. Weitere Details finden Sie unter [Kombinieren von Report Suites mit unterschiedlichen Schemata](/help/use-cases/aa-data/combine-report-suites.md).
1. **Aktivieren Sie Cross-Channel Analytics** bei Bedarf. Beim Kombinieren mehrerer Datensätze in CJA können die Funktionen zum Identitäts-Stitching von Cross-Channel Analytics dabei helfen, verschiedene ID-Namespaces zu einer einzigen stitchedID aufzulösen, was eine einzige Sicht auf den Kunden über alle Geräte und Kanäle hinweg erlaubt. Weitere Details finden Sie unter [Überblick über Cross-Channel Analytics](/help/connections/cca/overview.md).
1. **Erstellen Sie eine oder mehrere CJA-Verbindungen.** Sobald die Datensätze für Ihre Report Suites im AEP Data Lake verfügbar sind, können Sie eine oder mehrere [CJA-Verbindungen](/help/connections/overview.md) erstellen, um diese Datensätze in CJA zu übernehmen. Innerhalb einer Verbindung können Report Suite-Daten mit anderen Datentypen kombiniert werden, sodass Sie eine echte kanalübergreifende Darstellung der Kundenerlebnisse erstellen können.
1. **Erstellen Sie eine oder mehrere CJA-Datenansichten.** Eine [Datenansicht](/help/data-views/data-views.md) ist ein für Customer Journey Analytics spezifischer Container, mit dessen Hilfe Sie bestimmen können, wie Daten aus einer CJA-Verbindung zu interpretieren sind. Datenansichten verfügen über viele leistungsstarke [Konfigurationsoptionen](/help/data-views/create-dataview.md), mit denen Sie die Daten, die Sie den Benutzenden in [Analysis Workspace](/help/analysis-workspace/home.md) präsentieren, anpassen können.

## Vergleich von Customer Journey Analytics und Adobe Analytics

Customer Journey Analytics und Adobe Analytics weisen eine Reihe von Ähnlichkeiten auf. Beispielsweise bieten sowohl CJA als auch Adobe Analytics die Leistungsfähigkeit von Analysis Workspace für eine freie und blitzschnelle Analyse. Da CJA jedoch eine Anwendung innerhalb von Adobe Experience Platform ist und für die Datenerfassung AEP nutzt, unterscheiden sich CJA und Adobe Analytics in einer Reihe wichtiger Aspekte. Die folgenden Artikel sind hilfreich, um diese Unterschiede zu verstehen:

* [Vergleichen von Adobe Analytics-Daten mit Customer Journey Analytics-Daten](/help/troubleshooting/compare.md)
* [Unterstützung der Customer Journey Analytics-Funktion](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Vergleich der Terminologie für Analytics-Daten, die durch den Analytics Source Connector übergeben werden](/help/getting-started/aa-vs-cja/terminology.md)
* [Vergleich der Datenverarbeitung zwischen Reporting-Funktionen von Adobe Analytics und CJA](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Virtual Report Suites, Datenansichten, AEP-Sandboxes und der Analytics-Quell-Connector](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Verarbeitungsregeln, VISTA und Klassifizierungen versus Datenvorbereitung](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID und der Analytics-Quell-Connector](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
