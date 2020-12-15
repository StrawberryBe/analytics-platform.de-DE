---
description: Liste der bekannten Einschränkungen in Adobe Analysis Workspace und der zugehörigen Komponenten
title: Bekannte Einschränkungen in Analysis Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 93%

---


# Bekannte Einschränkungen in Analysis Workspace

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Weitere Informationen ...](/help/getting-started/cja-aa.md)

Im Folgenden finden Sie eine Liste der bekannten Einschränkungen in Analysis Workspace und der zugehörigen Komponenten:

## Tabellen

* Datumsvergleichsspalten können nicht hinzugefügt werden, wenn Datumsbereiche oder Metriken als Tabellenzeilen verwendet werden.
* „Metrik aus Auswahl erstellen“ ist deaktiviert, wenn Segmente als Zeilen einer Tabelle verwendet werden. Darüber hinaus sollte die Option „Metrik aus Auswahl erstellen“ nicht auf datumsorientierte Spalten angewendet werden.
* Bedingte Formatierung für Aufschlüsselungszeilen kann keine benutzerdefinierten Bereiche verwenden.
* Tabellengesamtzeilen können nicht als Trend-Ansicht dargestellt werden, wenn die Einstellung für die Berechnung der Summen durch Addition der Zeilenwerte angewendet wird (üblicherweise bei statischen Zeilenelementen).
* Die [!UICONTROL Beitragsanalyse] kann [!UICONTROL nur] mit der Granularität _Täglich_ ausgeführt werden. Sie kann nicht mit Daten des Typs [!UICONTROL Stündlich], [!UICONTROL Wöchentlich] usw. ausgeführt werden.

## Visualisierungen

* Visualisierungen, die die Segmentierung nutzen, wie [!UICONTROL Fallout], [!UICONTROL Fluss], [!UICONTROL Kohorte] und [!UICONTROL Histogramm], können keine berechneten Metriken als Eingaben akzeptieren.
* [!UICONTROL Fluss]: Einstiegs-/Ausstiegsdimensionen, z. B. [!UICONTROL Entrypage], können nicht im Fluss verwendet werden.
* [!UICONTROL Kohorte]: Nur Ganzzahlen können als Kohortenkriterien verwendet werden.

<!--## Panels

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.<-->

## Komponenten > Filter

* Bestimmte Metriken und Dimensionen können nicht segmentiert werden, wie [!UICONTROL Vorfälle], [!UICONTROL Unique Visitors] usw.
* Bestimmte Komponenten und Operatoren sind nicht verfügbar, wenn ein Filter aus Workspace erstellt wird (im Gegensatz zu [!UICONTROL Komponenten > Filter]). Beispiel: IP-Adresse.

## Komponenten > Berechnete Metriken

* Berechnete Metriken können in bestimmten Visualisierungen nicht verwendet werden. Siehe „Visualisierungen“ oben.
* Berechnete Metriken können nicht im Bereich [!UICONTROL Attribution] verwendet werden, da berechnete Metriken selbst separate Attributionsmodelle enthalten können.
* Bestimmte Komponenten und Operatoren sind nicht verfügbar, wenn eine berechnete Metrik aus Workspace erstellt wird (im Gegensatz zu [!UICONTROL Komponenten > Segmente]). Beispiel: [!UICONTROL IP-Adresse].

## Komponenten > Datumsbereiche

* Benutzerdefinierte Datumsbereiche werden nicht unterstützt [!UICONTROL Dieser Tag im letzten Jahr], [!UICONTROL Dieser Tag im letzten Monat] usw.

## Komponenten > Berichtseinstellungen

* Einige der Einstellungen auf der Seite [!UICONTROL Berichtseinstellungen] gelten nicht. Analysis Workspace verwendet nur die [!UICONTROL Einstellungen für Sprache/Währung/Kodierung] am unteren Rand: [!UICONTROL Tausendertrennzeichen], [!UICONTROL Kodierung des terminierten Berichts] und [!UICONTROL CSV-Trennzeichen].

## Attribution IQ

* Eine Untergruppe von Metriken wird in [!UICONTROL Attribution IQ] nicht unterstützt. Eine vollständige Liste finden Sie in den [häufig gestellten Fragen zu Attribution IQ](../attribution/faq.md).
