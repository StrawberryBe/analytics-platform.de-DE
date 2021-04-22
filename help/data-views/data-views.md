---
title: Was ist eine Datenansicht in Customer Journey Analytics?
description: Eine Datenansicht gibt an, wie Datenelemente in der Customer Journey Analytics-Verbindung zu interpretieren sind, beispielsweise Metriken, Dimensionen, Sitzungen usw.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
translation-type: tm+mt
source-git-commit: 9b45873dbdc1a400b849723051d921b49bff6d65
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 88%

---

# Was ist eine Datenansicht?

Eine Datenansicht befindet sich auf einer Customer Journey Analytics-[Verbindung](/help/connections/create-connection.md). Eine Verbindung kombiniert einen oder mehrere Datensätze aus Adobe Experience Platform und verbindet sie mit Customer Journey Analytics. Die Datenansicht gibt an, wie Datenelemente in der Verbindung zu interpretieren sind, beispielsweise Metriken, Dimensionen, Sitzungen usw. Datenansichten werden zur Vorbereitung für das Reporting zu Daten in Workspace definiert.

>[!NOTE]
>
>Alle Einstellungen, die Sie in einer Ansicht auswählen oder ändern, sind rückwirkend und nicht zerstörerisch. Mit anderen Worten, sie ändern Ihre zugrunde liegenden Daten nicht dauerhaft.

Sie können verschiedene Datenansichten für die gleiche Verbindung mit sehr unterschiedlichen Komponentensätzen (Dimensionen/Metriken) erstellen. Außerdem können Sie Datenansichten mit unterschiedlichen Einstellungen für Besuchs-Timeout, Zuordnung usw. erstellen. Sie könnten beispielsweise eine Datendimensionen mit [!UICONTROL Last Touch] und gleichzeitig eine andere Ansicht mit Daten (basierend auf demselben Datensatz) haben, bei denen alle Dimensionen auf [!UICONTROL First Touch] eingestellt sind.

Workspace-Projekte in Customer Journey Analytics basieren auf Datenansichten.

## Neue Funktionen in Datenansichten

Die neueste Aktualisierung der Datenansichten bietet Ihnen viel mehr Flexibilität bei den Nutzungsmöglichkeiten von Datenansichten. Mit diesen Erweiterungen können Sie **die Schema-Elementeinstellungen in Datenansichten spontan ändern, ohne dass das Schema in Adobe Experience Platform geändert oder Ihre Customer Journey Analytics-Umgebung erneut implementiert werden muss**.

* **Sie können eine Komponente von einer Metrik in eine Dimension ändern und umgekehrt**. Sie können Metriken aus Zeichenfolgenfeldern oder Dimensionen aus numerischen Feldern erstellen. Dies erleichtert Ihnen das Leben, da Sie kein numerisches Feld in Ihrem XDM-Schema für jede gewünschte Metrik erstellen müssen. Stattdessen können Sie sie spontan im Dialog „Dateiansichten“ erstellen. Im Folgenden finden Sie einige Beispiele:
   * **Erstellen Sie eine oder mehrere Dimensionen und/oder eine Dimension aus einem Schema-Feld**. Es ist eine Eins-zu-viele-Beziehung. Sie können beispielsweise eine oder mehrere Umsatzmetriken und/oder eine oder mehrere Umsatzdimensionen aus einem einzigen Schemafeld erstellen.
   * **Verwenden Sie ein Zeichenfolgenfeld als Metrik**: Wenn Sie ein Schema in Experience Platform mit einem Datensatz füllen, wissen Sie möglicherweise nicht schon gleich zu Beginn, welche Schema-Elemente Sie benötigen. Beispielsweise war Ihnen noch nicht bewusst, dass Sie eine Metrik für „Fehler auf einer Seite“ benötigen. Daher haben Sie kein numerisches Schema-Element für diesen Zweck erstellt. Durch Verwendung eines Zeichenfolgen-Elements als Metrik können Sie jetzt mithilfe der Einstellungen für Datenansichten festlegen, dass jede Zeichenfolge, die das Wort „Fehler“ enthält, als Metrik verwendet werden kann.
   * **Verwenden eines numerischen Felds als Dimension**: Wenn Sie beispielsweise die Umsatzmetrik aus der Umsatzdimension ziehen möchten, zeigt die Umsatzdimension jeden Wert als Dimensionselement an (100 $, 175 $, 1.000 $ usw.) und die Anzahl der Instanzen für jedes Dimensionselement. Umsatz als Metrik verhält sich wie immer.

* **Sie können mehrere Metriken mit verschiedenen Zuordnungsmodellen oder mit unterschiedlichen Lookback-Fenstern** aus demselben Schemafeld erstellen.

