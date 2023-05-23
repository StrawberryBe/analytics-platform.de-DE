---
title: Benutzerwachstum
description: Verfolgen Sie das Wachstum des Benutzerkreises Ihres Produkts.
source-git-commit: c47c4364cbf027c24a355bb306ee786c3e2446a9
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 2%

---

# Benutzerwachstum

{{release-limited-testing}}

Die **Benutzerwachstum** [Analysetyp](overview.md) bietet Einblicke in das Wachstum und die Akquise von Benutzern über einen bestimmten Zeitraum. Die horizontale Achse ist immer eine Zeitgranularität, während die vertikale Achse immer eine Benutzermessung ist. Benutzer werden ab Beginn des Datumsbereichs in vier Kategorien unterteilt:

* **Neu**: Es ist das erste Mal, dass der Benutzer im angegebenen Datumsbereich erscheint. Der erste Datenpunkt in einem Bericht ist immer zu 100 % neue Benutzer, da der Bericht Datumsangaben außerhalb des Berichtsbereichs nicht anzeigt.
* **Wiederholen**: Der Benutzer tauchte im unmittelbar vorherigen Datenpunkt und im aktuellen Datenpunkt auf.
* **Rückgabe**: Der Benutzer wurde nicht im unmittelbar vorherigen Datenpunkt angezeigt, ist jedoch kein neuer Benutzer. Rückkehrende Benutzer können nicht im ersten oder zweiten Datenpunkt angezeigt werden, da sie zuerst als neuer Benutzer und dann als ruhender Benutzer angezeigt werden müssen.
* **Dormant**: Der Benutzer wurde nicht im aktuellen Datenpunkt angezeigt, sondern im unmittelbar vorherigen Datenpunkt. Dormant-Benutzer zählen nicht zur Gesamtanzahl aktiver Benutzer.

Alle aktiven Benutzer (neu + Wiederholen + Rückgabe) werden als Teelichtenschatten über der horizontalen Achse angezeigt, während alle ruhenden Benutzer unter der horizontalen Achse orange dargestellt werden.

Anwendungsbeispiele für diesen Analysetyp sind:

* **Leistungsbewertung**: Mit der Benutzerentwicklung können Sie die Gesamtleistung Ihres Produkts im Hinblick auf die Akquise neuer Benutzer bewerten. Durch die Verfolgung von Wachstumstrends können Sie besser nachvollziehen, ob Ihr Produkt Benutzer in einem gewünschten Tempo anzieht und bindet.
* **Benutzerbindung und -abwanderung:** Dieser Bericht bietet eine klare Visualisierung für Zeiträume hoher oder niedriger Benutzerbindung. Die Erkennung dieser Zeiträume mit hoher oder niedriger Aufbewahrung kann Ihnen dabei helfen, Produktentscheidungen zu treffen, um eine hohe Beibehaltung zu fördern oder Abwanderung zu minimieren.
* **Kampagnenbewertung**: Die Anzeige eines benutzerspezifischen Wachstumsberichts für eine bestimmte Kampagne kann Ihnen dabei helfen, nicht nur zu verstehen, wie viel Traffic sie generiert hat, sondern auch, wie gut die Kampagne den Benutzern geholfen hat, weiter aktiv zu bleiben.

[Screenshot des Benutzerwachstums]

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **Veranstaltungen**: Legt das Ereignis fest, das Sie in Ihrem Bericht messen möchten. Da dieser Bericht benutzerbasiert ist, kann ein Benutzer das Ereignis innerhalb der festgelegten Datumsgranularität einmal berühren, damit es als aktiver Benutzer gezählt wird. Es wird nur ein Ereignis unterstützt.
* **Personen**: Legt das Segment fest, das Sie in Ihrem Bericht messen möchten. Es wird nur ein Segment unterstützt.

## Typen anzeigen

Das Benutzerwachstum bietet die folgenden Ansichtstypen. Sie können den Ansichtstyp über das Dropdown-Menü oben links im Diagramm ändern.

* **Aktiv:** Messen Sie das Wachstum Ihrer Benutzerbasis.

## Diagrammeinstellungen

Das Benutzerwachstum bietet die folgenden Diagrammeinstellungen. Sie können die Diagrammeinstellungen über das Menü zwischen dem Ansichtstyp und der Kalenderauswahl anpassen.

* **Metrik**: Legt die Metrik fest, die Sie messen möchten. Zu den Optionen gehören die Anzahl der Benutzer und der Prozentsatz der Benutzer.
* **Diagrammtyp**: Legt den Visualisierungstyp fest, den Sie verwenden möchten. Zu den Optionen gehören &quot;Gestapelte Leiste&quot;und &quot;Gestapelter Bereich&quot;.

## Datumsbereich

Legt den gewünschten Datumsbereich fest. Diese Einstellung umfasst zwei wichtige Komponenten:

* **Intervall**: Die Datumsgranularität, in der Sie Daten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise einen Bericht anzeigen, der sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während ein Bericht, der sich auf drei Tage mit stündlicher Granularität erstreckt, 72 Datenpunkte anzeigt.
* **Datum**: Das Start- und Enddatum des Projekts. Die Vorgaben für Datumsbereiche stehen Ihnen zur Verfügung oder Sie können mit der Kalenderauswahl das exakte gewünschte Datum festlegen.
