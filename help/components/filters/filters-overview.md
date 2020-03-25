---
title: Übersicht über Filter
description: Verstehen Sie, wofür Filter verwendet werden und wie Sie einen einfachen Filter erstellen.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Übersicht über Filter

Mit Customer Journey Analytics können Sie leistungsstarke, fokussierte Audience-Filter erstellen, verwalten, freigeben und auf Ihre Berichte anwenden. Mit Filtern können Sie Untergruppen von Besuchern anhand von Merkmalen oder Website-Interaktionen identifizieren. Filter sind als kodifizierte Einblicke in die Audience konzipiert, die Sie für Ihre spezifischen Anforderungen erstellen und dann überprüfen, bearbeiten und mit anderen Teammitgliedern teilen können.

Filter können auf Attributen (Browsertyp, Gerät, Anzahl der Besuche, Land, Geschlecht), Interaktionen (Kampagnen, Suchbegriffsuche, Suchmaschine), Ausstiege und Einträge (Besucher von Facebook, definierte Landingpage, Referrerdomäne), benutzerspezifischen Variablen (Formularfeld, definierte Kategorien, Kunden-ID) und anderen Kriterien basieren.

Sie können Filter im Filteraufbau erstellen und speichern oder Filter aus einer Fallout-Visualisierung (in Workspace) generieren. Darüber hinaus können Filter gemeinsam als gestapelte Filter verwendet werden.

>[!IMPORTANT]
Filter werden in Adobe Analytics als &quot;Segmente&quot;bezeichnet. Wir haben Segmente in Filter umbenannt, da Adobe Experience Platform eine andere Definition von &quot;segment&quot;hat. Ein Segment in AEP bezieht sich auf ...

Die Filterung umfasst den [Filteraufbau](/help/components/filters/create-filters.md) zum Erstellen von Filtern und zum Ausführen eines Vortests sowie den [Filter-Manager](/help/components/filters/manage-filters.md) zum Erfassen, Taggen, Genehmigen, Sicherheitseinstellungen und Freigeben von Filtern in Ihrem Unternehmen.

## Sequenzielle Filter

Mit sequenziellen Filtern können Sie Besucher basierend auf der Navigation und der Ansicht der Seite auf Ihrer Website identifizieren und so einen Filter für definierte Aktionen und Interaktionen bereitstellen. Sequenzielle Segmente helfen Ihnen dabei, herauszufinden, was ein Besucher mag und was ein Besucher vermeidet. Beim Erstellen sequenzieller Filter wird der DANN-Operator verwendet, um die Navigation des Besuchers zu definieren und anzuordnen.

Siehe folgendes Beispiel:

![](assets/sequential_fil.png)

| Erster Besuch | Zweiter Besuch | Dritter Besuch |
|---|---|---|
| Der Besucher besuchte die Hauptseite der Landingpage (A), schloss die Seite &quot;Kampagne&quot;(B) aus und sah dann die Produktseite (C) an. | Der Besucher besuchte erneut die Hauptseite der Landingpage (A), schloss die Kampagne (B) aus und wechselte erneut zur Produktseite (C) und dann zur neuen Seite (D). | Der Besucher trat ein und folgte demselben Pfad wie bei dem ersten und zweiten Besuch und schloss dann Seite F aus, um direkt zu einer zielgerichteten Produktseite (G) zu wechseln. |

## Container filtern

Filter basieren auf einer Hierarchie auf Ereignis-, Sitzungs- und Benutzerebene und verwenden ein verschachteltes Container-Modell. Mit verschachtelten Containern können Sie Personenattribute und Aktionen auf der Grundlage von Regeln zwischen und innerhalb der Container definieren.

>[!NOTE]
>Der Container &quot;Person&quot;wurde früher als &quot;Besucher-Container&quot;bezeichnet. Der Session-Container wurde als &quot;Besuch&quot;-Container bezeichnet, und der Ereignis-Container war früher der TrefferContainer.

