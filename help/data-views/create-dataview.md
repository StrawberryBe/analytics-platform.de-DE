---
title: Erstellen oder Bearbeiten einer Datenansicht
description: Alle Einstellungen, die Sie anpassen können, um eine Datenansicht zu erstellen oder zu bearbeiten.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 92511d2bedf322097b4d70ccede5ac6e0df7b0c6
workflow-type: tm+mt
source-wordcount: '1391'
ht-degree: 56%

---

# Erstellen oder Bearbeiten einer Datenansicht

Das Erstellen einer Datenansicht umfasst entweder die Erstellung von Metriken und Dimensionen aus Schemaelementen oder die Verwendung von Standardkomponenten. Die meisten Schemaelemente können je nach den Anforderungen Ihres Unternehmens entweder eine Dimension oder eine Metrik sein. Nachdem Sie ein Schemaelement in eine Datenansicht gezogen haben, werden rechts Optionen angezeigt, mit denen Sie anpassen können, wie die Dimension oder Metrik in Customer Journey Analytics funktioniert.

Im Folgenden finden Sie ein Video zum Thema:

>[!VIDEO](https://video.tv.adobe.com/v/35110/?quality=12&learn=on)

So erstellen oder bearbeiten Sie eine Datenansicht:

1. Anmelden bei [Customer Journey Analytics](https://analytics.adobe.com) und gehen Sie zu **[!UICONTROL Datenansichten]** Registerkarte.
1. Um eine Datenansicht zu erstellen, wählen Sie **[!UICONTROL Neue Datenansicht erstellen]**. Alternativ können Sie eine vorhandene Datenansicht aus der Liste der Datenansichten auswählen, um sie zu bearbeiten.


## Konfigurieren

So konfigurieren Sie eine neue oder vorhandene Datenansicht:

1. Wählen Sie die **[!UICONTROL Konfigurieren]** Registerkarte (falls noch nicht aktiv).

   ![Datenansicht konfigurieren](assets/dataview-configure.png)
1. Angeben [!UICONTROL Einstellungen], [!UICONTROL Container], und [!UICONTROL Kalender] Details (siehe unten).
1. Auswählen **[!UICONTROL Speichern und fortfahren]** um mit der Konfiguration der neuen oder vorhandenen Datenansicht fortzufahren. Auswählen **[!UICONTROL Speichern]** , um die Konfiguration für Ihre vorhandene Datenansicht zu speichern.


### Einstellungen

Stellt übergreifende Einstellungen für die Datenansicht bereit.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Verbindung] | In diesem Feld wird die Datenansicht mit der zuvor eingerichteten Verbindung verknüpft, die einen oder mehrere Adobe Experience Platform-Datensätze enthält. |
| [!UICONTROL Name] | Erforderlich. Der Name der Datenansicht. Dieser Wert wird in der oberen rechten Dropdown-Liste in Analysis Workspace angezeigt. |
| [!UICONTROL Beschreibung] | Optional. Adobe empfiehlt eine detaillierte Beschreibung, damit Benutzer verstehen, warum die Datenansicht vorhanden ist und für wen sie konzipiert ist. |

{style="table-layout:auto"}

### Behälter

Gibt den Namen der Container für die Datenansicht an. Container-Namen werden häufig in [Filtern](/help/components/filters/filters-overview.md#Filter-containers) verwendet.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Container-Name für Person] | [!UICONTROL Person] (Standard). Die [!UICONTROL Person] enthält alle Sitzungen und Ereignisse für Personen innerhalb des festgelegten Zeitraums. Wenn Ihr Unternehmen einen anderen Begriff verwendet (z. B. „Besucher“ oder „Benutzer“), können Sie den Container hier umbenennen. |
| [!UICONTROL Container-Name für Sitzung] | [!UICONTROL Sitzung] (Standard). Mit dem Sitzungs-Container können Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte [!UICONTROL Sitzung] identifiziert werden. Sie können diesen Container in „Besuch“ oder einen anderen von Ihrem Unternehmen bevorzugten Begriff umbenennen. |
| [!UICONTROL Container-Name für Ereignis] | [!UICONTROL Ereignis] (Standard). Der Container [!UICONTROL Ereignis] definiert einzelne Ereignisse in einem Datensatz. Wenn Ihr Unternehmen einen anderen Begriff verwendet (z. B. „Hits“ oder „Seitenansichten“), können Sie den Container hier umbenennen. |

{style="table-layout:auto"}

### Kalender

Gibt das Kalenderformat an, dem die Datenansicht folgen soll. Sie können mehrere Datenansichten basierend auf derselben [Verbindung](/help/connections/create-connection.md) haben und ihnen unterschiedliche Kalendertypen oder Zeitzonen zuweisen. Diese Datenansichten können es Teams, die verschiedene Kalendertypen verwenden, ermöglichen, ihre jeweiligen Anforderungen mit denselben zugrunde liegenden Daten zu erfüllen.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Zeitzone] | Wählen Sie die Zeitzone aus, in der Ihre Daten dargestellt werden sollen. Wenn Sie eine Zeitzone auswählen, die mit der Sommerzeit arbeitet, werden die Daten automatisch entsprechend angepasst. Im Frühling, wenn die Uhren eine Stunde vor gestellt werden, besteht eine Lücke von einer Stunde. Im Herbst, wenn die Uhren eine Stunde zurück gestellt werden, wird während der Sommerzeit eine Stunde wiederholt. |
| [!UICONTROL Kalendertyp] | Bestimmen Sie, wie die Wochen des Monats gruppiert werden.<br>**Gregorianisch:** Standardkalenderformat. Die Quartale werden nach Monat gruppiert.<br>**4-5-4 Einzelhandel:** Ein standardisierter 4-5-4 Einzelhandelskalender. Der erste und der letzte Monat des Quartals enthalten 4 Wochen, während der zweite Monat des Quartals aus 5 Wochen besteht.<br>**Benutzerspezifisch (4-5-4):** Ähnlich wie der 4-5-4-Kalender mit dem Unterschied, dass Sie den ersten Tag des Jahres und das Jahr auswählen können, in dem die „zusätzliche“ Woche liegt.<br>**Benutzerdefiniert (4-4-5):** Der erste und zweite Monat jedes Quartals enthalten 4 Wochen, während die letzte Woche jedes Quartals aus 5 Wochen besteht.<br>**Benutzerspezifisch (5-4-4):** Der erste Monat jedes Quartals umfasst 5 Wochen, während der zweite und dritte Monat jedes Quartals 4 Wochen umfassen. |
| [!UICONTROL Erster Monat des Jahres] und [!UICONTROL Erster Wochentag] | Sichtbar für den gregorianischen Kalender. Geben Sie an, in welchem Monat das Kalenderjahr beginnen soll und an welchem Tag jede Woche beginnen soll. |
| [!UICONTROL Erster Tag des aktuellen Jahres] | Für benutzerdefinierte Kalendertypen sichtbar. Geben Sie an, an welchem Tag des Jahres das aktuelle Jahr beginnen soll. Der Kalender formatiert automatisch den ersten Wochentag auf Grundlage dieses Werts. |
| [!UICONTROL Jahr mit „zusätzlicher“ Woche] | Mit den meisten 364-tägigen Kalendern (52 Wochen von jeweils 7 Tagen) sammeln sich jedes Jahr verbleibende Tage, bis sie eine zusätzliche Woche ergeben. Diese zusätzliche Woche wird dann zum letzten Monat des Jahres hinzugefügt. Geben Sie an, zu welchem Jahr die zusätzliche Woche hinzugefügt werden soll. |

{style="table-layout:auto"}

## Komponenten

Als Nächstes können Sie die Komponenten einer Datenansicht festlegen, d. h. Sie können Metriken und Dimensionen aus Schemaelementen erstellen. Sie können auch Standardkomponenten verwenden.

1. Wählen Sie die **[!UICONTROL Komponenten]** Registerkarte.

   ![Registerkarte „Komponenten“](assets/dataview-components.png)

   Links oben sehen Sie die [!UICONTROL Verbindung], die die Datensätze und die [!UICONTROL Schemafelder] unten enthält.  Bei den bereits eingeschlossenen Komponenten handelt es sich um Standardkomponenten (vom System generiert), die für alle Datenansichten benötigt werden (z. B. Ereignisse, Personen, Sitzungsmetriken und Dimensionen &quot;Minute&quot;, &quot;Quartal&quot;und &quot;Woche&quot;). Adobe wendet auch den Filter an **[!UICONTROL Enthält Daten]** und **[!UICONTROL ist nicht veraltet]** Standardmäßig werden nur Schemafelder angezeigt, die Daten enthalten und nicht veraltet sind.

1. Suchen Sie nach einem Schemafeld mit ![Suchsymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL Suchschemafelder]** oder suchen Sie ein Feld, indem Sie in eine der Datensatz-Sammlungen wechseln, z. B. ![Ordnersymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg) **[!UICONTROL Ereignis-Datensätze]**.<br/>Alternativ können Sie ein abgeleitetes Feld mit ![Datensymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **abgeleitetes Feld erstellen** . Siehe [Abgeleitete Felder](./derived-fields/derived-fields.md) für weitere Informationen.

1. Wenn Sie Ihr spezifisches Schemafeld gefunden oder Ihr abgeleitetes Feld definiert haben, ziehen Sie dieses Feld, z. B. ![Handle-Symbol](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Seitenname]**aus der linken Leiste in den Bereich Metriken oder Dimensionen .
Sie können dasselbe Schema mehrmals in die Bereiche „Dimensionen“ oder „Metriken“ ziehen und dieselbe Dimension oder Metrik auf unterschiedliche Weise konfigurieren. Beispielsweise können Sie im Feld &quot;pageName&quot;eine Dimension namens &quot;Produktseiten&quot;und eine weitere &quot;Fehlerseiten&quot;erstellen, indem Sie verschiedene [Komponenteneinstellungen](component-settings/overview.md) rechts.
Wenn Sie einen Ordner mit Schemafeldern aus der linken Leiste ziehen, werden diese automatisch in typische Abschnitte unterteilt. Zeichenfolgenfelder landen im Abschnitt [!UICONTROL Dimensionen] und numerische Schematypen landen im Abschnitt [!UICONTROL Metriken]. Sie können auch auf **[!UICONTROL Alle hinzufügen]** klicken, dann werden alle Schemafelder zu ihren jeweiligen Speicherorten hinzugefügt.

1. Nachdem Sie eine Komponente ausgewählt haben, werden die Einstellungen auf der rechten Seite angezeigt.

   ![Datenansichtskomponente ausgewählt](assets/dataview-component-pagename.png)

   Konfigurieren Sie die Komponente mit [Komponenteneinstellungen](component-settings/overview.md). Die verfügbaren Komponenteneinstellungen hängen davon ab, ob es sich bei der Komponente um eine Dimension/Metrik und um den Schemadatentyp handelt. Zu den Einstellungen gehören:

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Verhalten]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Werte einschließen/ausschließen]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Deduplizierung der Metrik]](component-settings/metric-deduplication.md)
   * [[!UICONTROL Keine Wertoptionen]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistenz]](component-settings/persistence.md)
   * [[!UICONTROL Wert-Bucketing]](component-settings/value-bucketing.md)

