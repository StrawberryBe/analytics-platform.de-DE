---
title: Was ist eine Ansicht der Daten in Customer Journey Analytics?
description: Eine Datenverbindung gibt an, wie Ansichten der Daten in der CJA-Verbindung wie Metriken, Dimensionen, Sitzungen usw. interpretiert werden sollen.
translation-type: tm+mt
source-git-commit: 1071ee32d0ff7fef1d3e96cb81c210dd521cedf0
workflow-type: tm+mt
source-wordcount: '1133'
ht-degree: 4%

---


# Was ist eine Ansicht von Daten?

>[!IMPORTANT]
>
>Diese Funktion ist ab dem 22. April 2021 allgemein verfügbar.

Eine Ansicht mit Daten befindet sich auf einem Customer Journey Analytics (CJA) [connection](/help/connections/create-connection.md). Eine Verbindung kombiniert einen oder mehrere Datensätze aus Adobe Experience Platform und verbindet sie mit CJA. Die Ansicht &quot;Daten&quot;gibt an, wie Datenelemente in der Verbindung interpretiert werden sollen, z. B. Metriken, Dimensionen, Sitzungen usw. Datendefinitionen werden zur Vorbereitung des Berichte auf die Daten in Workspace definiert.

Wenn Sie zuvor das herkömmliche Adobe Analytics verwendet haben, ähnelt eine Ansicht mit Daten einer Virtual Report Suite insofern, als es sich um eine gefilterte Ansicht der Daten handelt.

Sie können verschiedene Ansichten für die gleiche Verbindung erstellen, mit unterschiedlichen Einstellungen für Besuchs-Timeout, Zuordnung usw... Sie können auch mehrere Daten-Ansichten für einen Datensatz erstellen. Sie können beispielsweise eine Datendimensionen mit [!UICONTROL Last Touch] und gleichzeitig eine andere Datendimensionen mit [!UICONTROL First Touch]-Ansicht (basierend auf demselben Datensatz) mit allen Dimensionen mit First Touch verwenden.

Workspace-Projekte in Customer Journey Analytics basieren auf Datenansichten.

## Neue Funktionen in den Ansichten

Die neueste Aktualisierung der Daten-Ansichten bietet Ihnen viel mehr Flexibilität bei der Handhabung von Ansichten. Mit diesen Erweiterungen können Sie die Schema-Elementeinstellungen in Data-Ansichten spontan ändern, ohne das Schema in Adobe Experience Platform ändern oder Ihre CJA-Umgebung **erneut implementieren zu müssen.**

* **Sie können eine Komponente von einer Metrik in eine Dimension ändern und umgekehrt**. Sie können Metriken aus Zeichenfolgenfeldern erstellen oder Dimensionen aus numerischen Feldern erstellen. Dies erleichtert Ihnen das Leben, da Sie kein numerisches Feld in Ihrem XDM-Schema für jede gewünschte Metrik erstellen müssen. Stattdessen können Sie sie spontan im Dialogfeld &quot;Ansichten&quot;erstellen. Im Folgenden finden Sie einige Beispiele:
   * **Erstellen Sie eine oder mehrere und/oder eine Dimensionen aus einem Schema-Feld**. Es ist eine Eins-zu-viele-Beziehung. Sie können beispielsweise eine oder mehrere Umsatzmetriken und/oder eine oder mehrere Umsatzdimensionen aus einem Schema erstellen.
   * **Verwenden Sie ein Zeichenfolgenfeld als Metrik**: Wenn Sie ein Schema in Experience Platform mit einem Dataset füllen, wissen Sie möglicherweise nicht, welche Schema-Elemente Sie benötigen. Sie haben beispielsweise nicht erkannt, dass Sie eine Metrik für &quot;Fehler auf einer Seite&quot;benötigen. Daher haben Sie zu diesem Zweck kein numerisches Schema-Element erstellt. Durch Verwendung eines Zeichenfolgenelements als Metrik können Sie jetzt mithilfe der Ansichten für die Datenverarbeitung festlegen, dass ein String, der das Wort &quot;error&quot;enthält, als Metrik verwendet werden kann.
   * **Verwenden Sie ein numerisches Feld als Dimension**: Wenn Sie beispielsweise die Umsatzmetrik aus der Umsatzdimension ziehen möchten, zeigt die Umsatzdimension jeden Wert als Dimensionselement an ($100, $175, $1.000 usw.) und die Anzahl der Instanzen für jedes Dimensionselement. Umsatz als Metrik verhält sich wie immer.

* **Sie können mehrere Metriken mit verschiedenen Zuordnungsmodellen oder mit unterschiedlichen Lookback-** Fenstern aus demselben Schema erstellen.

