---
title: Datenansicht erstellen oder bearbeiten
description: Alle Einstellungen, die Sie anpassen können, um eine Datenansicht zu erstellen oder zu bearbeiten.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78,35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
source-git-commit: 36b7cc72c34e27f90af29146f7a32c525b279b9b
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 16%

---

# Datenansicht erstellen oder bearbeiten

Das Erstellen einer Datenansicht umfasst entweder das Erstellen von Metriken und Dimensionen aus Schemaelementen oder die Verwendung von Standardkomponenten. Die meisten Schemaelemente können je nach den Anforderungen Ihres Unternehmens entweder eine Dimension oder eine Metrik sein. Nachdem Sie ein Schemaelement in eine Datenansicht gezogen haben, werden rechts Optionen angezeigt, mit denen Sie anpassen können, wie die Dimension oder Metrik in CJA funktioniert.

## Datenansicht konfigurieren

1. Melden Sie sich bei [Customer Journey Analytics](https://analytics.adobe.com) an und wechseln Sie zur Registerkarte **[!UICONTROL Datenansichten]** .
2. Klicken Sie auf **[!UICONTROL Hinzufügen]**, um eine Datenansicht zu erstellen, oder klicken Sie auf eine vorhandene Datenansicht, um sie zu bearbeiten.

![Neue Datenansicht](assets/new-data-view.png)

### Einstellungen

Stellt übergreifende Einstellungen für die Datenansicht bereit.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Verbindung] | In diesem Feld wird die Datenansicht mit der zuvor eingerichteten Verbindung verknüpft, die einen oder mehrere Adobe Experience Platform-Datensätze enthält. |
| [!UICONTROL Name] | Erforderlich. Der Name der Datenansicht. Dieser Wert wird in der Dropdown-Liste oben rechts in Analysis Workspace angezeigt. |
| [!UICONTROL Beschreibung] | Optional. Adobe empfiehlt eine detaillierte Beschreibung, damit Benutzer verstehen, warum die Datenansicht vorhanden ist und für wen sie konzipiert ist. |

### Behälter