1. Auswählen **[!UICONTROL Speichern und fortfahren]** um mit der Konfiguration der neuen oder vorhandenen Datenansicht fortzufahren. Auswählen **[!UICONTROL Speichern]** , um die Konfiguration für Ihre vorhandene Datenansicht zu speichern.

**Duplizieren von Metriken oder Dimensionen**

Das Duplizieren von Metriken oder Dimensionen und das anschließende Ändern spezifischer Einstellungen ist eine einfache Möglichkeit, mehrere Metriken oder Dimensionen aus einem einzelnen Schemafeld zu erstellen. Wählen Sie die Einstellung [!UICONTROL Duplizieren] unter dem Namen der Metrik oder Dimension oben rechts aus. Ändern Sie dann die neue Dimension oder Metrik und speichern Sie sie unter einem aussagekräftigeren Namen.

**Filtern von Schemafeldern oder Datensätzen**

Sie können ![Filtersymbol](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) Schemafelder in der linken Leiste nach [!UICONTROL Datentyp], [!UICONTROL Datensätze], [!UICONTROL Data Governance], und [!UICONTROL other] Kriterien ([!UICONTROL enthält Daten], [!UICONTROL is identity], und [!UICONTROL ist nicht veraltet]):

![Felder filtern](assets/dataview-components-filter.png)


