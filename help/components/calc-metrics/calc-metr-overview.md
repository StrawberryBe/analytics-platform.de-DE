---
title: Übersicht über berechnete Metriken
description: 'Informationen zu den '
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Übersicht über berechnete Metriken

Berechnete und erweiterte berechnete (abgeleitete) Metriken sind benutzerdefinierte Metriken, die Sie über vorhandene Metriken erstellen können. Mit unseren Werkzeugen für berechnete Metriken können Sie Metriken auf flexiblere Weise erstellen, verwalten und kuratieren. Damit können Marketingexperten, Produktmanager und Analytiker Fragen zu den Daten beantworten, ohne die [!DNL Analytics]-Implementierung ändern zu müssen.

Sie können

* Create filtered metrics that are derived at report run time, [without having to change the implementation](https://youtu.be/CuQTm9RaUpY). Diese können historisch betrachtet werden, weil sie auf Filtern basieren.
* Metriken über Report Suites hinweg freigeben. Das bedeutet, dass alle neu erstellten Metriken für alle Report Suites in demselben Anmeldeunternehmen gelten.
* (Nur erweiterte berechnete Metriken) Filtern Sie nach Metriken. Sie können beispielsweise eine Metrik für „Neue Besucher“ erstellen, mit der Personen gezählt werden, für die dies die erste Sitzung ist.
* (Nur erweiterte berechnete Metriken) Statistische Funktionen miteinbeziehen, um Daten besser beschreiben zu können. Sie könnten beispielsweise die Elemente in einem Bericht zählen oder die Anzahl der Standardabweichungen für jedes Element addieren.

## Berechnete Metriken im Vergleich zu erweiterten berechneten Metriken

Hier sehen Sie einen Vergleich zwischen den jeweiligen Möglichkeiten, die berechnete und erweiterte berechnete Metriken bieten:

| Generatoroptionen | Berechnete Metriken | Erweiterte berechnete (abgeleitete) Metriken |
|---|---|---|
| Formatarten (Dezimal, Zeit, Prozent, Währung | Ja | Ja |
| Attributionsänderung (Standard, Linear, Teilnahme etc. | Ja | Ja |
| Metriktypen (Standard, Total | Ja | Ja |
| Grundrechenarten (Addieren, Subtrahieren, Multiplizieren, Dividieren) | Ja | Ja |
| Filter anwenden | Nein | Ja |
| [Allgemeine Funktionen (Zählen, Anzeigenwert, Mittel etc.)](/help/components/calc-metrics/cm-functions.md) | Nein | Ja |
| [Erweiterte Funktionen (Regression, Wenn-Dann, T-Transformation etc.)](/help/components/calc-metrics/cm-adv-functions.md) | Nein | Ja  |

## Tools

| Tool | Funktionen |
|--- |--- |
| Aufbau berechneter Metriken | <ul><li>Erstellen Sie einfache berechnete Metriken oder erweiterte berechnete Metriken mit erweiterten Zuordnungsmodellen.</li><li>Hinzufügen Filter inline zu metrischen Formeln.</li><li>Vergleichen Sie Filter im gleichen Bericht. (beispielsweise lokale Besucher mit internationalen Besuchern vergleichen.)</li><li>Statistische Funktionen verwenden.</li><li> Detaillierte Metrikbeschreibungen angeben (was die Metrik macht, wo sie verwendet werden sollte, wo sie NICHT verwendet werden sollte.)</li><li>Definitionen in neue Metriken kopieren.</li><li>Eine Inline-Metrikvorschau bereitstellen.</li><li>Die Metrikpolarität festlegen, die angibt, ob es gut oder schlecht ist, wenn ein bestimmtes benutzerspezifisches Ereignis (eine Metrik) steigt.</li><li>Metriken taggen.</li></ul> |
| Berechnete Metrik – Manager | <ul><li>Metriken für andere freigeben.</li><li>Metriken genehmigen und kuratieren.</li><li>Metriken organisieren (taggen), damit sie von Benutzern gefunden werden können.</li><li>Metriken löschen.</li><li>Metriken umbenennen.</li></ul> |
| API für berechnete Metriken | Teil des Adobe Analytics 2.0-API-Sets. |

