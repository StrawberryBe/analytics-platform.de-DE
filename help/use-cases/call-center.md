---
title: Call Center- und Webdaten importieren
description: Erfahren Sie, wie Sie ein Dataset erstellen, mit dem Sie Call Center- und Website-Daten verknüpfen.
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 3%

---


# Call Center- und Webdaten importieren

Customer Journey Analytics bietet die wertvolle und robuste Möglichkeit, Datensätze aus verschiedenen Quellen in einem einzigen Workspace-Projekt zu kombinieren. Verwenden Sie dieses Handbuch, um zu verstehen, wie Ihr Unternehmen Website-Daten mit Call-Center-Daten kombinieren kann.

## Voraussetzungen

* Die wichtigste Komponente für die Kombination dieser beiden Datensätze ist ein gemeinsamer Bezeichner zwischen den einzelnen Datenquellen. Beispiele sind eine Kunden-ID, eine Hash-E-Mail, ein Anmeldename oder eine Telefonnummer.
* Zugang zu Adobe Experience Platform und Customer Journey Analytics
* Wenn Ihr Datensatz Protokolle aus einem interaktiven Sprachreaktionssystem enthält, empfiehlt Adobe die Verarbeitung der Daten, sodass diese nur auffordern, Interaktionen aufzunehmen, bevor sie in die Plattform importiert werden.
* Wenn Ihr Datensatz Anrufprotokolle enthält, empfiehlt Adobe, die folgenden Spalten einzuschließen:
   * Datum/Uhrzeit des Starts des Anrufs
   * Aufruf
   * Call-Center-ID
   * Support-Mitarbeiter-ID
   * Anlaufzeit
   * Ergebnis des Abrufs
   * Kosten des Anrufs (falls verfügbar)
   * Alle zusätzlichen Call-Metadaten, die Ihre Organisation einbeziehen möchte

## Web- und Call-Center-Daten in die Plattform importieren

Importieren Sie Ihre Daten nach Adobe Experience Platform. Siehe [Erstellen eines Schemas](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/tutorials/create-schema-ui.html) und [Daten](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.html) in der Adobe Experience Platform-Dokumentation.

Beim Importieren von Daten in die Plattform können die folgenden Tipps dazu beitragen, den Einblick in die resultierenden Berichte zu erhöhen:

* Stellen Sie sicher, dass der Bezeichner, der zum Verknüpfen von Call Center- und Webdaten verwendet wird, ähnlich formatiert ist.
* Schließen Sie die Datenquelle in jeden Datensatz ein. Fügen Sie beispielsweise die Spalte `data_source` in jedes Schema ein und setzen Sie den Wert jedes Ereignisses auf `"Web"` bzw. `"Call center"`. <!--mapper-->

## Stellen Sie die Personen-IDs zusammen.

CJA erfordert einen gemeinsamen Bezeichner, um einen [kombinierten Datensatz](../connections/combined-dataset.md) zu generieren.

* Wenn Ihre Datensätze bereits auf jedem Ereignis in beiden Datensätzen eine gemeinsame ID aufweisen, können Sie diesen Schritt überspringen und eine Verbindung erstellen.
* Wenn einer Ihrer Datensätze nur auf einigen Ereignissen einen gemeinsamen Bezeichner enthält, können Sie Daten mithilfe von Cross-Kanal Analytics zusammenfügen. Informationen zum Aktivieren von CCA für diese beiden Datensätze finden Sie unter [Übersicht über die Kanal-übergreifende Analyse](/help/connections/cca/overview.md).

## Erstellen einer Verbindung in CJA

[Erstellen Sie eine ](/help/connections/create-connection.md) Verbindung in CJA.

* Wenn CCA verwendet wird, steht Ihnen ein neuer gehefteter Datensatz zur Verfügung. Verwenden Sie das neu erstellte ID-Feld als Personen-ID.
* Andernfalls können Sie sowohl Original-Web- als auch Call-Center-Datensätze zur Verwendung in der Verbindung auswählen.

## Datenansicht erstellen

Nach dem Erstellen einer Ansicht können Sie [eine Datenverbindung ](/help/data-views/create-dataview.md) für die Verwendung in Analysis Workspace erstellen. <!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## Visualisierungen erstellen

Die folgenden Visualisierungen können verwendet werden, um Einblicke aus Ihrem zusammengestellten Datensatz zu gewinnen.

### Datenüberschneidung

Diese Visualisierung hilft Ihnen zu verstehen, wie gut CCA Daten zusammenfügt.

1. Erstellen Sie zwei Filter. Die in diesen beiden Filtern verwendete Variable ist dieselbe, die oben erwähnt wurde und die Datenquelle jedes Ereignisses widerspiegelt. Weitere Informationen finden Sie unter [Filter erstellen](/help/components/filters/create-filters.md).
   * Container, bei dem die Dataset-ID Ihren Webdaten entspricht
   * Container, bei dem die Dataset-ID mit der Call-Center-Daten übereinstimmt
2. Ziehen Sie in Analysis Workspace eine Visualisierung für [Venn](/help/analysis-workspace/visualizations/venn.md) auf die Arbeitsfläche.
3. Ziehen Sie die beiden neu erstellten Filter in den Bereich **[!UICONTROL Hinzufügen Filter]** und die Metrik &quot;Personen&quot;in den Bereich **[!UICONTROL Hinzufügen Metrik]**.

Die resultierende Venn-Visualisierung zeigt die Anzahl der Personen in Ihrem Datensatz, die sowohl Web- als auch Call-Center-Daten enthalten. Je größer die Überschneidung, desto mehr Personen wurden erfolgreich zusammengestellt. Die Bereiche, die sich nicht überschneiden, stellen Personen dar, die sich ausschließlich in einem Datensatz oder in einem anderen befinden.

### Ereignis von Call-Center zu Webseiten zuordnen

In dieser Freiform-Tabelle werden die obersten Seiten angezeigt, die zum Aufruf von Center-Ereignissen beitragen. Stellen Sie zunächst sicher, dass die gewünschten Dimensionen und Metriken das richtige Zuordnungsmodell haben:

1. Ziehen Sie die Dimension, in der die Namen Ihrer Webseiten gespeichert sind, in eine Freiform-Tabelle-Visualisierung.
1. Ersetzen Sie die Metrik durch die gewünschte Call-Center-Metrik, die Sie die Konversion messen möchten.
1. Klicken Sie auf das Zahnradsymbol neben der Metriküberschrift. Klicken Sie auf **[!UICONTROL Nicht standardmäßiges Zuordnungsmodell]** verwenden.
1. Legen Sie das gewünschte [Zuordnungsmodell](/help/data-views/configure-dataviews.md#Attribution-model) fest.

Der resultierende Bericht zeigt die oberste Metrik aus den Call-Center-Daten. <!-- Complement with donut visualization -->

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

use sequential segmentation, but you lose the ability to use attribution IQ

## What to do when you've found insight -->

