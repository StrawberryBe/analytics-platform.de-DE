---
title: Trends
description: Finden Sie Muster und Änderungen in der Benutzerinteraktion im Zeitverlauf.
source-git-commit: 37699a674a190aa2f28125d5b39bb3c27ac88551
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 2%

---

# Trends

{{release-limited-testing}}

Die **Trends** [Analysetyp](overview.md) bietet wertvolle Einblicke in die Leistung Ihres Produkts oder das Verhalten Ihrer Benutzer im Zeitverlauf. Die horizontale Achse dieses Berichts ist immer eine Zeitgranularität, während die vertikale Achse Ihre gewünschten Ereignisse misst. Anwendungsbeispiele für diesen Analysetyp sind:

* **Bewertung der Produktleistung**: Trends ermöglichen es Ihnen, die Gesamtleistung Ihres Produkts über einen bestimmten Zeitraum zu bewerten. Durch die Analyse von Metriken wie Benutzerinteraktion, Konversionsraten oder Umsatz können Sie feststellen, ob die Leistung Ihres Produkts sich verbessert, stagniert oder sinkt.
* **Funktionsbereitstellung**: Trends zeigen Ihnen, wie Benutzer neue Funktionen oder Aktualisierungen übernehmen, die Sie veröffentlichen. Sie können bestimmen, welche Funktionen beliebt sind und welche Funktionen verbessert werden müssen. Diese Informationen ermöglichen es Ihnen, datenbasierte Entscheidungen darüber zu treffen, welche Funktionen Ihre Entwicklungsbemühungen priorisieren sollen.
* **Benutzerverhalten**: Trends können Einblicke in das Benutzerverhalten im Zeitverlauf bieten. Indem Sie bestimmte Aktionen untersuchen, die Benutzer ausführen, können Sie Muster identifizieren, in denen Benutzer abbrechen können. Sie können Einblicke aus diesem Analysetyp mit einer [Trichter](funnel.md) für noch mehr Einblicke in das Verhalten.
* **A/B-Tests und -Experimente**: Wenn Sie in Ihrem Produkt A/B-Tests durchführen, können Sie mithilfe von Trends messen, welche Tests im Laufe der Zeit am erfolgreichsten sind.

[Screenshot der Trends]

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **Veranstaltungen**: Die Ereignisse, die Sie in Ihrem Bericht messen möchten. Jedes hier ausgewählte Ereignis wird je nach Diagrammtyp als farbige Linie oder Balkensatz dargestellt. Der Tabelle wird eine Zeile hinzugefügt, die das Trendereignis darstellt. Sie können bis zu fünf Ereignisse einbeziehen.
* **Personen**: Die Segmente, die Sie in Ihrem Bericht messen möchten. Jedes hier ausgewählte Segment verdoppelt die Anzahl der Zeilen im Diagramm und Zeilen in der Tabelle. Jeder Satz von Ereignissen wird für jedes Segment dargestellt. Sie können bis zu fünf Segmente einbeziehen.

## Typen anzeigen

Trends bieten die folgenden Ansichtstypen. Sie können den Ansichtstyp über das Dropdown-Menü oben links im Diagramm ändern.

* **Verwendung:** Messen Sie die Benutzerinteraktion im Zeitverlauf.

## Diagrammeinstellungen

Trends bieten die folgenden Diagrammeinstellungen. Sie können die Diagrammeinstellungen über das Menü zwischen dem Ansichtstyp und der Kalenderauswahl anpassen.

* **Metrik**: Die Metrik, die Sie messen möchten. Zu den Optionen gehören Ereignisse, Sitzungen, Benutzer, Ereignisse pro Sitzung und Ereignisse pro Benutzer.
* **Diagrammtyp**: Die Art der Visualisierung, die Sie verwenden möchten. Zu den Optionen gehören &quot;Linie&quot;, &quot;Balken&quot;, &quot;Gestapelte Leiste&quot;und &quot;Gestapelter Bereich&quot;.

## Zeitvergleich anwenden

Trends bieten die Möglichkeit, den aktuellen Zeitraum mit einem vorherigen Zeitraum zu vergleichen. Wenn Sie in diesem Menü eine Option auswählen, erhält jede Zeile eine ähnlich farbige gepunktete Linie. Diese gepunktete Linie stellt dieselbe Metrik im ausgewählten vorherigen Datumsbereich dar. Wenn Sie diese Option festlegen, verdoppelt sich die Anzahl der Zeilen im Diagramm und der Zeilen in der Tabelle.

Zu den verfügbaren Zeitvergleichsoptionen gehören der vorherige Zeitraum, 13 Wochen zuvor, 52 Wochen zuvor und ein benutzerdefinierter Datumsbereich. Wenn Sie den benutzerdefinierten Datumsbereich auswählen, werden zusätzliche Optionen angezeigt, mit denen Sie die Zahl und Granularität auswählen können. Wenn Sie &quot;Keine&quot;auswählen, wird der Datumsvergleich entfernt.

## Datumsbereich

Legt den gewünschten Datumsbereich fest. Diese Einstellung umfasst zwei wichtige Komponenten:

* **Intervall**: Die Datumsgranularität, in der Sie Daten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **Datum**: Das Start- und Enddatum. Die Vorgaben für Datumsbereiche stehen Ihnen zur Verfügung oder Sie können mit der Kalenderauswahl das exakte gewünschte Datum festlegen.
