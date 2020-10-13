---
title: Filterübersicht
description: Erfahren Sie, wofür Filter verwendet werden und wie Sie einen einfachen Filter erstellen.
translation-type: ht
source-git-commit: 74b99933fb1b599c829e11117c41235754c189b9
workflow-type: ht
source-wordcount: '885'
ht-degree: 100%

---


# Filterübersicht

Mit Customer Journey Analytics können Sie leistungsstarke, zielgerichtete Zielgruppenfilter für Ihre Berichte erstellen, verwalten, freigeben und anwenden. Mit Filtern können Besucheruntergruppen anhand von Merkmalen oder Website-Interaktionen identifiziert werden. Filter sind als kodifizierte Zielgruppeneinblicke konzipiert, die Sie für Ihre speziellen Anforderungen erstellen und dann überprüfen, bearbeiten und mit anderen Team-Mitgliedern austauschen können.

Filter können auf Attributen (Browser-Typ, Gerät, Anzahl der Besuche, Land, Geschlecht), Interaktionen (Kampagnen, Keyword-Suche, Suchmaschine), Einstiegen und Ausstiegen (Besucher von Facebook, einer definierten Landingpage, Referrer-Domäne), benutzerdefinierten Variablen (Formularfeld, definierte Kategorien, Kunden-ID) und anderen Kriterien basieren.

Sie können Filter im Filtergenerator erstellen und speichern oder Filter aus einer Fallout-Visualisierung (in Workspace) generieren. Darüber hinaus können Filter zusammen als gestapelte Filter verwendet werden.

