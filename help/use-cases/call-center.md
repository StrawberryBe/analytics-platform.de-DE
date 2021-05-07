---
title: Callcenter- und Web-Daten importieren
description: Erfahren Sie, wie Sie einen Datensatz erstellen, mit dem Sie Callcenter- und Website-Daten verknüpfen.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
translation-type: ht
source-git-commit: f9fae62af3d57b2b700c26a402c7232c0255806b
workflow-type: ht
source-wordcount: '679'
ht-degree: 100%

---

# Callcenter- und Web-Daten importieren

Customer Journey Analytics bietet die wertvolle Möglichkeit, Datensätze aus verschiedenen Quellen in einem einzigen Workspace-Projekt zu kombinieren. Verwenden Sie diesen Leitfaden, um zu verstehen, wie Ihr Unternehmen Website-Daten mit Callcenter-Daten kombinieren kann.

## Voraussetzungen

* Die wichtigste Komponente für die Kombination dieser beiden Datensätze ist eine gemeinsame Kennung für die einzelnen Datenquellen. Beispiele sind eine Kunden-ID, eine gehashte E-Mail-Adresse, ein Anmeldename oder eine Telefonnummer.
* Zugang zu Adobe Experience Platform und Customer Journey Analytics
* Wenn Ihr Datensatz Protokolle aus einem Interactive Voice Response-System enthält, empfiehlt Adobe, die Daten vor dem Import in die Platform so zu verarbeiten, dass diese nur Aufforderungs-Interaktionen enthalten.
* Wenn Ihr Datensatz Anrufprotokolle enthält, empfiehlt Adobe, die folgenden Spalten einzubeziehen:
   * Datum/Uhrzeit des Anrufbeginns
   * Grund für den Anruf
   * Callcenter-ID
   * Callcenter-Mitarbeiter-ID
   * Dauer des Anrufs
   * Ergebnisse des Anrufs
   * Kosten des Anrufs (falls verfügbar)
   * Weitere Anruf-Metadaten, die Ihre Organisation einbeziehen kann

## Web- und Callcenter-Daten in die Platform importieren

Importieren Sie die Daten in Adobe Experience Platform. Informationen zum [Erstellen eines Schemas](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/tutorials/create-schema-ui.html) und [Aufnehmen von Daten](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.html) finden Sie in der Adobe Experience Platform-Dokumentation.

Beim Importieren von Daten in die Platform können folgende Tipps hilfreich sein, um einen besseren Einblick in die resultierenden Berichte zu gewinnen:

* Stellen Sie sicher, dass die Kennungen, die zum Verknüpfen von Callcenter- und Web-Daten verwendet werden, ähnlich formatiert sind.
* Beziehen Sie die Datenquelle in jeden Datensatz ein. Fügen Sie beispielsweise eine Spalte `data_source` in jedes Schema ein und setzen Sie den Wert jedes Ereignisses jeweils auf `"Web"` bzw. `"Call center"`. <!--mapper-->

## Ordnen Sie die Personen-IDs zu

Customer Journey Analytics erfordert eine gemeinsame Kennung, sodass ein [kombinierter Datensatz](../connections/combined-dataset.md) generiert werden kann.

* Wenn Ihre Datensätze bereits für jedes Ereignis in beiden Datensätzen eine gemeinsame Kennung aufweisen, können Sie diesen Schritt überspringen und eine Verbindung erstellen.
* Wenn einer Ihrer Datensätze nur für einige Ereignisse eine gemeinsame Kennung enthält, können Sie Daten mithilfe der kanalübergreifenden Analyse zuordnen. Informationen zum Aktivieren der kanalübergreifenden Analyse für diese beiden Datensätze finden Sie unter [Übersicht zur kanalübergreifenden Analyse](/help/connections/cca/overview.md).

## Erstellen einer Verbindung in Customer Journey Analytics

[Erstellen Sie eine Verbindung](/help/connections/create-connection.md) in Customer Journey Analytics.

* Wenn die kanalübergreifende Analyse verwendet wird, steht Ihnen ein neuer zugeordneter Datensatz zur Verfügung. Verwenden Sie das neu erstellte Feld für die zugeordnete ID als die Personen-ID.
* Andernfalls können Sie auch die ursprünglichen Web- und Callcenter-Datensätze für die Verbindung verwenden.

## Datenansicht erstellen

Nachdem Sie eine Verbindung erstellt haben, können Sie eine [Datenansicht erstellen](/help/data-views/create-dataview.md), die in Analysis Workspace verwendet werden kann. <!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## Visualisierungen erstellen

Die folgenden Visualisierungen können verwendet werden, um Einblicke aus Ihrem zugeordneten Datensatz zu gewinnen.

### Datensatz-Überschneidung

In dieser Visualisierung können Sie die Qualität der Datenzuordnung in der kanalübergreifenden Analyse erkennen.

1. Erstellen Sie zwei Filter. Die in diesen beiden Filtern verwendete Variable ist dieselbe wie die oben erwähnte, die die Datenquelle jedes Ereignisses widerspiegelt. Weitere Informationen finden Sie unter [Filter erstellen](/help/components/filters/create-filters.md).
   * Personen-Container, bei dem die Datensatz-ID mit Ihren Web-Daten übereinstimmt
   * Personen-Container, bei dem die Datensatz-ID mit Ihren Callcenter-Daten übereinstimmt
2. Ziehen Sie in Analysis Workspace eine [Venn](/help/analysis-workspace/visualizations/venn.md)-Visualisierung auf die Workspace-Arbeitsfläche.
3. Ziehen Sie die beiden neu erstellten Filter in den Bereich **[!UICONTROL Filter hinzufügen]** und die Metrik „Personen“ in den Bereich **[!UICONTROL Metrik hinzufügen]**.

In der entsprechenden Venn-Visualisierung wird die Anzahl der Personen in Ihrem Datensatz angezeigt, die sowohl Web- als auch Callcenter-Daten enthalten. Je größer die Überschneidung, desto mehr Personen wurden erfolgreich zugeordnet. Die Bereiche, die sich nicht überschneiden, stellen Personen dar, die sich ausschließlich in einem der beiden Datensätze befinden.

### Callcenter-Ereignisse zu Web-Seiten zuordnen

Diese Freiformtabelle zeigt die wichtigsten Seiten, die zum Aufruf von Callcenter-Ereignissen beitragen. Stellen Sie zunächst sicher, dass die gewünschten Dimensionen und Metriken das richtige Attributionsmodell haben:

1. Ziehen Sie die Dimension, die die Namen Ihrer Web-Seiten beinhaltet, in eine Freiformtabellen-Visualisierung.
1. Ersetzen Sie die Metrik durch die gewünschte Callcenter-Metrik, zu der Sie die Konversion messen möchten.
1. Klicken Sie auf das Zahnradsymbol neben der Metrikkopfzeile. Klicken Sie auf **[!UICONTROL Nicht-standardmäßiges Attributionsmodell verwenden]**.
1. Legen Sie das gewünschte [Attributionsmodell](/help/data-views/create-dataview.md) fest.

Der resultierende Bericht zeigt die wichtigste Metrik aus den Callcenter-Daten. <!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: 

Orrr we could also use dataset ID

### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
