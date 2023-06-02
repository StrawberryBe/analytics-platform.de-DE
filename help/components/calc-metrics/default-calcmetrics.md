---
description: Adobe bietet verschiedene berechnete Metriken, die Sie verwenden können. Auf dieser Seite werden diese Metriken und ihre Verwendungszwecke aufgelistet.
title: Standardmäßig berechnete Metriken
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 5e69b1aceb767343882b9cc85c0011bb1593f4af
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 25%

---

# Standardmäßig berechnete Metriken

Customer Journey Analytics bietet die folgenden berechneten Metriken, um die häufigsten Anwendungsfälle abzudecken:

| Name der berechneten Metrik | Beschreibung | Formel |
|---------|----------|---------|
| Startrate der Sitzung | Der Prozentsatz, zu dem ein Dimensionselement beim ersten Ereignis einer Sitzung aufgetreten ist.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die `[Session Starts]` [Standardkomponente](/help/data-views/component-reference.md) in [Datenansicht](/help/data-views/create-dataview.md).</p> | `[Session Starts] / [Sessions]` |
| Besuchszeit pro Person | Die durchschnittliche Zeit, die eine Person mit einem bestimmten Dimensionselement verbracht hat.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die `[Time Spent (seconds)]` [Standardkomponente](/help/data-views/component-reference.md) in [Datenansicht](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Users]` |
| Sitzungen pro Person | Die durchschnittliche Anzahl von Sitzungen pro Person. | `[Sessions] / [Users]` |
| Aufgewendete Zeit pro Sitzung | Die durchschnittliche Zeit, die eine Person pro Sitzung mit einem bestimmten Dimensionselement verbracht hat.<p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die `[Time Spent (seconds)]` [Standardkomponente](/help/data-views/component-reference.md) in [Datenansicht](/help/data-views/create-dataview.md).</p> | `[Time Spent (seconds)] / [Sessions]` |
| Endrate der Sitzung | Der Prozentsatz, zu dem ein Dimensionselement beim letzten Ereignis einer Sitzung aufgetreten ist. <p>Diese berechnete Metrik wird Workspace automatisch hinzugefügt, wenn Sie die `[Session Ends]` [Standardkomponente](/help/data-views/component-reference.md) in [Datenansicht](/help/data-views/create-dataview.md).</p> | `[Session Ends] / [Sessions]` |

{style="table-layout:auto"}
