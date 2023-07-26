---
title: Kontextbezogene Sitzungen
description: Einstellungen in einer Datenansicht können Sie zum Definieren kontextbezogener Sitzungen verwenden.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 92511d2bedf322097b4d70ccede5ac6e0df7b0c6
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---


# Kontextbezogene Sitzungen

Kontextbezogene Sitzungen in Datenansichten ändern, wie Customer Journey Analytics Sitzungen aus den Daten in Ihrer Verbindung berechnet.

Innerhalb der [!UICONTROL Einstellungen] -Registerkarte von Datenansichten können Sie eine Sitzung auf beliebige Weise definieren, um zu bestimmen, wie Personen mit Ihren digitalen Erlebnissen interagieren. Kontextbezogene Sitzungsdefinitionen sind zerstörungsfrei und ändern die zugrunde liegenden Daten nicht. Sie können mehrere Datenansichten mit jeweils einer spezifischen kontextbezogenen Sitzungsdefinition als Grundlage für Ihre Workspace-Projekte einrichten.

So definieren Sie den Kontext einer Sitzung für eine Datenansicht:

1. Auswählen **[!UICONTROL Datenansichten]** in der Customer Journey Analytics-Benutzeroberfläche.

1. Erstellen Sie eine neue oder bearbeiten Sie eine vorhandene Datenansicht. Siehe [Datenansicht erstellen oder bearbeiten](create-dataview.md) für weitere Informationen.

1. Wählen Sie die **[!UICONTROL Einstellungen]** Registerkarte. Darunter [!UICONTROL Sitzungseinstellungen]:

   1. Geben Sie einen Wert für ein **[!UICONTROL Sitzungs-Timeout]** in [!UICONTROL Minute(n)], [!UICONTROL Stunde(n)], [!UICONTROL Tag(e)]oder [!UICONTROL Woche(n)]. Der Sitzungs-Timeout bestimmt, wie lange eine Sitzung inaktiv sein kann (keine Ereignisse), bevor eine neue Sitzung gestartet wird.

   2. Wählen Sie eine Metrik aus der **[!UICONTROL Metrik hier ablegen]** Liste darunter [!UICONTROL Neue Sitzung mit einer Metrik starten]. Alternativ können Sie eine Metrik aus dem linken Bereich auf die **[!UICONTROL Metrikfeld ablegen]**. Die ausgewählte Metrik definiert den Beginn einer neuen Sitzung. Sie können mehr als eine Metrik definieren.

1. Auswählen **[!UICONTROL Speichern]** oder **[!UICONTROL Speichern und beenden]** , um die kontextbezogene Sitzungsdefinition zu speichern.

