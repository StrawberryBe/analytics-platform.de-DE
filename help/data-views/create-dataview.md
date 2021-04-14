---
title: Erstellen einer neuen Daten-Ansicht in Customer Journey Analytics.
description: Beschreibt alle zum Erstellen neuer Ansichten erforderlichen Einstellungen.
exl-id: 35cbf69c-e1e5-4cf0-9bb4-6105d3e4c78e
translation-type: tm+mt
source-git-commit: 7cad7b1231b08b8311dd9a1d8e0b5a6da3af9c73
workflow-type: tm+mt
source-wordcount: '2802'
ht-degree: 12%

---

# Neue Ansicht erstellen

>[!IMPORTANT]
>
>Diese Funktion ist ab dem 22. April 2021 allgemein verfügbar.

Das Erstellen einer Ansicht umfasst entweder das Erstellen von Metriken und Dimensionen aus Schema-Elementen oder die Verwendung von Standardkomponenten. Die Erstellung von Metriken oder Dimensionen bietet Ihnen eine enorme Flexibilität. Bisher wurde davon ausgegangen, dass bei Datensätzen in Adobe Experience Platform Zeichenfolgenfelder als Dimensionen und numerische Felder als Metriken verwendet wurden. Um diese Felder zu ändern, mussten Sie Ihr Schema in Plattform bearbeiten. Die Benutzeroberfläche &quot;Ansichten&quot;ermöglicht jetzt eine [Freiformdefinition von Metriken und Dimensionen](/help/data-views/data-views.md). Weitere Anwendungsfälle finden Sie unter [Anwendungsfälle für Data Ansichten](/help/data-views/data-views-usecases.md).

## 1. Einstellungen und Container für Data Ansichten konfigurieren

1. Gehen Sie in Customer Journey Analytics zur Registerkarte **[!UICONTROL Datenansichten]**.
2. Klicken Sie auf **[!UICONTROL Hinzufügen]**, um eine neue Data Ansicht zu erstellen und deren Einstellungen zu konfigurieren.

![](assets/new-data-view.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Verbindung] | In diesem Feld wird die Ansicht der Daten mit der zuvor eingerichteten Verbindung verknüpft, die einen oder mehrere Adobe Experience Platform-Datensätze enthält. |
| [!UICONTROL Name] | Geben Sie der Datenansicht einen Namen. Dies ist ein Pflichtfeld. |
| [!UICONTROL Beschreibung] | Eine detaillierte Beschreibung ist nicht obligatorisch, wird jedoch empfohlen. |
| [!UICONTROL Zeitzone] | Wählen Sie die Zeitzone aus, in der Ihre Daten angezeigt werden sollen. |
| [!UICONTROL Tags] | Mit Tags können Sie Ihre Datenansichten in Kategorien organisieren. |
| [!UICONTROL Behälter] | Sie können Ihre Container hier umbenennen und so werden sie in jedem Workspace-Projekt angezeigt, das auf dieser Ansicht basiert. Container werden in Filtern und Fallout/Fluss usw. verwendet, um zu definieren, wie breit oder schmal der Umfang oder Kontext ist. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) |
| [!UICONTROL Name des Containers...] | [!UICONTROL Person]  (Standard). Der Container [!UICONTROL Person] enthält alle Besuche und Ansichten für Besucher innerhalb eines bestimmten Zeitraums. Sie können diesen Begriff in &quot;Benutzer&quot;oder einen anderen von Ihnen bevorzugten Begriff umbenennen. |
| [!UICONTROL Der Name des Session Containers lautet...] | [!UICONTROL Sitzung]  (Standard). Mit dem Container [!UICONTROL Sitzung] können Sie Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifizieren. Sie können diesen Begriff in &quot;Besuch&quot;oder einen anderen von Ihnen bevorzugten Begriff umbenennen. |
| [!UICONTROL Ereignis Container name ist...] | [!UICONTROL Ereignis]  (Standard). Der Container [!UICONTROL Ereignis] definiert, welche Ereignis von Seiten Sie in einen Filter einbeziehen oder ausschließen möchten. |

