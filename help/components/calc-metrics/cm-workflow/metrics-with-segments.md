---
description: 'Durch die Segmentierung einzelner Metriken können Sie Metriken innerhalb eines Berichts vergleichen. '
title: Segmentierte Metriken
feature: Calculated Metrics
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 100%

---

# Gefilterte Metriken

Im Generator für berechnete Metriken können Sie Filter innerhalb Ihrer Metrikdefinition anwenden. Dies ist hilfreich, wenn Sie neue Metriken für Ihre Analyse ableiten möchten. Denken Sie daran, dass Filterdefinitionen über den Filter Builder aktualisiert werden können. Wenn Änderungen vorgenommen werden, wird der Filter automatisch überall dort aktualisiert, wo er angewendet wurde, auch wenn er Teil einer Definition für berechnete Metriken ist.

![](assets/german-visitors.png)

## Erstellen einer gefilterten Metrik {#create}

Beispiel: Sie möchten verschiedene Aspekte des Filters „Deutsche Besucher“ mit denen des Filters „Internationale Besucher“ vergleichen. Dazu können Sie Metriken erstellen, die Einblick in Folgendes ermöglichen:

* Wie sieht das Browsingverhalten im Vergleich zwischen den beiden Gruppen aus? (Ein weiteres Beispiel wäre: Wie sieht die Konversionsrate im Vergleich zwischen den beiden Filtern aus?)
* Wie viele Besucher aus Deutschland navigieren im Vergleich mit internationalen Besuchern zu bestimmten Seiten (als Prozentsatz der Gesamtbesucher)?
* Wo liegen die größten Unterschiede in Bezug darauf, welcher Inhalt von den verschiedenen Filtern aufgerufen wird?

1. Wenn kein vergleichbarer Filter vorhanden ist, erstellen Sie im Generator für berechnete Metriken einen Ad-hoc-Filter namens „Deutsche Besucher“, bei dem Sie für „Länder“ den Wert „Deutschland“ angeben. Ziehen Sie die Dimension „Länder“ einfach in die Arbeitsfläche „Definition“ und wählen Sie als Wert „Deutschland“:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Sie können diesen Vorgang auch im [Filter Builder](/help/components/filters/create-filters.md) durchführen, aber wir haben den Arbeitsablauf vereinfacht, indem Dimensionen jetzt auch im Generator für berechnete Metriken zur Verfügung stehen. „Ad hoc“ bedeutet, dass das Segment nicht in der Liste der **[!UICONTROL Filter]** in der linken Leiste angezeigt wird. Sie können es aber auch veröffentlichen, indem Sie über das „i“ daneben fahren und auf **[!UICONTROL Als öffentlich einstellen klicken]**.

1. Wenn kein vergleichbarer Filter vorhanden ist, erstellen Sie einen Filter namens „Internationale Besucher“, bei dem Sie für „Länder“ nicht „Deutschland“ angeben.
1. Erstellen und speichern Sie eine Metrik namens „Deutsche Besucher“, indem Sie den Filter „Deutschland“ in die Arbeitsfläche „Definition“ ziehen und dann die Metrik „Unique Visitors“ darauf ziehen:

   ![](assets/german-visitors.png)

1. Wiederholen Sie Schritt 3 mit dem Segment „Internationale Besucher“ und der Metrik „Unique Visitors“, um die Metrik „Internationale Besucher“ zu erstellen.
1. Ziehen Sie in Analysis Workspace die Dimension **[!UICONTROL Seite]** in eine Freiform-Tabelle und dann die zwei neuen berechneten Metriken nebeneinander oben in die Tabelle:

   ![](assets/workspace-pages.png)

Im Folgenden finden Sie eine Videoübersicht:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Prozent der Gesamtmetriken {#percent-total}

Sie können das obige Beispiel fortentwickeln, indem Sie Ihren Filter mit der Gesamtbevölkerung vergleichen. Erstellen Sie dazu zwei neue Metriken: „% aller deutschen Besucher“ und „% der Gesamtzahl internationaler Besucher“:

1. Ziehen Sie den Filter „Deutsche Besucher“ (oder „Internationale Besucher“) auf die Arbeitsfläche.
1. Legen Sie darunter einen weiteren Filter „Deutsche Besucher“ (oder „Internationale Besucher“) ab. Klicken Sie dieses Mal aber auf das zugehörige Konfigurationssymbol (Zahnrad), um den Metriktyp „Gesamt“ auszuwählen. Das Format sollte „Prozent“ lauten. Der Operator sollte „Geteilt durch“ lauten. Dadurch erhalten Sie die folgende Metrikdefinition:

   ![](assets/cm_metric_total.png)

1. Wenden Sie diese Metrik auf das Projekt an:

   ![](assets/cm_percent_total.png)