* **Sie können die ID einer Komponente**  bearbeiten. Dies wird zur Kompatibilität zwischen Daten und Ansichten verwendet. Die Komponenten-ID wird von der Berichte-API zur Identifizierung einer bestimmten Metrik oder Dimension verwendet. Da Sie beliebig viele Metriken oder Dimensionen aus einem XDM-Feld erstellen können, können Sie Ihre eigene Komponenten-ID definieren. Daher kann eine Metrik, die Sie in einem Workspace-Projekt verwenden, über Datenverbindungen (und die API) hinweg kompatibel sein, auch wenn sie auf völlig unterschiedlichen Ansichten von verschiedenen Ansichten oder Daten oder von einem anderen Schema in XDM basiert.

* **Sie können den Anzeigenamen der Komponente festlegen, der in Analysis Workspace** angezeigt wird. Standardmäßig wird dieser Name vom Anzeigenamen des Schemas übernommen, Sie können ihn jetzt jedoch für diese spezifische Ansicht überschreiben. (So funktioniert die Komponentenkuration auch in Virtual Report Suites im traditionellen Adobe Analytics).

* **Sie können weitere Schema-bezogene Informationen zu Komponenten**  Ansicht erstellen, z. B.: welcher Datensatztyp (Ereignis, Profil, Suche) er stammt; welcher Schema-Typ (Zeichenfolge, Ganzzahl usw.) es stammt aus; und den zugehörigen Schema-Pfad (das XDM-Feld, auf dem es basiert).

* **Sie können eine** Komponente taggen, um die Suche in Workspace zu vereinfachen.

* **Sie können eine Komponente in Berichte** ausblenden. Für einige Metriken und Dimensionseinstellungen ist eine zweite Metrik oder Dimension für die Konfiguration erforderlich (z. B. metrisches Deduplizierung-Duplikate oder Deduplizierung-Duplikate zum Einkauf). Auf diese Weise können Sie eine Metrik oder Dimension definieren, die in den Einstellungen einer anderen Metrik oder Dimension verwendet werden kann, ohne direkt in Berichte angezeigt zu werden (z. B. Kauf-ID).

* **Sie können Formatierungen auf eine Metrik** anwenden, z. B. Dezimalstellen, Uhrzeiten, Prozentwerte oder Währungen. die Angabe von Dezimalstellen; Aufwärtstrend als grün oder rot; und die Währungsoptionen festlegen.

* Sie können **eine Metrik oder Dimension nur auf Basis einiger Werte im Feld Schema** erstellen. Wenn Sie z. B. eine Fehlermetrik wünschen, können Sie eine Metrik aus dem Feld &quot;Seitenname&quot;erstellen, aber nur Seiten einschließen, die das Wort &quot;Fehler&quot;enthalten. Die auf dieser Grundlage erstellte Fehlermetrik wird von Filtern unterstützt, kann in berechnete Metriken eingefügt werden und funktioniert mit Zuordnung, Fluss, Trichteranalyse usw.

* Bei Dimensionen können Sie **automatisch nur bestimmte Werte in einem bestimmten Feld** ein- oder ausschließen. Wenn ein Entwickler beispielsweise einen falschen Wert von `dev mistake` in ein Feld gesendet hat, können Sie ihn mithilfe einer Ausschlussregel problemlos vom Berichte ausschließen und sich so verhalten, als ob er nie in den Daten vorhanden wäre.

* Sie können Ihre Container in einer Data Ansicht umbenennen und diese umbenannten Container in jedem Workspace-Projekt platzieren, das auf dieser Data Ansicht basiert.****

## Voraussetzung

* Bevor Sie Datenansichten erstellen können, müssen Sie [eine oder mehrere Verbindungen zu Experience Platform-Datensätzen einrichten](/help/connections/create-connection.md).
* Zum Erstellen oder Verwalten einer Ansicht benötigen Sie einen [Berechtigungssatz in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=de-DE#admin-access-permissions).

## Informationen zur Ansicht einer Komponente

Klicken Sie in Workspace auf das Informationssymbol (i), um die Ansicht des Schema-Felds, auf dem eine Komponente basiert, und der zugehörigen Einstellungen, z. B. einer Beschreibung, zu treffen.

## Einstellungen für die Ansicht von Daten, die Sie in Workspace überschreiben können

Einige Einstellungen für die Ansicht von Daten können in Analysis Workspace auf Projektebene überschrieben werden, andere nicht.

* Lookback-Fenster
* Metrikzuordnung
* Ob Benutzer den Zeileneintrag &quot;Kein Wert&quot;in einem Bericht sehen

## Einstellungen für die Ansicht von Daten, die Sie in Workspace nicht überschreiben können

* Typ der Komponente
* Metrikformatierung
* Name der Datenansicht
* Zuweisung von Dimensionen

## Löschen von Datenansichten

Wenn Sie eine Ansicht mit Daten in [!UICONTROL Customer Journey Analytics] löschen, wird eine Fehlermeldung angezeigt, dass Workspace-Projekte, die von dieser Ansicht der gelöschten Daten abhängen, nicht mehr funktionieren.
