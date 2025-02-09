---
description: Der Filter-Builder bietet eine Arbeitsfläche zum Ziehen und Ablegen von metrischen Dimensionen, Filtern und Ereignissen, um Personen basierend auf der Behälterhierarchielogik, den Regeln und Operatoren zu filtern. Mit diesem integrierten Entwicklungstool können Sie einfache oder komplexe Filter erstellen und speichern, mit denen Personenattribute und Aktionen bei Besuchen und Ereignissen identifiziert werden.
title: Erstellen von Filtern
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '1261'
ht-degree: 23%

---

# Filter-Builder

Die [!UICONTROL Filter Builder] können Sie einfache oder komplexe Filter erstellen, mit denen Personenattribute und Aktionen über Besuche und Ereignisse hinweg identifiziert werden. Es bietet eine Arbeitsfläche zum Ziehen und Ablegen von Metrikdimensionen, Ereignissen oder anderen Filtern, um Personen basierend auf Hierarchielogik, Regeln und Operatoren zu filtern.

Informationen zum Erstellen von Schnellfiltern, die nur für das Projekt gelten, in dem sie erstellt werden, finden Sie unter [Schnellfilter](/help/components/filters/quick-filters.md).

## Zugriff auf den Filter-Builder

Sie haben folgende Möglichkeiten, auf den Filter-Builder zuzugreifen:

* **Navigation oben**: Klicken **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Komponenten]** > **[!UICONTROL Filter]**.
* **[!UICONTROL Analysis Workspace]**: Wenn ein Projekt in Analysis Workspace geöffnet ist, wählen Sie **[!UICONTROL + Komponenten]** > **[!UICONTROL Filter erstellen]**.
* **[!UICONTROL Report Builder]**: [Arbeiten mit Filtern in Report Builder](/help/report-builder/work-with-filters.md).

## Übersicht über Builder-Kriterien {#section_F61C4268A5974C788629399ADE1E6E7C}