Als Nächstes können Sie Metriken und Dimensionen aus Schema-Elementen erstellen. Sie können auch Standardkomponenten verwenden.

## 2. Erstellen von Metriken und Dimensionen aus Schema-Elementen

1. Klicken Sie unter [!UICONTROL Customer Journey Analytics] > [!UICONTROL Data Ansichten] auf die Registerkarte [!UICONTROL Komponenten].

![](assets/components-tab.png)

Links oben sehen Sie die [!UICONTROL Verbindung], die die Datensätze und die [!UICONTROL Schema-Felder] enthält. Bedenken Sie Folgendes:

* Die bereits enthaltenen Komponenten sind die Standardkomponenten, die erforderlich sind (System generiert).
* Wir wenden den Filter **[!UICONTROL Enthält standardmäßig Daten]** an, sodass nur Schema-Felder mit Daten angezeigt werden. Wenn Sie nach einem Feld suchen, das keine Daten enthält, entfernen Sie einfach den Filter.

1. Ziehen Sie nun ein Schema, z. B. [!UICONTROL pageTitle], aus der linken Leiste in den Bereich Metriken oder Dimensionen.

   Sie können dasselbe Schema mehrmals in die Dimensionen oder Metrikabschnitte ziehen und dieselbe Dimension oder Metrik auf unterschiedliche Weise konfigurieren.
Beispielsweise können Sie im Feld **[!UICONTROL pageTitle]** eine Dimension namens &quot;Produktseiten&quot;und eine weitere Dimension &quot;Fehlerseiten&quot;usw. erstellen, indem Sie **[!UICONTROL Komponentenname]** rechts umbenennen. von **[!UICONTROL pageTitle]**; können Sie auch Metriken aus einem Zeichenfolgenwert erstellen. Sie können beispielsweise eine oder mehrere **[!UICONTROL Bestellungen]** Metriken mit unterschiedlichen Zuordnungseinstellungen und unterschiedlichen Ein-/Ausschlusswerten erstellen.

   ![](assets/components-tab-3.png)

   >[!NOTE]
   >
   >Sie können ganze Schema-Feldordner aus der linken Leiste ziehen und sie werden automatisch in herkömmliche Bereiche sortiert. Die Zeichenfolgenfelder werden im Abschnitt [!UICONTROL Dimensionen] und die Zahlen im Abschnitt [!UICONTROL Metriken] angezeigt. Sie können auch auf **[!UICONTROL Hinzufügen alle]** klicken und alle Schema-Felder werden hinzugefügt.

1. Nachdem Sie die Komponente ausgewählt haben, werden auf der rechten Seite eine Reihe von Einstellungen angezeigt. Konfigurieren Sie die Komponente mithilfe der unten beschriebenen Einstellungen.

### Komponenteneinstellungen konfigurieren

