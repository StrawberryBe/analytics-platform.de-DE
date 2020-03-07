---
title: Filterübersicht
description: Verstehen Sie, für welche Filter Sie sich entscheiden und wie Sie einen einfachen Filter erstellen.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Filterübersicht

Mit Customer Journey Analytics können Sie leistungsstarke, fokussierte Zielgruppenfilter erstellen, verwalten, freigeben und auf Ihre Berichte anwenden. Mit Filtern können Sie Untergruppen von Besuchern anhand von Merkmalen oder Website-Interaktionen identifizieren. Filter sind als kodifizierte Zielgruppeneinblicke konzipiert, die Sie für Ihre spezifischen Anforderungen erstellen und dann überprüfen, bearbeiten und mit anderen Teammitgliedern teilen können.

Filter können auf Attributen (Browsertyp, Gerät, Anzahl der Besuche, Land, Geschlecht), Interaktionen (Kampagnen, Suchbegriffsuche, Suchmaschine), Ausstiege und Einträge (Besucher von Facebook, eine definierte Einstiegsseite, Referrerdomäne), benutzerspezifischen Variablen (Formularfeld, definierte Kategorien, Kunden-ID) und anderen Kriterien basieren.

Sie können Filter im Filter Builder erstellen und speichern oder Filter aus einer Fallout-Visualisierung (in Workspace) generieren. Darüber hinaus können Filter gemeinsam als gestapelte Filter verwendet werden.

>[!IMPORTANT]
Filter werden in Adobe Analytics als &quot;Segmente&quot;bezeichnet. Wir haben Segmente in Filter umbenannt, da Adobe Experience Platform eine andere Definition von &quot;Segment&quot;hat. Ein Segment in AEP bezieht sich auf ...

Filtering includes the [Filter Builder](/help/components/filters/create-filters.md) to construct filters and run a pre-test, and the [Filter Manager](/help/components/filters/manage-filters.md) to collect, tag, approve, set security, and share filters across your organization.

## Sequenzielle Filter

Mit sequenziellen Filtern können Sie Besucher basierend auf der Navigation und dem Seitenaufruf auf Ihrer Site identifizieren und so einen Filter für definierte Aktionen und Interaktionen bereitstellen. Mit sequenziellen Segmenten können Sie erkennen, was ein Besucher mag und was er meidet. Beim Erstellen sequenzieller Filter wird der DANN-Operator verwendet, um die Besuchernavigation zu definieren und zu ordnen.

Siehe folgendes Beispiel:

![](assets/sequential_fil.png)

| Erster Besuch | Zweiter Besuch | Dritter Besuch |
|---|---|---|
| Der Besucher besuchte die Haupt-Landingpage (A), schloss die Kampagnenseite (B) aus und sah dann die Produktseite (C) an. | Der Besucher besuchte erneut die Haupt-Landingpage (A), schloss die Kampagnenseite (B) aus, wechselte erneut zur Produktseite (C) und dann zu einer neuen Seite (D). | Der Besucher hat denselben Pfad wie bei dem ersten und zweiten Besuch eingegeben und gefolgt und dann Seite F ausgeschlossen, um direkt zu einer zielgerichteten Produktseite (G) zu gelangen. |

## Filter-Behälter

Filter basieren auf einer Hierarchie auf der Ebene der Person, Sitzung und Ereignisse und verwenden ein verschachteltes Behältermodell. Die verschachtelten Behälter ermöglichen es Ihnen, Personenattribute und Aktionen basierend auf Regeln zwischen und innerhalb der Behälter zu definieren.

>[!NOTE]
>Der Behälter &quot;Person&quot;wurde früher als &quot;Besucherbehälter&quot;bezeichnet. Der Sitzungsbehälter wurde als Besuchsbehälter bezeichnet, und der Ereignisbehälter war früher der Trefferbehälter.