Sie können Regeldefinitionen und Container hinzufügen, um Ihre Filter zu definieren. (Informationen zum Zugriff auf den Filter-Builder finden Sie unter [Zugriff auf den Filter-Builder](#access-the-filter-builder).

![Filtergenerator mit neuen Filteroptionen, die in diesem Abschnitt beschrieben werden.](assets/segment_builder_ui_2.png)

| UI-Element | Beschreibung |
| --- | --- |
| **[!UICONTROL Titel]** | Benennen Sie den Filter |
| **[!UICONTROL Beschreibung]** | Geben Sie eine detaillierte Beschreibung für den Filter ein. |
| **[!UICONTROL Tags]** | [Filter taggen](/help/components/filters/manage-filters.md) Sie erstellen, indem Sie aus einer Liste vorhandener Tags wählen oder ein neues Tag erstellen. |
| **[!UICONTROL Definitionen]** | Hier sind Sie [Filter erstellen und konfigurieren](/help/components/filters/filters-overview.md), fügen Sie Regeln hinzu und verschachteln und sequenzieren Sie Container. |
| **[!UICONTROL Einschließlich]** | (Auswahl Oberster Behälter.) Ermöglicht die Auswahl der obersten Ebene [container](/help/components/filters/filters-overview.md) ( [!UICONTROL Person], [!UICONTROL Sitzung], [!UICONTROL Ereignis]). Der standardmäßige Container der obersten Ebene ist der Ereignis-Container. |
| **[!UICONTROL Optionen]** | Symbol (Zahnrad) | <ul><li>**[!UICONTROL Behälter hinzufügen]**: Hiermit können Sie der Filterdefinition einen neuen Behälter (unter dem obersten Behälter) hinzufügen.</li><li>**[!UICONTROL Ausschließen]**: Hiermit können Sie den Filter definieren, indem Sie eine oder mehrere Dimensionen, Filter oder Metriken ausschließen.</li></ul> |
| **[!UICONTROL Dimensionen]** | Komponenten werden aus der Liste der Dimensionen (orangefarbene Seitenleiste) gezogen und abgelegt. |
| **[!UICONTROL Operator]** | Sie können Werte mithilfe ausgewählter Operatoren vergleichen und beschränken. (gleich, ist nicht gleich, enthält, enthält alle usw.) |
| **[!UICONTROL Wert]** | Der Wert, den Sie für die Dimension, den Filter oder die Metrik eingegeben oder ausgewählt haben. |
| **[!UICONTROL Attributionsmodelle]** | Diese Modelle sind nur für Dimensionen verfügbar und bestimmen, nach welchen Werten in einer Dimension gefiltert werden soll. In sequenziellen Filtern sind Dimension-Modelle besonders nützlich.<ul><li>**[!UICONTROL Wiederholend]** (Standard): Umfasst Instanzen und beibehaltene Werte für die Dimension.</li><li>**[!UICONTROL Instanz]**: Umfasst Instanzen für die Dimension.</li><li>**[!UICONTROL Nicht wiederholende Instanz]**: Umfasst eindeutige Instanzen (nicht wiederholend) für die Dimension. Dies ist das im Fluss angewendete Modell, wenn Wiederholungsinstanzen ausgeschlossen werden.</li></ul>Ein Beispiel finden Sie unten im Abschnitt &quot;Attributionsmodelle&quot;. |
| **[!UICONTROL Und/Oder/Dann]** | Weist die Operatoren [!UICONTROL UND/ODER/DANN] zwischen Behältern oder Regeln zu. Mit dem Operator DANN können Sie [sequenzielle Filter definieren](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Metrik]** | (Grüne Seitenleiste) Metrik, die aus der Metrikliste gezogen und abgelegt wurde. |
| **[!UICONTROL X]** | (Löschen) Hiermit können Sie diesen Teil der Filterdefinition löschen. |
| **[!UICONTROL Zielgruppe aus Filter erstellen]** | Wenn Sie eine Audience aus einem Filter erstellen, können Sie den Filter zur Aktivierung für Adobe Experience Platform freigeben. [Weitere Informationen...](/help/components/audiences/audiences-overview.md) |
| **[!UICONTROL Suchkomponente]** | Durchsucht die Liste der Dimensionen, Filter oder Metriken. |
| **[!UICONTROL Dimensionen]** | (Liste) Die Liste der Dimensionen, die Sie in den Filter aufnehmen können. Klicken Sie auf die Kopfzeile zum Erweitern. |
| **[!UICONTROL Metriken]** | Die Liste der Metriken, die Sie in den Filter aufnehmen können. Klicken Sie auf die Kopfzeile zum Erweitern. |
| **[!UICONTROL Filter]** | Die Liste der vorhandenen Filter, die Sie in den Filter aufnehmen können. Klicken Sie auf die Kopfzeile zum Erweitern. |
| **[!UICONTROL Datenansichtsauswahl]** | Hier können Sie die Report Suite auswählen, unter der dieser Filter gespeichert wird. Sie können den Filter weiterhin in allen Datenansichten verwenden. |
| **[!UICONTROL Filtervorschau]** | Ermöglicht die Vorschau der Schlüsselmetriken, um festzustellen, ob ein gültiger Filter vorhanden ist und wie breit der Filter ist. Stellt die Aufschlüsselung des Datensatzes dar, den Sie erwarten können, wenn Sie diesen Filter anwenden. Zeigt 3 konzentrische Kreise und eine Liste mit der Anzahl und dem Prozentsatz der Übereinstimmungen für [!UICONTROL Personen], [!UICONTROL Sitzungen], und [!UICONTROL Berichtsausführung] für einen Filter, der mit einem Datensatz ausgeführt wird.<p>Dieses Diagramm wird sofort aktualisiert, nachdem Sie Ihre Filterdefinition erstellt oder geändert haben. |
| **[!UICONTROL Speichern]** oder **[!UICONTROL Abbrechen]** | Speichert oder bricht den Filter ab. Nach dem Klicken **[!UICONTROL Speichern]**, gelangen Sie zum Filter-Manager, in dem Sie den Filter verwalten können. |

## Erstellen eines Filters {#build-filters}

1. Ziehen Sie einfach eine Dimension, ein Filter- oder Metrikereignis aus dem linken Bereich in den [!UICONTROL Definitionen] -Feld.

   ![](assets/drag_n_drop_dimension.png)

1. Legen Sie den [Operator](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=de) im Dropdown-Menü fest.
1. Geben Sie für das ausgewählte Element einen Wert ein oder wählen Sie einen aus.
1. Fügen Sie, sofern erforderlich, mithilfe von **[!UICONTROL AND]**-, **[!UICONTROL OR]**- oder **[!UICONTROL THEN]**-Regeln weitere Behälter hinzu.
1. Nachdem Sie die Behälter platziert und die Regeln festgelegt haben, sehen Sie sich die Ergebnisse des Filters in der Validierungsdiagramm oben rechts an. Der Validator gibt den Prozentsatz und die absolute Anzahl der Seitenansichten, Besuche und eindeutigen Personen an, die mit dem erstellten Filter übereinstimmen.
1. under **[!UICONTROL Tags]**, [Tag](/help/components/filters/filters-tag.md) den Container durch Auswahl eines vorhandenen Tags oder Erstellen eines neuen.
1. Klicks **[!UICONTROL Speichern]** , um den Filter zu speichern.

   Sie werden zum [Filter Manager](/help/components/filters/manage-filters.md), wo Sie Filter auf verschiedene Arten taggen, freigeben und verwalten können.

## Hinzufügen von Containern {#containers}

Sie können [ein Framework aus Containern](/help/components/filters/filters-overview.md) erstellen und dann Logikregeln und Operatoren dazwischen platzieren.

1. Klicks **[!UICONTROL Optionen > Container hinzufügen]**.

   Eine neue [!UICONTROL **Ereignis**] Container ohne [!UICONTROL **Ereignis**] (Seitenansicht) identifiziert.

   ![](assets/new_container.png)

1. Ändern Sie gegebenenfalls den Behältertyp.
1. Ziehen Sie eine Dimension, einen Filter oder ein Ereignis aus dem linken Bereich in den Container.
1. Fügen Sie oben in der Definition weitere neue Behälter über die Schaltfläche **[!UICONTROL Optionen]** > **[!UICONTROL Behälter hinzufügen]** der obersten Ebene hinzu oder fügen Sie Behälter aus einem Behälter hinzu, um die Logik zu verschachteln.

   **OR**

   Wählen Sie eine oder mehrere Regeln aus und klicken Sie anschließend auf **[!UICONTROL Optionen]** > **[!UICONTROL Behälter aus Auswahl hinzufügen]**. Dadurch wird Ihre Auswahl zu einem separaten Behälter.

## Verwenden von Datumsbereichen {#date-ranges}

Sie können Filter erstellen, die rollierende Datumsbereiche enthalten, um Fragen zu laufenden Kampagnen oder Ereignissen zu beantworten.

Sie können beispielsweise einfach einen Filter erstellen, der &quot;alle, die in den letzten 60 Tagen einen Kauf getätigt haben&quot;enthält.

Sie erstellen einen Sitzungs-Container und fügen darin den [!UICONTROL Letzte 60 Tage] Zeitbereich und die Metrik [!UICONTROL Bestellungen größer als oder gleich 1], mit einem UND -Operator.

Im Folgenden finden Sie ein Video zur Verwendung rollierender Datumsbereiche in Filtern:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Stapeln von Filtern {#stack}

Die Stapelung von Filtern funktioniert, indem die Kriterien in jedem Filter mit einem &quot;und&quot;-Operator kombiniert und dann die kombinierten Kriterien angewendet werden. Dies kann in einem Workspace-Projekt direkt oder im Filter Builder erfolgen.

Wenn Sie beispielsweise einen Filter &quot;Mobiltelefonbenutzer&quot;und einen Filter &quot;US-Geografie&quot;stapeln, werden nur Daten für Mobiltelefonbenutzer in den USA zurückgegeben.

Stellen Sie sich diese Filter als Bausteine oder Module vor, die Sie in eine Filterbibliothek aufnehmen können, damit Benutzer sie nach Bedarf verwenden können. Auf diese Weise können Sie die Anzahl der benötigten Filter drastisch reduzieren. Angenommen, Sie haben 40 Filter:

* 20 für Mobiltelefonbenutzer in verschiedenen Ländern (USA_mobil, Deutschland_mobil, Frankreich_mobil, Brasilien_mobil usw.)
* 20 für Tabletbenutzer in verschiedenen Ländern (USA_tablet, Deutschland_tablet, Frankreich_tablet, Brasilien_tablet usw.)

Durch die Filterstapelung können Sie die Anzahl der Filter auf 22 reduzieren und sie nach Bedarf stapeln. Sie müssen diese Filter erstellen:

* Ein Filter für Mobilbenutzer
* Ein Filter für Tablet-Benutzer
* 20 Filter für die verschiedenen geografischen Regionen

>[!NOTE]
>
>Beim Stapeln von zwei Filtern werden diese standardmäßig durch eine AND-Anweisung verbunden. Dies kann nicht in eine OR-Anweisung geändert werden.

1. Navigieren Sie zum Filter-Builder.

1. Geben Sie einen Titel und eine Beschreibung für den Filter an.

1. Klicks **[!UICONTROL Filter anzeigen]** um die Liste der Filter im linken Navigationsbereich anzuzeigen.

1. Ziehen Sie die Filter, die Sie stapeln möchten, auf die Arbeitsfläche für die Filterdefinition.

1. Wählen Sie [!UICONTROL **Speichern**] aus.

## Attributionsmodelle {#attribution}

![](assets/attribution-models.jpg)

**Beispiel: Ereignisfilter, bei denen eVar 1 = A ist**

| Beispiel | A | A | A (persistent) | B | A | C |
|---|---|---|---|---|---|---|
| Wiederholend | X | X | X | – | X | – |
| Instanz | X | X | – | – | X | – |
| Nicht wiederholende Instanz | X | – | – | – | X | – |