![](assets/component-settings.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Typ der Komponente] | Erforderlich. Ermöglicht es Ihnen, eine Komponente von Metrik in Dimension zu ändern oder umgekehrt. |
| [!UICONTROL Komponentenname] | Erforderlich. Hier können Sie den Anzeigenamen angeben, der in Analysis Workspace angezeigt wird. Sie können eine Komponente umbenennen, um ihr einen datenspezifischen Ansichten-spezifischen Namen zu geben. |
| [!UICONTROL Beschreibung] | Optional, aber empfohlen, um Informationen über die Komponente für andere Benutzer bereitzustellen. |
| [!UICONTROL Tags] | Optional. Ermöglicht das Taggen der Komponente mit benutzerdefinierten oder vordefinierten Tags zur einfacheren Suche/Filterung in der Analysis Workspace-Benutzeroberfläche. |
| [!UICONTROL Feldname] | Der Name des Schema-Felds. |
| [!UICONTROL Typ des Datensatzes] | Erforderlich. Ein nicht bearbeitbares Feld, das anzeigt, von welchem Datensatztyp (Ereignis, Suche oder Profil) die Komponente stammt. |
| [!UICONTROL Datensatz] | Erforderlich. Ein nicht bearbeitbares Feld, das anzeigt, von welchem Feldtyp die Komponente stammt (z. B. String, Integer usw.). Dieses Feld kann mehrere Datensätze enthalten. |
| [!UICONTROL Typ des Schemas] | Gibt an, ob es sich bei der Komponente um eine Zeichenfolge, eine Ganzzahl usw. handelt. |
| [!UICONTROL Komponenten-ID] | Erforderlich. Die [CJA-API](https://adobe.io/cja-apis/docs) verwendet dieses Feld, um auf die Komponente zu verweisen. Sie können auf das Bearbeitungssymbol klicken und diese Komponenten-ID ändern. Wenn Sie diese Komponenten-ID ändern, werden jedoch alle vorhandenen Workspace-Projekte, die diese Komponente enthalten, umgangen.<br>Wenn Sie jemals eine andere Datenfelddimension erstellen, die ein anderes Ansicht für eine pageTitle-Dimension verwendet, können Sie diese umbenennen und die Ansicht der Dimension für Datenübergreifende Inhalte kompatibel machen. |
| [!UICONTROL Path] | Erforderlich. Ein nicht bearbeitbares Feld, das den Schema-Pfad anzeigt, von dem die Komponente stammt. |
| [!UICONTROL Komponente in Reports verbergen] | Standard = aus. Ermöglicht das Kuratieren der Komponente aus der Data-Ansicht, wenn sie in Berichte verwendet wird. Dies wirkt sich nicht auf Berechtigungen aus, sondern nur auf die Kuratierung von Komponenten. Mit anderen Worten, Sie können die Komponente in Berichte vor Nicht-Admins ausblenden. Administratoren können weiterhin darauf zugreifen, indem sie in einem Analysis Workspace-Projekt auf [!UICONTROL Alle Komponenten anzeigen] klicken. |

### Formateinstellungen konfigurieren

Die Formateinstellungen gelten nur für Metriken.

![](assets/format-settings.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Format] | Hier können Sie die Formatierung einer Metrik als Dezimal, Zeit, Prozent oder Währung angeben. |
| [!UICONTROL Dezimalstellen] | Hier können Sie die Anzahl der Dezimalstellen angeben, die eine Metrik anzeigen soll. |
| [!UICONTROL Aufwärts-Trend anzeigen als] | Hier können Sie angeben, ob ein Aufwärtstrend bei dieser Metrik als gut (grün) oder schlecht (rot) zu betrachten ist. |
| [!UICONTROL Währung] | Diese Einstellung wird nur angezeigt, wenn das ausgewählte Metrikformat [!UICONTROL Währung] lautet. Es steht eine Liste von Währungsoptionen zur Verfügung. Der Standardwert ist keine Währung. Auf diese Weise können Sie den Umsatz in der Währung Ihrer Wahl im Berichte darstellen. Dies ist keine Währungskonvertierung, sondern nur eine Formatierungsoption der Benutzeroberfläche. |

### Konfigurieren der Zuordnungseinstellungen

![](assets/attribution-settings.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Attribution festlegen] | Hier können Sie die Zuordnungseinstellungen angeben, die Sie bei Verwendung dieser Metrik standardmäßig anwenden möchten. Dieser Standard kann in einer Freiformtabelle oder in einer berechneten Metrik überschrieben werden. |
| [!UICONTROL Attributionsmodell] | Ermöglicht die Angabe eines Standardzuordnungsmodells - nur aktiv, wenn Sie die Einstellung [!UICONTROL Nicht standardmäßiges Zuordnungsmodell verwenden] aktivieren. Die Standardeinstellung ist [!UICONTROL Letztkontakt]. Die Optionen sind: Last Touch, First Touch, Linear, Participation, Same Touch, U-Shaped, J Curve, Inverse J, Time Decay, Custom, Algorithmic. Einige dieser Optionen erstellen zusätzliche Felder, die ausgefüllt werden müssen, z. B. &quot;Benutzerdefiniert&quot;oder &quot;Zeitraum&quot;. Sie können mehrere Metriken mit demselben Feld erstellen. Dies bedeutet, dass Sie eine [!UICONTROL Last touch] Umsatzmetrik und eine [!UICONTROL First Touch] Umsatzmetrik haben können, die jedoch auf demselben Umsatzfeld im Schema basiert. |
| [!UICONTROL Lookback-Fenster] | Ermöglicht die Angabe eines standardmäßigen Lookback-Fensters für eine Metrik - nur aktiv, wenn Sie die Einstellung [!UICONTROL Nicht standardmäßiges Zuordnungsmodell verwenden] aktivieren. Die Optionen sind: Person (Berichte-Fenster), Sitzung, Benutzerdefiniert. Wenn &quot;Benutzerdefiniert&quot;ausgewählt ist, können Sie auch eine beliebige Anzahl von Tagen/Wochen/Monaten/usw. auswählen. (bis zu 90 Tage), genau wie Attribution IQ. Sie können über mehrere Metriken verfügen, die dasselbe Schema verwenden, jedoch jeweils ein separates Lookback-Fenster. |

### Einstellungen zum Einschließen/Ausschließen von Werten konfigurieren

Mit dieser Einstellung können Sie die zugrunde liegenden Daten, auf denen Sie Berichte sind, zur Abfrage ändern. Es ist nicht dasselbe wie ein Filter. Aber Filter werden diese neue Dimension respektieren, ebenso wie Pfade und Zuordnungen.

Sie können beispielsweise eine Dimension aus dem Feld &quot;pageTitle&quot;erstellen, sie aber als &quot;Fehlerseiten&quot;bezeichnen und jede Seite einschließen, die [!UICONTROL die Wortgruppe] &quot;error&quot;enthält.

![](assets/include-exclude.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Von Schreibweise abhängig] | Standard = Ein. Diese Einstellung gilt nur für den Abschnitt [!UICONTROL Werte einschließen/ausschließen]. Damit können Sie angeben, ob bei der Regel zum Ein-/Ausschließen, die Sie anwenden, die Groß-/Kleinschreibung beachtet werden soll. |
| [!UICONTROL Übereinstimmung] | Ermöglicht die Angabe der Werte, die Sie für den Berichte vor der Zuordnung und den Filtern berücksichtigen möchten (z. B. nur Werte mit der Wortgruppe &quot;error&quot;). Sie können Folgendes angeben: **[!UICONTROL Wenn alle Kriterien erfüllt sind]** oder **[!UICONTROL Wenn ein Kriterium erfüllt ist]**. |
| [!UICONTROL Kriterien] | Hier können Sie die Übereinstimmungslogik angeben, die auf eine bestimmte Filterregel angewendet werden soll.<ul><li>**Zeichenfolge**: Enthält die Wortgruppe, Enthält einen Begriff, enthält alle Begriffe, enthält keinen Begriff, enthält nicht die Wortgruppe, Ist gleich, Ist nicht gleich, Beginn mit, endet mit</li><li>**Dublette/Ganzzahl**: gleich, ungleich, größer als, kleiner als, größer gleich oder gleich, kleiner gleich oder gleich</li><li>**Datum**: gleich, ungleich, ist später als, liegt vor, tritt innerhalb von</li></ul> |
| [!UICONTROL Übereinstimmungs-Operand] | Hiermit können Sie den Übereinstimmungs-Operanden angeben, auf den der Übereinstimmungsoperator angewendet werden soll.<ul><li>**Zeichenfolge**: Textfeld</li><li>**Dublette/Ganzzahl**: Textfeld mit Nach-oben-/Nach-unten-Pfeilen für numerische Werte</li><li>**Datum**: Granularitätsauswahl Tag (Kalender)</li><li>**Datums-Zeit**: Auswahl der Datums- und Uhrzeitgranularität</li></ul> |
| [!UICONTROL Regel hinzufügen] | Hiermit können Sie einen zusätzlichen Übereinstimmungsoperator und -opern angeben. |

### Verhaltenseinstellungen konfigurieren

![](assets/behavior-settings.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Instanzen zählen] | Hiermit können Sie festlegen, ob ein numerisches Feld oder ein Datumsfeld, das als Metrik verwendet wird, statt des Werts selbst gezählt werden soll, wie lange es festgelegt wurde.<br> Wenn Sie die Instanzen eines numerischen Felds hinzufügen möchten und einfach die Anzahl der  ** Einstellungen eines Felds anstatt des tatsächlichen Werts darin addieren möchten.<br>Dies ist beispielsweise hilfreich, um eine   Bestellmetrik aus einem   Umsatzfeld zu erstellen. Wenn der Umsatz festgelegt wurde, sollten wir 1 einzelne Bestellung anstelle des numerischen Umsatzbetrags zählen. |

### Einstellungen für [!UICONTROL Keine Wertoptionen] konfigurieren

[!UICONTROL Keine ] Wertoptionen sind im Berichte identisch mit   Nicht festgelegten oder   Nicht-Werten. In der Benutzeroberfläche &quot;Ansichten&quot;können Sie für jede Komponente festlegen, wie diese Werte in Berichte behandelt werden sollen. Sie können [!UICONTROL Kein Wert] auch in etwas umbenennen, das Ihrer Umgebung besser entspricht, z. B. [!UICONTROL Null], [!UICONTROL Nicht festgelegt] oder andere.

Beachten Sie außerdem, dass das, was Sie in diesem Feld angeben, für eine spezielle UI-Behandlung des Zeileneintrags [!UICONTROL Kein Wert] in Berichte verwendet werden kann, wie in der Einstellung [!UICONTROL Keine Wertoptionen] beschrieben.

![](assets/no-value-options.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Wenn angezeigt, wird &quot;Kein Wert&quot;aufgerufen...] | Hier können Sie **[!UICONTROL Kein Wert]** in etwas Anderes umbenennen. |
| [!UICONTROL Kein Wert standardmäßig anzeigen] | Zeigt diesen Wert nicht in Berichte an. |
| [!UICONTROL Standardmäßig keinen Wert anzeigen] | Zeigt diesen Wert in Berichte an. |
| [!UICONTROL Kein Wert als Wert behandeln] | Diese Einstellung ersetzt leere Werte in den Daten durch den Text, den Sie unter [!UICONTROL Wenn angezeigt, &quot;Kein Wert&quot; angeben ...]. Wenn Sie beispielsweise Mobilgerätetypen als Dimension haben, können Sie das Element **[!UICONTROL Kein Wert]** in &quot;Desktop&quot;umbenennen. Beachten Sie, dass beim Ändern dieses Felds in einen benutzerdefinierten Wert der benutzerdefinierte Wert als legitimer Zeichenfolgenwert behandelt wird. Wenn Sie also den Wert &quot;Red&quot;in dieses Feld eingeben, werden alle Instanzen der Zeichenfolge &quot;Red&quot;in den Daten selbst ebenfalls unter dem von Ihnen angegebenen Zeileneintrag rollierend. |

### Persistenzeinstellungen konfigurieren

![](assets/persistence.png)

Weitere Informationen finden Sie im Thema [Persistenz](/help/data-views/persistence.md).

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Persistenz festlegen] | Schlüssel umschalten |
| [!UICONTROL Zuordnung] | Hier können Sie das Zuordnungsmodell angeben, das für eine Dimension für Persistenz verwendet wird. Die Optionen sind: [!UICONTROL Zuletzt verwendet], [!UICONTROL Original], [!UICONTROL Instanz], [!UICONTROL Alle]. Wenn ein Wert beibehalten werden soll (ähnlich wie bei eVars in herkömmlichen Analytics), legen Sie ihn hier fest. Der einzige wichtige Unterschied besteht darin, dass die maximale Persistenz, die Sie einstellen können, 90 Tage beträgt. Außerdem ist [!UICONTROL Niemals ablaufen] keine Option. |
| [!UICONTROL Ablauf] | Hiermit können Sie das Persistenzfenster für eine Dimension angeben. Die Optionen sind: [!UICONTROL Sitzung] (Standard), [!UICONTROL Person], [!UICONTROL Zeit], [!UICONTROL Metrik]. Möglicherweise müssen Sie die Dimension bei einem Kauf ablaufen lassen (z. B. interne Suchbegriffe oder andere Merchandising-Verwendungsfälle).  Metriken, die Sie als Ablaufdatum für diese Dimension festlegen (z. B. eine   Kaufmetrik). |

