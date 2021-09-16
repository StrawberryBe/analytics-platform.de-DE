---
title: Verhaltenskomponenteneinstellungen
description: Geben Sie an, wie sich eine Dimension oder Metrik in Berichten verhält.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 4%

---


# Verhaltenskomponenteneinstellungen

Verhaltenseinstellungen sind sowohl für Dimensionen als auch für Metriken verfügbar. Die verfügbaren Einstellungen hängen vom Komponententyp und Schemadatyp ab.

![Verhaltenseinstellungen](../assets/behavior-settings.png)

## Verhaltenseinstellungen für Dimensionen

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Kleinbuchstaben] | Dedupliziert Zeilen mit demselben Wert, aber unterschiedlicher Groß-/Kleinschreibung. Wenn diese Option aktiviert ist, werden alle Instanzen einer Dimension mit demselben Wert als Kleinbuchstaben gemeldet. Ihre Daten enthalten beispielsweise die Werte `"liverpool"`, `"Liverpool"` und `"LIVERPOOL"` in einer Zeichenfolgendimension. Wenn [!UICONTROL Kleinbuchstaben] aktiviert ist, werden alle drei Werte zu `"liverpool"` kombiniert. Wenn diese Option deaktiviert ist, werden alle drei Werte als getrennt behandelt. |

![Groß-/Kleinschreibung beachten](../assets/case-sens-workspace.png)

>[!NOTE]
>
>Wenn Sie [!UICONTROL Kleinbuchstaben] für eine Lookup-Datensatzdimension aktivieren, können für dieselbe Kennung mehrere Lookup-Werte vorhanden sein. In diesem Fall verwendet CJA den ersten gesammelten ASCII-Wert (Werte in Großbuchstaben vor Kleinbuchstaben). Adobe rät davon ab, Lookup-Datensätze zu verwenden, die denselben Wert enthalten, wenn [!UICONTROL Kleinbuchstaben] aktiviert ist.

## Einstellungen für das Metrikverhalten

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Werte zählen] | Sichtbar bei Datentypen vom Typ Ganzes und Doppeltes Schema . Erhöhen Sie die Metrik um den angegebenen Betrag. Erhöht beispielsweise eine Metrik um 50, wenn der Wert der Spalte `50` lautet. |
| [!UICONTROL Instanzen zählen] | Sichtbar bei Datentypen vom Typ Ganzes und Doppeltes Schema . Erhöhen Sie die Metrik um 1, unabhängig vom Wert. Das Vorhandensein von Werten erhöht die Metrik. Erhöht beispielsweise eine Metrik um 1, wenn der Wert der Spalte `50` lautet. |
| [!UICONTROL Zu zählende Werte] | Sichtbar für boolesche Schemadaten. Ermöglicht Ihnen, zu bestimmen, ob die Metrik durch die Zählung von `true`, `false` oder beidem zunimmt. |

Sie können in Analysis Workspace sowohl die Metrik &quot;Bestellungen&quot;als auch die Metrik &quot;Umsatz&quot;generieren, indem Sie dieselbe Ereignis-Datensatzspalte mit unterschiedlichem Verhalten verwenden. Ziehen Sie die Datensatzspalte &quot;Umsatz&quot;zweimal in die Datenansicht und legen Sie einen auf &quot;Zählerwerte&quot;und den anderen auf &quot;Instanzen zählen&quot;fest. Die Metrik &quot;Bestellungen&quot;zählt Instanzen, während die Metrik &quot;Umsatz&quot;Werte zählt.
