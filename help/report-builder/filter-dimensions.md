---
title: Verwenden von Filtern in Report Builder in Customer Journey Analytics
description: Beschreibt die Verwendung von Filtern in Report Builder für CJA
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: dc6317bc754218c03d78145be1c8681ad202bcb8
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 2%

---


# Dimensionen filtern

Standardmäßig gibt jedes Dimensionselement in der Tabelle die 10 wichtigsten Elemente für diese Dimension zurück.

So ändern Sie die für jede Dimension zurückgegebenen Dimensionselemente

1. Wählen Sie einen Datenblock aus und klicken Sie im Bedienfeld BEFEHLE auf Datenblock bearbeiten .

1. Klicken Sie auf Weiter , um die Registerkarte Dimensionen anzuzeigen.

1. Klicken Sie auf **...** Symbol neben einem Komponentennamen in der Tabelle.

   ![](./assets/image27.png)

1. Wählen Sie **Filterdimension** im Popup-Menü aus, um den Bereich **Filterdimension** anzuzeigen.

1. Wählen Sie **Am beliebtesten** oder **Spezifisch**.

   ![](./assets/image28.png)

1. Wählen Sie je nach ausgewähltem Filtertyp die gewünschten Optionen aus.

1. Klicken Sie auf **Anwenden** , um den Filter hinzuzufügen.

   Report Builder zeigt eine Benachrichtigung zur Bestätigung des hinzugefügten Filters an.

Um angewendete Filter anzuzeigen, bewegen Sie den Mauszeiger über eine Dimension. Dimensionen mit angewendeten Filtern zeigen rechts neben dem Namen der Dimension ein Filtersymbol an.

## Filtertyp

Es gibt zwei Möglichkeiten, Dimensionselemente zu filtern: Am beliebtesten und am spezifischsten.

## Am beliebtesten

Mit der Option Am beliebtesten können Sie Dimensionselemente basierend auf Metrikwerten dynamisch filtern. Die beliebteste Filterung gibt die am höchsten bewerteten Dimensionselemente basierend auf Metrikwerten zurück. Standardmäßig werden die ersten 10 Dimensionselemente aufgelistet, sortiert nach der ersten Metrik, die zum Datenblock hinzugefügt wurde.

![Bilddateien](./assets/image29.png)


### Seiten- und Zeilenoptionen

Verwenden Sie die Felder **Seite** und **Zeilen** , um Daten in sequenzielle Gruppen oder Seiten zu unterteilen. Auf diese Weise können Sie andere Rangzeilenwerte als die höchsten Werte in Ihren Bericht ziehen. Diese Funktion ist besonders nützlich, um Daten über die 50.000 Zeilenbegrenzung hinaus abzurufen.

#### Standardeinstellungen für Seite und Zeilen

- Seite = 1
- Zeilen = 10

Die Standardeinstellungen Seite und Zeilen geben an, dass jede Seite 10 Datenzeilen enthält. Seite 1 gibt die 10 wichtigsten Elemente zurück, Seite 2 die nächsten 10 Elemente usw.

In der folgenden Tabelle finden Sie Beispiele für Seiten- und Zeilenwerte sowie die resultierende Ausgabe.

| Seite | Zeile | Ausgabe |
|------|--------|----------------------|
| 1 | 10 | Die 10 beliebtesten Elemente |
| 2 | 10 | Posten 11-20 |
| 1 | 100 | Die 100 beliebtesten Elemente |
| 2 | 100 | Posten 101-200 |
| 2 | 50.000 | Posten 50.001-100.000 |

#### Mindest- und Höchstwerte

- Startseite: Min. = 1, Max.: 50 Mio.
- Anzahl Zeilen: Min. = 1, Max.: 50.000

### &quot;Kein Wert&quot; einschließen

Im Customer Journey Analytics sammeln einige Dimensionen den Eintrag &quot;kein Wert&quot;. Mit diesem Filter können Sie diese Werte aus Berichten ausschließen. Sie können beispielsweise eine Classification wie die Classification &quot;Produktname&quot;basierend auf dem Produkt-SKU-Schlüssel erstellen. Wenn eine bestimmte Produkt-SKU nicht mit ihrer spezifischen Produktnamenklassifizierung eingerichtet wurde, wird der Produktnamenwert auf &quot;kein Wert&quot;gesetzt.

&quot;Include &quot;**No value**&quot;ist standardmäßig ausgewählt. Deaktivieren Sie diese Option, um Einträge ohne Wert auszuschließen.

### Nach Kriterien filtern

Sie können Dimensionselemente danach filtern, ob alle Kriterien erfüllt sind oder ob ein Kriterium erfüllt ist.