### Einstellungen für die Wertberechnung konfigurieren

So wird beispielsweise ein Bucket mit dem Wert &quot;zwischen 5 und 10&quot;als Zeileneintrag &quot;5 bis 10&quot;im Workspace-Berichte angezeigt.

![](assets/value-bucketing.png)

| Einstellung | Beschreibung/Verwendungsfall |
| --- | --- |
| [!UICONTROL Bucket-Wert] | Ermöglicht das Erstellen einer zusammengefassten Version einer numerischen Dimension. Auf diese Weise können Sie Berichte zu Umsatzbehältern oder anderen numerischen Werten als Dimension in Berichte erstellen. |
| [!UICONTROL Bis zu] | Hier können Sie die Grenzen des ersten numerischen Dimensionsbuckets angeben. Dies gilt nur für numerische Dimensionen. |
| [!UICONTROL Zwischen und bis] | Hier können Sie die Grenzen der nachfolgenden numerischen Dimensionsbehälter angeben. |
| [!UICONTROL Bucket hinzufügen] | Ermöglicht das Hinzufügen eines weiteren Behälters zum Bucket für numerische Dimensionen. |

### Verwenden Sie [!UICONTROL Standardkomponenten]

Neben der Erstellung von Metriken und Dimensionen aus Schema-Elementen können Sie auch Standardkomponenten in Ihren Daten-Ansichten verwenden.

