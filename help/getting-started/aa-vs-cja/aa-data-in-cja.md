---
title: Verwenden von Adobe Analytics Report Suite-Daten in Customer Journey Analytics
description: Konfigurieren von Adobe Analytics Report Suites für die Aufnahme in AEP und CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: tm+mt
source-wordcount: '767'
ht-degree: 13%

---

# Verwenden von Adobe Analytics Report Suite-Daten in Customer Journey Analytics

Adobe Analytics-Kunden können ihre Report Suites in Adobe Experience Platform und Customer Journey Analytics einfach mit der [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de). In der folgenden Diskussion wird erläutert, wie dies geschehen soll.

## Vorbereitung

Wenn Sie sich auf die Verwendung von Adobe Analytics Report Suites in AEP und CJA vorbereiten, sollten Sie verschiedene Maßnahmen ergreifen, um Ihre Daten für einen nahtlosen Wechsel zum Customer Journey Analytics vorzubereiten. Weitere Informationen finden Sie auf der folgenden Seite:

* [Umstieg von Adobe Analytics auf Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Report Suites für die Aufnahme in Adobe Experience Platform und CJA einrichten

Sobald Sie Ihre Daten vorbereitet haben, können Sie mit der Konfiguration von Report Suites für die Verwendung in AEP und CJA beginnen.

1. **Erstellen Sie einen Datenfluss für jede Report Suite, die Sie in AEP und CJA verwenden möchten.** Die [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) ist das Tool, mit dem Sie [Verbindung erstellen](/help/connections/create-connection.md) (auch als Datenfluss bezeichnet) zwischen Adobe Analytics und AEP. Verwenden Sie den Quell-Connector, um einen Datenfluss für jede Report Suite zu erstellen, die Sie in AEP verwenden möchten. Der Datenfluss erstellt eine Kopie Ihrer Report Suite-Daten, in die das Schema konvertiert wurde  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=de) für den Verbrauch durch AEP-Anwendungen einschließlich CJA. Jede Report Suite, die über den Quell-Connector mit einem Datenfluss konfiguriert wurde, wird als separater Datensatz im AEP Data Lake gespeichert. 13 Monate historischer Report Suite-Daten werden automatisch in jeden Datenfluss eingeschlossen und neue Daten werden laufend in AEP übertragen. Mit dem Analytics Source Connector müssen Sie sich nicht Gedanken darüber machen, das Schema vorzeitig zu erstellen. Für Adobe Analytics wird automatisch ein standardisiertes Schema erstellt. Die [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) kann verwendet werden, um dieses Schema zu erweitern, bevor die Daten im Data Lake gespeichert und CJA zur Verfügung gestellt werden. Beachten Sie, dass bestimmte Datentypen vom Quell-Connector herausgefiltert werden und nicht im Datensatz im AEP Data Lake vorhanden sein werden. Andere Zeilen können zwischen Data Lake und CJA herausgefiltert werden. Siehe [Adobe Analytics-Daten mit CJA-Daten vergleichen](/help/troubleshooting/compare.md) für weitere Details.
1. **Verwenden Sie die Datenvorbereitung , um Sie beim Kombinieren von Report Suites in Customer Journey Analytics zu unterstützen.** Die Datenvorbereitung kann für viele Arten der Datenumwandlung verwendet werden. Eine gängige Verwendung von Adobe Analytics-Daten besteht darin, Unterschiede bei den Eigenschaftsvariablen und/oder eVar-Mappings über mehrere Report Suites hinweg zu beheben, sodass Report Suites innerhalb von Customer Journey Analytics einfach kombiniert werden können. Siehe [Report Suites mit verschiedenen Schemas kombinieren](/help/use-cases/aa-data/combine-report-suites.md) für weitere Details.
1. **Aktivieren der kanalübergreifenden Analyse** nach Bedarf. Wenn mehrere Datensätze in CJA kombiniert werden, können die Funktionen zum Identitätszusammenfügen von Cross-Channel-Analyse dazu beitragen, verschiedene ID-Namespaces zu einer einzigen stitchedID zu lösen, sodass der Kunde geräteübergreifend und kanalübergreifend eine einzige Ansicht erhält. Siehe [Überblick über die kanalübergreifende Analyse](/help/connections/cca/overview.md) für weitere Details.
1. **Erstellen Sie eine oder mehrere CJA-Verbindungen.** Sobald die Datensätze für Ihre Report Suites im AEP Data Lake verfügbar sind, können Sie einen oder mehrere [CJA-Verbindungen](/help/connections/overview.md) , um diese Datensätze in CJA zu importieren. Innerhalb einer Verbindung können Report Suite-Daten mit anderen Datentypen kombiniert werden, sodass Sie eine echte kanalübergreifende Ansicht der Kundenerlebnisse erstellen können.
1. **Erstellen Sie eine oder mehrere CJA-Datenansichten.** A [Datenansicht](/help/data-views/data-views.md) ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie Daten aus einer CJA-Verbindung interpretiert werden. Datenansichten mit vielen leistungsstarken [Konfigurationsoptionen](/help/data-views/create-dataview.md) zum Anpassen der Daten, die Ihren Benutzern in [Analysis Workspace](/help/analysis-workspace/home.md).

## Vergleichen von Customer Journey Analytics und Adobe Analytics

Customer Journey Analytics und Adobe Analytics weisen eine Reihe von Ähnlichkeiten auf. Beispielsweise bieten sowohl CJA als auch Adobe Analytics die Leistungsfähigkeit von Analysis Workspace für eine gedankenfreie Analyse. Da CJA jedoch eine Anwendung innerhalb der Adobe Experience Platform ist und AEP für die Datenerfassung nutzt, unterscheiden sich CJA und Adobe Analytics in einer Reihe wichtiger Aspekte. Die folgenden Artikel sind hilfreich, um diese Unterschiede zu verstehen:

* [Vergleichen von Adobe Analytics-Daten mit Customer Journey Analytics-Daten](/help/troubleshooting/compare.md)
* [Customer Journey Analytics-Funktionen](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Vergleich der Terminologie für Analytics-Daten, die durch den Analytics Source Connector übergeben werden](/help/getting-started/aa-vs-cja/terminology.md)
* [Vergleich der Datenverarbeitung zwischen Adobe Analytics- und CJA-Reporting-Funktionen](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Virtual Report Suites, Datenansichten, AEP-Sandboxes und der Analytics-Quell-Connector](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Verarbeitungsregeln, VISTA und Klassifizierungen versus Datenvorbereitung](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID und der Analytics-Quell-Connector](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
