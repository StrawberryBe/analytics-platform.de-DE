---
title: Formatierungs-Komponenteneinstellungen
description: Konfigurieren Sie die Formatierung einer Metrik.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 585242be7ffff5b089d8452d34f7ee012a7d01f5
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 30%

---

# Formatierungs-Komponenteneinstellungen

Mit „Format“ können Sie bestimmen, wie eine bestimmte Metrik angezeigt wird.

![Formateinstellungen](../assets/format-settings.png)

| Einstellung | Beschreibung |
| --- | --- |
| **[!UICONTROL Format]** | Hier können Sie die Formatierung einer Metrik als Dezimal, Zeit, Prozent oder Währung angeben. |
| **[!UICONTROL Dezimalstellen]** | Nicht sichtbar bei Schemadatentypen des Typs „Ganzzahl“. Hier können Sie die Anzahl der Dezimalstellen angeben, die eine Metrik anzeigt. |
| **[!UICONTROL Datum]** | Hiermit können Sie bestimmen, wie das „date-time“-Feld angezeigt werden soll, wenn es als Dimension in Berichten verwendet wird. [Weitere Informationen](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Date-Time]** | Hiermit können Sie bestimmen, wie das „date-time“-Feld angezeigt werden soll, wenn es als Dimension in Berichten verwendet wird. [Weitere Informationen](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Währung]** | Hiermit können Sie festlegen, in welcher Währung die Metrik angezeigt werden soll. Siehe [Währung](#currency) Weitere Informationen. |
| **[!UICONTROL Aufwärts-Trend anzeigen als]** | Hier können Sie angeben, ob bei dieser Metrik ein Aufwärts-Trend gut (grün) oder schlecht (rot) ist. |
| **[!UICONTROL Wert „True“]** und **[!UICONTROL Wert „False“]** | Nur bei booleschen Schemadatentypen sichtbar. Ermöglicht die Anpassung der Bezeichnung des Dimensionselements für die Werte `true` und `false`. |

{style="table-layout:auto"}


## Währung

Wenn Sie **[!UICONTROL Währung]** als [!UICONTROL Format] für eine Metrik können Sie bestimmen, wie Währungen angezeigt und konvertiert werden.

### Währung anzeigen

So zeigen Sie eine Währung für eine Metrik an:

1. Geben Sie die Anzahl der **[!UICONTROL Dezimalstellen]**.

1. Wählen Sie eine Währung aus dem **[!UICONTROL Währung anzeigen in]** Liste.


### Währung umrechnen und anzeigen

So aktivieren Sie die Konvertierung einer Währung für eine oder mehrere Metriken:

- Richten Sie Ihre Customer Journey Analytics-Verbindung so ein, dass sie mindestens einen Ereignis-Datensatz enthält, der eine Währungscode-Dimension für jedes Ereignis enthält, das eine Währungsmetrik enthält. Diese Dimension des Währungscodes verwendet einen alphabetischen Währungscode, der dem [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) Standard für die Darstellung von Währungen. Diese Werte sollten in einem vollständigen Großbuchstabenformat vorliegen, z. B. USD für $, EUR für €, GBP für £.

   1. Wählen Sie die Dimension aus einem Ihrer Datensätze aus, die die Währungscodes enthält. Beispiel: [!UICONTROL Währungscode].

   1. Auswählen **[!UICONTROL Währungscode]** aus der Liste der Dimensionen.

- Wiederholen Sie diese Schritte für den Fall, dass Sie mehr Dimensionen haben, die Währungscodes enthalten, die Sie für die Währungsumrechnung verwenden möchten.

>[!NOTE]
>
>Die Metrik, die Sie für die Währungsumrechnung auswählen, muss einen numerischen Typ aufweisen (Double, Long, Integer, Short, Byte).


So definieren Sie, wie Sie eine Währung für eine Metrik konvertieren und anzeigen:

1. Geben Sie die Anzahl der **[!UICONTROL Dezimalstellen]**.

1. Auswählen **[!UICONTROL Konvertieren der Parallelität]**.

1. Wählen Sie die entsprechende Dimension aus der Liste der Dimensionen aus, die das Währungscode-Feld enthalten.

1. Wählen Sie eine Währung aus dem **[!UICONTROL Währung konvertieren und anzeigen in]** Liste.

### Häufig gestellte Fragen

+++ Wie wird die Währungsumrechnung ausgeführt?

Bei Berichtszeit werden der Wert der Metrik und der ursprüngliche Währungscode in USD konvertiert und dann in die für die Anzeige konfigurierte Währung konvertiert. Für diese Konversion werden die Tageswährungskurse verwendet, die für die Zeit des Ereignisses gelten.

+++


+++ Wie weit sind die täglichen Konversionsraten zurück?

Die täglichen Konversionsraten werden in den letzten vier Jahren beibehalten?

+++


+++ Was passiert, wenn ich kein Währungscode-Feld als Teil meines aktuellen Datenschemas verwende?

Es gibt verschiedene Optionen zum Erstellen eines neuen Währungscode-Felds, einschließlich Datenvorbereitung, Data Distiller und abgeleitete Felder. Data Prep wäre ideal für neue Implementierungen, da dies nur zukünftig möglich wäre. Je nach Einrichtung eines Unternehmens können Data Distiller und abgeleitete Felder verwendet werden, um historisch auf die Währungscodewerte zuzugreifen.

+++

