---
title: Verwalten von Datenblöcken mithilfe von Report Builder in Customer Journey Analytics
description: Beschreibt die Verwendung der Verwaltungsfunktion in Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: e9856269ee07b7119f75b98489b47e1f35f7cf5f
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 1%

---

# Verwalten von Datenblöcken in Report Builder

Mit dem Datenblock-Manager können Sie alle Datenblöcke einer Arbeitsmappe anzeigen und verwalten. Der Datenblock-Manager bietet Such-, Filter- und Sortierfunktionen, mit denen Sie bestimmte Datenblöcke schnell finden können. Nach Auswahl eines oder mehrerer Datenblöcke können Sie die ausgewählten Datenblöcke bearbeiten, löschen oder aktualisieren.

![image](./assets/image52.png)

## Datenblöcke anzeigen

Klicken **Verwalten** um eine Liste aller Datenblöcke in einer Arbeitsmappe anzuzeigen.


![image](./assets/image53.png)

Der Datenblock-Manager listet alle in einer Arbeitsmappe vorhandenen Datenblöcke auf. 

![image](./assets/image52.png)

## Sortieren der Liste der Datenblöcke

Sie können die Blockierungsliste der Daten nach einer angezeigten Spalte sortieren. Sie können beispielsweise die Blockierungsliste der Daten nach Report Suites, Filtern, Datumsbereich und anderen Variablen sortieren.

Um die Blockierungsliste der Daten zu sortieren, klicken Sie auf eine Spaltenüberschrift.

![image](./assets/image54.png)

## Durchsuchen der Daten-Blockierungsliste

Verwenden Sie das Feld Suchen , um etwas in der Datenblock-Tabelle zu suchen. Sie können beispielsweise nach Metriken suchen, die in den Datenblöcken oder in der Report Suite enthalten sind. Sie können auch nach Datumsangaben suchen, die in den Datumsbereich-, Datumsänderungs- oder Letztlaufdatumsspalten angezeigt werden.

![image](./assets/image55.png)

## Datenblöcke bearbeiten

Sie können die Datenansicht, den Datumsbereich oder die auf einen oder mehrere Datenblöcke angewendeten Filter bearbeiten.

Sie können beispielsweise einen vorhandenen Filter in einem oder mehreren Datenblöcken durch einen neuen Filter ersetzen.

1. Wählen Sie die zu aktualisierenden Datenblöcke aus. Sie können das Kontrollkästchen auf der obersten Ebene aktivieren, um alle Datenblöcke auszuwählen, oder Sie können einzelne Datenblöcke auswählen.

   ![image](./assets/image56.png)

1. Klicken Sie auf das Bearbeitungssymbol, um das Fenster Schnellbearbeitung anzuzeigen.

   ![image](./assets/image58.png)

1. Wählen Sie einen Filterlink aus, um Datenansichten, Datumsbereiche oder Filter zu aktualisieren.

   ![image](./assets/image59.png)

## Datenblöcke aktualisieren

Klicken Sie auf das Aktualisierungssymbol, um die Datenblöcke in der Liste zu aktualisieren.

<img src="./assets/refresh-icon.png" width="15%"/>

Um zu überprüfen, ob ein Datenblock aktualisiert wurde, rufen Sie das Symbol Aktualisierungsstatus auf. Ein Häkchen in einem grünen Kreis <img src="./assets/refresh-success.png" width="5%"/> gibt an, dass die Aktualisierung des Datenblocks erfolgreich war. Bei einem Datenblock, der nicht aktualisiert werden konnte, wird ein Warnsymbol angezeigt <img src="./assets/refresh-failure.png" width="5%"/>.  Dadurch lässt sich leicht erkennen, ob Datenblöcke Fehler aufweisen.


![image](./assets/image512.png)

## Datenblock löschen

Klicken Sie auf das Papierkorbsymbol, um einen ausgewählten Datenblock zu löschen.

## Gruppendatenblöcke

Sie können Datenblöcke mithilfe der **Gruppieren nach** oder Sie können auf einen Spaltentitel klicken. Um Datenblöcke nach Spalten zu sortieren, klicken Sie auf den Spaltentitel. Um Datenblöcke nach Gruppen zu gruppieren, wählen Sie einen Gruppennamen aus der **Gruppieren nach** Dropdown-Menü. Der folgende Screenshot zeigt beispielsweise nach Blatt gruppierte Datenblöcke. Es werden Datenblöcke angezeigt, die nach Blatt1 und Blatt2 gruppiert sind.  Dies ist beispielsweise im Anwendungsfall zum Ersetzen von Filtern nützlich. Wenn auf jeden Datenblock mehrere Filter angewendet werden, ist es hilfreich, eine Gruppe zu erstellen, die alle Datenblöcke enthält, die Sie ersetzen möchten. Dann können Sie sie einfach auswählen und alle gleichzeitig bearbeiten.

![image](./assets/group-data-blocks.png)

## Ändern der Ansicht &quot;Datenblock-Manager&quot;

Sie können ändern, welche Spalten im Fenster Datenblock-Manager angezeigt werden.


Klicken Sie auf die Spaltenliste <img src="./assets/image515.png" width="3%"/> -Symbol, um auszuwählen, welche Spalten im Datenblock-Manager aufgeführt werden. Wählen Sie einen Spaltennamen aus, um die Spalte anzuzeigen. Heben Sie die Auswahl des Spaltennamens auf, um die Spalte aus der Ansicht zu entfernen.

![Bild](./assets/image516.png)
