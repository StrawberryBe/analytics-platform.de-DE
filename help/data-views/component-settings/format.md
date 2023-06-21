---
title: Formatierungs-Komponenteneinstellungen
description: Konfigurieren Sie die Formatierung einer Metrik.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5c6e7c51369b451ac0efdcead86f71e38bd3a853
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 33%

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

2. Wählen Sie eine Währung aus dem **[!UICONTROL Währung anzeigen in]** Liste.


### Währung umrechnen und anzeigen

So aktivieren Sie die Konvertierung einer Währung für eine Metrik:

- Richten Sie Ihre Customer Journey Analytics-Verbindung so ein, dass sie mindestens einen Ereignis-Datensatz enthält, der eine Währungscode-Dimension für jedes Ereignis enthält, das eine Währungsmetrik enthält. Diese Dimension des Währungscodes verwendet einen alphabetischen Währungscode, der dem [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) Standard für die Darstellung von Währungen. Zum Beispiel USD für $, EUR für €, GBP für £.

- Sie haben (optional) die [!UICONTROL Währungscode] -Kontextbezeichnung zu einer oder mehreren Dimensionen, die in Ihrem Datensatz verfügbare Währungscodes definieren.

  So wenden Sie die [!UICONTROL Währungscode] -Kontextbezeichnung in der [!UICONTROL Komponenten] Registerkarte Ihrer Datenansicht:

  <!--![Currency Context Label](../assets/currency-context-label.png)-->

   1. Wählen Sie die Dimension aus einem Ihrer Datensätze aus, die die Währungscodes enthält. Beispiel: [!UICONTROL Währungscode].

   2. Auswählen **[!UICONTROL Währungscode]** von [!UICONTROL Kontextbezeichnungen] Liste.

  Wiederholen Sie diese Schritte für den Fall, dass Sie mehr Dimensionen haben, die Währungscodes enthalten, die Sie für die Währungsumrechnung verwenden möchten.

>[!NOTE]
>
>Die Metrik, die Sie für die Währungsumrechnung auswählen, muss einen numerischen Typ aufweisen (Double, Long, Integer, Short, Byte).


So definieren Sie, wie Sie eine Währung für eine Metrik konvertieren und anzeigen:

1. Geben Sie die Anzahl der **[!UICONTROL Dezimalstellen]**.

2. Auswählen **[!UICONTROL Konvertieren der Parallelität]**.

3. Basierend auf der angewendeten Kontextbeschriftung wird die entsprechende Dimension aus dem **[!UICONTROL Währungs-Code-Dimension]** automatisch ausgewählt wird. Sie können eine beliebige andere Dimension auswählen, einschließlich Dimensionen, auf die Sie zusätzlich die Kontextbeschriftung Währungscode angewendet haben.

4. Wählen Sie eine Währung aus dem **[!UICONTROL Währung konvertieren und anzeigen in]** Liste.

### Häufig gestellte Fragen

+++ Wie wird die Währungsumrechnung ausgeführt?

Bei Berichtszeit werden der Wert der Metrik und der ursprüngliche Währungscode in USD konvertiert und dann in die für die Anzeige konfigurierte Währung konvertiert. Für diese Konversion werden die Tageswährungskurse verwendet, die für die Zeit des Ereignisses gelten.

+++