So legen Sie Filterkriterien fest

1. Wählen Sie einen aus der Dropdownliste „Operator“ aus.

   ![](./assets/image31.png)

1. Geben Sie einen Wert in das Suchfeld ein.

1. Klicken Sie auf Zeile hinzufügen , um die Auswahl zu bestätigen und ein weiteres Kriterienelement hinzuzufügen.

1. Klicken Sie auf das Löschsymbol, um ein Kriterienelement zu entfernen.

   Sie können bis zu 10 Kriterienelemente einbeziehen.

### Filter ändern und Sortierreihenfolge ändern

Neben der Metrik zum Filtern und Sortieren des Datenblocks wird ein Pfeil angezeigt. Die Pfeilrichtung gibt an, ob die Metrik am größten oder am wenigsten am größten sortiert wird.

Um die Sortierrichtung zu ändern, klicken Sie auf den Pfeil neben der Metrik. 

So ändern Sie die zum Filtern und Sortieren des Datenblocks verwendete Metrik:

1. Bewegen Sie den Mauszeiger über die gewünschte Metrikkomponente im Tabellenaufbau, um zusätzliche Optionen anzuzeigen.

2. Klicken Sie auf den Pfeil der gewünschten Metrik. 

   ![](./assets/image30.png)


## Spezifische Filter

Mit der Option Spezifisch können Sie für jede Dimension eine feste Liste von Dimensionselementen erstellen. Verwenden Sie den Filtertyp **Spezifisch** , um die genauen Dimensionselemente anzugeben, die in Ihren Filter aufgenommen werden sollen. Sie können Elemente aus einer Liste oder aus einem Zellenbereich auswählen.

![](./assets/image32.png)

### Aus Liste

1. Wählen Sie die Option **Aus Liste** aus, um nach Dimensionselementen zu suchen und diese auszuwählen.

   Wenn Sie die Option **Aus Liste** auswählen, wird die Liste mit Dimensionselementen gefüllt, wobei die meisten Ereignisse zuerst auftreten.

   ![](./assets/image33.png)

   Die Liste **Verfügbare Elemente** wird von Dimensionselementen mit den meisten Ereignissen zu den Elementen mit den geringsten Werten sortiert.

1. Geben Sie einen Suchbegriff in das Feld **Element hinzufügen** ein, um die Liste zu durchsuchen.

1. Um nach einem Element zu suchen, das in den letzten 90 Tagen nicht enthalten war, klicken Sie auf **Elemente für die letzten 6 Monate anzeigen** , um die Suche zu erweitern.

   ![](./assets/image34.png)

   Nach den Daten der letzten sechs Monate, die geladen wurden, aktualisiert der Report Builder den Link auf **Elemente für die letzten 18 Monate anzeigen**.

1. Wählen Sie ein Dimensionselement aus.

   Ausgewählte Dimensionselemente werden automatisch zur Liste **Ausgewählte Elemente** hinzugefügt.

   ![](./assets/image35.png)

   Um ein Element aus der Liste zu löschen, klicken Sie auf das Löschsymbol, um das Element aus der Liste zu entfernen.

   Um ein Element in der Liste zu verschieben, ziehen Sie es per Drag-and-Drop oder klicken Sie auf ... , um das Verschiebemenü anzuzeigen.

   ![](./assets/image36.png)

1. Klicken Sie auf **Übernehmen**

   Report Builder aktualisiert die Liste, um die angewendeten spezifischen Filter anzuzeigen.

### Aus Zellenbereich

Wählen Sie die Option **Aus Zellenbereich** aus, um einen Zellenbereich auszuwählen, der die Liste der abzugleichenden Dimensionselemente enthält.

![](./assets/image37.png)

Beachten Sie bei der Auswahl eines Zellenbereichs die folgenden Einschränkungen:

- Der Bereich muss über mindestens eine Zelle verfügen.
- Der Bereich kann nicht mehr als 50.000 Zellen haben.
- Der Bereich muss sich in einer einzigen unterbrechungsfreien Zeile oder Spalte befinden.

Ihre Auswahl kann leere Zellen oder Zellen mit Werten enthalten, die nicht mit einem bestimmten Dimensionselement übereinstimmen.

### Auf der Registerkarte Dimensionen im Tabellenaufbau

Klicken Sie auf der Registerkarte **Dimensionen** auf das Pfeilsymbol neben einem Dimensionsnamen, um die Liste der Dimensionselemente anzuzeigen.

![](./assets/dimensions_chevron.png)

Sie können Elemente per Drag-and-Drop in die **Tabelle** ziehen oder auf einen Elementnamen doppelklicken, um ihn zum **Tabelle**-Builder hinzuzufügen.
