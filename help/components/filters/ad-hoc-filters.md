---
description: Verwenden Sie Ad-hoc-Filter in Analysis Workspace.
title: Ad-hoc-Projektfilter
feature: Workspace Basics
role: User, Admin
source-git-commit: 275c552b14a4c2a47e00d0600ac3eae6811beae9
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 17%

---


# Ad-hoc-Projektfilter

Im Folgenden finden Sie ein Video zum Erstellen von Ad-hoc-Projektfiltern:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Sie können Ad-hoc-Projektfilter erstellen, wenn Sie schnell untersuchen möchten, wie sich ein Filter auf Ihr Projekt auswirken könnte, ohne den Segment Builder aufzurufen. Stellen Sie sich diese Filter als temporäre Filter auf Projektebene vor. Sie sind normalerweise nicht wie Komponentenfilter in der linken Leiste Teil Ihrer Filter-&quot;Bibliothek&quot;. Sie können sie jedoch speichern, wie unten dargestellt.

Einen Vergleich dessen, was Ad-hoc-Projektfilter gegenüber ausgefeilten Filtern auf Komponentenebene können, finden Sie unter [hier](/help/components/filters/filters-overview.md).

1. Ziehen Sie einen beliebigen Komponententyp (Dimension, Dimensionselement, Ereignis, Metrik, Filter, Filtervorlage, Datumsbereich) in die Filter-Dropzone oben im Bedienfeld. Komponententypen werden automatisch in Filter umgewandelt.
Im Folgenden finden Sie ein Beispiel für die Erstellung eines Filters für die Twitter-Referrer-Domäne:

   ![](assets/ad-hoc1.png)

   In Ihrem Bedienfeld wird dieser Filter automatisch angewendet und Sie können die Ergebnisse sofort sehen.

1. Sie können einem Bedienfeld eine unbegrenzte Anzahl von Komponenten hinzufügen.
1. Wenn Sie diesen Filter speichern möchten, lesen Sie den folgenden Abschnitt.

Bitte beachten Sie:

* Folgende Komponenten können Sie **nicht** im Filterbereich ablegen: berechnete Metriken und Dimensionen/Metriken, aus denen Sie keine Filter erstellen können.
* Bei vollständigen Dimensionen und Ereignissen erstellt Analysis Workspace Hit-Filter mit „vorhanden“. Beispiele: `Hit where eVar1 exists` oder `Hit where event1 exists`.
* Wenn &quot;nicht angegeben&quot;oder &quot;keine&quot;in der Filter-Dropzone abgelegt werden, wird sie automatisch in einen Filter &quot;nicht vorhanden&quot;umgewandelt, damit sie beim Filtern korrekt behandelt wird.

>[!NOTE]
>
>Auf diese Weise erstellte Segmente sind interne Segmente des Projekts.

## Speichern von Ad-hoc-Projektfiltern {#ad-hoc-save}

Sie können diese Filter wie folgt speichern:

1. Bewegen Sie den Mauszeiger auf den Filter in der Dropzone und klicken Sie auf das Symbol „i“.
1. Klicken Sie im angezeigten Informationsfeld auf **[!UICONTROL Speichern]**.

   ![](assets/segment-info.png)

## Was sind reine Projektfilter?

Nur-Projekt-Filter sind entweder Schnellfilter oder Ad-hoc-Workspace-Projektfilter. Wenn Sie sie im Filter-Builder bearbeiten/öffnen, wird das Feld &quot;Nur Projekt&quot;angezeigt. Wenn sie einen Schnellfilter im Builder anwenden, aber nicht das Kontrollkästchen &quot;Verfügbar machen&quot;aktivieren, ist dieser Filter weiterhin nur Projekt, kann jedoch nicht mehr im QS-Builder geöffnet werden. Wenn sie das Kontrollkästchen aktivieren und SPEICHERN, ist es jetzt ein Komponentenlistenfilter.