* **Sie können die ID einer Komponente bearbeiten**. Dies wird zur Kompatibilität zwischen verschiedenen Datenansichten verwendet. Die Komponenten-ID wird von der Reporting-API zur Identifizierung einer bestimmten Metrik oder Dimension verwendet. Da Sie beliebig viele Metriken oder Dimensionen aus einem XDM-Feld erstellen können, haben Sie die Möglichkeit, Ihre eigene Komponenten-ID zu definieren. Daher kann eine Metrik, die Sie in einem Workspace-Projekt verwenden, über Datenansichten (und die API) hinweg kompatibel sein, auch wenn sie auf völlig unterschiedlichen Feldern aus unterschiedlichen Verbindungen oder Datenansichten oder aus einem anderen XDM-Schema basiert.

* **Sie können den Anzeigenamen der Komponente festlegen, der in Analysis Workspace angezeigt wird**. Standardmäßig wird dieser Name vom Anzeigenamen des Schemas übernommen, Sie können ihn jetzt jedoch für diese spezifische Ansicht überschreiben.

* **Sie können weitere Schema-bezogene Informationen zu Komponenten sehen**, beispielsweise von welchem Datensatztyp (Ereignis, Profil, Suche) sie stammen, von welchem Schema-Typ (String, Integer usw.) sie stammen und was der zugehörige Schema-Pfad ist (das XDM-Feld, auf dem sie basieren).

* **Sie können eine Komponente taggen**, um die Suche nach ihr in Workspace zu erleichtern.

* **Sie können eine Komponente in Berichten ausblenden**. Für einige Metrik- und Dimensionseinstellungen ist eine zweite Metrik oder Dimension für die Konfiguration erforderlich (beispielsweise für metrische Deduplizierung oder Kauf-Deduplizierung). Auf diese Weise können Sie eine Metrik oder Dimension definieren, die in den Einstellungen einer anderen Metrik oder Dimension verwendet werden kann, ohne dass sie direkt in Berichten auftaucht (beispielsweise eine Kauf-ID).

* **Sie können Formatierungen auf eine Metrik anwenden**, beispielsweise zur Darstellung von Dezimalstellen, Uhrzeiten, Prozentwerten oder Währungen, zur Anzeige der Dezimalstellen, zur grünen oder roten Darstellung von Aufwärtstrends oder zum Festlegen der Währungsoptionen.

* Sie können **eine Metrik oder Dimension nur auf Basis einiger Werte im Schemafeld erstellen**. Wenn Sie beispielsweise eine Metrik für „Fehler“ wünschen, können Sie eine Metrik aus dem Feld „Seitenname“ erstellen, aber nur Seiten einschließen, die das Wort „Fehler“ enthalten. Die auf dieser Grundlage erstellte Fehlermetrik wird von Filtern unterstützt, kann in berechnete Metriken eingefügt werden und funktioniert mit Attribution, Fluss, Fallout usw.

* Bei Dimensionen können Sie **automatisch nur bestimmte Werte in einem bestimmten Feld ein- oder ausschließen**. Wenn ein Entwickler beispielsweise einen falschen Wert von `dev mistake` in ein Feld gesendet hat, können Sie ihn mithilfe einer Ausschlussregel problemlos vom Bericht ausschließen und der Wert wird sich so verhalten, als ob er nie in den Daten vorhanden gewesen wäre.

* Sie können **Ihre Container in einer Datenansicht umbenennen** und diese umbenannten Container in jedem Workspace-Projekt platzieren, das auf dieser Datenansicht basiert.

## Voraussetzungen für die Ansicht von Daten

* Bevor Sie Datenansichten erstellen können, müssen Sie [eine oder mehrere Verbindungen zu Experience Platform-Datensätzen einrichten](/help/connections/create-connection.md).
* Zum Erstellen oder Verwalten einer Datenansicht benötigen Sie einen [Berechtigungssatz in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=de-DE#admin-access-permissions).

## Einstellungen für die Ansicht von Daten, die Sie in Workspace überschreiben können

Einige Einstellungen für die Datenansicht können in Analysis Workspace auf Projektebene überschrieben werden, andere nicht.

* [!UICONTROL Lookback-Fenster]
* Metrikzuordnung
* Gibt an, ob Benutzer den Zeileneintrag [!UICONTROL Kein Wert] in einem Bericht sehen

## Einstellungen für die Ansicht von Daten, die Sie in Workspace nicht überschreiben können

* [!UICONTROL Typ der Komponente]
* Formatierung von Metriken
* Name der Datenansicht
* Zuweisung von Dimensionen

## Löschen von Datenansichten

Wenn Sie eine Datenansicht in [!UICONTROL Customer Journey Analytics] löschen, wird eine Fehlermeldung angezeigt, die besagt, dass alle Workspace-Projekte, die von dieser gelöschten Datenansicht abhängig sind, nicht mehr funktionieren.

## Nächste Schritte

* [Ansichten erstellen](/help/data-views/create-dataview.md)
* [Anwendungsfälle zur Datenansicht](/help/data-views/data-views-usecases.md)
* Details zur Funktionsweise von [Persistenz](/help/data-views/persistence.md)
