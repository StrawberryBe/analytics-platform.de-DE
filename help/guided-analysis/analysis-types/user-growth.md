---
title: Benutzerwachstum
description: Verfolgen Sie das Wachstum des Benutzerkreises Ihres Produkts.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
source-git-commit: c18ed01f899b7a521c67ed6a0008210099b858bf
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Benutzerwachstum

{{release-limited-testing}}

Die **Benutzerwachstum** [Analysetyp](overview.md) bietet Einblicke in das Wachstum und die Akquise von Benutzern über einen bestimmten Zeitraum. Die horizontale Achse ist immer eine Zeitgranularität, während die vertikale Achse immer eine Benutzermessung ist. Benutzer werden ab Beginn des Datumsbereichs in vier Kategorien unterteilt:

* **Neu**: Es ist das erste Mal, dass der Benutzer im angegebenen Datumsbereich erscheint. Der erste Datenpunkt sind immer 100 % neue Benutzer, da die Analyse nicht außerhalb des Datumsbereichs aussieht.
* **Wiederholen**: Der Benutzer tauchte im unmittelbar vorherigen Datenpunkt und im aktuellen Datenpunkt auf.
* **Rückgabe**: Der Benutzer wurde nicht im unmittelbar vorherigen Datenpunkt angezeigt, ist jedoch kein neuer Benutzer. Rückkehrende Benutzer können nicht im ersten oder zweiten Datenpunkt angezeigt werden, da sie zuerst als neuer Benutzer und dann als ruhender Benutzer angezeigt werden müssen.
* **Dormant**: Der Benutzer wurde nicht im aktuellen Datenpunkt angezeigt, sondern im unmittelbar vorherigen Datenpunkt. Dormant-Benutzer zählen nicht zur Gesamtanzahl aktiver Benutzer.

Alle aktiven Benutzer (neu + Wiederholen + Rückgabe) werden als Teelichtenschatten über der horizontalen Achse angezeigt, während alle ruhenden Benutzer unter der horizontalen Achse orange dargestellt werden.

Anwendungsbeispiele für diesen Analysetyp sind:

* **Leistungsbewertung**: Mit der Benutzerentwicklung können Sie die Gesamtleistung Ihres Produkts im Hinblick auf die Akquise neuer Benutzer bewerten. Durch die Verfolgung von Wachstumstrends können Sie besser nachvollziehen, ob Ihr Produkt Benutzer in einem gewünschten Tempo anzieht und bindet.
* **Benutzerbindung und -abwanderung:** Das Benutzerwachstum bietet eine klare Visualisierung für Zeiträume hoher oder niedriger Benutzerbindung. Die Erkennung dieser Zeiträume mit hoher oder niedriger Aufbewahrung kann Ihnen dabei helfen, Produktentscheidungen zu treffen, um eine hohe Beibehaltung zu fördern oder Abwanderung zu minimieren.
* **Kampagnenbewertung**: Wenn Sie das Benutzerwachstum auf einer bestimmten Kampagne betrachten, können Sie nicht nur nachvollziehen, wie viel Traffic durch die Kampagne generiert wurde, sondern auch, wie gut die Kampagne den Benutzern geholfen hat, weiter aktiv zu bleiben.

[Screenshot des Benutzerwachstums]

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **Veranstaltungen**: Das Ereignis, das Sie messen möchten. Da dieser Analysetyp benutzerbasiert ist, kann ein Benutzer das Ereignis innerhalb der festgelegten Datumsgranularität einmal berühren, damit es als aktiver Benutzer gezählt wird. Sie können nur ein Ereignis in eine Abfrage einschließen.
* **Personen**: Das Segment, das Sie messen möchten. Sie können nur ein Segment in eine Abfrage einschließen.

## Typen anzeigen

Das Benutzerwachstum bietet die folgenden Ansichtstypen. Sie können den Ansichtstyp über das Dropdown-Menü oben links im Diagramm ändern.

* **Aktiv:** Messen Sie das Wachstum Ihrer Benutzerbasis.

## Diagrammeinstellungen

Das Benutzerwachstum bietet die folgenden Diagrammeinstellungen. Sie können die Diagrammeinstellungen über das Menü zwischen dem Ansichtstyp und der Kalenderauswahl anpassen.

* **Metrik**: Die Metrik, die Sie messen möchten. Zu den Optionen gehören die Anzahl der Benutzer und der Prozentsatz der Benutzer.
* **Diagrammtyp**: Die Art der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören &quot;Gestapelte Leiste&quot;und &quot;Gestapelter Bereich&quot;.

## Datumsbereich

Der gewünschte Datumsbereich. Diese Einstellung umfasst zwei wichtige Komponenten:

* **Intervall**: Die Datumsgranularität, in der Sie Daten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **Datum**: Das Start- und Enddatum. Die Vorgaben für Datumsbereiche stehen Ihnen zur Verfügung oder Sie können mit der Kalenderauswahl das exakte gewünschte Datum festlegen.
