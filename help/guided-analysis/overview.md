---
title: Geführte Analyse – Übersicht
description: Eine Methode zur Datenanalyse in Customer Journey Analytics, mit der Produktteams einfach Berichte und Einblicke generieren können.
exl-id: 6a8a92db-f030-424e-af9b-f8f6502084f6
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Geführte Analyse – Übersicht

{{release-limited-testing}}

Geführte Analyse ist ein Berichtsformat, das es Produktteams ermöglicht, schnell ihre Datenanforderungen selbst zu erfüllen, sodass sie datengesteuerte Produktentscheidungen treffen können. Funktions-Teams können in Echtzeit eine Verbindung herstellen, um diese Berichte zu verwenden und zu verstehen.

Ähnlich wie bei Analysis Workspace- und Mobile-Scorecards verwendet ein Bericht mit einer geführten Analyse Daten aus einer [Datenansicht](../data-views/data-views.md), die Daten in Adobe Experience Platform über einen [Verbindung](../connections/overview.md). Alle in der geführten Analyse erstellten Berichte können nahtlos zur weiteren Recherche an Analysis Workspace übermittelt werden.

Geführte Analysen bieten mehrere Möglichkeiten zur Datenanalyse. Diese Ansichtstypen können dieselben Daten auf unterschiedliche Weise anzeigen, was zu unterschiedlichen Einblicken mit denselben Ereignissen und Segmenten führt. Je nach dem gewählten Ansichtstyp erhalten Sie verschiedene Abfrageleisten- und Visualisierungsoptionen. Sie können frei zwischen Ansichtstypen wechseln und alle entsprechenden Komponenten der Abfrageleiste übernehmen, wenn der Ansichtstyp sie unterstützt.

Geführte Analyse kategorisiert Ansichtstypen in **Analysetypen**. Die folgenden Analyse- und Ansichtstypen sind verfügbar:

| Analysetyp | Ansichtstyp | Beschreibung |
| --- | --- | --- |
| Wirkung | [Version](types/release.md) | Leistung in gleichen Zeiträumen vor und nach Veröffentlichung vergleichen. |
| Wirkung | [Erstmalige Verwendung](types/first-use.md) | Messen der Auswirkung der erstmaligen Verwendung von Funktionen auf Schlüsselindikatoren. |
| Trichter | [Reibung](types/friction.md) | Konversionsraten zwischen den Schritten vergleichen. |
| Trichter | [Konversions-Trends](types/conversion-trends.md) | Verfolgen Sie Veränderungen der Konversionsraten im Laufe der Zeit. |
| Benutzerwachstum | [Aktiv](types/active.md) | Wachstum der Benutzerbasis messen. |
| Benutzerwachstum | [Nettowachstum](types/net-growth.md) | Saldo Nutzergewinne und -verluste. |
| Trends | [Nutzung](types/usage.md) | Benutzerinteraktion im Lauf der Zeit messen. |

{style="table-layout:auto"}

## Benutzeroberfläche

Die Benutzeroberfläche für die geführte Analyse umfasst unabhängig vom Analysetyp die folgenden Hauptelemente der Benutzeroberfläche:

1. **Abfrageleiste**: Verwenden Sie diese Leiste auf der linken Seite, um Ihre Analyse zu erstellen.
1. **Diagramm**: Nachdem Sie die gewünschten Ereignisse, Personen oder Schritte ausgewählt haben, wird rechts ein Diagramm mit den Daten angezeigt.
1. **Verzeichnis**: Eine Tabelle unter dem Diagramm, die die in der Visualisierung verwendeten Zahlen anzeigt.
1. **Einstellungen und Einblicke**: Mehrere UI-Elemente über dem Diagramm, mit denen Sie die zurückgegebenen Daten anpassen können.

[Screenshot der Benutzeroberfläche]

Die geführte Analyse enthält die folgenden Schnittstellenteile:

| Benutzeroberfläche | UI-Element | Beschreibung |
| --- | --- | --- |
| ![Abfrageleiste](assets/query-rail.png) | Abfrageleiste | Konfigurieren Sie die gewünschten Komponenten, aus denen ein Bericht besteht. Verschiedene Analysetypen haben mehrere Abfrageoptionen. Wenn zwei Analysetypen Abfrageoptionen gemeinsam nutzen, werden sie beim Wechsel der Analysetypen übernommen. |
| ![Diagramm](assets/chart.png) | Diagramm | Eine Visualisierung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Welche Visualisierung Sie sehen, hängt vom Ansichtstyp über dem Diagramm ab. Die verfügbaren Ansichtstypen hängen vom Analysetyp über der Abfrageleiste ab. |
| ![Tabelle](assets/table.png) | Tabelle | Eine Tabellendarstellung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Die Spalten in der Tabelle hängen vom Ansichtstyp über dem Diagramm ab. Die verfügbaren Ansichtstypen hängen vom Analysetyp über der Abfrageleiste ab. |
| ![Visualisierungseinstellungen](assets/visualization-settings.png) | Visualisierungseinstellungen | Mehrere Optionen über dem Diagramm ermöglichen es Ihnen, anzupassen, wie das Diagramm und die Tabelle Daten zurückgeben.<ul><li>**Ansichtstyp**: Eine Dropdown-Auswahl, mit der Sie Daten für einen bestimmten Analysetyp auf andere Weise darstellen können. Jeder Analysetyp hat mindestens zwei Ansichtstypen.</li><li>**Diagrammeinstellungen**: Passen Sie an, wie Ihr Diagramm aussieht und welche Ereignisse Sie verwenden möchten. Die verfügbaren Optionen hängen vom ausgewählten Ansichtstyp ab.</li><li>**Datumsbereich**: Eine Kalenderauswahl, mit der Sie den Datumsbereich des Berichts ermitteln können. Einige Analysetypen ermöglichen auch Intervalle, z. B. täglich, wöchentlich oder monatlich.</li><li>**Insights**: Bietet je nach angezeigtem Bericht kontextbezogene Einblicke. Sie können diese Einblicke mithilfe des Glühbirnensymbols oben rechts ein- oder ausblenden.</li></ul> |
| ![Menü](assets/menu.png) | Analysemenü | Befehle oben rechts in der geführten Analyse, die übergreifende Aktionen bereitstellen.<ul><li>**Datenansichtsauswahl**: Ändern Sie die Datenansicht, die von dieser Analyse verwendet wird. Wenn Sie die Datenansicht ändern, ändern sich auch die verfügbaren Komponenten in der Abfrageleiste.</li><li>**Speichern**: Speichert die Analyse. Wenn Sie eine neue Analyse speichern, wird ein modales Fenster angezeigt, das einen Namen und eine Beschreibung anfordert.</li><li>**Speichern unter**: Speichert die Analyse getrennt von der aktuellen Analyse und erstellt eine Kopie. Es wird ein modales Fenster angezeigt, das einen neuen Namen und eine neue Beschreibung anfordert.</li><li>**In Workspace öffnen**: Erstellt die aktuelle geführte Analyse in Analysis Workspace erneut. Das Workspace-Projekt wird in einer neuen Registerkarte erstellt, wodurch Unterbrechungen beim Arbeiten mit der geführten Analyse verhindert werden. Verwenden Sie diesen Befehl, wenn die geführte Analyse Ihnen nicht die gewünschte Flexibilität oder spezifische Einblicke bietet. Sie möchten beispielsweise eine [Nutzung](types/usage.md) -Bericht verwenden, der Sitzungen für ein Segment und Personen für ein anderes Segment verwendet.</li><li>**PNG herunterladen**: Laden Sie die Diagrammgrafik als `.png`. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li><li>**SVG herunterladen**: Laden Sie die Diagrammgrafik als `.svg`. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li></ul> |

{style="table-layout:auto"}

## Bereitstellung

Geführte Analysen sind Teil des Adobe Product Analytics, bei dem es sich um ein kostenpflichtiges Add-on für Customer Journey Analytics handelt. Wenden Sie sich an Ihr Adobe Account Team, wenn Ihr Unternehmen mit der Verwendung dieser Funktion beginnen möchte.

Nachdem Ihr Unternehmen für die Verwendung der geführten Analyse bereitgestellt wurde, können Produktprofiladministratoren Zugriff auf diese in der Adobe Admin Console gewähren.

1. Melden Sie sich bei der [Adobe Admin Console](https://adminconsole.adobe.com).
1. Auswählen **[!UICONTROL Customer Journey Analytics]** in der Liste der Erzeugnisse.
1. Wählen Sie das gewünschte Produktprofil aus, um Berechtigungen zu bearbeiten.
1. Klicken Sie auf **[!UICONTROL Berechtigungen]** Registerkarte und klicken Sie dann auf **[!UICONTROL Bearbeiten]** under [!UICONTROL Reporting-Tools].
1. Klicken Sie auf das Pluszeichen neben **[!UICONTROL Geführter Zugriff auf Analysen]** in der Liste der [!UICONTROL Verfügbare Berechtigungselemente] , um sie zur Liste der [!UICONTROL Eingeschlossene Berechtigungselemente].
1. Klicken Sie auf **[!UICONTROL Speichern]**.