Ein Filter legt Bedingungen zum Filtern eines Besuchers auf der Grundlage seiner Attribute oder Interaktionen mit Ihrer Site fest. Um Bedingungen in einem Filter festzulegen, legen Sie Regeln zum Filtern von Besuchern auf der Grundlage von Besucher- und/oder Navigationsmerkmalen fest. Zur weiteren Aufschlüsselung von Besucher-Daten können Sie für jeden Besucher nach bestimmten Besuchen und/oder Seitentreffern filtern. Der Filteraufbau bietet eine einfache Architektur zum Erstellen dieser Untergruppen und zum Anwenden von Regeln als verschachtelte, hierarchische Container für Person, Sitzung oder Ereignis.

Die im Filteraufbau verwendete Container-Architektur definiert den Begriff &quot;&quot;als äußersten Container, der übergreifende Daten enthält, die für den Besucher spezifisch sind, und zwar besuchsübergreifend und seitenübergreifend, d. h. über Ansichten hinweg. In einem verschachtelten Session-Container können Sie Regeln festlegen, um die Daten des Besuchers auf Grundlage von Sitzungen aufzuschlüsseln. In einem verschachtelten Ereignis-Container können Sie die Informationen zum Besucher auf der Grundlage der einzelnen Ansichten aufschlüsseln. Mit jedem Container können Sie Berichte über den Verlauf eines Besuchers, Interaktionen nach Sitzungen unterteilt oder einzelne Ereignis unterteilen.

### Container

Der Container &quot;Person&quot;umfasst alle Besuche und Ansichten für Besucher innerhalb eines bestimmten Zeitraums. Ein Filter auf der Ebene der Person gibt die Seite zurück, die die Bedingung erfüllt, sowie alle anderen vom Besucher angezeigten Seiten (und nur durch definierte Datumsbereiche eingeschränkt). Als am weitesten definierter Container geben Berichte, die auf der Ebene des Containers erstellt werden, bei allen Besuchen Ansichten der Seite zurück und ermöglichen es Ihnen, eine mehrfache Analyse zu generieren. Der Container &quot;Person&quot;ist daher je nach definierten Datumsbereichen am ehesten für eine Änderung geeignet.
Container können Werte einbeziehen, die auf dem Gesamtverlauf des Besuchers basieren:

* Tage bis Erstkauf

* Ursprüngliche Entrypage

* Ursprünglich Referrerdomänen

### Session Container

Mit dem Session Container können Sie Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifizieren. Der Session Container ist der am häufigsten verwendete Container, da er Verhaltensweisen für die gesamte Besuchssitzung erfasst, sobald die Regel erfüllt ist, und Sie definieren können, welche Sitzungen Sie beim Erstellen und Anwenden eines Segments einbeziehen oder ausschließen möchten. Es kann Ihnen bei der Beantwortung dieser Fragen helfen:

* Wie viele Besucher haben den Bereich &quot;Nachrichten und Sport&quot;in derselben Sitzung angesehen?

* Welche Seiten haben zu einer erfolgreichen Umrechnung zu einem Verkauf beigetragen?

Sitzungs-Container enthalten Werte, die auf dem Vorkommen pro Sitzung basieren:

* Sitzung Nr.

* Einstieg Seite

* Rückkehrhäufigkeit

* Beitragsmetriken

* Linear zugeordnete Metriken

### Ereignis Container

Der Container &quot;Ereignis&quot;definiert, welche Ereignis von Seiten Sie in einen Filter einschließen oder ausschließen möchten. Es handelt sich dabei um die kleinsten verfügbaren Container, mit denen Sie bestimmte Klicks und die Ansicht der Seite identifizieren können, bei denen eine Bedingung wahr ist, sodass Sie einen einzigen Rückverfolgungscode oder ein isoliertes Verhalten innerhalb eines bestimmten Bereichs Ihrer Site Ansicht haben. Möglicherweise möchten Sie auch einen bestimmten Kanal genau bestimmen, wenn eine Aktion ausgeführt wird, z. B. den Marketingwert, wenn eine Bestellung aufgegeben wurde.

Ereignis-Container enthalten Werte, die auf Einzelseitenunterteilungen basieren:

* Produkte

* Listen-Props

* Abmessungen der Liste

* Merchandising-Dimensionen (im Kontext von Ereignissen)