---
description: Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben.
title: Zeileneinstellungen
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '472'
ht-degree: 100%

---

# Zeileneinstellungen

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=de). [Weitere Informationen...](/help/getting-started/cja-aa.md)

Sehen Sie sich hier ein Video zu Zeilen- und Spalteneinstellungen an:

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

Die Zeileneinstellungen variieren je nachdem, welche Komponente Sie in die Tabelle gezogen haben. Um auf die Einstellungen der Tabellenzeilen zuzugreifen, klicken Sie auf das Symbol [!UICONTROL Einstellungen] neben einer Dimension, einem Filter, einer Metrik, einem Zeitraum oder einer Aufschlüsselung im jeweiligen Element:

![](assets/row-settings.png)

| Einstellung | Beschreibung |
| --- | --- |
| Datum ausrichten | Mit dieser Einstellung auf Tabellenebene können Sie die Daten in allen Spalten so ausrichten, dass sie alle in derselben Zeile beginnen. Die Datumsausrichtung ist standardmäßig aktiviert, wenn eine Zeitdimension in den Tabellenzeilen verwendet wird und unterschiedliche Datumsbereiche in den Spalten angewendet werden. In einer täglichen Tabelle, bei der Oktober und September auf die Spalten angewendet werden, beginnt beispielsweise die linke Spalte mit dem 1. Oktober und die rechte Spalte mit dem 1. September. |
| Aufschlüsselung nach Position | Standardmäßig ist diese Einstellung deaktiviert und die Aufschlüsselungen sind auf statische Zeilenelemente festgelegt. Angenommen, Sie schlüsseln die drei oberen Elemente der Dimension „Seite“ (Startseite, Suchergebnisse, Checkout) nach Marketing-Kanälen auf. Dann verlassen Sie das Projekt und kehren zwei Wochen später zurück. Beim erneuten Öffnen des Projekts haben sich die drei oberen Seiten geändert, und jetzt sind Startseite, Suchergebnisse und Checkout stattdessen die oberen Seiten vier bis sechs. Standardmäßig werden Ihre Marketing-Kanal-Aufschlüsselungen weiterhin unter Startseite, Suchergebnisse und Checkout angezeigt, auch wenn sie sich jetzt in den Zeilen 4-6 befinden. <br> Im Gegensatz dazu werden bei einer **Aufschlüsselung nach Position** immer die drei obersten Elemente aufgeschlüsselt, unabhängig davon, worum es sich bei ihnen handelt. Um auf unser Beispiel zurückzukommen: Wenn Sie Ihr Projekt erneut öffnen, werden die Aufschlüsselungen der Marketing-Kanäle an die ersten 3 Seiten in der Tabelle gebunden, nicht an  Startseite, Suchergebnisse und Checkout, die sich jetzt in den Zeilen 4-6 befinden. |
| Prozentsatz | **Prozentsätze pro Spalte berechnen**: Ist die Standardeinstellung. Die in einer Spalte sichtbaren Prozentsätze werden auf der Grundlage der Spaltensumme berechnet. <br>**Prozentsätze pro Zeile berechnen**: Erzwingt, dass in der Freiform-Tabelle die Zellprozentsätze über die Zeile anstatt für die Spalte berechnet werden. Dabei sit die Gesamtsumme der Nenner. Dies ist besonders nützlich für die Trend-Darstellung von Prozentangaben. Diese Einstellung ist standardmäßig aktiviert, wenn Sie das Symbol „Visualisieren“ verwenden. |
| Spaltensummen | Diese Einstellungen sind nur für [statische Zeilen](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) verfügbar. <br> **Als Summe der aktuellen Zeilen anzeigen**: Zeigt eine Client-seitige Summe der Zeilen in der Tabelle, was bedeutet, dass die Gesamtsumme die Metriken wie „Besuche“ oder „Besucher“ *nicht* dedupliziert. <br> **Gesamtsumme anzeigen**: Zeigt eine Server-seitige Summe an, d. h. die Gesamtsumme dedupliziert die Metriken. |

## Ändern der Zeilenanzahl

So ändern Sie die Anzahl der angezeigten Zeilen:

1. Klicken Sie auf die Zahl neben [!UICONTROL Zeilen] oberhalb der Tabelle.

   ![](assets/row-number.png)

1. Wählen Sie aus der Dropdown-Liste die Anzahl der Zeilen aus, die die Tabelle anzeigen soll.