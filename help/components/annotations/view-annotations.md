---
title: Anzeigen von Anmerkungen
description: Anzeigen von Anmerkungen in Workspace.
role: User, Admin
feature: Components
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: b4e65903c720ecd9e684f8b7a764e2ba8f74baed
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 50%

---

# Anzeigen von Anmerkungen

>[!NOTE]
>
>Diese Funktion wird derzeit eingeschränkt getestet.

Anmerkungen werden je nachdem, ob sie sich über einen einzelnen Tag oder einen Datumsbereich erstrecken, etwas unterschiedlich angezeigt.

## Anzeigen von Anmerkungen in Liniendiagrammen oder Tabellen

| Datum | Erscheinungsbild |
| --- | --- |
| **Einzeltag** | ![](assets/single-day.png)<p>Wenn Sie den Mauszeiger über die Anmerkung bewegen, können Sie deren Details anzeigen, sie durch Auswahl des Stiftsymbols bearbeiten oder sie löschen:<p> ![](assets/hover.png) |
| **Datumsbereich** | Das Symbol ändert sich, und wenn Sie den Mauszeiger darüber bewegen, wird der Datumsbereich angezeigt.<p>![](assets/multi-day.png)<p>Wenn Sie sie im Liniendiagramm auswählen, werden die Anmerkungsmetadaten angezeigt und Sie können sie bearbeiten oder löschen:![](assets/multi-hover.png)<p>In einer Tabelle wird an jedem Datum im Datumsbereich ein Symbol angezeigt.<p>![](assets/multi-day-table.png) |
| **Überlappende Anmerkungen** | An Tagen mit mehr als einer Anmerkung wird das Symbol grau dargestellt.<p>![](assets/grey.png)<p>Wenn Sie den Mauszeiger über das graue Symbol bewegen, werden alle überlappenden Anmerkungen angezeigt:<p>![](assets/overlap.png) |

## Anzeigen von Anmerkungen in einem Zusammenfassungsdiagramm

![](assets/ann-summary.png)

## Anzeigen von Anmerkungen in einer PDF-Datei

Da Symbole in einer PDF-Datei nicht auf den Mauszeiger reagieren können, enthält diese Datei (nach dem Export) am unteren Rand eines Bedienfelds Anmerkungen zu Erklärungen. Siehe folgendes Beispiel:

![](assets/ann-pdf.png)

## Anzeigen von Anmerkungen, die nicht auf Daten basieren

Manchmal sind Anmerkungen nicht an ein Datum gebunden, sondern an eine bestimmte Dimension. In diesem Fall werden sie nur in einer Zusammenfassungsanmerkung in der rechten unteren Ecke angezeigt. Siehe folgendes Beispiel:

![](assets/non-date.png)
