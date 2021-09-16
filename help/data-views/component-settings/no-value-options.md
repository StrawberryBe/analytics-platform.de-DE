---
title: Komponenteneinstellungen für Optionen für Werte
description: Bestimmen Sie, wie eine Dimension verarbeitet werden soll, wenn sie leer ist.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 35%

---


# Komponenteneinstellungen für &quot;No Value Options&quot;

Mit den Optionen &quot;Keine Werte&quot;können Sie festlegen, wie Analysis Workspace Situationen handhabt, in denen ein Ereignis in einem Datensatz eine Metrik enthält, die Dimension jedoch keinen Wert enthielt. Sie können den Namen dieses Dimensionselements auswählen, es vollständig ausblenden oder es sogar als tatsächlichen Wert behandeln.

![Keine Wertoptionen](../assets/no-value-options.png)

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Wenn angezeigt, wird &quot;Kein Wert&quot;aufgerufen.] | Ein Textfeld, mit dem Sie das Dimensionselement **[!UICONTROL Kein Wert]** in etwas Anderes umbenennen können. |
| [!UICONTROL Standardmäßig nicht „Kein Wert“ anzeigen] | Zeigt diesen Wert im Reporting nicht an. Metrikereignisse, die nicht an diese Dimension gebunden sind, sind im Bericht nicht sichtbar. |
| [!UICONTROL Standardmäßig „Kein Wert“ anzeigen] | Zeigt diesen Wert in Berichten an. |
| [!UICONTROL „Kein Wert“ als Wert behandeln] | Ersetzt leere Werte in den Daten durch den Text, den Sie unter [!UICONTROL Wenn angezeigt, rufen Sie &quot;No value&quot;] auf. Wenn Sie beispielsweise Mobilgerätetypen als Dimension haben, können Sie das Element **[!UICONTROL Kein Wert]** in „Desktop“ umbenennen. Wenn Sie dieses Feld in einen benutzerdefinierten Wert ändern, wird der benutzerdefinierte Wert als legitimer Zeichenfolgenwert behandelt. Wenn Sie also z. B. den Wert „Rot“ in dieses Feld eingeben, werden alle Instanzen der Zeichenfolge „Rot“, die in den Daten selbst vorkommen, auch unter demselben von Ihnen angegebenen Zeileneintrag erscheinen. |
