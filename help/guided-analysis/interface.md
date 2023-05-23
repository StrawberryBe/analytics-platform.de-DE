---
title: Geführte Analyse-Oberfläche
description: Erfahren Sie mehr über die Gesamtstruktur der Benutzeroberfläche des Geführten Analyseprojekts.
source-git-commit: d73dc0eb1740f28c0cd0b7b64fee86069c402b63
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---

# Guide Analysis-Benutzeroberfläche

{{release-limited-testing}}

Die Benutzeroberfläche für ein geführtes Analyseprojekt umfasst unabhängig vom Analysetyp die folgenden Hauptelemente der Benutzeroberfläche:

* **Abfrageleiste**: Verwenden Sie diese Leiste auf der linken Seite Ihres Projekts, um Ihre Analyse zu erstellen.
* **Diagramm**: Nachdem Sie die gewünschten Ereignisse, Personen oder Schritte ausgewählt haben, wird rechts ein Diagramm mit den Daten angezeigt.
* **Verzeichnis**: Eine Tabelle unter dem Diagramm, die die in der Visualisierung verwendeten Zahlen anzeigt.
* **Einstellungen und Einblicke**: Mehrere UI-Elemente über dem Diagramm, mit denen Sie die zurückgegebenen Daten anpassen können.

[Screenshot der Benutzeroberfläche]

## Abfrageleiste

[Screenshot der Abfrageleiste]

In der Abfrageleiste konfigurieren Sie die gewünschten Komponenten, aus denen ein Bericht besteht. Verschiedene Analysetypen haben mehrere Abfrageoptionen. Wenn zwei Analysetypen Abfrageoptionen gemeinsam nutzen, werden sie beim Wechsel der Analysetypen übernommen. Siehe [Analysetypen](analysis-types/overview.md) für weitere Informationen zu den Abfrageoptionen für die einzelnen Analysetypen.

## Diagramm

[Screenshot eines Diagramms]

Eine Visualisierung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Welche Visualisierung Sie sehen, hängt vom Ansichtstyp über dem Diagramm ab. Die verfügbaren Ansichtstypen hängen von der [Analysetyp](analysis-types/overview.md) über der Abfrageleiste.

## Tabelle

[Screenshot der Tabelle]

Eine Tabellendarstellung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Die Spalten in der Tabelle hängen vom Ansichtstyp über dem Diagramm ab. Die verfügbaren Ansichtstypen hängen von der [Analysetyp](analysis-types/overview.md) über der Abfrageleiste.

## Einstellungen 

[Screenshot der Einstellungen]

Mehrere Optionen über dem Diagramm ermöglichen es Ihnen, anzupassen, wie das Diagramm und die Tabelle Daten zurückgeben.

* **Ansichtstyp**: Eine Dropdown-Auswahl, mit der Sie Daten für eine bestimmte [Analysetyp](analysis-types/overview.md) auf eine andere Weise. Jeder Analysetyp hat mindestens zwei Ansichtstypen.
* **Diagrammeinstellungen**: Passen Sie an, wie Ihr Diagramm aussieht und welche Ereignisse Sie verwenden möchten. Die verfügbaren Optionen hängen vom ausgewählten Ansichtstyp ab.
* **Datumsbereich**: Eine Kalenderauswahl, mit der Sie den Datumsbereich des Berichts ermitteln können. Einige Analysetypen ermöglichen auch Intervalle, z. B. täglich, wöchentlich oder monatlich.
* **Insights**: Bietet je nach angezeigtem Bericht kontextbezogene Einblicke. Sie können diese Einblicke mithilfe des Glühbirnensymbols oben rechts ein- oder ausblenden.

## Menü Projekt

[Screenshot des Projektmenüs]

Befehle oben rechts im Projekt, die übergreifende Aktionen bereitstellen.

* **Datenansichtsauswahl**: Ändern Sie die Datenansicht, die dieses Projekt verwendet. Wenn Sie die Datenansicht ändern, ändern sich auch die verfügbaren Komponenten in der Abfrageleiste.
* **Speichern**: Speichert das Projekt. Wenn Sie ein neues Projekt speichern, wird ein modales Fenster angezeigt, das einen Namen und eine Beschreibung anfordert.
* **Speichern unter**: Speichert das Projekt getrennt vom aktuellen Projekt und erstellt eine Kopie. Es wird ein modales Fenster angezeigt, das einen neuen Namen und eine neue Beschreibung anfordert.
* **In Workspace öffnen**: Erstellt das aktuelle Geführte Analyseprojekt in Analysis Workspace erneut. Das Workspace-Projekt wird in einer neuen Registerkarte erstellt, wodurch Unterbrechungen bei der Arbeit an Ihrem geführten Analyseprojekt verhindert werden. Verwenden Sie diesen Befehl, wenn die geführte Analyse Ihnen nicht die gewünschte Flexibilität oder spezifische Einblicke bietet. Sie möchten beispielsweise eine [Trends](analysis-types/trends.md) -Bericht verwenden, der Sitzungen für ein Segment und Personen für ein anderes Segment verwendet.
* **PNG herunterladen**: Laden Sie die Diagrammgrafik als `.png`. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.
* **SVG herunterladen**: Laden Sie die Diagrammgrafik als `.svg`. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.
