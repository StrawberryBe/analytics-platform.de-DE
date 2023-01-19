---
title: Funktionsweise der Wiederholung
description: Das Konzept der „Wiederholung“ in Cross-Channel Analytics
exl-id: 1100043a-4e4f-4dbc-9cfc-9dcba5db5f67
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: 11ad1c91d07e8d4d6dd0186de68b1cc1d715ffe1
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 100%

---

# Funktionsweise der Wiederholung

Cross-Channel Analytics führt zwei Durchläufe der Daten für eine bestimmte Verbindung durch:

* **Echtzeit-Zuordnung**: Die CCA versucht, jeden ankommenden Treffer zuzuordnen. Neue Geräte im Datensatz, die noch nie angemeldet wurden, werden in der Regel nicht auf dieser Ebene zugeordnet. Bereits erkannte Geräte werden sofort zugeordnet.
* **Wiederholen**: CCA wiederholt Daten basierend auf eindeutigen Kennungen, die es gelernt hat. In dieser Phase werden neue Geräte in der Verbindung zugeordnet. Adobe bietet zwei Wiederholungsintervalle:
   * Täglich: Die Daten werden täglich mit einem 24-Stunden-Lookback-Fenster wiederholt. Diese Option bietet den Vorteil, dass Wiederholungen viel häufiger vorkommen. Nicht authentifizierte Besucher müssen sich jedoch an dem Tag authentifizieren, an dem sie Ihre Website besuchen.
   * Wöchentlich: Die Daten werden einmal pro Woche mit einem 7-Tage-Lookback-Fenster wiederholt. Diese Option bietet den Vorteil, dass nicht authentifizierte Sitzungen über einen weniger eng gefasst Zeitraum für die Authentifizierung verfügen. Daten, die weniger als eine Woche alt sind, werden jedoch nicht zugeordnet.

Daten, die über das Lookback-Fenster hinausgehen, werden nicht wiederholt. Ein Besucher muss sich innerhalb eines gegebenen Lookback-Fensters authentifiziert haben, damit ein nicht authentifizierter Besuch und ein authentifizierter Besuch gemeinsam identifiziert werden können. Sobald ein Gerät erkannt wurde, wird es von diesem Punkt an live zugeordnet.

## Schritt 1: Echtzeit-Zuordnung

Die CCA versucht bei der Erfassung, jedes Ereignis bekannten Geräten und Kanälen zuzuordnen. Betrachten wir das folgende Beispiel, in dem Bob zwei Kanäle verwendet.

*Daten, wie sie am Tag der Erfassung erscheinen:*

| Zeitstempel | Beständige Web-Datensatz-ID | Vorübergehende Web-Datensatz-ID | Callcenter-Mitarbeiter-ID | Verwendete Benutzer-ID | Erläuterung des Treffers | Metrik „Personen“ (kumulativ) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | – | – | `246` | Bob besucht Ihre Website auf seinem Desktop und ist nicht authentifiziert. | `1` (246) |
| `2` | `246` | `Bob` | – | `Bob` | Bob meldet sich auf seinem Desktop an. | `2` (246 und Bob) |
| `3` | – | – | `Bob` | `Bob` | Bob ruft den Kundendienst an | `2` (246 und Bob) |
| `4` | `3579` | – | – | `3579` | Bob greift über sein Smartphone oder Tablet auf Ihre Website zu und ist nicht authentifiziert | `3` (246, Bob und 3579) |
| `5` | `3579` | `Bob` | – | `Bob` | Bob meldet sich über ein Smartphone oder Tablet an | `3` (246, Bob und 3579) |
| `6` | – | – | `Bob` | `Bob` | Bob ruft erneut den Kundendienst an | `3` (246, Bob und 3579) |
| `7` | `246` | – | – | `Bob` | Bob greift erneut auf Ihre Website auf dem Desktop zu und ist nicht authentifiziert | `3` (246, Bob und 3579) |

Sowohl nicht authentifizierte als auch authentifizierte Ereignisse auf neuen Geräten werden (vorübergehend) als separate Personen gezählt. Nicht authentifizierte Ereignisse auf erkannten Geräten werden in Echtzeit zugeordnet.

Die Attribution funktioniert, sobald die identifizierende benutzerdefinierte Variable mit einem Gerät verknüpft ist. Im obigen Beispiel werden alle Ereignisse mit Ausnahme der Ereignisse 1 und 4 in Echtzeit zugeordnet (sie verwenden alle die Kennung `Bob`). Die Attribution funktioniert bei den Ereignissen 1 und 4 nach der Wiederholungszuordnung.

## Schritt 2: Wiederholungszuordnung

In regelmäßigen Abständen (einmal pro Woche oder einmal pro Tag, je nach ausgewähltem Lookback-Fenster) berechnet CCA historische Daten erneut basierend auf Geräten, die es jetzt erkennt. Wenn ein nicht authentifiziertes Gerät anfänglich Daten sendet und sich dann anmeldet, verknüpft CCA diese nicht authentifizierten Ereignisse mit der richtigen Person. Die folgende Tabelle stellt dieselben Daten wie oben dar, zeigt jedoch unterschiedliche Zahlen basierend auf der Wiederholung der Daten.

*Dieselben Daten nach der Wiederholung:*

| Zeitstempel | Beständige Web-Datensatz-ID | Vorübergehende Web-Datensatz-ID | Callcenter-Mitarbeiter-ID | Verwendete Benutzer-ID | Erläuterung des Treffers | Metrik „Personen“ (kumulativ) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | – | – | `Bob` | Bob besucht Ihre Website auf seinem Desktop und ist nicht authentifiziert. | `1` (Bob) |
| `2` | `246` | `Bob` | – | `Bob` | Bob meldet sich auf seinem Desktop an. | `1` (Bob) |
| `3` | – | – | `Bob` | `Bob` | Bob ruft den Kundendienst an | `1` (Bob) |
| `4` | `3579` | – | – | `Bob` | Bob greift über sein Smartphone oder Tablet auf Ihre Website zu und ist nicht authentifiziert | `1` (Bob) |
| `5` | `3579` | `Bob` | – | `Bob` | Bob meldet sich über ein Smartphone oder Tablet an | `1` (Bob) |
| `6` | – | – | `Bob` | `Bob` | Bob ruft erneut den Kundendienst an | `1` (Bob) |
| `7` | `246` | – | – | `Bob` | Bob greift erneut auf Ihre Website auf dem Desktop zu und ist nicht authentifiziert | `1` (Bob) |

>[!NOTE]
>
>Daten werden nur für den Website-Datensatz wiederholt. Der Callcenter-Datensatz bleibt unverändert, stimmt jedoch überein, wenn die richtige Personen-ID verwendet wird.

## Zusammenfassung

* Mit CCA werden bekannte Geräte sofort zugeordnet, neue oder nicht erkannte Geräte werden jedoch nicht sofort zugeordnet.
* Die Daten werden in regelmäßigen Abständen wiederholt und ändern die historischen Daten in der Verbindung basierend auf Geräten, die sie zu identifizieren gelernt hat.
