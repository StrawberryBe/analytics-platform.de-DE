---
title: Filter erstellen
description: Machen Sie sich mit der Benutzeroberfläche zur Filtererstellung vertraut.
translation-type: tm+mt
source-git-commit: 0c5bd5ce0b0ba4ba758a1ef1adf5a4a519e9cf8c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 38%

---


# Filter erstellen

Der Filtergenerator bietet eine Arbeitsfläche zum Ziehen und Ablegen von Metriken, Dimensionen, Filtern und Ereignissen für das Filtern von Besuchern anhand von Container-Hierarchielogik, Regeln und Operatoren. Mit diesem integrierten Entwicklungstool können Sie einfache oder komplexe Filter erstellen und speichern, mit deren Hilfe Besucherattribute und Aktionen bei Besuchen und Seitenaufrufen identifiziert werden.

Sie können sofortige Filter erstellen, indem Sie jeden beliebigen Komponententyp (Dimension, Dimensionselement, Ereignis, Metrik, Segment, Segmentvorlage, Datumsbereich) oben im Bedienfeld in die Filter-Dropzone verschieben.

Komponententypen werden automatisch in Filter konvertiert. Alternatively, you can click the &quot;+&quot; sign in the **[!UICONTROL Add Filter]** drop box.

Bedenken Sie Folgendes:

* You **cannot** drop the following component types into the filter zone: calculated metrics and dimensions/metrics from which you cannot build filters.
* Für vollständige Dimensionen und Ereignis erstellt Analysis Workspace Trefferfelder vom Typ &quot;vorhanden&quot;. Beispiele: „Hit, wenn eVar1 vorhanden ist“ oder „Hit, wenn event1 vorhanden ist“.
* Wenn &quot;Nicht angegeben&quot;oder &quot;Keine&quot;in der Filter-Dropzone abgelegt wird, wird sie automatisch in einen Filter &quot;Nicht vorhanden&quot;konvertiert, damit er korrekt behandelt wird.

![](assets/segment-dropzone.png)

>[!NOTE] Auf diese Weise erstellte Filter sind intern im Projekt.

Führen Sie folgende Schritte aus, um diese Filter öffentlich (global) zu machen:

1. Bewegen Sie den Mauszeiger über den Filter in der Dropzone und klicken Sie auf das Symbol &quot;i&quot;.
1. Klicken Sie dann im angezeigten Informationsfeld auf **[!UICONTROL Als öffentlich einstellen]**.

   ![](assets/segment-info.png)

## Andere Methoden zur Anwendung von Filtern

Es gibt verschiedene weitere Methoden zum Anwenden von Filtern auf ein Projekt:

| Aktion | Beschreibung |
|--- |--- |
| Filter aus Auswahl erstellen | Erstellen Sie einen Inline-Filter. Wählen Sie Zeilen aus, klicken Sie mit der rechten Maustaste auf die Auswahl und erstellen Sie dann einen Inline-Filter. Dieser Filter gilt nur für das geöffnete Projekt und wird nicht als CJA-Filter gespeichert. 1. Zeilen auswählen.  2. Rechtsklick auf die Auswahl.  3. Click *Create filter from selection*. |
| Komponenten > Neuer Filter | Zeigt den Filter-Builder an. See [Filter Builder](https://docs.adobe.com/content/help/de-DE/analytics/components/segmentation/segmentation-workflow/seg-build.html) for more information about filtering. |
| „Freigeben“ > „Projekt freigeben“ oder „Freigeben“ > „Projektdaten kuratieren“ | In [Curate and Share](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), learn how filters that you apply to the project are available in shared analysis for the recipient. |
| Filter als Dimensionen verwenden | Video: [Verwenden von Segmenten als Dimensionen in Analysis Workspace](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
