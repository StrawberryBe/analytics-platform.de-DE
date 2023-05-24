---
title: Filterübersicht
description: Erfahren Sie, wofür Filter verwendet werden und wie Sie einen einfachen Filter erstellen.
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 58%

---


# Filterübersicht {#overview}

Mit Customer Journey Analytics können Sie leistungsstarke, zielgerichtete Zielgruppenfilter für Ihre Berichte erstellen, verwalten, freigeben und anwenden. Mit Filtern können Sie Untergruppen von Personen anhand von Merkmalen oder Website-Interaktionen identifizieren. Filter sind als kodifizierte Zielgruppeneinblicke konzipiert, die Sie für Ihre speziellen Anforderungen erstellen und dann überprüfen, bearbeiten und mit anderen Team-Mitgliedern austauschen können.

Filter können auf Attributen (Browsertyp, Gerät, Anzahl Besuche, Land, Geschlecht), Interaktionen (Kampagnen, Keyword-Suche, Suchmaschine), Ausstiegen und Einstiegen (Personen aus Facebook, einer definierten Landingpage, Referrer-Domäne), benutzerdefinierten Variablen (Formularfeld, definierte Kategorien, Kunden-ID) und anderen Kriterien basieren.

Sie können Filter im Filtergenerator erstellen und speichern oder Filter aus einer Fallout-Visualisierung (in Workspace) generieren. Darüber hinaus können Filter zusammen als gestapelte Filter verwendet werden.

Die Filterung umfasst den [Filtergenerator](/help/components/filters/filter-builder.md) zum Aufbau von Filtern und zur Ausführung eines Vorab-Tests sowie den [Filter-Manager](/help/components/filters/manage-filters.md) zur Erfassung, Kennzeichnung, Freigabe, Sicherheitseinstellung und Weitergabe von Filtern in Ihrer Organisation.

Die maximale Anzahl von Filtern, die Sie pro IMS-Organisation erstellen können, beträgt 50.000.

## Filtertypen {#types}

Informationen zu den verfügbaren Filtertypen und deren Erstellung finden Sie unter [Filter erstellen](/help/components/filters/create-filters.md).

## Sequenzielle Filter {#sequential}

Mit sequenziellen Filtern können Sie Personen anhand der Navigation und Seitenansicht auf Ihrer Site identifizieren und einen Filter für definierte Aktionen und Interaktionen bereitstellen. Mit sequenziellen Filtern können Sie erkennen, was eine Person mag und was sie meidet. Beim Erstellen sequenzieller Filter wird der Operator THEN verwendet, um die Personennavigation zu definieren und zu ordnen.

Siehe folgendes Beispiel:

![](assets/sequential_fil.png)

| Erster Besuch | Zweiter Besuch | Dritter Besuch |
| --- | --- | --- |
| Der Benutzer besuchte die Haupt-Landingpage (A), schloss die Kampagnenseite (B) aus und sah sich dann die Produktseite (C) an. | Die Person besuchte erneut die Haupt-Landingpage (A), schloss die Kampagnenseite (B) aus, besuchte erneut die Produktseite (C) und dann eine neue Seite (D). | Die Person hat denselben Pfad wie beim ersten und zweiten Besuch eingegeben und gefolgt und dann Seite F ausgeschlossen, um direkt zu einer Targeting-Produktseite (G) zu wechseln. |

## Filter-Container {#containers}

Filter basieren auf einer Hierarchie auf Ereignis-, Sitzungs- und Benutzerebene und verwenden ein verschachteltes Container-Modell. Mit verschachtelten Container können Sie Besucherattribute definieren sowie Aktionen, die auf Regeln zwischen den Containern und innerhalb der Container basieren.

>[!NOTE]
>Der Personen-Container wurde früher als Besucher-Container bezeichnet. Der Sitzungs-Container wurde als Besuchs-Container bezeichnet, und der Ereignis-Container war früher der Treffer-Container.

Ein Filter legt Bedingungen zum Filtern einer Person anhand ihrer Attribute oder Interaktionen mit Ihrer Site fest. Um Bedingungen in einem Filter festzulegen, legen Sie Regeln fest, mit denen Personen nach Personenmerkmalen und/oder Navigationsmerkmalen gefiltert werden. Um Personendaten weiter aufzuschlüsseln, können Sie für jede Person nach spezifischen Besuchen und/oder Seitenansichtstreffen filtern. Der Filtergenerator bietet eine einfache Architektur zum Erstellen dieser Untergruppen und das Anwenden von Regeln als verschachtelte hierarchische Personen-, Sitzungs- oder Ereignis-Container.

Die im Filtergenerator verwendete Behälterarchitektur definiert Person als den äußersten Behälter, der übergreifende Daten enthält, die für die Person über Besuche und Seitenansichten hinweg spezifisch sind. Mit einem verschachtelten Sitzungs-Container können Sie Regeln festlegen, mit denen die Daten der Person auf der Grundlage von Sitzungen aufgeschlüsselt werden, und einen verschachtelten Ereignis-Container, mit dem die Personeninformationen auf der Grundlage einzelner Seitenansichten aufgeschlüsselt werden. Jeder Container ermöglicht Berichte über den Verlauf einer Person, nach Sitzungen aufgeschlüsselte Interaktionen oder aufgeschlüsselte einzelne Ereignisse.

### Personen-Container {#person}

Der Personen-Container enthält alle Besuche und Seitenansichten für Personen innerhalb eines bestimmten Zeitraums. Ein Filter auf der Ebene der Person gibt die Seite zurück, die die Bedingung erfüllt, sowie alle anderen Seiten, die von der Person angezeigt wurden (und nur durch definierte Datumsbereiche eingeschränkt sind). Da es sich um den am weitesten definierten Container handelt, liefern Berichte, die auf der Ebene des Personen-Containers erstellt werden, Seitenansichten über alle Besuche hinweg und ermöglichen eine Analyse mehrerer Besuche. Der Personen-Container ändert sich daher auf der Grundlage der definierten Datumsbereiche am wahrscheinlichsten.
Personen-Container können Werte enthalten, die auf dem Gesamtverlauf einer Person basieren:

* Tage bis Erstkauf
* Ursprüngliche Einstiegsseite
* Ursprünglich Referrerdomänen

### Sitzungs-Container {#session}

Mit dem Sitzungs-Container können Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifiziert werden. Der Sitzungs-Container ist der am häufigsten verwendete Container, da er die Verhaltensweisen der gesamten Besuchssitzung erfasst, sobald die Regel erfüllt wird, und Ihnen die Möglichkeit gibt, zu definieren, welche Sitzungen ein- oder ausgeschlossen werden sollen, indem Sie einen Filter erstellen und anwenden. Er kann Ihnen bei der Beantwortung dieser Fragen helfen:

* Bei wie vielen Sitzungen wurden sowohl Web- als auch Callcenter-Datenquellen verwendet?
* Welche Seiten haben zu einer erfolgreichen Konversion in einem Verkauf beigetragen?

Sitzungs-Container enthalten Werte, die auf dem Auftreten pro Sitzung basieren:

* Sitzungstyp
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
