---
title: Übersicht über berechnete Metriken
description: 'Weitere Informationen '
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Übersicht über berechnete Metriken

Berechnete und erweiterte berechnete (abgeleitete) Metriken sind benutzerdefinierte Metriken, die Sie über vorhandene Metriken erstellen können. Unsere Tools für berechnete Metriken bieten eine äußerst flexible Möglichkeit zum Erstellen, Verwalten und Kuratieren von Metriken. Damit können Marketingexperten, Produktmanager und Analytiker Fragen zu den Daten beantworten, ohne die [!DNL Analytics]-Implementierung ändern zu müssen.

Sie können

* Erstellen Sie gefilterte Metriken, die zur Berichtslaufzeit abgeleitet werden, [ohne die Implementierung](https://youtu.be/CuQTm9RaUpY)ändern zu müssen. Diese können historisch betrachtet werden, weil sie auf Filtern basieren.
* Metriken über Report Suites hinweg freigeben Das bedeutet, dass alle neu erstellten Metriken für alle Report Suites in derselben Firma gelten.
* (Nur erweiterte berechnete Metriken) Filtern Sie nach Metriken. Sie können beispielsweise eine Metrik für &quot;Neue Besucher&quot;mit einer Anzahl von Personen erstellen, für die dies die erste Sitzung ist.
* (Nur erweiterte berechnete Metriken) Integrieren Sie statistische Funktionen, um Ihre Daten besser zu beschreiben. Sie könnten beispielsweise die Elemente in einem Bericht zählen oder die Anzahl der Standardabweichungen für jedes Element addieren.

## Berechnete Metriken im Vergleich zu erweiterten berechneten Metriken

Im Folgenden finden Sie einen Vergleich der Funktionen für berechnete Metriken und erweiterte berechnete Metriken:

| Builder-Optionen | Berechnete Metriken | Erweiterte berechnete (abgeleitete) Metriken |
|---|---|---|
| Formatarten (Dezimal, Zeit, Prozent, Währung | Ja | Ja |
| Attributionsänderung (Standard, Linear, Teilnahme etc. | Ja | Ja |
| Metriktypen (Standard, Total | Ja | Ja |
| Grundlegende Operatoren (hinzufügen, subtrahieren, multiplizieren, dividieren) | Ja | Ja |
| Filter anwenden | Nein | Ja |
| [Allgemeine Funktionen (Zählen, Anzeigenwert, Mittel etc.)](/help/components/calc-metrics/cm-functions.md) | Nein | Ja |
| [Erweiterte Funktionen (Regression, Wenn-Dann, T-Transformation etc.)](/help/components/calc-metrics/cm-adv-functions.md) | Nein | Ja  |

## Tools

| Tool | Funktionen |
|--- |--- |
| Aufbau berechneter Metriken | <ul><li>Erstellen Sie berechnete und erweiterte berechnete Metriken mit erweiterten Zuordnungsmodellen.</li><li>Hinzufügen Filter inline zu metrischen Formeln.</li><li>Vergleichen Sie Filter im gleichen Bericht. (beispielsweise lokale Besucher mit internationalen Besuchern vergleichen.)</li><li>Statistische Funktionen verwenden.</li><li> Detaillierte Metrikbeschreibungen angeben (was die Metrik macht, wo sie verwendet werden sollte, wo sie NICHT verwendet werden sollte.)</li><li>Definitionen in neue Metriken kopieren.</li><li>Eine Inline-Metrikvorschau bereitstellen.</li><li>Die Metrikpolarität festlegen, die angibt, ob es gut oder schlecht ist, wenn ein bestimmtes benutzerspezifisches Ereignis (eine Metrik) steigt.</li><li>Metriken taggen.</li></ul> |
| Berechnete Metrik – Manager | <ul><li>Metriken für andere freigeben.</li><li>Metriken genehmigen und kuratieren.</li><li>Metriken organisieren (taggen), damit sie von Benutzern gefunden werden können.</li><li>Metriken löschen.</li><li>Metriken umbenennen.</li></ul> |
| API für berechnete Metriken | Teil des Adobe Analytics 2.0-API-Sets. |

