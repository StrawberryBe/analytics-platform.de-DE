---
title: Aktiv
description: Wachstum der Benutzerbasis messen.
exl-id: 0a300bb2-7620-4e29-a6b5-542476893009
feature: Guided Analysis
source-git-commit: 84cafd2756a09537c93524ff728ea78b7cbf5c8e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Aktiv

{{release-limited-testing}}

Die **Aktiv** Der Ansichtstyp bietet Einblicke in das Wachstum und die Akquise von Benutzern über einen bestimmten Zeitraum. Die horizontale Achse ist immer eine Zeitgranularität, während die vertikale Achse immer eine Benutzermessung ist. Benutzer werden ab Beginn des Datumsbereichs in vier Kategorien unterteilt:

* **Neu**: Der Benutzer war während des aktuellen Datenpunkts aktiv und wurde in früheren Datenpunkten nicht angezeigt. Bewegen des Mauszeigers über &quot;[!UICONTROL Neue Benutzer]&#39; in der Legende des Diagramms, um zu sehen, wie weit der Bericht zurückblickt, um einen neuen Benutzer zu bestimmen. Dieses Datum wird basierend auf der Länge und Granularität des Datumsbereichs dynamisch ausgewählt.
* **Wiederholen**: Der Benutzer tauchte im unmittelbar vorherigen Datenpunkt und im aktuellen Datenpunkt auf.
* **Rückgabe**: Der Benutzer wurde nicht im unmittelbar vorherigen Datenpunkt angezeigt, ist jedoch kein neuer Benutzer.
* **Dormant**: Der Benutzer wurde nicht im aktuellen Datenpunkt angezeigt, sondern im unmittelbar vorherigen Datenpunkt. Dormant-Benutzer zählen nicht zur Gesamtanzahl aktiver Benutzer.

Alle aktiven Benutzer (neu + Wiederholen + Rückgabe) werden als Teelichtenschatten über der horizontalen Achse angezeigt, während alle ruhenden Benutzer unter der horizontalen Achse orange dargestellt werden.

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Benutzerbindung und -abwanderung:** Bietet eine klare Visualisierung für Zeiträume hoher oder niedriger Benutzerbindung. Die Erkennung dieser Zeiträume mit hoher oder niedriger Aufbewahrung kann Ihnen dabei helfen, Produktentscheidungen zu treffen, um eine hohe Beibehaltung zu fördern oder Abwanderung zu minimieren.
* **Kampagnenbewertung**: Die Anzeige einer bestimmten Kampagne kann Ihnen dabei helfen, nicht nur zu verstehen, wie viel Traffic sie generiert hat, sondern auch, wie gut die Kampagne den Benutzern geholfen hat, aktiv zu bleiben.
* **Analyse des Benutzerlebenszyklus**: Die Analyse des aktiven Nutzerwachstums während des gesamten Benutzerlebenszyklus kann dabei helfen, spezifische Phasen zu identifizieren, in denen die Benutzerinteraktion abnimmt. Wenn beispielsweise eine hohe Anzahl ruhender Benutzer für Personen im Onboarding-Stadium vorhanden ist, kann dies auf Benutzerfreundlichkeits-Probleme oder die Notwendigkeit einer besseren produktinternen Anleitung hinweisen.

![Aktiv](../assets/active.png)

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **Veranstaltungen**: Das Ereignis, das Sie messen möchten. Da dieser Ansichtstyp benutzerbasiert ist, kann ein Benutzer das Ereignis innerhalb der festgelegten Datumsgranularität einmal berühren, damit es als aktiver Benutzer gezählt wird. Sie können nur ein Ereignis in eine Abfrage einschließen.
* **Personen**: Das Segment, das Sie messen möchten. Sie können nur ein Segment in eine Abfrage einschließen.

## Diagrammeinstellungen

Dieser Ansichtstyp bietet die folgenden Diagrammeinstellungen. Sie können die Diagrammeinstellungen über das Menü zwischen dem Ansichtstyp und der Kalenderauswahl anpassen.

* **Metrik**: Die Metrik, die Sie messen möchten. Zu den Optionen gehören die Anzahl der Benutzer und der Prozentsatz der Benutzer.
* **Diagrammtyp**: Die Art der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören &quot;Gestapelte Leiste&quot;und &quot;Gestapelter Bereich&quot;.

## Zeitvergleich anwenden

{{apply-time-comparison}}

![Vergleich der aktiven Zeit](../assets/active-compare.png)

## Datumsbereich

Der gewünschte Datumsbereich. Diese Einstellung umfasst zwei wichtige Komponenten:

* **Intervall**: Die Datumsgranularität, in der Sie Daten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **Datum**: Das Start- und Enddatum. Die Vorgaben für Datumsbereiche stehen Ihnen zur Verfügung oder Sie können mit der Kalenderauswahl das exakte gewünschte Datum festlegen.
