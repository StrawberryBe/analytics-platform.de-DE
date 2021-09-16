---
title: Datenansicht erstellen
description: Alle Einstellungen, die Sie anpassen können, um eine Datenansicht zu erstellen oder zu bearbeiten.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 49b4998194274eec2ab8eca231029ccb5ccf648d
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 77%

---

# Datenansicht erstellen

Das Erstellen einer Datenansicht umfasst entweder das Erstellen von Metriken und Dimensionen aus Schemaelementen oder die Verwendung von Standardkomponenten. Die meisten Schemaelemente können je nach den Anforderungen Ihres Unternehmens entweder eine Dimension oder eine Metrik sein. Nachdem Sie ein Schemaelement in eine Datenansicht gezogen haben, werden rechts Optionen angezeigt, mit denen Sie anpassen können, wie die Dimension oder Metrik in CJA funktioniert.

## Einstellungen und Container für Datenansichten konfigurieren

1. Gehen Sie in Customer Journey Analytics zur Registerkarte **[!UICONTROL Datenansichten]**.
2. Klicken Sie auf **[!UICONTROL Hinzufügen]**, um eine neue Datenansicht zu erstellen und deren Einstellungen zu konfigurieren.

![Neue Datenansicht](assets/new-data-view.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Verbindung] | In diesem Feld wird die Datenansicht mit der zuvor eingerichteten Verbindung verknüpft, die einen oder mehrere Adobe Experience Platform-Datensätze enthält. |
| [!UICONTROL Name] | Geben Sie der Datenansicht einen Namen. Dies ist ein Pflichtfeld. |
| [!UICONTROL Beschreibung] | Eine detaillierte Beschreibung ist nicht zwingend erforderlich, wird jedoch empfohlen. |
| [!UICONTROL Zeitzone] | Wählen Sie die Zeitzone aus, in der Ihre Daten angezeigt werden sollen. |
| [!UICONTROL Tags] | [!UICONTROL Mit Tags können Sie Ihre Datenansichten in Kategorien organisieren.] |
| [!UICONTROL Behälter] | Sie können Ihre Container hier umbenennen, um zu bestimmen, wie sie in jedem Workspace-Projekt erscheinen sollen, das auf dieser Datenansicht basiert. [!UICONTROL Container] werden in Filtern und Fallout/Fluss usw. verwendet, um zu definieren, wie breit oder schmal der Umfang oder Kontext ist. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=de#filter-containers) |
| [!UICONTROL Name des Personen-Containers...] | [!UICONTROL Person] (Standard). Der [!UICONTROL Person]-Container enthält sämtliche Besuche und Seitenansichten für Besucher innerhalb eines bestimmten Zeitrahmens. Sie können diesen Container in „Benutzer“ oder einen anderen von Ihnen bevorzugten Begriff umbenennen. |
| [!UICONTROL Der Name des Sitzungs-Containers lautet...] | [!UICONTROL Sitzung] (Standard). Mit dem Sitzungs-Container können Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte [!UICONTROL Sitzung] identifiziert werden. Sie können diesen Container in „Besuch“ oder einen anderen von Ihnen bevorzugten Begriff umbenennen. |
| [!UICONTROL Der Name des Ereignis-Containers ist...] | [!UICONTROL Ereignis] (Standard). Der [!UICONTROL Ereignis]-Container definiert, welche Seitenereignisse von einem Filter eingeschlossen oder ausgeschlossen werden sollen. |

Als Nächstes können Sie Metriken und Dimensionen aus Schemaelementen erstellen. Sie können auch Standardkomponenten verwenden.

## Erstellen von Metriken und Dimensionen aus Schemaelementen

1. Klicken Sie unter [!UICONTROL Customer Journey Analytics] > [!UICONTROL Datenansichten] auf die Registerkarte [!UICONTROL Komponenten].

![Registerkarte &quot;Komponenten&quot;](assets/components-tab.png)

Links oben sehen Sie die [!UICONTROL Verbindung], die die Datensätze und die [!UICONTROL Schemafelder] unten enthält. Bedenken Sie Folgendes:

* Die bereits enthaltenen Komponenten sind die erforderlichen Standardkomponenten (vom System generiert).
* Adobe wendet standardmäßig den Filter **[!UICONTROL Enthält Daten]** an, so dass nur Schemafelder erscheinen, die Daten enthalten. Wenn Sie nach einem Feld suchen, das keine Daten enthält, entfernen Sie den Filter.

