---
title: Filter verwalten
description: schlankes Verwalten von Filtern in Customer Journey Analytics
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Filter verwalten

Der Filter-Manager bietet viele Möglichkeiten zum Kuratieren von Segmenten, wie Freigeben, Taggen, Genehmigen, Kopieren, Löschen und Kennzeichnen als Favoriten.

Der Filter-Manager zeigt Ihnen alle Filter an, deren Inhaber Sie sind und die für Sie freigegeben wurden. Benutzer auf Administratorebene können alle Filter in der Organisation sehen. Diese Übersicht zeigt die Benutzeroberfläche und die Funktionen des Filter-Managers.

Rufen Sie den Filter-Manager auf, indem Sie **[!UICONTROL Customer Journey Analysis]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]** in der oberen Navigation navigieren.

## Filter Manager-Benutzeroberfläche

![](assets/filter-manager-ui.png)

| Nr. | Funktion der Benutzeroberfläche | Beschreibung |
|---|---|---|
| 1 | Werkzeugleiste für die Filterverwaltung | Nachdem Sie einen Filter markiert haben, wird diese Werkzeugleiste angezeigt. Über diese Werkzeugleiste können die meisten Verwaltungsaufgaben erledigt werden. |
| 2 | Kontrollkästchen | Überprüfen Sie einen Filter, um ihn zu verwalten. |
| 4 | Favoriten | Wenn Sie auf den Stern neben einem Filter klicken, wird der Stern gelb dargestellt und kennzeichnet den Filter als Favorit. |
| 5 | Titel und Beschreibung | Wird im Filter Builder bereitgestellt. Um den Titel und die Beschreibung zu bearbeiten, klicken Sie auf den Titel-Link, um zum Filter-Builder zurückzukehren. |
| 6 | Report Suites | Diese Spalte zeigt an, in welcher Report Suite der Filter zuletzt gespeichert wurde. |
| 7 | Inhaber | Gibt an, wem der Filter gehört. Als Nicht-Administrator können Sie nur Filter anzeigen, deren Inhaber Sie sind, oder Filter, die für Sie freigegeben wurden. |
| 8 | Tags (in der Spaltenauswahl nicht aktiviert, weshalb die Spalte nicht angezeigt wird) | Tags, die entweder von Ihnen oder von Personen, die den Filter für Sie freigegeben haben, auf den Filter angewendet wurden. |
| 9 | Freigegeben für | Listet Personen oder Gruppen (nur Administrator) oder Alle (nur Administrator) auf, für die Sie den Filter freigegeben haben. |
| 10 | Änderungsdatum | Zeigt das Datum der letzten Änderung des Filters an. |
| 11 | Spaltenauswahl | (Oben rechts) Hier können Sie auswählen, welche Spalten im Filter-Manager angezeigt werden sollen. |
| 12 | Gemeinsam-Symbol | Gibt an, dass dieser Filter von Ihnen oder für Sie freigegeben wird. |
| 13 | Freigegeben-Symbol | Gibt an, dass dieser Filter von einem Administrator genehmigt wurde. |
| 14 | Weitere Filter | Ermöglicht die Anzeige von Filtern nach Tags, Report Suites, Inhabern und anderen (Alle anzeigen, Meine, Für mich freigegeben, Genehmigt, Favoriten). |

## Planfilter

Wenn Sie für die Planung von Segmenten etwas Zeit aufwenden, verbessern Sie die Chancen, dass diese für Ihre Organisation von Nutzen sein werden und dass deren Anzahl unter Kontrolle bleibt.

* Bedenken Sie die Zielgruppe: Wer wird es benutzen? Für wen werden Sie es freigeben? Welche Personengruppen verwenden diesen Filter und wie sollte ich ihn entsprechend taggen? Dies bedeutet auch eine gute Filterbeschreibung. Die Beschreibung sollte mindestens die folgenden Fragen beantworten:

   * Wofür ist dieser Filter nützlich?

   * Wann sollte ich diesen Filter verwenden?

* Legen Sie den Filterbereich fest. Welcher [Filterbehälter](/help/components/filters/filters-overview.md) stellt den Bereich am besten dar? Benutzen Sie den kleinstmöglichen Behälter.

* Entscheiden Sie, welche Elemente in die Filterdefinition aufgenommen werden sollen und welche Werte.

* Überlegen Sie, wie der Genehmigungsprozess verlaufen soll. Wird eine einzelne Person Filter überprüfen und genehmigen oder wird es sich um eine Ausschussentscheidung handeln?

* Definieren Sie Ihre Filter mit Blick auf eine Filterbibliothek, die es Geschäftsbenutzern ermöglicht, Filterelemente oder Komponenten modular zu stapeln und wiederzuverwenden. Welche „Module“ müssen Sie definieren, um diese Bibliothek zu realisieren?

### Tag-Filter

Im Filter-Manager können Sie diese Filter mit Tags organisieren. Alle Benutzer können Tags für Filter erstellen und eines oder mehrere Tags auf ein Segment anwenden. Sie können Tags jedoch nur für die Filter anzeigen, deren Inhaber Sie sind oder die für Sie freigegeben wurden.