Ein Filter legt Bedingungen zum Filtern eines Besuchers auf der Grundlage seiner Attribute oder Interaktionen mit Ihrer Site fest. Um Bedingungen in einem Filter festzulegen, legen Sie Regeln zum Filtern von Besuchern auf der Grundlage von Besuchermerkmalen und/oder Navigationsmerkmalen fest. Um die Besucherdaten weiter herunterzubrechen, können Sie jeden Besucher auf der Grundlage bestimmter Besuche und/oder Seitenansichten filtern. Der Filter Builder bietet eine einfache Architektur, um diese Untergruppen zu erstellen und Regeln als verschachtelte, hierarchische Personen-, Sitzungs- oder Ereignisbehälter anzuwenden.

Die im Filter Builder verwendete Behälterarchitektur definiert den Benutzer als den äußersten Behälter, der übergreifende besucherspezifische Daten über Besuche und Seitenansichten enthält. Mit einem verschachtelten Sitzungsbehälter können Sie Regeln festlegen, um die Besucherdaten basierend auf Sitzungen zu unterteilen, und mit einem verschachtelten Ereignisbehälter können Sie Besucherinformationen basierend auf individuellen Seitenansichten unterteilen. Mit jedem Behälter können Sie Berichte über den Verlauf eines Besuchers, nach Sitzungen aufgeschlüsselte Interaktionen oder einzelne Ereignisse erstellen.

### Benutzerbehälter

Der Behälter &quot;Person&quot;enthält alle Besuche und Seitenansichten von Besuchern innerhalb eines bestimmten Zeitraums. Ein Filter auf der Ebene der Person gibt die Seite zurück, die die Bedingung erfüllt, sowie alle anderen vom Besucher angezeigten Seiten (und nur durch definierte Datumsbereiche eingeschränkt). Als am weitesten definierter Behälter geben Berichte, die auf der Ebene des Personenbehälters erstellt werden, Seitenansichten über alle Besuche hinweg zurück und ermöglichen Ihnen die Erstellung einer Analyse mit mehreren Besuchen. Folglich ist der Personenbehälter basierend auf definierten Datumsbereichen am empfindlichsten zu ändern.
Personenbehälter können Werte basierend auf dem Gesamtverlauf eines Besuchers enthalten:

* Tage bis Erstkauf

* Ursprüngliche Entrypage

* Ursprünglich Referrerdomänen

### Sitzungsbehälter

Mit dem Sitzungsbehälter können Sie Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifizieren. Der Sitzungsbehälter ist der am häufigsten verwendete Behälter, da er Verhalten für die gesamte Besuchssitzung erfasst, sobald die Regel erfüllt ist, und Sie definieren können, welche Sitzungen Sie beim Erstellen und Anwenden eines Segments einbeziehen oder ausschließen möchten. Es kann Ihnen bei der Beantwortung dieser Fragen helfen:

* Wie viele Besucher haben den Abschnitt Nachrichten und Sport in derselben Sitzung angesehen?

* Welche Seiten haben zu einer erfolgreichen Umrechnung zu einem Verkauf beigetragen?

Sitzungsbehälter enthalten Werte, die auf dem Vorkommen pro Sitzung basieren:

* Sitzung Nr.

* Entrypage

* Rückkehrhäufigkeit

* Beitragsmetriken

* Linear zugeordnete Metriken

### Ereignisbehälter

Der Ereignisbehälter definiert, welche Seitenereignisse von einem Filter ein- oder ausgeschlossen werden sollen. Dies ist der engste verfügbare Behälter, mit dem Sie spezifische Klicks und Seitenansichten identifizieren können, für die eine Bedingung wahr ist, wobei Sie einen einzelnen Trackingcode oder ein isoliertes Verhalten in einem bestimmten Bereich Ihrer Site anzeigen können. Sie können auch einen bestimmten Wert erkennen, wenn eine Aktion stattfindet, z. B. den Marketing-Kanal, wenn ein Auftrag platziert wurde.

Ereignisbehälter enthalten Werte, die auf Einzelseitenunterteilungen basieren:

* Produkte

* Listen-Props

* Listendimensionen

* Merchandising-Dimensionen (im Kontext von Ereignissen)