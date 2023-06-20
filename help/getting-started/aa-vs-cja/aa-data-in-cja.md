---
title: Verwenden von Daten aus Report Suites von Adobe Analytics in Customer Journey Analytics
description: Konfigurieren von Adobe Analytics Report Suites für die Aufnahme in Adobe Experience Platform und Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: ca329bd551990c1fefeda2fe272ed17551cfaac8
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 30%

---

# Verwenden von Daten aus Report Suites von Adobe Analytics in Customer Journey Analytics

Adobe Analytics-Kunden können ihre Report Suites aus Adobe Experience Platform und Customer Journey Analytics einfach mit dem [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) nutzen. Im Folgenden wird erörtert, wie man dazu vorgehen kann.

## Vorbereitung

Wenn Sie sich auf die Verwendung von Adobe Analytics Report Suites in Adobe Experience Platform und Customer Journey Analytics vorbereiten, sollten Sie verschiedene Maßnahmen ergreifen, um Ihre Daten für einen nahtlosen Wechsel zum Customer Journey Analytics vorzubereiten. Weitere Informationen finden Sie auf der folgenden Seite:

* [Umstieg von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Report Suites für die Aufnahme in Adobe Experience Platform und Customer Journey Analytics einrichten

Sobald Sie Ihre Daten vorbereitet haben, können Sie mit der Konfiguration von Report Suites für die Verwendung in Adobe Experience Platform und Customer Journey Analytics beginnen.

1. **Erstellen Sie für jede Report Suite, die Sie in Adobe Experience Platform und Customer Journey Analytics verwenden möchten, einen Datenfluss.** Die [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) ist das Tool, mit dem Sie [Verbindung erstellen](/help/connections/create-connection.md) (auch als Datenfluss bezeichnet) zwischen Adobe Analytics und Adobe Experience Platform. Verwenden Sie den Quell-Connector, um einen Datenfluss für jede Report Suite zu erstellen, die Sie in Adobe Experience Platform verwenden möchten. Der Datenfluss erstellt eine Kopie Ihrer Report Suite-Daten, in die das Schema konvertiert wurde  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=de) für den Verbrauch durch Adobe Experience Platform-Anwendungen einschließlich Customer Journey Analytics.<p>Jede Report Suite, die über den Quell-Connector mit einem Datenfluss konfiguriert wurde, wird als separater Datensatz im Adobe Experience Platform Data Lake gespeichert. 13 Monate historischer Report Suite-Daten werden automatisch in jeden Datenfluss eingeschlossen und neue Daten fließen fortlaufend in Adobe Experience Platform. (Beachten Sie, dass die Aufstockung in Nicht-Produktions-Sandboxes ab dem 26. April 2023 auf 3 Monate beschränkt ist.) Mit dem Analytics-Quell-Connector müssen Sie sich nicht im Voraus um die Erstellung des Schemas kümmern. Für Adobe Analytics wird automatisch ein standardisiertes Schema erstellt. Adobe Experience Platform [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) kann verwendet werden, um dieses Schema zu erweitern, bevor die Daten im Data Lake gespeichert und dem Customer Journey Analytics zur Verfügung gestellt werden. Beachten Sie, dass bestimmte Datentypen vom Quell-Connector herausgefiltert werden und nicht im Datensatz im Adobe Experience Platform Data Lake vorhanden sein werden. Andere Zeilen können zwischen Data Lake und Customer Journey Analytics herausgefiltert werden. Siehe [Adobe Analytics-Daten mit Customer Journey Analytics-Daten vergleichen](/help/troubleshooting/compare.md) für weitere Details.
1. **Verwenden Sie die Datenvorbereitung , um die Kombination von Report Suites in Customer Journey Analytics zu erleichtern.** Die Datenvorbereitung kann für viele Arten der Datenumwandlung verwendet werden. Eine gängige Verwendung von Adobe Analytics-Daten besteht darin, Unterschiede bei der Props- und/oder eVar-Zuordnung über mehrere Report Suites hinweg zu beheben, sodass Report Suites innerhalb des Customer Journey Analytics einfach kombiniert werden können. Weitere Details finden Sie unter [Kombinieren von Report Suites mit unterschiedlichen Schemata](/help/use-cases/aa-data/combine-report-suites.md).
1. **Aktivieren Sie Cross-Channel Analytics** bei Bedarf. Wenn mehrere Datensätze in Customer Journey Analytics kombiniert werden, können die Funktionen zum Identitätszusammenfügen von Cross-Channel-Analysen dazu beitragen, verschiedene ID-Namespaces zu einer einzigen Stitch-ID zu vereinen, sodass der Kunde geräteübergreifend und kanalübergreifend betrachtet werden kann. Weitere Details finden Sie unter [Überblick über Cross-Channel Analytics](/help/cca/overview.md).
1. **Erstellen Sie eine oder mehrere Customer Journey Analytics-Verbindungen.** Sobald die Datensätze für Ihre Report Suites im Adobe Experience Platform Data Lake verfügbar sind, können Sie einen oder mehrere [Customer Journey Analytics-Verbindungen](/help/connections/overview.md) , um diese Datensätze in Customer Journey Analytics zu bringen. Innerhalb einer Verbindung können Report Suite-Daten mit anderen Datentypen kombiniert werden, sodass Sie eine echte kanalübergreifende Darstellung der Kundenerlebnisse erstellen können.
1. **Erstellen Sie eine oder mehrere Customer Journey Analytics-Datenansichten.** A [Datenansicht](/help/data-views/data-views.md) ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie Daten aus einer Customer Journey Analytics-Verbindung interpretiert werden. Datenansichten verfügen über viele leistungsstarke [Konfigurationsoptionen](/help/data-views/create-dataview.md), mit denen Sie die Daten, die Sie den Benutzenden in [Analysis Workspace](/help/analysis-workspace/home.md) präsentieren, anpassen können.

## Vergleich von Customer Journey Analytics und Adobe Analytics

Customer Journey Analytics und Adobe Analytics weisen eine Reihe von Ähnlichkeiten auf. So bieten beispielsweise sowohl Customer Journey Analytics als auch Adobe Analytics die Leistungsfähigkeit von Analysis Workspace für eine gedankenfreie Analyse. Da Customer Journey Analytics jedoch eine Anwendung innerhalb der Adobe Experience Platform ist und Adobe Experience Platform für die Datenerfassung nutzt, unterscheiden sich Customer Journey Analytics und Adobe Analytics auf verschiedene wichtige Arten. Die folgenden Artikel sind hilfreich, um diese Unterschiede zu verstehen:

* [Adobe Analytics-Daten mit Customer Journey Analytics-Daten vergleichen](/help/troubleshooting/compare.md)
* [Unterstützung der Customer Journey Analytics-Funktion](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Vergleich der Terminologie für Analytics-Daten, die durch den Analytics Source Connector übergeben werden](/help/getting-started/aa-vs-cja/terminology.md)
* [Vergleich der Datenverarbeitung über die Berichterstellungsfunktionen von Adobe Analytics und Customer Journey Analytics hinweg](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Virtual Report Suites, Datenansichten, Adobe Experience Platform-Sandboxes und der Analytics Source Connector](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Verarbeitungsregeln, VISTA und Klassifizierungen versus Datenvorbereitung](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID und der Analytics-Quell-Connector](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
