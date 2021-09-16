---
title: Einstellungen der Attribution-Komponente
description: Hier können Sie die Standardzuordnung für eine Metrik festlegen.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 69%

---


# Einstellungen der Attribution-Komponente

Mit Attribution können Sie ein standardmäßiges Attributionsmodell für eine Metrik festlegen. Sie können das Attributionsmodell einer bestimmten Metrik überschreiben, während Sie in Analysis Workspace arbeiten.

![Attribution](../assets/attribution-settings.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Attribution festlegen] | Aktiviert ein standardmäßiges Attributionsmodell, wenn diese Metrik verwendet wird. Dieser Standard kann in einer [!UICONTROL Freiformtabelle] oder in einer berechneten Metrik überschrieben werden. |
| [!UICONTROL Attributionsmodell] | Hier können Sie angeben, welches standardmäßige [Attributionsmodell](/help/analysis-workspace/attribution/models.md) verwendet werden soll. Die Standardeinstellung ist [!UICONTROL Letztkontakt]. Die Optionen sind: Erstkontakt, Letztkontakt, Linear, Teilnahme, Same Touch, U-Shaped, J Curve, Inverse J, Time Decay, Benutzerdefiniert, Algorithmisch. Einige dieser Optionen erstellen zusätzliche Felder, die ausgefüllt werden müssen, z. B. „Benutzerdefiniert“ oder „Time Decay“. Sie können mehrere Metriken mit demselben Feld erstellen. Dies bedeutet, dass Sie z. B. eine Umsatzmetrik für den [!UICONTROL Letztkontakt] und eine Umsatzmetrik für den [!UICONTROL Erstkontakt] haben können, die jedoch beide auf demselben Umsatzfeld im Schema basieren. |
| [!UICONTROL Lookback-Fenster] | Ermöglicht die Angabe eines standardmäßigen Lookback-Fensters für eine Metrik. Die Optionen sind: [!UICONTROL Person] (Reporting-Fenster), [!UICONTROL Sitzung], [!UICONTROL Benutzerdefiniert]. Wenn [!UICONTROL Benutzerdefiniert] ausgewählt ist, können Sie auch eine beliebige Anzahl von Tagen/Wochen/Monaten usw. auswählen. (bis zu 90 Tage), genau wie [!UICONTROL Attribution IQ]. Sie können über mehrere Metriken verfügen, die dasselbe Schema verwenden, jedoch jeweils ein separates Rückblickfenster. |