[!UICONTROL Standardkomponenten ] sind Komponenten, die nicht aus Datenaset-Schema-Feldern generiert werden, sondern stattdessen vom System generiert werden. Einige Systemkomponenten sind in jeder Data Ansicht erforderlich, um die Funktionen des Berichte in Analysis Workspace zu erleichtern, andere Systemkomponenten sind optional.

![](assets/standard-components.png)

Erforderliche Standardkomponenten werden standardmäßig zu Ihrer Ansicht hinzugefügt.

| Komponentenname | Dimension oder Metrik | Hinweise |
| --- | --- | --- |
| [!UICONTROL Personen] | Metrik | Diese Metrik basiert auf der in einer Verbindung angegebenen Person-ID. |
| [!UICONTROL Sitzungen] | Metrik | Diese Metrik basiert auf den unten angegebenen Sitzungseinstellungen. |
| [!UICONTROL Ereignisse] | Metrik | Diese Metrik stellt die Anzahl der Zeilen aus allen Ereignis-Datensätzen in einer Verbindung dar. |
| [!UICONTROL Tag] | Dimension | Die Dimension &quot;Tag&quot;zeigt den Tag an, an dem eine bestimmte Metrik aufgetreten ist. Das erste Dimensionselement ist der erste Tag im Datumsbereich und das letzte Dimensionselement der letzte Tag im Datumsbereich. |
| [!UICONTROL Woche] | Dimension | Die Dimension &quot;Woche&quot;zeigt die Woche an, in der eine bestimmte Metrik aufgetreten ist. Das erste Dimensionselement ist die erste Woche im Datumsbereich und das letzte Dimensionselement die letzte Woche im Datumsbereich. |
| [!UICONTROL Monat] | Dimension | Die Dimension &quot;Monat&quot;zeigt den Monat an, in dem eine bestimmte Metrik aufgetreten ist. Das erste Dimensionselement ist der erste Monat im Datumsbereich und das letzte Dimensionselement der letzte Monat im Datumsbereich. |
| [!UICONTROL Quartal] | Dimension | Die Dimension &quot;Quartal&quot;zeigt das Quartal an, in dem eine bestimmte Metrik aufgetreten ist. Das erste Dimensionselement ist das erste Quartal im Datumsbereich und das letzte Dimensionselement das letzte Quartal im Datumsbereich. |
| [!UICONTROL Jahr] | Dimension | Die Dimension &quot;Jahr&quot;zeigt das Jahr an, in dem eine bestimmte Metrik aufgetreten ist. Das erste Dimensionselement ist das erste Jahr im Datumsbereich und das letzte Dimensionselement das letzte Jahr im Datumsbereich. |
| [!UICONTROL Stunde] | Dimension | Die Dimension &quot;Stunde&quot;gibt die Stunde an, zu der eine bestimmte Metrik aufgetreten ist (abgerundet). Das erste Dimensionselement ist die erste Stunde im Datumsbereich und das letzte Dimensionselement die letzte Stunde im Datumsbereich. |
| [!UICONTROL Minute] | Dimension | Die Dimension &quot;Minute&quot;berichtet, in welchem Moment eine bestimmte Metrik aufgetreten ist (abgerundet). Das erste Dimensionselement ist die erste Minute im Datumsbereich und das letzte Dimensionselement die letzte Minute im Datumsbereich. |

