---
title: Verbindungen verwalten
description: Beschreibt das Verwalten von Verbindungen zu Platform-Datensätzen.
translation-type: ht
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: ht
source-wordcount: '400'
ht-degree: 100%

---


# Verbindungen verwalten

Nachdem Sie eine oder mehrere Verbindungen erstellt haben, können Sie diese im [!UICONTROL Verbindungs-Manager] verwalten. Sie können

* eine Verbindung löschen.
* eine Verbindung umbenennen.
* eine Datenschicht aus einer Verbindung erstellen.
* Daten-Streaming starten und beenden.

![Connections Manager](assets/connections-manager.png)

1. Klicken Sie auf die Registerkarte **[!UICONTROL Verbindungen]**.

2. Wählen Sie die Verbindungen aus, die Sie bearbeiten oder verwalten möchten.

3. Führen Sie eine der folgenden Aktionen aus:

   | Aktion | Beschreibung |
   |---|---|
   | [!UICONTROL Löschen] | Durch das Löschen einer Verbindung wird der Datensatz nicht gelöscht, da sich die Daten noch in [!DNL Adobe Experience Platform] befinden. Siehe „Verbindungen löschen“ weiter unten. |
   | [!UICONTROL Umbenennen] | Sie können die Verbindung mit einem beschreibenden Namen umbenennen. |
   | [!UICONTROL Datenansicht erstellen] | Über diesen Link gelangen Sie zum [Generator für Datenansichten](/help/data-views/create-dataview.md). |
   | [!UICONTROL Daten-Streaming starten und beenden] | Mit „Streaming“ ist gemeint, dass, wenn neue Batches zu einem Datensatz in der Verbindung hinzugefügt werden, diese neuen Daten für das Reporting in [!UICONTROL Customer Journey Analytics] herangezogen werden. |

## Verbindungen löschen

| Was ist, wenn ich... | Dies geschieht |
| --- | --- |
| eine Verbindung in [!UICONTROL Customer Journey Analytics] lösche? | Eine Fehlermeldung weist darauf hin, dass<ul><li>für die gelöschte Verbindung erstellte Datenansichten nicht mehr funktionieren.</li><li> Ebenso funktionieren alle Workspace-Projekte nicht mehr, die von den Datenansichten der gelöschten Verbindung abhängig sind.</li></ul> |
| einen Datensatz in [!UICONTROL Adobe Experience Platform] lösche? | Durch das Löschen eines Datensatzes in Adobe Experience Platform wird der Datenfluss von diesem Datensatz zu allen Verbindungen, die diesen Datensatz enthalten, angehalten. Daten aus diesem Datensatz werden nicht automatisch aus zugehörigen Customer Journey Analytics-Verbindungen gelöscht. |
| einen Datensatz in [!UICONTROL Customer Journey Analytics] lösche? | Derzeit ist es nicht möglich, einen Datensatz in einer gespeicherten Verbindung zu löschen. Dazu müssten Sie die gesamte Verbindung löschen und von Neuem beginnen. (Sie können einen Datensatz jedoch in [!UICONTROL Adobe Experience Platform] löschen.) |
| einen Batch aus einem Datensatz (in [!UICONTROL Adobe Experience Platform]) lösche? | Wenn ein Batch aus einem [!UICONTROL Adobe Experience Platform]-Datensatz gelöscht wird, wird derselbe Batch aus allen [!UICONTROL Customer Journey Analytics]-Verbindungen entfernt, die diesen Batch enthalten. [!UICONTROL Customer Journey Analytics] wird über Batches benachrichtigt, die in [!UICONTROL Adobe Experience Platform] gelöscht wurden. |
| einen Batch **lösche, während er** in [!UICONTROL Customer Journey Analytics] aufgenommen wird? | Wenn nur ein Batch im Datensatz vorhanden ist, erscheinen keine Daten oder Teildaten aus diesem Batch in [!UICONTROL Customer Journey Analytics]. Die Aufnahme wird zurückgesetzt. Wenn es beispielsweise 5 Batches im Datensatz gibt und 3 davon beim Löschen des Datensatzes bereits aufgenommen wurden, erscheinen die Daten dieser 3 Batches in [!UICONTROL Customer Journey Analytics]. |
