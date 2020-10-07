---
title: Filter erstellen
description: Machen Sie sich mit der Benutzeroberfläche zur Filtererstellung vertraut.
translation-type: tm+mt
source-git-commit: 21bf268600c12dbf1db24dbc10028a0c29fc48a7
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 33%

---


# Filter erstellen

Der Filtergenerator bietet eine Arbeitsfläche zum Ziehen und Ablegen von Metriken, Dimensionen, Filtern und Ereignissen für das Filtern von Besuchern anhand von Container-Hierarchielogik, Regeln und Operatoren. Mit diesem integrierten Entwicklungstool können Sie einfache oder komplexe Filter erstellen und speichern, mit deren Hilfe Besucherattribute und Aktionen bei Besuchen und Seitenaufrufen identifiziert werden.

Sie können sofortige Filter erstellen, indem Sie jeden beliebigen Komponententyp (Dimension, Dimensionselement, Ereignis, Metrik, Segment, Segmentvorlage, Datumsbereich) oben im Bedienfeld in die Filter-Dropzone verschieben.

Komponententypen werden automatisch in Filter konvertiert. Alternativ können Sie auch auf das &quot;+&quot;-Zeichen in der **[!UICONTROL hinzufügen]** ablegen.

Bedenken Sie Folgendes:

* you **cannot** Legen Sie die folgenden Komponententypen in die Filterzone ab: berechnete Metriken und Dimensionen/Metriken, aus denen Sie keine Filter erstellen können.
* Für vollständige Dimensionen und Ereignis erstellt Analysis Workspace Trefferfelder vom Typ &quot;vorhanden&quot;und &quot;vorhanden&quot;Filter. Beispiele: „Hit, wenn eVar1 vorhanden ist“ oder „Hit, wenn event1 vorhanden ist“.
* Wenn &quot;Nicht angegeben&quot;oder &quot;Keine&quot;in der Filter-Dropzone abgelegt wird, wird sie automatisch in einen Filter &quot;Nicht vorhanden&quot;konvertiert, damit er korrekt behandelt wird.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Auf diese Weise erstellte Filter sind intern im Projekt.

Führen Sie folgende Schritte aus, um diese Filter öffentlich (global) zu machen:

1. Bewegen Sie den Mauszeiger über den Filter in der Dropzone und klicken Sie auf das Symbol &quot;i&quot;.
1. Klicken Sie dann im angezeigten Informationsfeld auf **[!UICONTROL Als öffentlich einstellen]**.

   ![](assets/segment-info.png)

## Andere Methoden zur Anwendung von Filtern

Es gibt verschiedene weitere Methoden zum Anwenden von Filtern auf ein Projekt:

| Aktion | Beschreibung |
|--- |--- |
| Filter aus Auswahl erstellen | Erstellen Sie einen Inline-Filter. Wählen Sie Zeilen aus, klicken Sie mit der rechten Maustaste auf die Auswahl und erstellen Sie dann einen Inline-Filter. Dieser Filter gilt nur für das geöffnete Projekt und wird nicht als CJA-Filter gespeichert. 1. Zeilen auswählen.  2. Rechtsklick auf die Auswahl.  3. Klicken *Filter aus Auswahl erstellen*. |
| Komponenten > Neuer Filter | Zeigt den Filter-Builder an. Siehe [Filter Builder](https://docs.adobe.com/content/help/de-DE/analytics/components/segmentation/segmentation-workflow/seg-build.html) für weitere Informationen zum Filtern. |
| „Freigeben“ > „Projekt freigeben“ oder „Freigeben“ > „Projektdaten kuratieren“ | In [Kuratieren und Freigeben](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), erfahren Sie, wie Filter, die Sie auf das Projekt anwenden, in der freigegebenen Analyse für den Empfänger verfügbar sind. |
| Filter als Dimensionen verwenden | Video: Filter als Dimensionen in Analysis Workspace verwenden |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
