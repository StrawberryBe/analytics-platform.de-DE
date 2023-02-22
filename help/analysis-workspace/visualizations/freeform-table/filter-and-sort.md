---
description: Dokumentation, in der beschrieben wird, wie Tabellen in Analysis Workspace gefiltert und sortiert werden.
title: Tabellen filtern und sortieren
feature: Visualizations
exl-id: 3af637ec-bb6c-49b7-a7b3-e1d310e71101
source-git-commit: 43c8af6f9010354258a702fb702a330873d9cb8e
workflow-type: ht
source-wordcount: '692'
ht-degree: 100%

---

# Tabellen filtern und sortieren

Freiformtabellen in Analysis Workspace bilden die Grundlage für die interaktive Datenanalyse. Daher können sie Tausende von Informationszeilen enthalten. Das Filtern und Sortieren der Daten kann ein wichtiger Teil der effizienten Aufdeckung der wichtigsten Informationen sein.

<!--The following video covers filter and sort options in Analysis Workspace, in addition to pagination options:

>[!VIDEO](https://video.tv.adobe.com/v/23968)-->

## Tabellen filtern {#section_36E92E31442B4EBCB052073590C1F025}

Mit Filtern in Analysis Workspace können Sie die wichtigsten Informationen aufdecken.

So filtern Sie Daten in Freiformtabellen:

1. Bewegen Sie in einer Freiformtabelle den Mauszeiger über die Spalte, die die Daten enthält, die Sie filtern möchten. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Klicken Sie auf das **Filter**-Symbol, wenn es angezeigt wird.

   ![Filtersymbol in einer Tabelle](assets/table-filter-icon.png)

1. Geben Sie im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] ein Wort oder eine Phrase an, nach dem bzw. der Sie filtern möchten. Es werden nur Zeilen angezeigt, die das Wort oder die exakte Phrase enthalten.

1. (Optional) Um nach verschiedenen Kriterien oder nach mehreren Kriterien zu filtern, wählen Sie [!UICONTROL **Erweiterte Einstellungen anzeigen**].

   Die folgenden Optionen sind verfügbar

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **Nicht spezifizierte einschließen (keine)**] | Aktivieren Sie diese Option, um Daten in der Tabelle anzuzeigen, die nicht in eine der Dimensionen der Tabelle fallen. <!--what is this?--> |
   | [!UICONTROL **Übereinstimmung**] | <p>Wählen Sie [!UICONTROL **Wenn alle Kriterien erfüllt sind**] aus, um nur Daten anzuzeigen, die alle angegebenen Kriterien erfüllen. Diese Option führt normalerweise zu verfeinerten Daten.</p> <p>Wählen Sie [!UICONTROL **Wenn ein Kriterium erfüllt ist**] aus, um Daten anzuzeigen, die eines der von Ihnen angegebenen Filterkriterien erfüllen. Diese Option führt normalerweise zu weniger verfeinerten Daten.</p> |
   | [!UICONTROL **Kriterien**] | <p>Treffen Sie eine Auswahl aus den folgenden Filteroptionen:</p><p>(Wählen Sie [!UICONTROL **Zeile hinzufügen**] aus, um mehrere Filterkriterien hinzuzufügen. Die Option, die Sie im Abschnitt [!UICONTROL **Übereinstimmung**] auswählen, bestimmt, ob alle oder eines der hinzugefügten Kriterien erfüllt sein müssen.)</p><ul><li><p>[!UICONTROL **Enthält die Phrase**]: Nur Daten, die die von Ihnen angegebene Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen in der Reihenfolge vorliegen, die im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] angegeben ist.<p>Dies ist die Standardeinstellung bei einer einfachen Suche.</p></p></li><li><p>[!UICONTROL **Enthält einen der Begriffe**]: Nur Daten, die ein oder mehrere Wörter aus der von Ihnen angegebenen Wortgruppe enthalten, werden in die gefilterten Ergebnisse aufgenommen. </p></li><li><p>[!UICONTROL **Enthält alle Begriffe**]: Nur Daten, die alle Wörter aus der von Ihnen angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen nicht in der Reihenfolge des Feldes [!UICONTROL **Nach Wort oder Phrase suchen**] vorliegen.</p></li><li><p>[!UICONTROL **Enthält keinen der Begriffe**]: Nur Daten, die keines der Wörter aus der von Ihnen angegebenen Phrase enthalten, werden in die gefilterten Ergebnisse aufgenommen. </p></li><li><p>[!UICONTROL **Enthält nicht die Phrase**]: Nur Daten, die nicht exakt die Phrase enthalten, die Sie angegeben haben, werden in die gefilterten Ergebnisse aufgenommen. Die Wörter müssen in der Reihenfolge vorliegen, die im Feld [!UICONTROL **Nach Wort oder Phrase suchen**] angegeben ist.</p></li><li><p>[!UICONTROL **Gleich**]: Nur Daten, die genau mit der von Ihnen angegebenen Phrase übereinstimmen, werden in die gefilterten Ergebnisse aufgenommen. </p></li><li><p>[!UICONTROL **Ist nicht gleich**]: Nur Daten, die nicht genau mit der von Ihnen angegebenen Phrase übereinstimmen, werden in die gefilterten Ergebnisse aufgenommen. </p></li><li><p>[!UICONTROL **Beginnt mit**]: Nur Daten, die mit dem Wort oder der Phrase beginnen, die Sie angegeben haben, werden in die gefilterten Ergebnisse aufgenommen. </p></li><li><p>[!UICONTROL **Endet in**]: Nur Daten, die mit dem Wort oder der Phrase enden, das bzw. die Sie angegeben haben, werden in die gefilterten Ergebnisse aufgenommen. </p></li></ul> |
   | [!UICONTROL **Elemente immer ausschließen**] | Geben Sie den Namen der Elemente an, die Sie aus den gefilterten Daten ausschließen möchten. |

1. Klicken Sie auf [!UICONTROL **Anwenden**], um die Daten zu filtern.

   Das **Filter**-Symbol ![Blaues Filtersymbol zur Filterung der Tabelle](assets/table-filter-blue-icon.png) wird angezeigt, wenn ein Filter auf die Tabelle angewendet wird.

## Tabellen sortieren

Sie können die Daten einer Freiformtabelle nach jeder Spalte in Analysis Workspace sortieren, die entweder eine Dimension oder eine Metrik ist.

Ein Pfeil-nach-unten-Symbol ![Pfeil nach unten zur Sortierung einer Tabellenspalte](assets/table-sort-arrow-icon.png) ist in der Kopfzeile der Spalte sichtbar, nach der die Daten derzeit sortiert sind.

1. Klicken Sie in einer beliebigen Freiformtabelle in Analysis Workspace auf den Pfeil neben dem Namen der Dimension oder der Metrik.

   Beachten Sie beim Sortieren Folgendes:

   * Der Nach-unten-Pfeil sortiert in absteigender Reihenfolge und der Nach-oben-Pfeil (Standard) in aufsteigender Reihenfolge.
   * Sie können Dimensionen alphabetisch oder numerisch sortieren. Beispielsweise können Sie in einem Workflow nummerierte Schritte verwenden und nach der Schrittnummer sortieren. Eine datumsbezogene Dimension kann nach Datum sortiert werden. Oder Sie können, wie in der folgenden Abbildung, Datenquellen alphabetisch sortieren.

   ![](assets/sort-dimensions.png)


