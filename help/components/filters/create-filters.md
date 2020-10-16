---
title: Filter erstellen
description: Machen Sie sich mit der Benutzeroberfläche zur Filtererstellung vertraut.
translation-type: tm+mt
source-git-commit: 21bf268600c12dbf1db24dbc10028a0c29fc48a7
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 100%

---


# Filter erstellen

Der Filtergenerator bietet eine Arbeitsfläche zum Ziehen und Ablegen von Metriken, Dimensionen, Filtern und Ereignissen für das Filtern von Besuchern anhand von Container-Hierarchielogik, Regeln und Operatoren. Mit diesem integrierten Entwicklungstool können Sie einfache oder komplexe Filter erstellen und speichern, mit deren Hilfe Besucherattribute und Aktionen bei Besuchen und Seitenaufrufen identifiziert werden.

Sie können sofort Filter erstellen, indem Sie einen beliebigen Komponententyp (Dimension, Dimensionselement, Ereignis, Metrik, Segment, Segmentvorlage, Datenreichweite) in die Ablagefläche für Segmente oben in einem Bereich ablegen.

Komponententypen werden automatisch in Filter umgewandelt. Alternativ können Sie auf das „+“-Symbol im Ablagefeld **[!UICONTROL Filter hinzufügen]** klicken.

Bedenken Sie Folgendes:

* Folgende Komponenten können Sie **nicht** im Filterbereich ablegen: berechnete Metriken und Dimensionen/Metriken, aus denen Sie keine Filter erstellen können.
* Bei vollständigen Dimensionen und Ereignissen erstellt Analysis Workspace Hit-Filter mit „vorhanden“. Beispiele: „Hit, wenn eVar1 vorhanden ist“ oder „Hit, wenn event1 vorhanden ist“.
* Wenn „nicht angegeben“ oder „keine“ im Filterablagebereich abgelegt werden, werden sie automatisch in einen Filter mit „nicht vorhanden“ umgewandelt, damit sie korrekt behandelt werden.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Auf diese Weise erstellte Filter sind interne Filter des Projekts.

Sie können diese Filter wie folgt öffentlich (global) machen:

1. Bewegen Sie den Mauszeiger auf den Filter in der Dropzone und klicken Sie auf das Symbol „i“.
1. Klicken Sie dann im angezeigten Informationsfeld auf **[!UICONTROL Als öffentlich einstellen]**.

   ![](assets/segment-info.png)

## Andere Methoden, um Filter anzuwenden

Es gibt verschiedene weitere Methoden für das Anwenden von Filtern auf ein Projekt:

| Aktion | Beschreibung |
|--- |--- |
| Filter aus Auswahl erstellen | Erstellen Sie einen Inline-Filter. Wählen Sie Zeilen aus, klicken Sie mit der rechten Maustaste auf die Auswahl und erstellen Sie einen Inline-Filter. Dieser Filter wird nur auf das geöffnete Projekt angewendet und nicht als CJA-Filter gespeichert. 1. Zeilen auswählen.  2. Rechtsklick auf die Auswahl.  3. Klick auf *Filter aus Auswahl erstellen*. |
| Komponenten > Neuer Filter | Zeigt den Filter Builder an. Weitere Informationen zur Filterung finden Sie unter [Filter Builder](https://docs.adobe.com/content/help/de-DE/analytics/components/segmentation/segmentation-workflow/seg-build.html). |
| „Freigeben“ > „Projekt freigeben“ oder „Freigeben“ > „Projektdaten kuratieren“ | In [Kuratieren und freigeben](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6) werden Filter, die Sie auf das Projekt anwenden, in freigegebenen Analysen für den Empfänger verfügbar. |
| Filter als Dimensionen verwenden | Video: Verwenden von Filtern als Dimensionen in Analysis Workspace |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
