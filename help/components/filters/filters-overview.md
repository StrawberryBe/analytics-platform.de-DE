---
title: Filterübersicht
description: Erfahren Sie, wofür Filter verwendet werden und wie Sie einen einfachen Filter erstellen.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
source-git-commit: 67489fc6e9c0733589bccdd136837db8caca14a2
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 98%

---


# Filterübersicht {#overview}

Mit Customer Journey Analytics können Sie leistungsstarke, zielgerichtete Zielgruppenfilter für Ihre Berichte erstellen, verwalten, freigeben und anwenden. Mit Filtern können Besucheruntergruppen anhand von Merkmalen oder Website-Interaktionen identifiziert werden. Filter sind als kodifizierte Zielgruppeneinblicke konzipiert, die Sie für Ihre speziellen Anforderungen erstellen und dann überprüfen, bearbeiten und mit anderen Team-Mitgliedern austauschen können.

Filter können auf Attributen (Browser-Typ, Gerät, Anzahl der Besuche, Land, Geschlecht), Interaktionen (Kampagnen, Keyword-Suche, Suchmaschine), Einstiegen und Ausstiegen (Besucher von Facebook, einer definierten Landingpage, Referrer-Domäne), benutzerdefinierten Variablen (Formularfeld, definierte Kategorien, Kunden-ID) und anderen Kriterien basieren.

Sie können Filter im Filtergenerator erstellen und speichern oder Filter aus einer Fallout-Visualisierung (in Workspace) generieren. Darüber hinaus können Filter zusammen als gestapelte Filter verwendet werden.

Die Filterung umfasst den [Filtergenerator](/help/components/filters/create-filters.md) zum Aufbau von Filtern und zur Ausführung eines Vorab-Tests sowie den [Filter-Manager](/help/components/filters/manage-filters.md) zur Erfassung, Kennzeichnung, Freigabe, Sicherheitseinstellung und Weitergabe von Filtern in Ihrer Organisation.

Die maximale Anzahl von Filtern, die Sie pro IMS-Organisation erstellen können, beträgt 50.000.

## Filtertypen {#types}

Sie können verschiedene Filtertypen in Workspace und im Filtergenerator erstellen, je nachdem, wie komplex sie sein müssen, ob sie nur für dieses Projekt gelten sollen usw. Im Folgenden finden Sie eine Zusammenfassung der Filtertypen:

| Filtertyp | Wo erstellt? | Wird wo angewendet? | Verwendungsbereiche |
| --- | --- | --- | --- |
| Komponentenlistenfilter | Klicken Sie auf „+“, wodurch Sie zum [Filtergenerator](/help/components/filters/create-filters.md) gelangen. | Alle Workspace-Projekte | Für komplexere Filter, sequenzielle Filter |
| Schnellfilter | [Schnellfilter-Generator](/help/components/filters/quick-filters.md) | Nur im Projekt, Speichern und Hinzufügen zur Segmentliste möglich. | Flexibilität für Hinzufügen/Bearbeiten einer oder mehrerer Regeln |
| Ad-hoc-Projektfilter | [Ziehen und Ablegen in den Segmentablagebereich eines Projekts](/help/components/filters/ad-hoc-filters.md) | Nur im Projekt, Speichern und Hinzufügen zur Segmentliste möglich. | Für Einzelregelfilter |
| Filter in Fallout-Analyse | [Fallout-Visualisierung](/help/analysis-workspace/visualizations/fallout/compare-segments-fallout.md) in Analysis Workspace | Für individuelle Fallout-Visualisierungen | Erstellen von Filtern von einem Touchpoint aus, Hinzufügen von Filtern als Touchpoint und Vergleichen wichtiger Workflows über verschiedene Filter hinweg. |
| Auf berechneten Metriken basierende Filter | [Generator für berechnete Metriken](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/metrics-with-segments.html?lang=de) | Für einzelne berechnete Metriken | Anwenden von Filtern innerhalb Ihrer Metrikdefinition |

## Sequenzielle Filter {#sequential}

Mit sequenziellen Filtern können Sie Besucher anhand der Navigation und den Seitenansichten innerhalb Ihrer Site identifizieren, indem Sie einen Filter mit definierten Aktionen und Interaktionen bereitstellen. Mit sequenziellen Filtern können Sie erkennen, was ein Besucher mag und was er meidet. Beim Erstellen sequenzieller Filter wird der Operator THEN eingesetzt, um die Navigation des Besuchers zu definieren und zu ordnen.

Siehe folgendes Beispiel:

![](assets/sequential_fil.png)

| Erster Besuch | Zweiter Besuch | Dritter Besuch |
| --- | --- | --- |
| Der Besucher besuchte die Haupt-Landingpage (A), schloss die Kampagnenseite (B) aus und sah sich dann die Produktseite (C) an. | Der Besucher besuchte die Haupt-Landingpage (A) erneut, schloss die Kampagnenseite (B) aus, besuchte erneut die Produktseite (C) und dann eine neue Seite (D). | Der Besucher folgte demselben Weg wie beim ersten und zweiten Besuch, schloss dann die Seite (F) aus, um direkt zu einer Targeting-Produktseite (G) zu wechseln. |

## Filter-Container {#containers}

