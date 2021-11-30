---
title: Attributions-Komponenteneinstellungen
description: Hier können Sie die Standardattribution für eine Metrik festlegen.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 100%

---

# Attributions-Komponenteneinstellungen

Mit Attribution können Sie ein standardmäßiges Attributionsmodell für eine Metrik festlegen. Sie können das Attributionsmodell einer bestimmten Metrik überschreiben, während Sie in Analysis Workspace arbeiten.

![Attribution](../assets/attribution-settings.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Attribution festlegen] | Aktiviert ein standardmäßiges Attributionsmodell, wenn diese Metrik verwendet wird. Dieser Standard kann in einer [!UICONTROL Freiformtabelle] oder in einer berechneten Metrik überschrieben werden. |
| [!UICONTROL Attributionsmodell] | Hier können Sie angeben, welches standardmäßige [Attributionsmodell](/help/analysis-workspace/attribution/models.md) verwendet werden soll. Die Standardeinstellung ist [!UICONTROL Letztkontakt]. Die Optionen sind: Erstkontakt, Letztkontakt, Linear, Teilnahme, Same Touch, U-Shaped, J Curve, Inverse J, Time Decay, Benutzerdefiniert, Algorithmisch. Einige dieser Optionen erstellen zusätzliche Felder, die ausgefüllt werden müssen, z. B. „Benutzerdefiniert“ oder „Time Decay“. Sie können mehrere Metriken mit demselben Feld erstellen. Dies bedeutet, dass Sie z. B. eine Umsatzmetrik für den [!UICONTROL Letztkontakt] und eine Umsatzmetrik für den [!UICONTROL Erstkontakt] haben können, die jedoch beide auf demselben Umsatzfeld im Schema basieren. |
| [!UICONTROL Lookback-Fenster] | Ermöglicht die Angabe eines standardmäßigen Lookback-Fensters für eine Metrik. Die Optionen sind: [!UICONTROL Person] (Reporting-Fenster), [!UICONTROL Sitzung], [!UICONTROL Benutzerdefiniert]. Wenn [!UICONTROL Benutzerdefiniert] ausgewählt ist, können Sie auch eine beliebige Anzahl von Tagen/Wochen/Monaten usw. auswählen. (bis zu 90 Tage), genau wie [!UICONTROL Attribution IQ]. Sie können über mehrere Metriken verfügen, die dasselbe Schema verwenden, jedoch jeweils ein separates Rückblickfenster. |