Gibt den Namen der Container für die Datenansicht an. Container-Namen werden häufig in [Filtern](/help/components/filters/filters-overview.md#Filter-containers) verwendet.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Container-Name für Person] | [!UICONTROL Person] (Standard). Der Container [!UICONTROL Person] enthält alle Sitzungen und Ereignisse für Besucher innerhalb des angegebenen Zeitraums. Wenn Ihr Unternehmen einen anderen Begriff verwendet (z. B. &quot;Besucher&quot;oder &quot;Benutzer&quot;), können Sie den Container hier umbenennen. |
| [!UICONTROL Container-Name für Sitzung] | [!UICONTROL Sitzung] (Standard). Mit dem Sitzungs-Container können Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte [!UICONTROL Sitzung] identifiziert werden. Sie können diesen Container in &quot;Besuch&quot;oder einen anderen von Ihrem Unternehmen bevorzugten Begriff umbenennen. |
| [!UICONTROL Container-Name für Ereignis] | [!UICONTROL Ereignis] (Standard). Der Container [!UICONTROL Event] definiert einzelne Ereignisse in einem Datensatz. Wenn Ihr Unternehmen einen anderen Begriff verwendet (z. B. &quot;Treffer&quot;oder &quot;Seitenansichten&quot;), können Sie den Container hier umbenennen. |

### Kalender

Gibt das Kalenderformat an, dem die Datenansicht folgen soll. Sie können mehrere Datenansichten basierend auf derselben [Verbindung](/help/connections/create-connection.md) haben und ihnen unterschiedliche Kalendertypen oder Zeitzonen zuweisen. Diese Datenansichten können Teams, die verschiedene Kalendertypen verwenden, ermöglichen, ihre jeweiligen Anforderungen mit denselben zugrunde liegenden Daten zu erfüllen.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Zeitzone] | Wählen Sie die Zeitzone aus, in der Ihre Daten angezeigt werden sollen. Wenn Sie eine Zeitzone auswählen, die mit der Sommerzeit arbeitet, werden die Daten automatisch entsprechend angepasst. Im Frühling, wenn die Uhren eine Stunde voraus sind, besteht eine Lücke von einer Stunde. Im Herbst, wenn sich die Uhren eine Stunde später einstellen, wird während der Sommerzeit eine Stunde wiederholt. |
| [!UICONTROL Kalendertyp] | Bestimmen Sie, wie die Wochen des Monats gruppiert werden.<br>**Gregorianisch:** Standardkalenderformat. Die Quartale werden nach Monat gruppiert.<br>**4-5-4 Einzelhandel:** Ein standardisierter 4-5-4 Einzelhandelskalender. Der erste und der letzte Monat des Quartals enthalten 4 Wochen, während der zweite Monat des Quartals aus 5 Wochen besteht.<br>**Benutzerspezifisch (4-5-4):**  Ähnlich wie der 4-5-4-Kalender mit dem Unterschied, dass Sie den ersten Tag des Jahres und das Jahr auswählen können, in dem die &quot;zusätzliche&quot;Woche stattfindet.<br>**Benutzerspezifisch (4-4-5):**  Der erste und zweite Monat jedes Quartals enthalten 4 Wochen, während die letzte Woche jedes Quartals aus 5 Wochen besteht.<br>**Benutzerspezifisch (5-4-4):**  Der erste Monat jedes Quartals besteht aus 5 Wochen, während der zweite und dritte Monat jedes Quartals aus 4 Wochen besteht. |
| [!UICONTROL Erster Monat des ] Jahres und  [!UICONTROL Erster Wochentag] | Sichtbar für den gregorianischen Kalendertyp. Geben Sie an, in welchem Monat das Kalenderjahr beginnen soll und an welchem Tag jede Woche beginnen soll. |
| [!UICONTROL Erster Tag des aktuellen Jahres] | Für benutzerdefinierte Kalendertypen sichtbar. Geben Sie an, an welchem Tag des Jahres das aktuelle Jahr beginnen soll. Der Kalender formatiert automatisch den ersten Wochentag auf Grundlage dieses Werts. |
| [!UICONTROL Jahr mit „zusätzlicher“ Woche] | Mit den meisten 364-tägigen Kalendern (52 Wochen von jeweils 7 Tagen) sammeln sich jedes Jahr verbleibende Tage, bis sie eine zusätzliche Woche bilden. Diese zusätzliche Woche wird dann zum letzten Monat des Jahres hinzugefügt. Geben Sie an, zu welchem Jahr die zusätzliche Woche hinzugefügt werden soll. |

## Komponenten einer Datenansicht festlegen

Als Nächstes können Sie Metriken und Dimensionen aus Schemaelementen erstellen. Sie können auch Standardkomponenten verwenden.

