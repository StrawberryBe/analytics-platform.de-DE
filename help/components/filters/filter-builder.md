---
description: Der Filter-Builder bietet eine Arbeitsfläche zum Ziehen und Ablegen von metrischen Dimensionen, Filtern und Ereignissen, um Personen basierend auf der Behälterhierarchielogik, den Regeln und Operatoren zu filtern. Mit diesem integrierten Entwicklungstool können Sie einfache oder komplexe Filter erstellen und speichern, mit denen Personenattribute und Aktionen bei Besuchen und Ereignissen identifiziert werden.
title: Erstellen von Filtern
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '2052'
ht-degree: 28%

---

# Filter Builder

Die [!UICONTROL Filter Builder] können Sie einfache oder komplexe Filter erstellen, mit denen Personenattribute und Aktionen über Besuche und Ereignisse hinweg identifiziert werden. Es bietet eine Arbeitsfläche zum Ziehen und Ablegen von Metrikdimensionen, Ereignissen oder anderen Filtern, um Personen basierend auf Hierarchielogik, Regeln und Operatoren zu filtern.

Informationen zum Erstellen von Schnellfiltern, die nur für das Projekt gelten, in dem sie erstellt werden, finden Sie unter [Schnellfilter](/help/components/filters/quick-filters.md).

## Zugriff auf den Filter-Builder

Sie haben folgende Möglichkeiten, auf den Filter-Builder zuzugreifen:

* **Obere Navigation in Analytics**: Klicken **[!UICONTROL Analytics]** > **[!UICONTROL Komponenten]** > **[!UICONTROL Filter]**.
* **[!UICONTROL Analysis Workspace]**: Öffnen Sie ein Projekt in Analysis Workspace und wählen Sie **[!UICONTROL + Komponenten]** > **[!UICONTROL Filter erstellen]**.
* **[!UICONTROL Reports &amp; Analytics]**: Klicken **[!UICONTROL Analytics]** > **[!UICONTROL Berichte]**, öffnen Sie einen vorhandenen Bericht und klicken Sie auf die **Filter** Symbol in der linken Navigation und klicken Sie dann auf **[!UICONTROL Hinzufügen]**.
* **[!UICONTROL Report Builder]**: [Filter in Report Builder hinzufügen oder bearbeiten](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/data-requests/segmentation.html?lang=de).

## Übersicht über Builder-Kriterien {#section_F61C4268A5974C788629399ADE1E6E7C}