## Einstellungen 

1. Wählen Sie die **[!UICONTROL Einstellungen]** Registerkarte.
1. Konfigurieren Sie Filter, die auf die gesamte Datenansicht angewendet werden sollen. Siehe [Einstellungen (Filter)](#settings-filters) unten.
1. Konfigurieren Sie Sitzungs-Timeout und Metriken. Siehe [Sitzungseinstellungen](#session-settings) unten.
1. Auswählen **[!UICONTROL Speichern und fortfahren]** um mit der Konfiguration der neuen oder vorhandenen Datenansicht fortzufahren. Auswählen **[!UICONTROL Speichern]** , um die Konfiguration für Ihre vorhandene Datenansicht zu speichern.

### Einstellungen (Filter)

Sie können Filter hinzufügen, die für die gesamte Datenansicht gelten. Dieser Filter wird auf alle Berichte angewendet, die Sie in Arbeitsbereich ausführen. Ziehen Sie einen Filter aus der Liste in das Feld [!UICONTROL Filter hinzufügen] in der linken Leiste.

### Sitzungseinstellungen

Legen Sie den Zeitraum der Inaktivität zwischen Ereignissen fest, bevor eine Sitzung abläuft und eine neue gestartet wird. Ein Zeitraum ist erforderlich. Sie können optional auch den Start einer neuen Sitzung erzwingen, wenn ein Ereignis eine bestimmte Metrik enthält. Siehe [Kontextbezogene Sitzungen](context-aware-sessions.md) für weitere Details.

Nachdem alle gewünschten Einstellungen angegeben wurden, klicken Sie auf **[!UICONTROL Speichern und beenden]**.