1. Ziehen Sie nun ein Schema, z. B. [!UICONTROL pageTitle], aus der linken Leiste in den Bereich „Metriken“ oder „Dimensionen“.

   Sie können dasselbe Schema mehrmals in die Bereiche „Dimensionen“ oder „Metriken“ ziehen und dieselbe Dimension oder Metrik auf unterschiedliche Weise konfigurieren.
Beispielsweise können Sie im Feld **[!UICONTROL pageTitle]** eine Dimension namens „Produktseiten“ und eine weitere Dimension „Fehlerseiten“ usw. erstellen, indem Sie den **[!UICONTROL Komponentennamen]** rechts umbenennen. Vom Feld **[!UICONTROL pageTitle]** aus können Sie auch Metriken aus einem Zeichenfolgenwert erstellen. Sie können beispielsweise eine oder mehrere Metriken für **[!UICONTROL Bestellungen]** mit unterschiedlichen Attributionseinstellungen und unterschiedlichen Ein-/Ausschlusswerten erstellen.

   ![Tab 3](assets/components-tab-3.png)

   >[!NOTE]
   >
   >Sie können ganze Ordner mit Schemafeldern aus der linken Leiste ziehen und sie werden automatisch in traditionelle Abschnitte unterteilt. Die Zeichenfolgenfelder werden im Abschnitt [!UICONTROL Dimensionen] und die Zahlen im Abschnitt [!UICONTROL Metriken] angezeigt. Alternativ können Sie auf **[!UICONTROL Alle]** hinzufügen klicken und alle Schemafelder werden hinzugefügt.

1. Nachdem Sie die Komponente ausgewählt haben, werden auf der rechten Seite eine Reihe von Einstellungen angezeigt. Konfigurieren Sie die Komponente mithilfe der Einstellungen, die unter

* [ Komponenteneinstellungen - Übersicht](/help/data-views/component-settings/overview.md)
* [ Attributionskomponenteneinstellungen](/help/data-views/component-settings/attribution.md)
* [ Behaviorcomponent-Einstellungen](/help/data-views/component-settings/behavior.md)
* [ Formatkomponenteneinstellungen](/help/data-views/component-settings/format.md)
* [[!UICONTROL Include|] excludecomponent settings](/help/data-views/component-settings/include-exclude-values.md)
* [[!UICONTROL Einstellungen ] der Metrik-Deduplizierung](/help/data-views/component-settings/metric-deduplication.md)
* [[!UICONTROL Keine Einstellungen ] der Komponente](/help/data-views/component-settings/no-value-options.md)
* [ Persistenzkomponenten-Einstellungen](/help/data-views/component-settings/persistence.md)
   [[!UICONTROL Einstellungen ] der Wertaufschlüsselungskomponente](/help/data-views/component-settings/value-bucketing.md)

## Verwenden Sie die Funktion [!UICONTROL Duplizieren].

Das Duplizieren von Metriken oder Dimensionen und das anschließende Ändern spezifischer Einstellungen ist eine einfache Möglichkeit, mehrere Metriken oder Dimensionen aus einem einzelnen Schemafeld zu erstellen. Wählen Sie einfach die Einstellung [!UICONTROL Duplizieren] unter dem Namen der Metrik oder Dimension oben rechts aus. Ändern Sie dann die neue Metrik oder Dimension und speichern Sie sie unter einem Namen, der sie besser beschreibt.

![Duplizieren](assets/duplicate.png)

## Filtern von Schemafeldern und Dimensionen/Metriken

Sie können die Schemafelder in der linken Leiste nach folgenden Datentypen filtern:

![Felder filtern](assets/filter-fields.png)

Sie können auch nach Datensätzen filtern und danach, ob ein Schemafeld Daten enthält oder ob es sich um eine Identität handelt. Standardmäßig wird der Filter **[!UICONTROL Enthält Daten]** auf alle Ansichten angewendet.

![Andere filtern](assets/filter-other.png)

## Globalen Filter zur Datenansicht hinzufügen

Sie können Filter hinzufügen, die für eine gesamte Datenansicht gelten. Dieser Filter wird auf alle Berichte angewendet, die Sie in Workspace ausführen.

1. Klicken Sie auf die Registerkarte [!UICONTROL Einstellungen] in [!UICONTROL Datenansichten].
1. Ziehen Sie einen Filter aus der Liste in das Feld [!UICONTROL Filter hinzufügen] in der linken Leiste.
