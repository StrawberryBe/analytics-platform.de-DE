---
description: Verwenden von Ad-hoc-Filtern in Analysis Workspace.
title: Ad-hoc-Projektfilter
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: 6627c8e8f6e88fd93ffaad12b38e5e1dbbc844a8
workflow-type: ht
source-wordcount: '302'
ht-degree: 100%

---

# Ad-hoc-Projektfilter

Mit Ad-hoc-Projektfiltern können Sie beliebige Komponenten direkt in die Ablagefläche des Bedienfelds ziehen, um einen Filter zu erstellen. Der Filter wird zu einem [Filter auf Projektebene](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html?lang=de), der lokal im aktuellen Projekt verwendet werden kann.

Im Folgenden finden Sie ein Video zum Erstellen von Ad-hoc-Projektfiltern:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. Legen Sie einen beliebigen Komponententyp (Dimension, Dimensionselement, Ereignis, Metrik, Segment, Segmentvorlage, Datumsbereich) oben in einem Bedienfeld in der Ablagefläche für Filter ab. Komponententypen werden, sofern kompatibel, automatisch in Ad-hoc-Filter oder [Schnellfilter](/help/components/filters/quick-filters.md) konvertiert.

   Im Folgenden finden Sie ein Beispiel für die Erstellung eines Filters für die Twitter-Referrer-Domain:

   ![](assets/ad-hoc1.png)

   In Ihrem Bedienfeld wird dieser Filter automatisch angewendet und Sie können die Ergebnisse sofort sehen.

1. Sie können einem Bedienfeld eine unbegrenzte Anzahl von Filtern hinzufügen.
1. Wenn Sie diesen Filter speichern möchten, lesen Sie den folgenden Abschnitt.

Bitte beachten Sie:

* Folgende Komponenten können Sie **nicht** im Filterbereich ablegen: berechnete Metriken und Dimensionen/Metriken, aus denen Sie keine Filter erstellen können.
* Bei vollständigen Dimensionen und Ereignissen erstellt Analysis Workspace Hit-Filter mit „vorhanden“. Beispiele: `Hit where eVar1 exists` oder `Hit where event1 exists`.
* Wenn „nicht angegeben“ oder „keine“ im Filterablagebereich abgelegt werden, werden sie automatisch in einen Filter mit „nicht vorhanden“ umgewandelt, damit sie beim Filtern korrekt behandelt werden.

## Speichern von Ad-hoc-Projektfiltern {#ad-hoc-save}

Sie können wie folgt vorgehen, um diese Filter zu speichern:

1. Bewegen Sie den Mauszeiger auf den Filter in der Dropzone und klicken Sie auf das Symbol „i“.
1. Klicken Sie auf den Stift zum Bearbeiten, um zum Filtergenerator zu wechseln.
1. Aktivieren Sie die Option **[!UICONTROL Für alle Projekte verfügbar machen und der Komponentenliste hinzufügen]**.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

Nach dem Speichern ist der Filter in der Komponentenliste der linken Leiste verfügbar und kann über den Filter-Manager für andere Benutzer freigegeben werden.

