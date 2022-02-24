---
title: Auswirkungen des Löschens
description: Das passiert, wenn Sie Verbindungen, Datensätze oder Stapel in Customer Journey Analytics oder Adobe Experience Platform löschen.
exl-id: a89694c9-0909-440e-939c-b245fc4dd6bf
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '339'
ht-degree: 100%

---

# Auswirkungen des Löschens

Beachten Sie Folgendes, bevor Sie Verbindungen, Datensätze oder Stapel in Customer Journey Analytics oder Adobe Experience Platform löschen:

| Wenn Sie... | Auswirkung |
| --- | --- |
| Löschen einer Verbindung in [!UICONTROL Customer Journey Analytics] | Eine Fehlermeldung weist darauf hin, dass<ul><li>für die gelöschte Verbindung erstellte Datenansichten nicht mehr funktionieren.</li><li> Ebenso funktionieren alle Arbeitsbereich-Projekte nicht mehr, die von den Datenansichten der gelöschten Verbindung abhängig sind.</li></ul> |
| Löschen eines Datensatzes in [!UICONTROL Adobe Experience Platform] (AEP) | Durch das Löschen eines Datensatzes in Adobe Experience Platform wird der Datenfluss von diesem Datensatz zu allen Verbindungen, die diesen Datensatz enthalten, angehalten. Daten aus diesem Datensatz werden nicht automatisch aus zugehörigen Customer Journey Analytics-Verbindungen gelöscht. |
| Löschen eines Datensatzes in [!UICONTROL Customer Journey Analytics] | Derzeit ist es nicht möglich, einen Datensatz in einer gespeicherten Verbindung zu löschen. Dazu müssten Sie die gesamte Verbindung löschen und von Neuem beginnen. (In [!UICONTROL Adobe Experience Platform] können Sie jedoch einen Datensatz löschen.) |
| Löschen von einem Batch aus einem Datensatz (in [!UICONTROL Adobe Experience Platform]) | Wenn ein Batch aus einem [!UICONTROL Adobe Experience Platform]-Datensatz gelöscht wird, wird derselbe Batch aus allen [!UICONTROL Customer Journey Analytics]-Verbindungen entfernt, die diesen Batch enthalten. [!UICONTROL Customer Journey Analytics] wird über Batches benachrichtigt, die in [!UICONTROL Adobe Experience Platform] gelöscht wurden. |
| Löschen von einem Batch, **während er** in [!UICONTROL Customer Journey Analytics] aufgenommen wird | Wenn in dem Datensatz nur ein Batch vorhanden ist, erscheinen keine Daten oder nur teilweise Daten aus diesem Batch in [!UICONTROL Customer Journey Analytics]. Die Aufnahme wird zurückgesetzt. Wenn es in dem Datensatz beispielsweise 5 Batches gibt und 3 davon bereits aufgenommen wurden, als der Datensatz gelöscht wurde, erscheinen die Daten dieser 3 Batches in [!UICONTROL Customer Journey Analytics]. |
| Löschen von Lookup-Datensätzen in [!UICONTROL Adobe Experience Platform] | Das Löschen von Datensätzen ist zwar für andere Quell-Connectoren möglich, wird aber derzeit für den [Analytics Classifications Data-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/classifications.html?lang=de) nicht unterstützt. Wenn Sie einen Datensatz versehentlich löschen, wenden Sie sich an die Kundenunterstützung von Adobe. |