Sie können Regeldefinitionen und Container hinzufügen, um Ihre Filter zu definieren. (Informationen zum Zugriff auf den Filter-Builder finden Sie unter [Zugriff auf den Filter-Builder](#access-the-filter-builder).

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Titel]**: Benennen Sie den Filter.
1. **[!UICONTROL Beschreibung]**: Geben Sie eine Beschreibung für den Filter ein.
1. **[!UICONTROL Tags]**: [Filter taggen](/help/components/filters/manage-filters.md) Sie erstellen, indem Sie aus einer Liste vorhandener Tags wählen oder ein neues Tag erstellen.
1. **[!UICONTROL Definitionen]**: Hier sind Sie [Filter erstellen und konfigurieren](/help/components/filters/filters-overview.md), fügen Sie Regeln hinzu und verschachteln und sequenzieren Sie Container.
1. **[!UICONTROL Anzeigen]**: (Auswahl des obersten Containers.) Ermöglicht die Auswahl der obersten Ebene [container](/help/components/filters/filters-overview.md) ( [!UICONTROL Person], [!UICONTROL Sitzung], [!UICONTROL Ereignis]). Der standardmäßige Container der obersten Ebene ist der Ereignis-Container.
1. **[!UICONTROL Optionen]**: (Zahnrad)-Symbol

   * **[!UICONTROL Behälter hinzufügen]**: Ermöglicht das Hinzufügen eines neuen Containers (unter dem obersten Behälter) zur Filterdefinition.
   * **[!UICONTROL Ausschließen]**: Hiermit können Sie den Filter definieren, indem Sie eine oder mehrere Dimensionen, Filter oder Metriken ausschließen.

1. **[!UICONTROL Dimensionen]**: Komponenten werden aus der Liste der Dimensionen (orangefarbene Seitenleiste) gezogen und abgelegt.
1. **[!UICONTROL Operator]**: Sie können Werte mithilfe ausgewählter Operatoren vergleichen und beschränken.
1. **[!UICONTROL Wert]**: Der Wert, den Sie für die Dimension, den Filter oder die Metrik eingegeben oder ausgewählt haben.
1. **[!UICONTROL Attributionsmodelle]**: Diese Modelle sind nur für Dimensionen verfügbar und bestimmen, nach welchen Werten in einer Dimension gefiltert werden soll. In sequenziellen Filtern sind Dimension-Modelle besonders nützlich.

   * **[!UICONTROL Wiederholend]** (Standard): Umfasst Instanzen und beibehaltene Werte für die Dimension.
   * **[!UICONTROL Instanz]**: Umfasst Instanzen für die Dimension.
   * **[!UICONTROL Nicht wiederholende Instanz]**: Umfasst eindeutige Instanzen (nicht wiederholend) für die Dimension. Dies ist das im Fluss angewendete Modell, wenn Wiederholungsinstanzen ausgeschlossen werden.

   ![](assets/attribution-models.jpg)

   **Beispiel: Ereignisfilter, bei dem eVar1 = A ist**

   | Beispiel | A | A | A (persistent) | B | A | C |
   |---|---|---|---|---|---|---|
   | Wiederholend | X | X | X | – | X | – |
   | Instanz | X | X | – | – | X | – |
   | Nicht wiederholende Instanz | X | – | – | – | X | – |
1. **[!UICONTROL And/Or/Then]**: Weist die [!UICONTROL AND/OR/THEN]-Operatoren zwischen Containern oder Regeln zu. Mit dem THEN -Operator können Sie [sequenzielle Filter definieren](/help/components/filters/filters-overview.md).
1. **[!UICONTROL Metrik]** (Grüne Seitenleiste): Metrik, die aus der Liste „Metriken“ gezogen und abgelegt wurde.
1. Operator **[!UICONTROL Vergleich]**: Sie können Werte mithilfe ausgewählter Operatoren vergleichen und beschränken.
1. **[!UICONTROL Wert]**: Der Wert, den Sie für die Dimension, den Filter oder die Metrik eingegeben oder ausgewählt haben.
1. **[!UICONTROL X]**: (Löschen) Hiermit können Sie diesen Teil der Filterdefinition löschen.
1. **[!UICONTROL Veröffentlichung von Experience Clouden]**: Wenn Sie einen Adobe Analytics-Filter in das Experience Cloud veröffentlichen, können Sie den Filter für die Marketing-Aktivität in [!DNL Audience Manager] und in anderen Aktivierungskanälen. [Weitere Informationen...](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=de)
1. **[!UICONTROL Zielgruppenbibliothek]**: Die Zielgruppendienste von Adobe verwalten die Übersetzung von Personendaten in Zielgruppenfilter. Auf diese Weise erfolgt die Erstellung und Verwaltung von Zielgruppen so ähnlich wie die Erstellung und Verwendung von Filtern, mit dem zusätzlichen Vorteil, dass der Zielgruppenfilter für das Experience Cloud freigegeben werden kann. [Weitere Informationen...](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=de)
1. **[!UICONTROL Suche]**: Durchsucht die Liste der Dimensionen, Filter oder Metriken.
1. **[!UICONTROL Dimensionen]** (Liste): Klicken Sie auf die Kopfzeile zum Erweitern.
1. **[!UICONTROL Metriken]**: Klicken Sie auf die Kopfzeile zum Erweitern.
1. **[!UICONTROL Filter]**: Klicken Sie auf die Kopfzeile zum Erweitern.
1. **[!UICONTROL Datenansichtsauswahl]**: Hier können Sie die Report Suite auswählen, unter der dieser Filter gespeichert wird. Sie können den Filter weiterhin in allen Datenansichten verwenden.
1. **[!UICONTROL Filtervorschau]**: Ermöglicht die Vorschau der Schlüsselmetriken, um festzustellen, ob ein gültiger Filter vorhanden ist und wie breit der Filter ist. Stellt die Aufschlüsselung des Datensatzes dar, den Sie erwarten können, wenn Sie diesen Filter anwenden. Zeigt 3 konzentrische Kreise und eine Liste mit der Anzahl und dem Prozentsatz der Übereinstimmungen für [!UICONTROL Ereignis], [!UICONTROL Person]und [!UICONTROL Sitzung] für einen Filter, der mit einem Datensatz ausgeführt wird. Dieses Diagramm wird sofort aktualisiert, nachdem Sie Ihre Filterdefinition erstellt oder geändert haben.
1. **[!UICONTROL Produktkompatibilität]**: Enthält eine Liste der Adobe Analytics-Produkte (Analysis Workspace, [!UICONTROL Reports &amp; Analytics], Data Warehouse), mit dem der von Ihnen erstellte Filter kompatibel ist. Die meisten Filter sind mit allen Produkten kompatibel. Es sind jedoch nicht alle Operatoren und Dimensionen mit allen Analytics-Produkten kompatibel. Dies betrifft insbesondere  [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). Dieses Diagramm wird sofort aktualisiert, nachdem Sie Ihre Filterdefinition geändert haben.
1. **[!UICONTROL Speichern]** oder **[!UICONTROL Abbrechen]**: Speichert oder bricht den Filter ab. Nach dem Klicken **[!UICONTROL Speichern]**, gelangen Sie zum Filter-Manager, in dem Sie den Filter verwalten können.

Filter mit eingebetteten Datumsbereichen funktionieren in Analysis Workspace weiterhin anders als [!UICONTROL Reports &amp; Analytics]: In Workspace überschreibt ein Filter mit einem eingebetteten Datumsbereich den Datumsbereich des Bedienfelds. Im Gegensatz dazu [!UICONTROL Reports &amp; Analytics] gibt die Schnittmenge des Datumsbereichs des Berichts und des eingebetteten Datumsbereichs des Filters an.

## Erstellen eines Filters {#build-filters}

1. Ziehen Sie einfach eine Dimension, ein Filter- oder Metrikereignis aus dem linken Bereich in den [!UICONTROL Definitionen] -Feld.

   ![](assets/drag_n_drop_dimension.png)

1. Legen Sie den [Operator](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html?lang=de) im Dropdown-Menü fest.
1. Geben Sie für das ausgewählte Element einen Wert ein oder wählen Sie einen aus.
1. Fügen Sie, sofern erforderlich, mithilfe von **[!UICONTROL AND]**-, **[!UICONTROL OR]**- oder **[!UICONTROL THEN]**-Regeln weitere Behälter hinzu.
1. Nachdem Sie die Behälter platziert und die Regeln festgelegt haben, sehen Sie sich die Ergebnisse des Filters in der Validierungsdiagramm oben rechts an. Der Validator gibt den Prozentsatz und die absolute Anzahl der Seitenansichten, Besuche und eindeutigen Personen an, die mit dem erstellten Filter übereinstimmen.
1. under **[!UICONTROL Tags]**, [Tag](/help/components/filters/manage-filters.md) den Container durch Auswahl eines vorhandenen Tags oder Erstellen eines neuen.
1. Klicken **[!UICONTROL Speichern]** , um den Filter zu speichern.

   Sie werden zum [Filter Manager](/help/components/filters/manage-filters.md), wo Sie Filter auf verschiedene Arten taggen, freigeben und verwalten können.

## Hinzufügen von Containern {#section_1C38F15703B44474B0718CEF06639EFD}

Sie können [ein Framework aus Containern](/help/components/filters/filters-overview.md) erstellen und dann Logikregeln und Operatoren dazwischen platzieren.

1. Klicken **[!UICONTROL Optionen > Container hinzufügen]**.

   Eine neue [!UICONTROL **Ereignis**] Container ohne [!UICONTROL **Ereignis**] (Seitenansicht) identifiziert.

   ![](assets/new_container.png)

1. Ändern Sie gegebenenfalls den Behältertyp.
1. Ziehen Sie eine Dimension, einen Filter oder ein Ereignis aus dem linken Bereich in den Container.
1. Fügen Sie oben in der Definition weitere neue Behälter über die Schaltfläche **[!UICONTROL Optionen]** > **[!UICONTROL Behälter hinzufügen]** der obersten Ebene hinzu oder fügen Sie Behälter aus einem Behälter hinzu, um die Logik zu verschachteln.

   **OR**

   Wählen Sie eine oder mehrere Regeln aus und klicken Sie anschließend auf **[!UICONTROL Optionen]** > **[!UICONTROL Behälter aus Auswahl hinzufügen]**. Dadurch wird Ihre Auswahl zu einem separaten Behälter.

## Verwenden von Datumsbereichen {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Sie können Filter erstellen, die rollierende Datumsbereiche enthalten, um Fragen zu laufenden Kampagnen oder Ereignissen zu beantworten.

Sie können beispielsweise einfach einen Filter erstellen, der &quot;alle, die in den letzten 60 Tagen einen Kauf getätigt haben&quot;enthält.

Sie erstellen einen Sitzungs-Container und fügen darin den [!UICONTROL Letzte 60 Tage] Zeitbereich und die Metrik [!UICONTROL Bestellungen größer als oder gleich 1], mit einem UND -Operator.

Im Folgenden finden Sie ein Video zur Verwendung rollierender Datumsbereiche in Filtern:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Stapeln von Filtern {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

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

1. Klicken **[!UICONTROL Filter anzeigen]** um die Liste der Filter im linken Navigationsbereich anzuzeigen.

1. Ziehen Sie die Filter, die Sie stapeln möchten, auf die Arbeitsfläche für die Filterdefinition.

1. Wählen Sie [!UICONTROL **Speichern**] aus.

## Vorlagen filtern {#concept_5098446CC78D441E93B8E4D1D1EA6558}

Filtervorlagen werden für gängige Anwendungsfälle von Filtern bereitgestellt, z. B. &quot;Erstbesuche&quot;oder &quot;Besuche von Mobilgeräten&quot;. Sie sind in Workspace-Projekten und im Filter Builder als Bausteine für neue Filter verfügbar.

Vorlagen werden mit dem Adobe-Logo „A“ gekennzeichnet. Nachfolgend sind einige Beispielvorlagen aufgeführt:

<table id="table_98B87D807E9344C9BEBF072C65D87B1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Vorlagenname </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Warenkorb vorzeitig verlassen </td> 
   <td colname="col2">Daten zu Personen anzeigen, die Artikel zu ihrem Warenkorb hinzugefügt, aber nichts bestellt haben. In der Filterdefinition ist der Behälter "Besuch". Die Regel für diesen sequenziellen Filter ist <p> Zusätze zum Warenkorb ist nicht null </p> <p>Dann </p> <p>Bestellungen gleich 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erstbesuche </td> 
   <td colname="col2">Daten zu Personen anzeigen, die maximal ein [1] Mal besucht haben. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Besuchsnummer gleich 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nichtkäufer </td> 
   <td colname="col2">Daten zu Personen anzeigen, die nicht an einem Bestellereignis teilgenommen haben. In der Filterdefinition ist der Behälter Besucher. Dieser Filter verwendet die Ausschlusslogik. Die Regel ist <p>Bestellungen ist nicht null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nicht-Einzelseitenbesuche (Keine Absprünge) </td> 
   <td colname="col2">Daten zu Personen anzeigen, die mehr als einen Besuch durchgeführt haben. In der Filterdefinition ist der Behälter Besucher. Dieser Filter verwendet die Ausschlusslogik. Die Regel ist <p>Einzelzugriff ist nicht null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Paid Search </td> 
   <td colname="col2">Daten zu Personen anzeigen, die aus einer gebührenpflichtigen Suche stammen. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Gebührenpflichtige Sucherkennung gleich 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Käufern </td> 
   <td colname="col2">Daten zu Personen anzeigen, die an einem Bestellereignis teilgenommen haben. In der Filterdefinition ist der Behälter Besucher. Die Regel ist <p>Bestellungen ist nicht null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rückkehrende Besucher </td> 
   <td colname="col2">Daten zu Personen anzeigen, die mindestens einen Besuch durchgeführt haben. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Besuchsnummer ist größer als 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Einzelseitenbesuche </td> 
   <td colname="col2"> Daten zu Besuchen anzeigen, bei denen ein Einzelseitenwert vorliegt, auch wenn während des Besuchs mehrere Seitenansichten übermittelt werden. Einzelseitenbesuche mit Exitlink-Ereignissen sind im Filter enthalten. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Einzelseitenbesuche gleich 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Angesehenes Produkt wurde nicht dem Warenkorb hinzugefügt </td> 
   <td colname="col2">Daten zu Personen anzeigen, die Produkte angesehen, aber keine Zusatz zum Warenkorb hatten. In der Filterdefinition ist der Behälter "Besuch". Die Regel für diesen sequenziellen Filter ist <p>Produktansichten ist nicht null </p> <p>Dann </p> <p> Warenkorbzusätze gleich 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besuche von Kampagnen </td> 
   <td colname="col2">Daten zu Personen anzeigen, die durch Kampagnen verwiesen wurden. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Trackingcode ist nicht null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besuche von Mobilgeräten </td> 
   <td colname="col2">Daten zu Personen anzeigen, die Mobilgeräte verwenden. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Mobiles Gerät ist ungleich null. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besuche über eine kostenlose Suche </td> 
   <td colname="col2">Daten zu Personen anzeigen, die nicht von einer gebührenpflichtigen Suche stammen. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Gebührenpflichtige Sucherkennung gleich 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besuche von Nicht-Mobilgerät </td> 
   <td colname="col2">Daten zu Personen anzeigen, die keine Mobilgeräte verwenden. In der Filterdefinition ist der Behälter "Besuch". Dieser Filter verwendet die Ausschlusslogik. Die Regel ist <p>Mobilgerätetyp gleich Mobiltelefon </p> <p>Oder </p> <p>Mobilgerätetyp gleich Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besuche von Smartphones </td> 
   <td colname="col2">Daten zu Personen anzeigen, die Smartphones verwenden. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Gerätetyp gleich Mobiltelefon. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besuche über Suchmaschinen </td> 
   <td colname="col2">Daten zu Personen anzeigen, die von Suchmaschinen verwiesen wurden. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Referrer-Typ gleich Suchmaschinen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besuche von sozialen Netzwerken aus </td> 
   <td colname="col2">Daten zu Personen anzeigen, die von Social Sites verwiesen wurden. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Referrer-Typ gleich soziale Netzwerke. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besuche von Tablets </td> 
   <td colname="col2">Daten zu Personen anzeigen, die Tablets verwenden. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Gerätetyp gleich Tablet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Besuche mit Besucher-ID-Cookie </td> 
   <td colname="col2">Daten von Personen zu Ihrer Site anzeigen, für die ein beständiges Cookie erforderlich ist. In der Filterdefinition ist der Behälter "Besuch". Die Regel ist <p>Beständiges Cookie gleich 1. </p> </td> 
  </tr> 
 </tbody> 
</table>