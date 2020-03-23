---
title: Arbeitsbereich - Grundlagen
description: Beschreibt, wie Sie grundlegende Berichte in Workspace abrufen
translation-type: tm+mt
source-git-commit: eba2b60496976eb6027d58e0ce231ee046c8fc02

---


# Arbeitsbereich - Grundlagen

Wenn Sie mit dem Tool Workspace noch nicht vertraut sind, hier einige Tipps zum Einstieg.

Workspace ist das führende Werkzeug von Adobe, um datenbasierte Entscheidungen für Ihr Unternehmen zu treffen. Mit der am häufigsten verwendeten Visualisierung, der Freiformtabelle, können Sie ganz einfach benutzerspezifische Berichte mit Dimensionen, Metriken, Segmenten und Datumsbereichen erstellen.

## Abrufen eines einfachen Rangberichts in Workspace

Ein Rangbericht zeigt eine aggregierte Gesamtansicht jedes Dimensionswerts an, wobei die größten Werte zuerst angezeigt werden. Diese Berichtstypen sind nützlich, um zu sehen, welche Komponenten Ihrer Site am effektivsten sind, z. B. welche Seiten den meisten Traffic erhalten oder welche Produkte am häufigsten verkauft werden.

1. Vergewissern Sie sich, dass Sie bei [analytics.adobe.com](https://analytics.adobe.com)angemeldet sind.
1. In the top navigation bar, click **[!UICONTROL Workspace]**.
1. Klicken Sie auf **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. Links sehen Sie eine Liste mit Dimensionen, Metriken, Segmenten und Datumsbereichen. Suchen Sie die Dimension „Seiten“ (orange) und ziehen Sie sie auf die Arbeitsfläche mit der Angabe „Dimension hier ablegen“.
1. Es wird ein Bericht mit den wichtigsten Seiten für diesen Monat angezeigt. Analysis Workspace füllt den Bericht automatisch mit der Metrik [Vorfälle](https://docs.adobe.com/content/help/en/analytics/components/variables/metrics/metrics-occurrences.html).
1. Suchen Sie die Metrik „Besuche“ (grün) und ziehen Sie sie entweder **über** oder **neben** die Kopfzeile der Metrik „Vorfälle“ (vermeiden Sie, sie über der Metrik zu platzieren). Wenn Sie die Metrik „Besuche“ über Vorfälle ziehen, wird die Metrik in den Berichten ersetzt. Wenn Sie die Metrik „Besuche“ neben „Vorfälle“ ziehen, werden beide Metriken nebeneinander angezeigt.
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## Abrufen eines einfachen Trend-Berichts in Workspace

Ein Trend-Bericht zeigt eine Zeitverlaufsansicht der Metriken unter Verwendung des ausgewählten Datumsbereichs an. Diese Berichtstypen sind nützlich, um Trends im Zeitverlauf zu identifizieren, und können zur Messung des Erfolgs oder Misserfolgs von Geschäftsentscheidungen verwendet werden. Sie könnten sich beispielsweise einen Trend-Bericht zu Seitenansichten im Lauf der Zeit ansehen, um festzustellen, ob eine Site-Umgestaltung dazu beigetragen hat, den Traffic zu erhöhen oder zu verringern.

1. Vergewissern Sie sich, dass Sie bei [analytics.adobe.com](https://analytics.adobe.com)angemeldet sind.
1. In the top navigation bar, click **[!UICONTROL Workspace]**.
1. Klicken Sie auf **[!UICONTROL Create New Project]**.
1. In the modal popup, make sure &#39;Blank Project&#39; is selected, then click **[!UICONTROL Create]**.
1. Links sehen Sie eine Liste mit Dimensionen, Metriken, Segmenten und Datumsbereichen. Locate the Page Views dimension, and drag it to the small space on the canvas labeled **[!UICONTROL Drop a Metric Here]**. Vermeiden Sie es (zumindest für diese Übung), ihn in dem für Dimensionen reservierten Bereich abzulegen.
1. Beachten Sie, dass bei einer Report Suite mit Daten ein einfacher Trend-Bericht für die Seitenansichten im laufenden Monat angezeigt werden sollte. Analysis Workspace hat automatisch den Datumsbereich „Tag“ eingefügt, damit Sie den Trend der Seitenansichten für den aktuellen Monat sehen können.
1. Suchen Sie links in der Liste der Datumsbereichskomponenten den Datumsbereich „Woche“ (violett). Klicken Sie auf den Titel des Datumsbereichs, um alle Komponenten des Datumsbereichs zu erweitern und anzuzeigen, oder verwenden Sie die Suchleiste.
1. Ziehen Sie den Datumsbereich „Woche“ auf die Kopfzeile des Datumsbereichs „Tag“ auf der Arbeitsfläche, um ihn zu ersetzen.
1. Beachten Sie, dass Ihr Trend-Bericht jetzt nach Woche statt nach Tag aggregiert wird.
1. If you&#39;d like to save your project, click **[!UICONTROL Project]>[!UICONTROL Save]**in the upper left menu.

## Mit dem Werkzeug experimentieren

Da Workspace ein Berichtswerkzeug ist, hat dies keine Auswirkungen auf die Datenerfassung. Komponenten wahllos in ein Projekt zu ziehen, um zu sehen, was funktioniert, hat keine weiteren Folgen. Ziehen Sie verschiedene Kombinationen von Dimensionen und Metriken in Ihr Workspace-Projekt, um zu sehen, welche Möglichkeiten Sie haben.

Wenn Sie versehentlich eine ungültige Komponente in Ihr Workspace-Projekt ziehen oder einen Schritt zurückgehen möchten, drücken Sie Strg+Z (Windows) oder Befehl+Z (Mac), um die letzte durchgeführte Aktion rückgängig zu machen. You can also start with a clean slate by clicking **[!UICONTROL Project]>[!UICONTROL New]**in the upper left menu.

## Fehlerbehebung

### Wenn ich eine Metrik ziehe, wird die Meldung „Ungültige Daten“ angezeigt.

„Ungültige Daten“ bedeuten, dass Adobe keine Daten mit der Kombination von Dimensionen und Metriken zurückgeben kann, die im Bericht verwendet werden. Beispielsweise können zwei Metriken, die übereinander gestapelt sind, nicht als Daten zurückgegeben werden, da es nicht möglich ist, zwei Metriken in dieser Weise anzuzeigen. Platzieren Sie die Metriken stattdessen nebeneinander.

### Wenn ich eine Metrik ziehe, sehe ich keine tatsächlichen Daten - nur Nullen.

Wenn Sie erfolgreich einen Workspace-Bericht erstellen, aber keine Daten vorhanden sind, können Sie einige Punkte prüfen:

* Überprüfen Sie die Report Suite und stellen Sie sicher, dass sie mit Daten gefüllt ist.
* Wenn Sie ein Segment in Ihrem Bericht verwenden, stimmen die Segmentkriterien möglicherweise nicht mit den Daten überein. Versuchen Sie, das Segment zu entfernen oder die Segmentdefinition anzupassen.
* Überprüfen Sie den Datumsbereich oben rechts und stellen Sie sicher, dass er auf einen erwarteten Wert eingestellt ist.
* Navigieren Sie zu Ihrer Website und überprüfen Sie mit dem Debugger, ob Daten erfasst werden.

## Zusätzliche Ressourcen

Beachten Sie, dass die folgenden Ressourcen auf die Verwendung von Workspace im herkömmlichen Adobe Analytics-Produkt verweisen können, nicht in Customer Journey Analytics.

* Blog-Beiträge:
   * [Empowering Organizations with Smarter Analysis](https://theblog.adobe.com/adobe-analytics-fall-2016-release-empowering-organizations-smarter-analysis/) (Englisch)
   * [Arbeitsbereich für Analysen: Die Geheimnis-Sauce wird besser](https://theblog.adobe.com/analysis-workspace-secret-sauce-getting-tastier/)
   * [Why You Should Be Using Analysis Workspace](https://theblog.adobe.com/why-you-should-be-using-analysis-workspace-in-adobe-analytics/) (Englisch)
   * [5 Tips to Maximize Your Productivity with Analysis Workspace](https://theblog.adobe.com/5-tips-maximize-productivity-analysis-workspace/) (Englisch)

## Nächste Schritte

Es gibt viele Ressourcen, mit deren Hilfe Sie Workspace besser verstehen können. Im Folgenden finden Sie einige Grundlagen, die Adobe empfiehlt:

### Für Endbenutzer, die Kenntnisse zur Verwendung von Workspace erweitern möchten

* [Details zur Workspace-Benutzeroberfläche](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/t-freeform-project.html): Nachdem Sie jetzt einen grundlegenden Bericht erstellt haben, sollten Sie sich mit dem Rest der Oberfläche vertraut machen.
* [Visualisierungen in Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html): Freiformtabellen sind nur eine Art der Visualisierung in Analysis Workspace. Erfahren Sie, wie Sie andere Visualisierungen wie Liniendiagramme, Balkendiagramme und geografische Karten verwenden.
* [Dimensionen in Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html): Erfahren Sie mehr über Dimensionen und ihre Verwendung in mehr als nur Rangberichten.
* [Metriken in Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/apply-create-metrics.html): Erfahren Sie mehr darüber, was Metriken sind und wie sie in anderen Teilen von Freiformtabellen verwendet werden.
* [Einführung in die Segmentierung](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html): Erfahren Sie, was Segmente sind, und erstellen Sie einen einfachen Bericht mit einem Segment.
* [Datumsbereiche in Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html): Erfahren Sie mehr über relative und rollierende Daten und verwenden Sie sie in Workspace-Projekten.
* [Freigeben von Projekten in Workspace: Zeigen Sie Ihrem Kollegen das fantastische Workspace-Projekt, das Sie erstellt haben.](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html)

### Für Analysten und Administratoren, die die Workspace-Qualität in ihrem Unternehmen verbessern möchten

* [Berechtigungen in Analysis Workspace](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html): Weisen Sie über Adobe Admin Console Benutzerberechtigungen für Workspace zu.
* [Vorlagen in Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html): Erstellen Sie Vorlagen, damit Ihre Kollegen mit einem auf ihre Bedürfnisse zugeschnittenen Projektraum beginnen können.
* [Workspace-Kuratierung](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html): Erstellen Sie ein Projekt, das die verfügbaren Komponenten einschränkt, damit Workspace für diejenigen, die mit dem Tool weniger vertraut sind, leichter zugänglich ist.
