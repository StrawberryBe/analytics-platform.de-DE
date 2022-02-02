---
description: Liste der bekannten Einschränkungen in Adobe Analysis Workspace und der zugehörigen Komponenten
title: Bekannte Einschränkungen in Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 69%

---

# Bekannte Einschränkungen in Analysis Workspace

Im Folgenden finden Sie eine Liste der bekannten Einschränkungen in Analysis Workspace und der zugehörigen Komponenten:

## Tabellen

* Datumsvergleichsspalten können nicht hinzugefügt werden, wenn Datumsbereiche oder Metriken als Tabellenzeilen verwendet werden.
* Die Option Metrik aus Auswahl erstellen ist deaktiviert, wenn Filter als Zeilen einer Tabelle verwendet werden. Darüber hinaus sollte die Option „Metrik aus Auswahl erstellen“ nicht auf datumsorientierte Spalten angewendet werden.
* Bedingte Formatierung für Aufschlüsselungszeilen kann keine benutzerdefinierten Bereiche verwenden.
* Tabellengesamtzeilen können nicht als Trend-Ansicht dargestellt werden, wenn die Einstellung für die Berechnung der Summen durch Addition der Zeilenwerte angewendet wird (üblicherweise bei statischen Zeilenelementen).
* Die [!UICONTROL Beitragsanalyse] kann [!UICONTROL nur] mit der Granularität _Täglich_ ausgeführt werden. Sie kann nicht mit Daten des Typs [!UICONTROL Stündlich], [!UICONTROL Wöchentlich] usw. ausgeführt werden.

## Visualisierungen

* Visualisierungen, die Filter nutzen, z. B. [!UICONTROL Fallout], [!UICONTROL Fluss], [!UICONTROL Kohorte]und [!UICONTROL Histogramm], können keine berechneten Metriken als Eingaben akzeptieren.
* [!UICONTROL Fluss]: Einstiegs-/Ausstiegsdimensionen, z. B. [!UICONTROL Entrypage], können nicht im Fluss verwendet werden.
* [!UICONTROL Kohorte]: Nur Ganzzahlen können als Kohortenkriterien verwendet werden.

## Komponenten > Filter

* Bestimmte Metriken und Dimensionen können nicht gefiltert werden, z. B. [!UICONTROL Vorfälle], [!UICONTROL Unique Visitors], usw.
* Ad-hoc-Filter, die im [Bedienfeld-Dropzone](/help/analysis-workspace/c-panels/panels.md) wird nicht in der linken Leiste von Workspace oder im Komponenten-Manager für Filter angezeigt, es sei denn, sie werden veröffentlicht. Bearbeiten Sie dazu den Filter und wählen Sie **[!UICONTROL Filter öffentlich machen]**.

## Komponenten > Berechnete Metriken

* Berechnete Metriken können in bestimmten Visualisierungen nicht verwendet werden. Siehe „Visualisierungen“ oben.
* Berechnete Metriken können nicht im Bereich [!UICONTROL Attribution] verwendet werden, da berechnete Metriken selbst separate Attributionsmodelle enthalten können.
* Bestimmte Komponenten und Operatoren sind nicht verfügbar, wenn eine berechnete Metrik aus Workspace erstellt wird (im Gegensatz zu [!UICONTROL Komponenten > Filter]). Beispiel: [!UICONTROL IP-Adresse].

## Komponenten > Datumsbereiche

* Benutzerdefinierte Datumsbereiche werden nicht unterstützt [!UICONTROL Dieser Tag im letzten Jahr], [!UICONTROL Dieser Tag im letzten Monat] usw.


## Komponenten > Berichtseinstellungen

* Einige der Einstellungen auf der Seite [!UICONTROL Berichtseinstellungen] gelten nicht. Analysis Workspace verwendet nur die [!UICONTROL Einstellungen für Sprache/Währung/Kodierung] am unteren Rand: [!UICONTROL Tausendertrennzeichen], [!UICONTROL Kodierung des terminierten Berichts] und [!UICONTROL CSV-Trennzeichen].

## Attribution IQ

* Eine Untergruppe von Metriken wird in [!UICONTROL Attribution IQ] nicht unterstützt. Eine vollständige Liste finden Sie in den [häufig gestellten Fragen zu Attribution IQ](../attribution/faq.md).