### Optionale Standardkomponenten

Optionale Standardkomponenten sind auf der Registerkarte **[!UICONTROL Standardkomponenten]** verfügbar.

| Komponentenname | Dimension oder Metrik | Hinweise |
| --- | --- | --- |
| [!UICONTROL Sitzung beginnt] | Metrik | Diese Metrik zählt die Anzahl der Ereignis, die das erste Ereignis einer Sitzung waren. Bei Verwendung in einer Filterdefinition (z. &#39;[!UICONTROL Session Beginns] existiert&quot;), wird nur das erste Ereignis jeder Sitzung Filter. |
| [!UICONTROL Sitzung endet] | Metrik | Diese Metrik zählt die Anzahl der Ereignis, die das letzte Ereignis einer Sitzung waren. Ähnlich wie [!UICONTROL Sitzungs-Beginn] kann es auch in einer Filterdefinition verwendet werden, um Dinge bis zum letzten Ereignis jeder Sitzung zu filtern. |
| [!UICONTROL Aufgewendete Zeit (Sekunden)] | Metrik | Die Metrik [!UICONTROL Besuchszeit] addiert die Zeit zwischen zwei verschiedenen Werten für eine Dimension. |
| [!UICONTROL Aufgewendete Zeit pro Ereignis] | Dimension | [!UICONTROL Die Zeit pro ] Ereignis fasst die  [!UICONTROL Besuchszeit ] in   Eventbuckets zusammen. |
| [!UICONTROL Aufgewendete Zeit pro Sitzung] | Dimension | [!UICONTROL Die Zeit pro ] Sitzung erfasst die  [!UICONTROL Besuchszeit ] in   Sessionbuckets. |
| [!UICONTROL Aufgewendete Zeit pro Person] | Dimension | [!UICONTROL Die Zeit pro ] Personbucket ordnet die  [!UICONTROL Besuchszeitmetrik ] in   Personbuckets ein. |
| [!UICONTROL Batch-ID] | Dimension | Stellt den Experience Platformen-Stapel dar, zu dem ein [!UICONTROL Ereignis] gehört hat. |
| [!UICONTROL Datensatz-ID] | Dimension | Stellt den Dataset der Experience Platform dar, zu dem ein [!UICONTROL Ereignis] gehört. |

### Filtern von Schema-Feldern und Dimensionen/Metriken

Sie können die Schema-Felder in der linken Leiste nach folgenden Datentypen filtern:

![](assets/filter-fields.png)

Sie können auch nach Datensätzen und danach filtern, ob ein Schema Daten enthält oder ob es sich um eine Identität handelt. Standardmäßig wird der Filter **[!UICONTROL Enthält Daten]** auf alle Ansichten angewendet.

![](assets/filter-other.png)


## 3. hinzufügen einer globalen Ansicht

Sie können Filter hinzufügen, die für die gesamte Ansicht der Daten gelten. Dieser Filter wird auf alle Berichte angewendet, die Sie in Workspace ausführen.

1. Klicken Sie auf die Registerkarte [!UICONTROL Settings] in [!UICONTROL Data Ansichten].
1. Ziehen Sie einen Filter aus der Liste in der linken Leiste in das Feld [!UICONTROL Hinzufügen Filter].
