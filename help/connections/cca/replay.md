---
title: Funktionsweise der Wiederholung
description: Verstehen Sie das Konzept der "Wiederholung"in Cross-Kanal Analytics.
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 16%

---


# Funktionsweise der Wiederholung

Bei Analytics werden Daten über mehrere Kanal an eine bestimmte Verbindung weitergegeben:

* **Live-Heften**: Die CCA versucht, jeden Treffer beim Eintreten zu verbinden. Netto-neue Geräte mit dem Datensatz, die sich noch nicht angemeldet haben, werden in der Regel nicht auf dieser Ebene verknüpft. Bereits erkannte Geräte werden sofort zugeordnet.
* **Wiederholen**: CCA &quot;wiederholt&quot;Daten basierend auf eindeutigen Bezeichnern, die sie gelernt hat. In dieser Phase werden neue Geräte an die Verbindung angeschlossen. Adobe Angebot zwei Wiederholungsintervalle:
   * Täglich: Die Daten werden täglich mit einem 24-Stunden-Lookback-Fenster wiedergegeben. Diese Option bietet einen Vorteil, dass Wiederholungen viel häufiger auftreten, aber nicht authentifizierte Besucher müssen sich am Tag authentifizieren, an dem sie Ihre Site besuchen.
   * Wöchentlich: Daten werden einmal pro Woche mit einem 7-Tage-Lookback-Fenster wiedergegeben. Diese Option bietet einen Vorteil, der die Authentifizierung von nicht authentifizierten Sitzungen erheblich lockerer macht. Daten, die weniger als eine Woche alt sind, werden jedoch nicht zusammengeführt.

## Schritt 1: Live-Heften

CCA versucht, jedes Ereignis bei der Erfassung an bekannte Geräte und Kanal zu binden. Betrachten wir das folgende Beispiel, in dem Bob zwei verschiedene Kanal verwendet.

*Daten, wie sie am Tag der Erfassung erscheinen:*

| Zeitstempel | Beständige Webdataset-ID | Webdataset - Vorübergehende ID | Call-Center-Mitarbeiter-ID | Benutzer-ID verwendet | Erläuterung des Treffers | Metrik &quot;Personen&quot;(kumulativ) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | – | – | `246` | Bob besucht Ihre Site auf seinem Desktop, nicht authentifiziert | `1` (246) |
| `2` | `246` | `Bob` | – | `Bob` | Bob meldet sich auf dem Desktop an | `2` (246 und Bob) |
| `3` | – | – | `Bob` | `Bob` | Bob ruft den Kundendienst an | `2` (246 und Bob) |
| `4` | `3579` | – | – | `3579` | Bob greift auf Ihre Website auf seinem Mobilgerät zu, das nicht authentifiziert ist | `3` (246, Bob und 3579) |
| `5` | `3579` | `Bob` | – | `Bob` | Bob meldet sich über Mobilgeräte an | `3` (246, Bob und 3579) |
| `6` | – | – | `Bob` | `Bob` | Bob ruft erneut den Kundendienst an | `3` (246, Bob und 3579) |
| `7` | `246` | – | – | `Bob` | Bob besucht Ihre Site erneut auf seinem Desktop, nicht authentifiziert | `3` (246, Bob und 3579) |

Sowohl nicht authentifizierte als auch authentifizierte Ereignis auf neuen Geräten werden (vorübergehend) als separate Personen gezählt. Nicht authentifizierte Ereignis auf erkannten Geräten werden live zugeschnitten.

Die Attribution funktioniert, sobald die identifizierende benutzerdefinierte Variable mit einem Gerät verknüpft ist. Im obigen Beispiel sind alle Ereignis mit Ausnahme der Ereignis 1 und 4 live verbunden (sie verwenden alle den Bezeichner `Bob`). Die Zuordnung funktioniert auf den Ereignissen 1 und 4 nach der Wiederholungszuordnung.

## Schritt 2: Wiederholungszuordnung

In regelmäßigen Abständen (einmal pro Woche oder einmal am Tag, je nach ausgewähltem Lookback-Fenster) berechnet CCA historische Daten auf Grundlage von Geräten, die es jetzt erkennt. Wenn ein Gerät Daten anfänglich sendet, ohne authentifiziert zu sein, und sich dann anmeldet, verknüpft CCA diese nicht authentifizierten Ereignis mit der richtigen Person. Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch unterschiedliche Zahlen basierend auf der Wiederholung der Daten.

*Dieselben Daten nach der Wiederholung:*

| Zeitstempel | Beständige Webdataset-ID | Webdataset - Vorübergehende ID | Call-Center-Mitarbeiter-ID | Benutzer-ID verwendet | Erläuterung des Treffers | Metrik &quot;Personen&quot;(kumulativ) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | – | – | `Bob` | Bob besucht Ihre Site auf seinem Desktop, nicht authentifiziert | `1` (Bob) |
| `2` | `246` | `Bob` | – | `Bob` | Bob meldet sich auf dem Desktop an | `1` (Bob) |
| `3` | – | – | `Bob` | `Bob` | Bob ruft den Kundendienst an | `1` (Bob) |
| `4` | `3579` | – | – | `Bob` | Bob greift auf Ihre Website auf seinem Mobilgerät zu, das nicht authentifiziert ist | `1` (Bob) |
| `5` | `3579` | `Bob` | – | `Bob` | Bob meldet sich über Mobilgeräte an | `1` (Bob) |
| `6` | – | – | `Bob` | `Bob` | Bob ruft erneut den Kundendienst an | `1` (Bob) |
| `7` | `246` | – | – | `Bob` | Bob besucht Ihre Site erneut auf seinem Desktop, nicht authentifiziert | `1` (Bob) |

## Zusammenfassung

* Mit CCA werden bekannte Geräte sofort zusammengeführt, aber keine neuen oder nicht erkannten Geräte sofort zusammengeführt.
* Die Daten werden in regelmäßigen Abständen wiedergegeben und ändern historische Daten in der Verbindung auf der Grundlage von Geräten, die sie identifizieren gelernt haben.