1. Melden Sie sich bei [Customer Journey Analytics](https://analytics.adobe.com) an und wechseln Sie zur Registerkarte **[!UICONTROL Datenansichten]** .
1. Klicken Sie auf **[!UICONTROL Hinzufügen]**, um eine Datenansicht zu erstellen, oder klicken Sie auf eine vorhandene Datenansicht, um sie zu bearbeiten.
1. Klicken Sie auf die Registerkarte **[!UICONTROL Komponenten]** .

   ![Registerkarte &quot;Komponenten&quot;](assets/components-tab.png)

   Links oben sehen Sie die [!UICONTROL Verbindung], die die Datensätze und die [!UICONTROL Schemafelder] unten enthält. Beachten Sie, dass es sich bei den bereits eingeschlossenen Komponenten um standardmäßige erforderliche Komponenten (vom System generiert) für alle Datenansichten handelt. Adobe wendet standardmäßig auch den Filter **[!UICONTROL Enthält Daten]** an, sodass nur Schemafelder mit Daten angezeigt werden. Wenn Sie ein Feld wünschen, das keine Daten enthält, entfernen Sie diesen Filter.

1. Ziehen Sie ein Schemafeld wie `pageTitle` aus der linken Leiste in den Bereich Metriken oder Dimensionen .

   Sie können dasselbe Schema mehrmals in die Bereiche „Dimensionen“ oder „Metriken“ ziehen und dieselbe Dimension oder Metrik auf unterschiedliche Weise konfigurieren. Beispielsweise können Sie im Feld `pageTitle` eine Dimension namens &quot;Produktseiten&quot;und eine weitere &quot;Fehlerseiten&quot;erstellen, indem Sie rechts unterschiedliche [Komponenteneinstellungen](component-settings/overview.md) verwenden.

   ![Tab 3](assets/components-tab-3.png)

   Wenn Sie einen Ordner mit Schemafeldern aus der linken Leiste ziehen, werden diese automatisch in typische Abschnitte unterteilt. Zeichenfolgenfelder landen im Abschnitt [!UICONTROL Dimensionen] und numerische Schematypen landen im Abschnitt [!UICONTROL Metriken] . Sie können auch auf **[!UICONTROL Alle]** hinzufügen klicken und alle Schemafelder werden zu ihren jeweiligen Speicherorten hinzugefügt.

1. Nachdem Sie die Komponente ausgewählt haben, werden rechts mehrere Einstellungen angezeigt. Konfigurieren Sie die Komponente mit [Komponenteneinstellungen](component-settings/overview.md). Die verfügbaren Komponenteneinstellungen hängen davon ab, ob es sich bei der Komponente um eine Dimension/Metrik und um den Schemadatyp handelt. Zu den Einstellungen gehören:

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Verhalten]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Werte einschließen/ausschließen]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Deduplizierung der Metrik]](component-settings/metric-deduplication.md)
   * [[!UICONTROL Keine Wertoptionen]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistenz]](component-settings/persistence.md)
   * [[!UICONTROL Wert-Bucketing]](component-settings/value-bucketing.md)

Bei Bedarf können Sie die folgenden Funktionen verwenden:

* **[!UICONTROL Duplizieren]**: Das Duplizieren von Metriken oder Dimensionen und das anschließende Ändern spezifischer Einstellungen ist eine einfache Möglichkeit, mehrere Metriken oder Dimensionen aus einem einzelnen Schemafeld zu erstellen. Wählen Sie die Einstellung [!UICONTROL Duplizieren] unter dem Namen der Metrik oder Dimension oben rechts aus. Ändern Sie die neue Dimension oder Metrik und speichern Sie sie unter einem beschreibenden Namen.

   ![Duplizieren](assets/duplicate.png)

* **[!UICONTROL Filter]**: Sie können Schemafelder in der linken Leiste nach folgenden Datentypen filtern:

   ![Felder filtern](assets/filter-fields.png)

   Sie können auch nach Datensätzen filtern und danach, ob ein Schemafeld Daten enthält oder ob es sich um eine Identität handelt. Standardmäßig wendet Adobe zunächst den Filter **[!UICONTROL Enthält Daten]** auf alle Datenansichten an.

   ![Andere filtern](assets/filter-other.png)

## Einstellungen

1. Melden Sie sich bei [Customer Journey Analytics](https://analytics.adobe.com) an und wechseln Sie zur Registerkarte **[!UICONTROL Datenansichten]** .
1. Klicken Sie auf **[!UICONTROL Hinzufügen]**, um eine Datenansicht zu erstellen, oder klicken Sie auf eine vorhandene Datenansicht, um sie zu bearbeiten.
1. Klicken Sie auf die Registerkarte **[!UICONTROL Einstellungen]** .

### Globaler Filter

Sie können Filter hinzufügen, die für eine gesamte Datenansicht gelten. Dieser Filter wird auf alle Berichte angewendet, die Sie in Workspace ausführen. Ziehen Sie einen Filter aus der Liste in das Feld [!UICONTROL Filter hinzufügen] in der linken Leiste.

### Sitzungseinstellungen

Legen Sie den Zeitraum der Inaktivität zwischen Ereignissen fest, bevor eine Sitzung abläuft und eine neue gestartet wird.

Ein Zeitraum ist erforderlich. Sie können optional auch den Start einer neuen Sitzung erzwingen, wenn ein Ereignis eine bestimmte Metrik enthält.

Nachdem alle gewünschten Einstellungen angegeben wurden, klicken Sie auf **[!UICONTROL Speichern und beenden]**.
