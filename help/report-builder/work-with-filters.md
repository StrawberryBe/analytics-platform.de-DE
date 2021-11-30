---
title: Verwenden von Filtern in Report Builder in Customer Journey Analytics
description: Beschreibt die Verwendung von Filtern in Report Builder für Customer Journey Analytics
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 100%

---

# Arbeiten mit Filtern in Report Builder

Filter können angewendet werden, wenn Sie einen neuen Datenblock erstellen oder wenn Sie die Option **Datenblock bearbeiten** im Bedienfeld „Befehle“ auswählen.

## Filter auf einen Datenblock anwenden

Um einen Filter auf den gesamten Datenblock anzuwenden, doppelklicken Sie auf einen Filter oder ziehen Sie Filter aus der Komponentenliste in den Bereich „Filter“ der Tabelle.

## Filter auf einzelne Metriken anwenden

Um Filter auf einzelne Metriken anzuwenden, ziehen Sie einen Filter auf eine Metrik in der Tabelle. Sie können auch auf das Symbol **...** rechts neben einer Metrik im Tabellenbereich klicken und dann die **Filtermetrik** auswählen. Um angewendete Filter anzuzeigen, bewegen Sie den Mauszeiger über eine Metrik im Tabellenbereich oder wählen Sie sie aus. Metriken mit angewendeten Filtern zeigen ein Filtersymbol an.

<!-- ![](./assets/image24.png) -->

![](./assets/filter_by.png)

## Schnellbearbeitungs-Filter

Sie können im Bereich „Schnellbearbeitung“ Filter für vorhandene Datenblöcke hinzufügen, entfernen oder ersetzen.

Wenn Sie einen Zellenbereich im Arbeitsblatt auswählen, wird der Link **Filter** im Bereich „Schnellbearbeitung“ eine zusammenfassende Liste der Filter anzeigen, die von den in dieser Auswahl enthaltenen Datenblöcken verwendet werden.

So bearbeiten Sie Filter über das Bedienfeld „Schnellbearbeitung“

1. Wählen Sie einen Zellenbereich aus einem oder mehreren Datenblöcken aus.

   ![](./assets/select_multiple_dbs.png)

1. Klicken Sie auf den Link „Filter“, um das Bedienfeld „Schnellbearbeitung – Filter“ zu öffnen.

   ![](./assets/quick_edit_filters.png)

### Hinzufügen oder Entfernen eines Filters

Mithilfe der Optionen „Hinzufügen“/„Entfernen“ können Sie Filter hinzufügen oder entfernen.

1. Wählen Sie die Registerkarte **Hinzufügen/Entfernen** im Bedienfeld „Schnellbearbeitungsfilter“ aus.

   Alle auf die ausgewählten Datenblöcke angewendeten Filter werden im Bedienfeld „Schnellbearbeitungsfilter“ aufgeführt. Filter, die auf alle Datenblöcke in der Auswahl angewendet werden, werden unter der Überschrift **Auf alle ausgewählten Datenblöcke angewendet** gelistet. Filter, die auf einige, aber nicht alle Datenblöcke angewendet werden, werden unter der Überschrift **Auf einen oder mehrere ausgewählte Datenblöcke angewendet** gelistet.

   Wenn in den ausgewählten Datenblöcken mehrere Filter vorhanden sind, können Sie mithilfe des Suchfelds **Filter hinzufügen** nach konkreten Filtern suchen.

   ![](./assets/add_filter.png)

1. Fügen Sie Filter hinzu, indem Sie Filter aus dem Dropdown-Menü **Filter hinzufügen** auswählen.

   Die Liste durchsuchbarer Filter enthält alle Filter, die für die Datenansichten, die in einem oder mehreren der ausgewählten Datenblöcke vorhanden sind, zugänglich sind, sowie alle Filter, die in der Organisation global verfügbar sind.

   Durch Hinzufügen eines Filters wird der Filter auf alle Datenblöcke in der Auswahl angewendet.

1. Um Filter zu entfernen, klicken Sie auf das Löschsymbol **x** rechts neben den Filtern in der Liste **Angewendete Filter**.

1. Klicken Sie auf **Anwenden**, um Änderungen zu speichern und zum Hub-Bedienfeld zurückzukehren.

   Report Builder zeigt eine Meldung zur Bestätigung der angewendeten Filteränderungen an.

### Filter ersetzen

Sie können einen vorhandenen Filter durch einen anderen Filter ersetzen, um zu ändern, wie die Daten gefiltert werden.

1. Wählen Sie die Registerkarte **Ersetzen** im Bedienfeld „Schnellbearbeitungsfilter“.

   ![](./assets/replace_filter.png)

1. Suchen Sie mithilfe des Suchfelds **Suchliste** nach bestimmten Filtern.

1. Wählen Sie einen oder mehrere Filter aus, die Sie ersetzen möchten.

1. Suchen Sie im Feld „Ersetzen durch“ nach einem oder mehreren Filtern.

   Wenn Sie einen Filter auswählen, wird dieser der Liste **Ersetzen durch**... hinzugefügt.

   ![](./assets/replace_screen_new.png)

1. Klicken Sie auf **Anwenden**.

   Report Builder aktualisiert die Filterliste entsprechend der Ersetzung.
