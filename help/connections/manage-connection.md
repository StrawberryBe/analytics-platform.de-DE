---
title: Verbindungen verwalten
description: Beschreibt das Verwalten von Verbindungen zu Platform-Datensätzen.
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 23%

---


# Verbindungen verwalten

Nachdem Sie eine oder mehrere Verbindungen erstellt haben, können Sie diese im Manager [!UICONTROL Verbindungen] verwalten. Sie können

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
   | [!UICONTROL Löschen] | Durch das Löschen einer Verbindung wird der Datensatz nicht gelöscht, da sich die Daten noch in [!DNL Adobe Experience Platform] befinden. Siehe &quot;Löschen von Verbindungen&quot;weiter unten. |
   | [!UICONTROL Umbenennen] | Sie können die Verbindung mit einem beschreibenden Namen umbenennen. |
   | [!UICONTROL Ansicht &quot;Daten erstellen&quot;] | Über diesen Link gelangen Sie zum [Generator für Datenansichten](/help/data-views/create-dataview.md). |
   | [!UICONTROL Beginn- oder Stopp-Datenstreaming] | &quot;Streaming&quot;bedeutet, dass, wenn neue Stapel zu einem Datensatz in der Verbindung hinzugefügt werden, diese neuen Daten zum Berichte in [!UICONTROL Customer Journey Analytics] eingebracht werden. |

## Verbindungen löschen

| Was ist, wenn ich... | Dies geschieht |
| --- | --- |
| Löschen Sie eine Verbindung in [!UICONTROL Customer Journey Analytics]? | Eine Fehlermeldung weist darauf hin, dass<ul><li>Für die gelöschte Verbindung erstellte Ansichten funktionieren nicht mehr.</li><li> Ebenso funktionieren alle Workspace-Projekte, die von den Ansichten der gelöschten Verbindung abhängig sind, nicht mehr.</li></ul> |
| Löschen Sie einen Datensatz in [!UICONTROL Adobe Experience Platform]? | Durch das Löschen eines Datensatzes in AEP wird der Datenfluss von diesem Datensatz zu allen Verbindungen, die diesen Datensatz enthalten, gestoppt. Daten aus diesem Datensatz werden nicht automatisch aus den zugehörigen CJA-Verbindungen gelöscht. |
| Löschen Sie einen Datensatz in [!UICONTROL Customer Journey Analytics]? | Derzeit ist es nicht möglich, einen Datensatz in einer gespeicherten Verbindung zu löschen. Sie müssen die gesamte Verbindung und den Beginn löschen. (Sie können einen Datensatz jedoch unter [!UICONTROL Adobe Experience Platform] löschen.) |
| Stapel aus einem Datensatz löschen (in [!UICONTROL Adobe Experience Platform])? | Wenn ein Stapel aus einem [!UICONTROL Adobe Experience Platform]-Datensatz gelöscht wird, wird derselbe Stapel aus allen [!UICONTROL Customer Journey Analytics]-Verbindungen entfernt, die diesen spezifischen Stapel enthalten. [!UICONTROL Customer Journey ] Analyticsis benachrichtigt über Stapel, die in  [!UICONTROL Adobe Experience Platform] gelöscht wurden. |
| Löschen Sie einen Stapel **während er in [!UICONTROL Customer Journey Analytics] aufgenommen wird?** | Wenn der Datensatz nur einen Stapel enthält, werden keine Daten oder Teildaten aus diesem Stapel in [!UICONTROL Customer Journey Analytics] angezeigt. Die Erfassung wird rückgängig gemacht. Wenn der Datensatz beispielsweise 5 Stapel enthält und 3 davon bereits beim Löschen des Datensatzes aufgenommen wurden, werden die Daten aus diesen 3 Stapeln in [!UICONTROL Customer Journey Analytics] angezeigt. |
