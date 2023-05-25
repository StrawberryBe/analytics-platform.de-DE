---
title: Geführte Analyse – Übersicht
description: Eine Methode zur Datenanalyse in Customer Journey Analytics, mit der Produktteams einfach Berichte und Einblicke generieren können.
source-git-commit: 03f6b0cef6fa4259041a82173acda852d91e06b5
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 1%

---

# Geführte Analyse – Übersicht

{{release-limited-testing}}

Geführte Analyse ist ein Berichtsformat, das es Produktteams ermöglicht, schnell ihre Datenanforderungen selbst zu erfüllen, sodass sie datengesteuerte Produktentscheidungen treffen können. Funktions-Teams können in Echtzeit eine Verbindung herstellen, um diese Berichte zu verwenden und zu verstehen.

Ähnlich wie bei Analysis Workspace- und Mobile-Scorecards verwendet ein Bericht mit einer geführten Analyse Daten aus einer [Datenansicht](../data-views/data-views.md), die Daten in Adobe Experience Platform über einen [Verbindung](../connections/overview.md). Alle in der geführten Analyse erstellten Berichte können nahtlos zur weiteren Recherche an Analysis Workspace übermittelt werden.

Geführte Analyseberichte bieten derzeit drei Analysetypen: [Trichter](analysis-types/funnel.md), [Trends](analysis-types/trends.md)und [Benutzerwachstum](analysis-types/user-growth.md). Jeder dieser Analysetypen verfügt über mehrere Ansichtstypen, die zusätzliche Einblicke in die einzelnen Berichte bieten.

## Bereitstellung

Geführte Analyse ist ein kostenpflichtiges Add-on für Customer Journey Analytics. Wenden Sie sich an Ihr Adobe Account Team, wenn Ihr Unternehmen mit der Verwendung dieser Funktion beginnen möchte.

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
| [Screenshot der Abfrageleiste] | Abfrageleiste | Konfigurieren Sie die gewünschten Komponenten, aus denen ein Bericht besteht. Verschiedene Analysetypen haben mehrere Abfrageoptionen. Wenn zwei Analysetypen Abfrageoptionen gemeinsam nutzen, werden sie beim Wechsel der Analysetypen übernommen. Siehe [Analysetypen](analysis-types/overview.md) für weitere Informationen zu den Abfrageoptionen für die einzelnen Analysetypen. |
| [Screenshot eines Diagramms] | Diagramm | Eine Visualisierung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Welche Visualisierung Sie sehen, hängt vom Ansichtstyp über dem Diagramm ab. Die verfügbaren Ansichtstypen hängen von der [Analysetyp](analysis-types/overview.md) über der Abfrageleiste. |
| [Screenshot der Tabelle] | Tabelle | Eine Tabellendarstellung der zurückgegebenen Daten basierend auf Ihrer Eingabe aus der Abfrageleiste und den Einstellungen. Die Spalten in der Tabelle hängen vom Ansichtstyp über dem Diagramm ab. Die verfügbaren Ansichtstypen hängen von der [Analysetyp](analysis-types/overview.md) über der Abfrageleiste. |
| [Screenshot der Einstellungen] | Einstellungen  | Mehrere Optionen über dem Diagramm ermöglichen es Ihnen, anzupassen, wie das Diagramm und die Tabelle Daten zurückgeben.<ul><li>**Ansichtstyp**: Eine Dropdown-Auswahl, mit der Sie Daten für eine bestimmte [Analysetyp](analysis-types/overview.md) auf eine andere Weise. Jeder Analysetyp hat mindestens zwei Ansichtstypen.</li><li>**Diagrammeinstellungen**: Passen Sie an, wie Ihr Diagramm aussieht und welche Ereignisse Sie verwenden möchten. Die verfügbaren Optionen hängen vom ausgewählten Ansichtstyp ab.</li><li>**Datumsbereich**: Eine Kalenderauswahl, mit der Sie den Datumsbereich des Berichts ermitteln können. Einige Analysetypen ermöglichen auch Intervalle, z. B. täglich, wöchentlich oder monatlich.</li><li>**Insights**: Bietet je nach angezeigtem Bericht kontextbezogene Einblicke. Sie können diese Einblicke mithilfe des Glühbirnensymbols oben rechts ein- oder ausblenden.</li></ul> |
| [Screenshot des Analysemenüs] | Analysemenü | Befehle oben rechts in der geführten Analyse, die übergreifende Aktionen bereitstellen.<ul><li>**Datenansichtsauswahl**: Ändern Sie die Datenansicht, die von dieser Analyse verwendet wird. Wenn Sie die Datenansicht ändern, ändern sich auch die verfügbaren Komponenten in der Abfrageleiste.</li><li>**Speichern**: Speichert die Analyse. Wenn Sie eine neue Analyse speichern, wird ein modales Fenster angezeigt, das einen Namen und eine Beschreibung anfordert.</li><li>**Speichern unter**: Speichert die Analyse getrennt von der aktuellen Analyse und erstellt eine Kopie. Es wird ein modales Fenster angezeigt, das einen neuen Namen und eine neue Beschreibung anfordert.</li><li>**In Workspace öffnen**: Erstellt die aktuelle geführte Analyse in Analysis Workspace erneut. Das Workspace-Projekt wird in einer neuen Registerkarte erstellt, wodurch Unterbrechungen beim Arbeiten mit der geführten Analyse verhindert werden. Verwenden Sie diesen Befehl, wenn die geführte Analyse Ihnen nicht die gewünschte Flexibilität oder spezifische Einblicke bietet. Sie möchten beispielsweise eine [Trends](analysis-types/trends.md) -Bericht verwenden, der Sitzungen für ein Segment und Personen für ein anderes Segment verwendet.</li><li>**PNG herunterladen**: Laden Sie die Diagrammgrafik als `.png`. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li><li>**SVG herunterladen**: Laden Sie die Diagrammgrafik als `.svg`. Die Abfrageleiste und die Tabelle sind nicht in der Grafik enthalten.</li></ul> |

{style="table-layout:auto"}

## Zugriffsberechtigung

Adobe plant, zukünftig spezifische Berechtigungen für die geführte Analyse bereitzustellen.

<!-- Once your organization is provisioned to use Guided analysis, product profile administrators can grant access to it in the Adobe Admin Console.

1. Log in to the [Adobe admin console](https://adminconsole.adobe.com).
1. Select **[!UICONTROL Customer Journey Analytics]** in the list of products.
1. Select the desired product profile to edit permissions.
1. Click the **[!UICONTROL Permissions]** tab, then click **[!UICONTROL Edit]** under [!UICONTROL Reporting Tools].
1. Drag **[!UICONTROL Guided analysis]** from the list of [!UICONTROL Available Permission Items] to the list of [!UICONTROL Included Permission Items].
1. Click **[!UICONTROL Save]**. -->
