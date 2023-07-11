---
title: Nettowachstum
description: Saldo Nutzergewinne und -verluste.
feature: Guided Analysis
source-git-commit: 14c7aa342649afbe9923b0086947e5a0adeefff2
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 1%

---

# Nettowachstum

{{release-limited-testing}}

Die **Nettowachstum** Der Ansichtstyp bietet Einblicke in die Rate, mit der Sie Benutzer über einen bestimmten Zeitraum erwerben oder verlieren. Die horizontale Achse ist immer eine Zeitgranularität, während die vertikale Achse immer die Wachstumsmessung ist.

Jeder Datenpunkt stellt das Nettowachstum des Datenpunkts dar, das anhand der folgenden Formel berechnet wird:

`([New users] + [Return users]) / [Dormant users]`

Ähnlich wie bei [Aktiv](active.md) Ansichtstyp, werden Benutzer wie folgt definiert:

* **Neu**: Der Benutzer war während des aktuellen Datenpunkts aktiv und wurde in früheren Datenpunkten nicht angezeigt.
* **Rückgabe**: Der Benutzer wurde nicht im unmittelbar vorherigen Datenpunkt angezeigt, ist jedoch kein neuer Benutzer.
* **Dormant**: Der Benutzer wurde nicht im aktuellen Datenpunkt angezeigt, sondern im unmittelbar vorherigen Datenpunkt. Dormant-Benutzer zählen nicht zur Gesamtanzahl aktiver Benutzer.

**Wiederholen** -Benutzer werden bei dieser Berechnung nicht berücksichtigt, da sie kein Wachstum oder keinen Verlust darstellen.

Das Ergebnis dieser Formel ist ein Verhältnis, mit dem die Benutzerbasis während dieses Datenpunkts wuchs oder schrumpfte. Nettowachstum `1` stellt ein Gleichgewicht dar; das Produkt die gleiche Anzahl von Anwendern wie verloren. Nettowachstum größer als `1` ein positives Wachstum darstellt; Es gab mehr neue/wiederkehrende Benutzer als ruhende Benutzer. Ebenso ein Nettowachstum von weniger als `1` einen Verlust aktiver Benutzer darstellt; Es waren mehr ruhende Benutzer als neue/wiederkehrende Benutzer.

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Benutzerakquise-Analyse**: Ermöglicht es Ihnen, die Effektivität Ihrer Benutzerakquisestrategien zu bewerten. Die Analyse der Quellen für das Benutzerwachstum, wie Suchmaschinen, Kampagnen oder andere Marketingkanäle, ermöglicht es Ihnen, die wichtigsten Wachstumsquellen zu identifizieren, sodass Sie Ressourcen entsprechend zuordnen können.
* **Leistungsbewertung**: Ermöglicht es Ihnen, die Gesamtleistung Ihres Produkts im Hinblick auf die Akquise neuer Benutzer zu bewerten. Durch die Verfolgung von Wachstumstrends können Sie besser nachvollziehen, ob Ihr Produkt Benutzer in einem gewünschten Tempo anzieht und bindet.
* **Abwanderungsanalyse**: Das Nettowachstum umfasst die Ablösung in der Formel (ruhende Nutzer). Sie können die allgemeine Gesundheit Ihrer Benutzerbasis im Laufe der Zeit bewerten. Wenn das Nettowachstum konsequent niedriger ist `1`, deutet es auf eine hohe Anzahl von Abbrüchen hin, die Sie auffordern, die Gründe dafür zu untersuchen und Aufbewahrungsstrategien zu implementieren.

[Screenshot des Benutzerwachstums]

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **Veranstaltungen**: Das Ereignis, das Sie messen möchten. Da dieser Ansichtstyp benutzerbasiert ist, kann ein Benutzer das Ereignis innerhalb der festgelegten Datumsgranularität einmal berühren, um sich im Nettowachstum zu befinden. Sie können nur ein Ereignis in eine Abfrage einschließen.
* **Personen**: Das Segment, das Sie messen möchten. Sie können nur ein Segment in eine Abfrage einschließen.

## Datumsbereich

Der gewünschte Datumsbereich. Diese Einstellung umfasst zwei wichtige Komponenten:

* **Intervall**: Die Datumsgranularität, in der Sie Daten anzeigen möchten. Gültige Optionen sind &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **Datum**: Das Start- und Enddatum. Die Vorgaben für Datumsbereiche stehen Ihnen zur Verfügung oder Sie können mit der Kalenderauswahl das exakte gewünschte Datum festlegen.
