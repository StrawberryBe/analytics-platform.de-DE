---
title: Kontextbezogene Sitzungen
description: Einstellungen in einer Datenansicht können Sie zum Definieren kontextbezogener Sitzungen verwenden.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: ht
source-wordcount: '236'
ht-degree: 100%

---


# Kontextbezogene Sitzungen

Kontextbezogene Sitzungen in Datenansichten verändern die Art und Weise, wie Customer Journey Analytics Sitzungen aus den Daten in Ihrer Verbindung berechnet.

Auf der Registerkarte [!UICONTROL Einstellungen] von Datenansichten können Sie eine Sitzung entsprechend dessen definieren, wie Personen mit Ihren digitalen Erlebnissen interagieren. Kontextbezogene Sitzungsdefinitionen sind zerstörungsfrei und verändern die zugrunde liegenden Daten nicht. Sie können mehrere Datenansichten – jede mit ihrer spezifischen kontextbezogenen Sitzungsdefinition – als Grundlage für Ihre Workspace-Projekte einrichten.

So definieren Sie den Kontext einer Sitzung für eine Datenansicht:

1. Wählen Sie **[!UICONTROL Datenansichten]** in der Customer Journey Analytics-Benutzeroberfläche.

1. Erstellen Sie eine neue oder bearbeiten Sie eine vorhandene Datenansicht. Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Datenansicht](create-dataview.md).

1. Wählen Sie die Registerkarte **[!UICONTROL Einstellungen]** aus. Unter [!UICONTROL Sitzungseinstellungen]:

   1. Geben Sie einen Wert für ein **[!UICONTROL Sitzungs-Timeout]** in [!UICONTROL Minute(n)], [!UICONTROL Stunde(n)], [!UICONTROL Tag(en) ] oder [!UICONTROL Woche(n)] ein. Durch das Sitzungs-Timeout ist festgelegt, wie lange eine Sitzung inaktiv sein kann (es treten keine Ereignisse auf), bevor eine neue Sitzung gestartet wird.

   2. Wählen Sie eine Metrik aus der Liste **[!UICONTROL Metrik hier ablegen]** unter [!UICONTROL Neue Sitzung mit einer Metrik starten] aus. Alternativ können Sie per Drag-and-Drop eine Metrik aus dem linken Bereich auf den Bereich **[!UICONTROL Metrik ablegen]** ziehen. Die ausgewählte Metrik definiert den Beginn einer neuen Sitzung. Sie können mehr als eine Metrik definieren.

1. Wählen Sie **[!UICONTROL Speichern]** oder **[!UICONTROL Speichern und beenden]**, um die kontextbezogene Sitzungsdefinition zu speichern.

