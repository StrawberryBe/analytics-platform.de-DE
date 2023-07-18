---
title: Netto-Wachstumsansicht
description: Gewinnen oder verlieren Sie Nutzende?
feature: Guided Analysis
source-git-commit: 9f176bc6bc12291dcdab80af50c32df7d8edf220
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 1%

---

# Netto-Wachstumsansicht

Die **Nettowachstum** Der Ansichtstyp bietet Einblicke in die Rate, mit der Sie in einem bestimmten Zeitraum Benutzer gewinnen oder verlieren. Die horizontale Achse ist ein Zeitintervall, während die vertikale Achse die Wachstumsmessung darstellt.

Jeder Datenpunkt stellt das Nettowachstum dar, das anhand der folgenden Formel berechnet wird:

`([New users] + [Return users]) / [Dormant users]`

Das Ergebnis dieser Formel ist ein Verhältnis. Nettowachstum `1` ein Gleichgewicht darstellt; das Produkt die gleiche Anzahl von Anwendern wie verloren. Nettowachstum größer als `1` ein positives Wachstum darstellt; Es gab mehr neue + wiederkehrende Benutzer als ruhende Benutzer. Ebenso ein Nettowachstum von weniger als `1` einen Verlust darstellt; es waren mehr ruhende Benutzer als neue + wiederkehrende Benutzer.

Ähnlich wie bei [Aktiv](active.md) Ansichtstyp, werden Benutzer wie folgt definiert:

* **[!UICONTROL Neu]**: Der Benutzer war im aktuellen Zeitraum aktiv, jedoch nicht zuvor. Ermitteln Sie, wie weit die Analyse zurückblickt, um einen neuen Benutzer zu ermitteln, indem Sie den Mauszeiger über &quot;[!UICONTROL Neue Benutzer]&#39; in der Diagrammlegende. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Rückgabe]**: Der Benutzer war im aktuellen Zeitraum aktiv und nicht im unmittelbar vorherigen Zeitraum aktiv, war aber zu einem früheren Zeitpunkt aktiv. Ermitteln Sie, wie weit die Analyse zurückblickt, um einen wiederkehrenden Benutzer zu ermitteln, indem Sie den Mauszeiger über &quot;[!UICONTROL Wiederkehrende Benutzer]&#39; in der Diagrammlegende. Der Lookback-Bereich wird basierend auf dem ausgewählten Datumsbereich und Intervall dynamisch bestimmt.
* **[!UICONTROL Dormant]**: Der Benutzer war im unmittelbar vorherigen Zeitraum aktiv, ist aber im aktuellen Zeitraum nicht aktiv. Dormant-Benutzer zählen nicht zur Gesamtanzahl aktiver Benutzer.

>[!NOTE]
>
>Wiederholte Benutzer werden nicht in diese Berechnung einbezogen, da sie keinen Gewinn oder Verlust von Benutzern darstellen.

![Nettowachstum](../assets/net-growth.png)

## Siehe Net Growth view in action

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?learn=on)

## Anwendungsbeispiele

Anwendungsbeispiele für diesen Ansichtstyp sind:

* **Leistungsbewertung**: Ermöglicht es Ihnen, die Gesamtleistung Ihres Produkts im Hinblick auf die Akquise neuer Benutzer zu bewerten. Durch die Verfolgung von Wachstumstrends können Sie besser nachvollziehen, ob Ihr Produkt Benutzer in einem gewünschten Tempo anzieht und bindet.
* **Benutzerakquise-Analyse**: Ermöglicht es Ihnen, die Effektivität Ihrer Benutzerakquisestrategien zu bewerten. Die Analyse der Quellen für das Benutzerwachstum, wie Suchmaschinen, Kampagnen oder andere Marketingkanäle, ermöglicht es Ihnen, die wichtigsten Wachstumsquellen zu identifizieren, sodass Sie Ressourcen entsprechend zuordnen können.
* **Abwanderungsanalyse**: Das Nettowachstum beinhaltet die Ablösung in der Formel (ruhende Nutzer). Sie können die allgemeine Gesundheit Ihrer Benutzerbasis im Laufe der Zeit bewerten. Wenn das Nettowachstum konsequent niedriger ist `1`, deutet dies auf eine hohe Anzahl von Abbrüchen hin, die die Implementierung von Bindungsstrategien erforderlich machen könnten.

## Abfrageleiste

In der Abfrageleiste können Sie die folgenden Komponenten konfigurieren:

* **[!UICONTROL Veranstaltungen]**: Das Ereignis, das Sie messen möchten. Da dieser Ansichtstyp benutzerbasiert ist, wird ein Benutzer, der innerhalb des Zeitraums einmal mit dem Ereignis interagiert, als aktiver Benutzer gezählt. Sie können ein Ereignis in eine Abfrage einbeziehen.
* **[!UICONTROL Personen]**: Das Segment, das Sie messen möchten. Sie können ein Segment in eine Abfrage einbeziehen.

## Datumsbereich

Der gewünschte Datumsbereich für Ihre Analyse. Diese Einstellung umfasst zwei Komponenten:

* **[!UICONTROL Intervall]**: Die Datumsgranularität, mit der Sie Trenddaten anzeigen möchten. Gültige Optionen sind &quot;Stündlich&quot;, &quot;Täglich&quot;, &quot;Wöchentlich&quot;, &quot;Monatlich&quot;und &quot;Quartal&quot;. Derselbe Datumsbereich kann unterschiedliche Intervalle haben, die sich auf die Anzahl der Datenpunkte im Diagramm und die Anzahl der Spalten in der Tabelle auswirken. Wenn Sie beispielsweise eine Analyse betrachten, die sich auf drei Tage mit täglicher Granularität erstreckt, werden nur drei Datenpunkte angezeigt, während eine Analyse, die drei Tage mit stündlicher Granularität umfasst, 72 Datenpunkte anzeigen würde.
* **[!UICONTROL Datum]**: Das Start- und Enddatum. Vorgaben für rollierende Datumsbereiche und zuvor gespeicherte benutzerdefinierte Bereiche stehen Ihnen zur Verfügung. Alternativ können Sie mit der Kalenderauswahl einen festen Datumsbereich auswählen.
