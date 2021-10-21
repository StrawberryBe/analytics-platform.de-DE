---
description: 'Durch die Segmentierung einzelner Metriken können Sie Metriken innerhalb eines Berichts vergleichen. '
title: Segmentierte Metriken
uuid: 88f9829b-76e4-4598-9494-084a91602bc1
exl-id: 1e7e048b-9d90-49aa-adcc-15876c864e04
source-git-commit: 0865c318c1390f2ad6d9864915254a7b8f68030f
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 45%

---

# Gefilterte Metriken

Im Generator für berechnete Metriken können Sie Filter innerhalb Ihrer Metrikdefinition anwenden. Dies ist hilfreich, wenn Sie neue Metriken für Ihre Analyse ableiten möchten. Beachten Sie, dass Filterdefinitionen über den Filter-Builder aktualisiert werden können. Wenn Änderungen vorgenommen werden, wird der Filter automatisch an allen Stellen aktualisiert, an denen er angewendet wird, auch wenn er Teil einer Definition für berechnete Metriken ist.

![](assets/german-visitors.png)

## Gefilterte Metrik erstellen {#create}

Angenommen, Sie möchten verschiedene Aspekte eines Filters &quot;Deutsche Besucher&quot;mit denen eines Filters &quot;Internationale Besucher&quot;vergleichen. Dazu können Sie Metriken erstellen, die Einblick in Folgendes ermöglichen:

* Wie sieht das Browsingverhalten im Vergleich zwischen den beiden Gruppen aus? (Ein weiteres Beispiel wäre: Wie unterscheidet sich die Konversionsrate zwischen den beiden Filtern?)
* Wie viele Besucher aus Deutschland navigieren im Vergleich mit internationalen Besuchern zu bestimmten Seiten (als Prozentsatz der Gesamtbesucher)?
* Wo liegen die größten Unterschiede hinsichtlich des Zugriffs auf Inhalte durch diese verschiedenen Filter?

1. Wenn Sie keinen vergleichbaren Filter haben, erstellen Sie direkt im Generator für berechnete Metriken ein Ad-hoc-Segment namens &quot;Deutsche Besucher&quot;, wobei &quot;Länder&quot;gleich &quot;Deutschland&quot;ist. Ziehen Sie die Dimension „Länder“ einfach in die Arbeitsfläche „Definition“ und wählen Sie als Wert „Deutschland“:

   ![](assets/segment-from-dimension.png)

   >[!NOTE]
   >
   >Sie können dies auch im Abschnitt [Filter Builder](/help/components/filters/create-filters.md), aber wir haben den Workflow vereinfacht, indem wir Dimensionen im Generator für berechnete Metriken zur Verfügung gestellt haben. &quot;Ad Hoc&quot;bedeutet, dass das Segment nicht im **[!UICONTROL Filter]** in der linken Leiste. Sie können es aber auch veröffentlichen, indem Sie über das „i“ daneben fahren und auf **[!UICONTROL Als öffentlich einstellen klicken]**.

1. Wenn Sie keinen vergleichbaren Filter haben, erstellen Sie einen Filter namens &quot;Internationale Besucher&quot;, bei dem &quot;Länder&quot;nicht mit &quot;Deutschland&quot;übereinstimmt.
1. Erstellen und speichern Sie eine Metrik namens &quot;Deutsche Besucher&quot;, indem Sie den Filter &quot;Deutschland&quot;in die Arbeitsfläche &quot;Definition&quot;ziehen und die Metrik &quot;Unique Visitors&quot;darin ziehen:

   ![](assets/german-visitors.png)

1. Wiederholen Sie Schritt 3 mit dem Segment „Internationale Besucher“ und der Metrik „Unique Visitors“, um die Metrik „Internationale Besucher“ zu erstellen.
1. Ziehen Sie in Analysis Workspace die Dimension **[!UICONTROL Seite]** in eine Freiform-Tabelle und dann die zwei neuen berechneten Metriken nebeneinander oben in die Tabelle:

   ![](assets/workspace-pages.png)

Im Folgenden finden Sie eine Videoübersicht:

>[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12)

## Prozent der Gesamtmetriken {#percent-total}

Im obigen Beispiel können Sie den Filter mit der Gesamtpopulation vergleichen. Erstellen Sie dazu zwei neue Metriken: „% aller deutschen Besucher“ und „% der Gesamtzahl internationaler Besucher“:

1. Ziehen Sie den Filter Deutsche (oder Internationale) Besucher in die Arbeitsfläche.
1. Ziehen Sie unten einen weiteren Filter für deutsche (oder internationale) Besucher in den Arbeitsbereich. Klicken Sie dieses Mal aber auf das zugehörige Konfigurationssymbol (Zahnrad), um den Metriktyp „Gesamt“ auszuwählen. Das Format sollte „Prozent“ lauten. Der Operator sollte „Geteilt durch“ lauten. Dadurch erhalten Sie die folgende Metrikdefinition:

   ![](assets/cm_metric_total.png)

1. Wenden Sie diese Metrik auf das Projekt an:

   ![](assets/cm_percent_total.png)