>[!IMPORTANT]
>Filter werden in Adobe Analytics als „Segmente“ bezeichnet. Wir haben Segmente in Filter umbenannt, da Adobe Experience Platform [eine andere Definition von „Segment“ verwendet. ](https://docs.adobe.com/content/help/de-DE/experience-platform/segmentation/home.html)

Die Filterung umfasst den [Filtergenerator](/help/components/filters/create-filters.md) zum Aufbau von Filtern und zur Ausführung eines Vorab-Tests sowie den [Filter-Manager](/help/components/filters/manage-filters.md) zur Erfassung, Kennzeichnung, Freigabe, Sicherheitseinstellung und Weitergabe von Filtern in Ihrer Organisation.

## Sequenzielle Filter

Mit sequenziellen Filtern können Sie Besucher anhand der Navigation und den Seitenansichten innerhalb Ihrer Site identifizieren, indem Sie einen Filter mit definierten Aktionen und Interaktionen bereitstellen. Mit sequenziellen Segmenten können Sie erkennen, was ein Besucher mag und was er meidet. Beim Erstellen sequenzieller Filter wird der Operator DANN (THEN) eingesetzt, um die Navigation des Besuchers zu definieren und zu ordnen.

Siehe folgendes Beispiel:

![](assets/sequential_fil.png)

| Erster Besuch | Zweiter Besuch | Dritter Besuch |
| --- | --- | --- |
| Der Besucher besuchte die Haupt-Landingpage (A), schloss die Kampagnenseite (B) aus und sah sich dann die Produktseite (C) an. | Der Besucher besuchte die Haupt-Landingpage (A) erneut, schloss die Kampagnenseite (B) aus, besuchte erneut die Produktseite (C) und dann eine neue Seite (D). | Der Besucher folgte demselben Weg wie beim ersten und zweiten Besuch, schloss dann die Seite (F) aus, um direkt zu einer Targeting-Produktseite (G) zu wechseln. |

## Filter-Container

Filter basieren auf einer Hierarchie auf Ereignis-, Sitzungs- und Benutzerebene und verwenden ein verschachteltes Container-Modell. Mit verschachtelten Container können Sie Besucherattribute definieren sowie Aktionen, die auf Regeln zwischen den Containern und innerhalb der Container basieren.

>[!NOTE]
>Der Personen-Container wurde früher als Besucher-Container bezeichnet. Der Sitzungs-Container wurde als Besuchs-Container bezeichnet, und der Ereignis-Container war früher der Treffer-Container.

Ein Filter legt Bedingungen für das Filtern eines Besuchers auf der Grundlage seiner Attribute oder Interaktionen mit Ihrer Site fest. Um in einem Filter Bedingungen festzulegen, legen Sie Regeln für die Filterung von Besuchern auf der Grundlage von Besuchermerkmalen und/oder Navigationsverhalten fest. Um die Besucherdaten weiter herunterzubrechen, können Sie jeden Besucher auf der Grundlage bestimmter Besuche und/oder Seitenansichten filtern. Der Filtergenerator bietet eine einfache Architektur zum Erstellen dieser Untergruppen und das Anwenden von Regeln als verschachtelte hierarchische Personen-, Sitzungs- oder Ereignis-Container.

Die im Filtergenerator verwendete Container-Architektur definiert Person als den äußersten Container, der übergreifende Daten enthält, die für den Besucher über Besuche und Seitenansichten hinweg spezifisch sind. Mit einem verschachtelten Sitzungs-Container können Sie Regeln festlegen, mit denen die Besucherdaten auf der Grundlage von Sitzungen aufgeschlüsselt werden, und einen verschachtelten Ereignis-Container, mit dem die Besucherinformationen auf der Grundlage einzelner Seitenansichten aufgeschlüsselt werden. Jeder Container ermöglicht Berichte über den Verlauf eines Besuchers, nach Sitzung aufgeschlüsselte Interaktionen oder aufgeschlüsselte einzelne Ereignisse.

### Personen-Container

Der Personen-Container enthält sämtliche Besuche und Seitenansichten für Besucher innerhalb eines bestimmten Zeitraums. Ein Filter auf der Personenebene gibt die Seite zurück, die die Bedingung erfüllt, sowie alle anderen Seiten, die vom Besucher angesehen wurden (und dies nur durch definierte Datumsbereiche beschränkt). Da es sich um den am weitesten definierten Container handelt, liefern Berichte, die auf der Ebene des Personen-Containers erstellt werden, Seitenansichten über alle Besuche hinweg und ermöglichen eine Analyse mehrerer Besuche. Der Personen-Container ändert sich daher auf der Grundlage der definierten Datumsbereiche am wahrscheinlichsten.
Personen-Container können Werte enthalten, die auf dem Gesamtverlauf eines Besuchers basieren:

* Tage bis Erstkauf
* Ursprüngliche Entrypage
* Ursprünglich Referrerdomänen

### Sitzungs-Container

Mit dem Sitzungs-Container können Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifiziert werden. Der Sitzungs-Container ist der am häufigsten verwendete Behälter, da er die Verhaltensweisen der gesamten Besuchssitzung erfasst, sobald die Regel erfüllt wird, und Ihnen die Möglichkeit gibt, zu definieren, welche Sitzungen ein- oder ausgeschlossen werden sollen, indem Sie ein Segment erstellen und anwenden. Er kann Ihnen bei der Beantwortung dieser Fragen helfen:

* Wie viele Besucher haben die Bereiche „Nachrichten“ und „Sport“ in derselben Sitzung angesehen?
* Welche Seiten haben zu einer erfolgreichen Konversion in einem Verkauf beigetragen?

Sitzungs-Container enthalten Werte, die auf dem Auftreten pro Sitzung basieren:

* Sitzungsnummer
* Entrypage
* Rückkehrhäufigkeit
* Beitragsmetriken
* Linear zugeordnete Metriken

### Ereignis-Container

Der Ereignis-Container definiert, welche Seitenereignisse von einem Filter eingeschlossen oder ausgeschlossen werden sollen. Dies ist der engste verfügbare Behälter, mit dem Sie spezifische Klicks und Seitenansichten identifizieren können, für die eine Bedingung wahr ist, wobei Sie einen einzelnen Trackingcode oder ein isoliertes Verhalten in einem bestimmten Bereich Ihrer Site anzeigen können. Sie können auch einen bestimmten Wert erkennen, wenn eine Aktion stattfindet, z. B. den Marketing-Kanal, wenn ein Auftrag platziert wurde.

Zu den Ereignis-Containern zählen wertbasierte Einzelseitenunterteilungen:

* Produkte
* Listen-Props
* Listendimensionen
* Merchandising-Dimensionen (im Kontext von Ereignissen)