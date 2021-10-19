---
description: Verwenden Sie Ad-hoc-Filter in Analysis Workspace.
title: Ad-hoc-Projektfilter
feature: Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: 5877c7a39605f7a5ce1f84673dbd4123762ccc61
workflow-type: ht
source-wordcount: '370'
ht-degree: 100%

---

# Ad-hoc-Projektfilter

Im Folgenden finden Sie ein Video zum Erstellen von Ad-hoc-Projektfiltern:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Sie können Ad-hoc-Projektfilter erstellen, wenn Sie schnell untersuchen möchten, wie sich ein Filter auf Ihr Projekt auswirken könnte, ohne den Segment Builder aufzurufen. Stellen Sie sich diese Filter als temporäre Filter auf Projektebene vor. Sie sind normalerweise nicht wie die Komponentenfilter in der linken Leiste Teil Ihrer Filter-„Bibliothek“. Sie können sie jedoch speichern, wie unten dargestellt.

Einen Vergleich zwischen Ad-hoc-Projektfiltern und vollständigen Filtern auf Komponentenebene finden Sie [hier](/help/components/filters/filters-overview.md).

1. Legen Sie einen beliebigen Komponententyp (Dimension, Dimensionselement, Ereignis, Metrik, Filter, Filtervorlage, Datumsbereich) in die Ablagezone für Filter oben in einem Bedienfeld ab. Komponententypen werden automatisch in Filter umgewandelt.
Im Folgenden finden Sie ein Beispiel für die Erstellung eines Filters für die Twitter-Referrer-Domain:

   ![](assets/ad-hoc1.png)

   In Ihrem Bedienfeld wird dieser Filter automatisch angewendet und Sie können die Ergebnisse sofort sehen.

1. Sie können einem Bedienfeld eine unbegrenzte Anzahl von Komponenten hinzufügen.
1. Wenn Sie diesen Filter speichern möchten, lesen Sie den folgenden Abschnitt.

Bitte beachten Sie:

* Folgende Komponenten können Sie **nicht** im Filterbereich ablegen: berechnete Metriken und Dimensionen/Metriken, aus denen Sie keine Filter erstellen können.
* Bei vollständigen Dimensionen und Ereignissen erstellt Analysis Workspace Hit-Filter mit „vorhanden“. Beispiele: `Hit where eVar1 exists` oder `Hit where event1 exists`.
* Wenn „nicht angegeben“ oder „keine“ im Filterablagebereich abgelegt werden, werden sie automatisch in einen Filter mit „nicht vorhanden“ umgewandelt, damit sie beim Filtern korrekt behandelt werden.

>[!NOTE]
>
>Auf diese Weise erstellte Segmente sind interne Segmente des Projekts.

## Speichern von Ad-hoc-Projektfiltern {#ad-hoc-save}

Sie können wie folgt vorgehen, um diese Filter zu speichern:

1. Bewegen Sie den Mauszeiger auf den Filter in der Dropzone und klicken Sie auf das Symbol „i“.
1. Klicken Sie im angezeigten Informationsfenster auf **[!UICONTROL Speichern]**.

   ![](assets/segment-info.png)

## Was sind reine Projektfilter?

Reine Projektfilter sind entweder Schnellfilter oder Ad-hoc-Workspace-Projektfilter. Wenn Sie sie im Filtergenerator bearbeiten/öffnen, wird das Feld für reine Projektfilter angezeigt. Wenn sie einen Schnellfilter im Generator ANWENDEN, aber nicht Kontrollkästchen „Verfügbar machen“ nicht aktivieren, ist dieser Filter weiterhin ein reiner Projektfilter, kann jedoch nicht mehr im QS-Builder geöffnet werden. Wenn sie das Kontrollkästchen aktivieren und SPEICHERN, ist es jetzt ein Komponentenlistenfilter.