Filter basieren auf einer Hierarchie auf Ereignis-, Sitzungs- und Benutzerebene und verwenden ein verschachteltes Container-Modell. Mit verschachtelten Container können Sie Besucherattribute definieren sowie Aktionen, die auf Regeln zwischen den Containern und innerhalb der Container basieren.

>[!NOTE]
>Der Personen-Container wurde früher als Besucher-Container bezeichnet. Der Sitzungs-Container wurde als Besuchs-Container bezeichnet, und der Ereignis-Container war früher der Treffer-Container.

Ein Filter legt Bedingungen für das Filtern eines Besuchers auf der Grundlage seiner Attribute oder Interaktionen mit Ihrer Site fest. Um in einem Filter Bedingungen festzulegen, legen Sie Regeln für die Filterung von Besuchern auf der Grundlage von Besuchermerkmalen und/oder Navigationsverhalten fest. Um die Besucherdaten weiter herunterzubrechen, können Sie jeden Besucher auf der Grundlage bestimmter Besuche und/oder Seitenansichten filtern. Der Filtergenerator bietet eine einfache Architektur zum Erstellen dieser Untergruppen und das Anwenden von Regeln als verschachtelte hierarchische Personen-, Sitzungs- oder Ereignis-Container.

Die im Filtergenerator verwendete Container-Architektur definiert Person als den äußersten Container, der übergreifende Daten enthält, die für den Besucher über Besuche und Seitenansichten hinweg spezifisch sind. Mit einem verschachtelten Sitzungs-Container können Sie Regeln festlegen, mit denen die Besucherdaten auf der Grundlage von Sitzungen aufgeschlüsselt werden, und einen verschachtelten Ereignis-Container, mit dem die Besucherinformationen auf der Grundlage einzelner Seitenansichten aufgeschlüsselt werden. Jeder Container ermöglicht Berichte über den Verlauf eines Besuchers, nach Sitzung aufgeschlüsselte Interaktionen oder aufgeschlüsselte einzelne Ereignisse.

### Personen-Container {#person}

Der Personen-Container enthält sämtliche Besuche und Seitenansichten für Besucher innerhalb eines bestimmten Zeitraums. Ein Filter auf der Personenebene gibt die Seite zurück, die die Bedingung erfüllt, sowie alle anderen Seiten, die vom Besucher angesehen wurden (und dies nur durch definierte Datumsbereiche beschränkt). Da es sich um den am weitesten definierten Container handelt, liefern Berichte, die auf der Ebene des Personen-Containers erstellt werden, Seitenansichten über alle Besuche hinweg und ermöglichen eine Analyse mehrerer Besuche. Der Personen-Container ändert sich daher auf der Grundlage der definierten Datumsbereiche am wahrscheinlichsten.
Personen-Container können Werte enthalten, die auf dem Gesamtverlauf eines Besuchers basieren:

* Tage bis Erstkauf
* Ursprüngliche Einstiegsseite
* Ursprünglich Referrerdomänen

### Sitzungs-Container {#session}

Mit dem Sitzungs-Container können Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifiziert werden. Der Sitzungs-Container ist der am häufigsten verwendete Container, da er die Verhaltensweisen der gesamten Besuchssitzung erfasst, sobald die Regel erfüllt wird, und Ihnen die Möglichkeit gibt, zu definieren, welche Sitzungen ein- oder ausgeschlossen werden sollen, indem Sie einen Filter erstellen und anwenden. Er kann Ihnen bei der Beantwortung dieser Fragen helfen:

* Wie viele Besucher haben die Bereiche „Nachrichten“ und „Sport“ in derselben Sitzung angesehen?
* Welche Seiten haben zu einer erfolgreichen Konversion in einem Verkauf beigetragen?

Sitzungs-Container enthalten Werte, die auf dem Auftreten pro Sitzung basieren:

* Sitzungsnummer
* Einstiegsseite
* Rückkehrhäufigkeit
* Beitragsmetriken
* Linear zugeordnete Metriken

### Ereignis-Container {#event}

Der Ereignis-Container definiert, welche Seitenereignisse von einem Filter eingeschlossen oder ausgeschlossen werden sollen. Dies ist der engste verfügbare Container, mit dem Sie spezifische Klicks und Seitenansichten identifizieren können, für die eine Bedingung wahr ist, wobei Sie einen einzelnen Trackingcode oder ein isoliertes Verhalten in einem bestimmten Bereich Ihrer Site anzeigen können. Sie können auch einen bestimmten Wert erkennen, wenn eine Aktion stattfindet, z. B. den Marketing-Kanal, wenn ein Auftrag platziert wurde.

Zu den Ereignis-Containern zählen wertbasierte Einzelseitenunterteilungen:

* Produkte
* Listen-Props
* Listendimensionen
* Merchandising-Dimensionen (im Kontext von Ereignissen)

## Vordefinierte Filtervorlage {#template}

Die herkömmliche Analytics-Version enthält eine Vielzahl vordefinierter Vorlagenfilter (Filter) und berechneter Metriken. Viele von ihnen gelten nicht für Customer Journey Analytics oder müssen umbenannt oder neu erstellt werden. Andere hängen von einer Lösung für kontextsensitive Variablen in Customer Journey Analytics ab.

| Filtername | Beschreibung |
| --- | --- |
| Alle Daten | Dies ist ein erforderlicher Filter, der dynamisch zum Reporting hinzugefügt wird, wenn eine Metrik zur Zeile einer Freiform-Tabelle hinzugefügt wird. |
