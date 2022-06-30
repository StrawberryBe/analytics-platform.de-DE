---
title: Filter erstellen
description: Machen Sie sich mit der Benutzeroberfläche zur Filtererstellung vertraut.
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
source-git-commit: 7013237e11cb173d54dcbe236967b49d89810975
workflow-type: ht
source-wordcount: '371'
ht-degree: 100%

---

# Filter erstellen

Der Filtergenerator bietet eine Arbeitsfläche zum Ziehen und Ablegen von Metriken, Dimensionen, Filtern und Ereignissen für das Filtern von Besuchern anhand von Container-Hierarchielogik, Regeln und Operatoren. Mit diesem integrierten Entwicklungstool können Sie einfache oder komplexe Filter erstellen und speichern, mit deren Hilfe Besucherattribute und Aktionen bei Besuchen und Seitenaufrufen identifiziert werden.

Sie können unmittelbar Filter erstellen, indem Sie einen beliebigen Komponententyp (Dimension, Dimensionselement, Ereignis, Metrik, Filter, Filtervorlage, Datumsbereich) in die Ablagezone für Filter oben in einem Bedienfeld ablegen.

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
| --- | --- |
| Filter aus Auswahl erstellen | Erstellen Sie einen Inline-Filter. Dieser Filter wird nur auf das geöffnete Projekt angewendet und nicht als CJA-Filter gespeichert.<p> 1. Die Tabellenzeilen auswählen, die Teil des Filters sein sollen. 2. Rechtsklick auf die Auswahl.  3. Klick auf *Filter aus Auswahl erstellen*. |
| Arbeitsbereich [!UICONTROL Komponenten] > [!UICONTROL Neuer Filter] | Zeigt den Filter Builder an. Weitere Informationen zur Filterung finden Sie unter [Filter Builder](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=de). |
| „Freigeben“ > „Projekt freigeben“ oder „Freigeben“ > „Projektdaten kuratieren“ | In [Kuratieren und freigeben](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=de#concept_4A9726927E7C44AFA260E2BB2721AFC6) werden Filter, die Sie auf das Projekt anwenden, in freigegebenen Analysen für den Empfänger verfügbar. |
| Filter als Dimensionen verwenden | Siehe das Video unten: Verwenden von Filtern als Dimensionen in Analysis Workspace. |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