Welche Arten von Tags sollten Sie erstellen? Hier finden Sie einige Vorschläge für nützliche Tags:

* Auf Teamnamen basierende Tags wie Social Marketing, Mobile Marketing

* Projekt-Tags (Analyse-Tags) wie Entrypage-Analyse

* Kategorie-Tags: Männer, Region

* Arbeitsablauf-Tags: Genehmigung ausstehend, kuratiert für (einen bestimmten Geschäftsbereich)

So markieren Sie einen Filter:

1. Markieren Sie im Filter-Manager das Kontrollkästchen neben dem Filter, den Sie taggen möchten. Die Symbolleiste für die Filterverwaltung wird angezeigt.

1. Klicken **[!UICONTROL Tag]** Sie auf und

   * wählen Sie entweder ein vorhandenes Tag aus oder

   * Geben Sie einen neuen Tag-Namen ein und drücken Sie **[!UICONTROL Enter]** die Eingabetaste.

1. Click **[!UICONTROL Tag]** again to tag the segment.

Das Tag wird jetzt in der Spalte „Tags“ angezeigt. (Klicken Sie oben rechts auf das Zahnradsymbol, um Ihre Spalten zu verwalten.)
You can also filter on tags by going to **[!UICONTROL Filters > Tags]**.

### Filter genehmigen

Im Filter-Manager können Sie einen Arbeitsablauf einrichten, der die Genehmigung von Filtern für verschiedene Anwendungsebenen, für bestimmte Abteilungen oder Gruppen und die Übereinstimmung mit Berichterstellungsrichtlinien umfasst.

So kennzeichnen Sie einen Filter als genehmigt:

1. Aktivieren Sie im Filter-Manager das Kontrollkästchen links neben dem Filtertitel.

1. Klicken Sie **[!UICONTROL Approve]** in der Taskleiste für die Filterverwaltung auf .

1. Entscheiden Sie, ob Sie die genehmigten Segmente für Ihre Organisation freigeben möchten.

1. Klicken Sie auf **[!UICONTROL OK]**.

   Beachten Sie das Genehmigungssymbol neben dem Filter in der Liste:

   ![](assets/seg_approved.png)

1. You can also unapprove an approved segment by clicking **[!UICONTROL Unapprove]**.

### Freigeben von Filtern

Je nach Ihren Berechtigungen können Sie Filter für Ihre gesamte Organisation, für Gruppen oder für einzelne Benutzer freigeben.

| Administrator | Nicht-Administrator |
|---|---|
| Kann Filter für alle, für Gruppen und für Benutzer freigeben. Weitere Informationen finden Sie in der Dokumentation [zur](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) Admin-Konsole. | Kann Filter nur für einzelne Benutzer freigeben. |

Wann sollten Sie Filter für das gesamte Unternehmen freigeben und wann nur für eine Gruppe von Benutzern oder Einzelpersonen? Im Folgenden finden Sie einige Best Practices, an denen Sie sich orientieren können:

* Geben Sie als Administrator einen Filter für &quot;Alle&quot;frei, wenn er für das gesamte Unternehmen von Nutzen ist und alle Benutzer ihn problemlos verwenden können. In diesem Fall sollten Sie auch erwägen, ihn zu einem genehmigten Filter zu machen.

* Geben Sie als Administrator einen Filter mit einem bestimmten Produktprofil frei, wenn der Filter für dieses Team einen guten Geschäftswert bietet. Diesen Filtertyp nicht offiziell genehmigen.

* Geben Sie als Administrator oder als einzelner Benutzer einen Filter für andere Personen frei, um einen Filter zu prüfen und zu validieren. Wenn sie sich als nicht nützlich erweist, kann sie verworfen werden. Diesen Filtertyp nicht offiziell genehmigen.

So geben Sie einen Filter frei:

1. Markieren Sie im Filter-Manager das Kontrollkästchen neben dem Filter, den Sie freigeben möchten.

1. Klicken Sie in der Symbolleiste für die Filterverwaltung auf **[!UICONTROL Share]**.

1. Wenn Sie Administrator sind, können Sie Alle oder Gruppen und Benutzer in Ihrer Organisation auswählen. Als Nicht-Administrator sehen Sie nur einzelne Benutzer. Benutzen Sie das Feld Suchen, um nach Gruppen oder Benutzern zu suchen. Klicken Sie auf **[!UICONTROL Share]**. The Shared icon appears next to the filter: ![](assets/share_icon.png)

1. Sie können nach Filtern filtern, die für Sie freigegeben wurden, indem Sie Filter > Weitere Filter > Für mich freigegeben wählen.

### Markieren von Filtern als Favoriten

Das Kennzeichnen von Segmenten als Favoriten bietet eine weitere Möglichkeit, diese für eine einfache Verwendung zu organisieren.

1. Markieren Sie im Filter-Manager den Stern neben dem Filter, den Sie als Favoriten kennzeichnen möchten. Der Stern wird gelb, wenn Sie ihn auswählen.

1. Sie können unter Filter > Weitere Filter > Favoriten nach Favoriten filtern.

