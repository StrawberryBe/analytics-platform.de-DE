---
description: Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben.
title: Zeileneinstellungen
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: df326581abbbd0dd0d29638962ccb71bb0aee837
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 24%

---


# Zeileneinstellungen

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Mehr Infos...](/help/getting-started/cja-aa.md)

Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben. Um auf die Tabellenzeileneinstellungen zuzugreifen, klicken Sie auf das Einstellungs-Symbol neben einer Dimension, einem Segment, einer Metrik, einem Zeitraum oder einer Aufschlüsselung im jeweiligen Element:

![](assets/row-settings.png)

| Einstellung | Beschreibung |
|--- |--- |
| Datumsausrichtung | Bei dieser Einstellung auf Tabellenebene werden Datumsangaben aus den einzelnen Spalten an allen Beginn in derselben Zeile ausgerichtet. Die Datumsausrichtung ist standardmäßig aktiviert, wenn eine Zeitdimension in den Tabellenzeilen verwendet wird und unterschiedliche Datumsbereiche in den Spalten angewendet werden. In einer Tabelle mit Tagespauschale, bei der Oktober und September auf die Spalten angewendet werden, werden die Beginn mit der linken Spalte mit dem 1. Oktober und die Beginn mit der rechten Spalte mit dem 1. September angezeigt. |
| Aufschlüsselung nach Position | Standardmäßig ist diese Einstellung deaktiviert und die Aufschlüsselungen sind auf statische Zeilenelemente fixiert. Nehmen wir beispielsweise an, Sie unterteilen die drei wichtigsten Dimensionselemente der Seite (Homepage, Suchergebnisse, Kasse) nach Marketing-Kanal. Dann verlassen Sie das Projekt und kehren zwei Wochen später zurück. Nach dem erneuten Öffnen des Projekts haben sich die drei wichtigsten Seiten geändert. Jetzt sind Homepage, Suchergebnisse und Kasse die Top-4-6-Seiten. Standardmäßig werden Ihre Marketing-Kanal-Aufschlüsselungen weiterhin unter Homepage, Suchergebnisse und Checkout angezeigt, auch wenn sie sich jetzt in den Zeilen 4-6 befinden. <br> Im Gegensatz dazu **Aufschlüsselung nach Position** werden immer die drei wichtigsten Elemente unterteilt, unabhängig davon, was sie sind. Wenn Sie auf unser Beispiel zurückgreifen, werden die Marketing Kanal-Aufschlüsselungen beim erneuten Öffnen des Projekts an die drei obersten Tabellenseiten gebunden, nicht an Homepage, Suchergebnisse und Checkout, die sich nun in den Zeilen 4 bis 6 befinden. |
| Prozentsatz | **Prozentsätze nach Spalte berechnen** ist die Standardeinstellung; die in einer Spalte sichtbaren Prozentsätze werden auf Basis der Spaltensumme berechnet. <br>**Prozentsätze nach Zeile berechnen** erzwingt die Freiform-Tabelle, die Zellprozentsätze in der Zeile zu berechnen, anstatt in der Spalte, wobei die Gesamtsumme als Nenner dient. Dies ist besonders nützlich für die Trend-Darstellung von Prozentangaben. Diese Einstellung ist bei Verwendung des Visualize-Symbols standardmäßig aktiviert. |
| Spaltensummen | Diese Einstellungen stehen nur für [statische Zeilen](manual-vs-dynamic-rows.md). <br> **Als Summe der aktuellen Zeilen anzeigen** zeigt eine clientseitige Summe der Zeilen in der Tabelle, was bedeutet, dass die Summe *not* Metriken zum Löschen von Duplikaten wie Besuchen oder Besuchern. <br> **Gesamtsumme anzeigen** zeigt eine serverseitige Summe an, was bedeutet, dass die Metriken zum Entfernen des Duplikats insgesamt gelöscht werden. |
