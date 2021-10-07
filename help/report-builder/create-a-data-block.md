---
title: Erstellen eines Datenblocks mit Report Builder in CJA
description: Beschreibt, wie ein Datenblock erstellt wird.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: d946e6dbda608499594cf48a9456131485e7349a
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---


# Erstellen eines Datenblocks

Ein *Datenblock* ist die Datentabelle, die von einer einzelnen Datenanforderung erstellt wird. Eine Report Builder-Arbeitsmappe kann mehrere Datenblöcke enthalten. Konfigurieren Sie bei der Erstellung eines Datenblocks zunächst den Datenblock und dann den Datenblock.

## Datenblock konfigurieren

Konfigurieren Sie die anfänglichen Datenblockparameter für die Position der Datenblöcke, die Datenansichten und einen Datumsbereich.

1. Klicken Sie auf **Datenblock erstellen**.

   ![](./assets/create_db.png)

1. Legen Sie den Speicherort **Datenblock** fest.

   Die Option &quot;Datenblock-Speicherort&quot;definiert den Speicherort des Arbeitsblatts, an dem ReportBuilder die Daten zu Ihrem Arbeitsblatt hinzufügt.

   Um den Speicherort des Datenblocks anzugeben, wählen Sie eine einzelne Zelle im Arbeitsblatt aus oder geben Sie eine Zellenadresse ein, z. B. a3, \\\$a3, a\\$3 oder sheet1!a2. Die angegebene Zelle ist die obere linke Ecke des Datenblocks, wenn die Daten abgerufen werden.

1. Wählen Sie **Datenansichten** aus.

   Mit der Option Datenansichten können Sie eine Datenansicht aus einem Dropdown-Menü auswählen oder auf eine Datenansicht aus einer Zellenposition verweisen.

1. Legen Sie den **Datumsbereich** fest.

   Mit der Option Datumsbereich können Sie einen Datumsbereich auswählen. Datumsbereiche können fest oder rollierend sein. Weitere Informationen zu den Datumsbereichsoptionen finden Sie unter &lt;&lt; Abschnitt zum Datumsbereich >>.

1. Klicken Sie auf **Next**.

   ![](./assets/choose_date_data_view3.png)

   Nach der Konfiguration des Datenblocks können Sie Dimensionen, Metriken und Filter auswählen, um Ihren Datenblock zu erstellen. Die Registerkarten &quot;Dimensionen&quot;, &quot;Metriken&quot;und &quot;Filter&quot;werden über dem Bereich &quot;Tabellenaufbau&quot;angezeigt.
<!--
    ![](./assets/image9.png)
  -->


## Datenblock erstellen

Um den Datenblock zu erstellen, wählen Sie Berichtkomponenten aus und passen Sie dann das Layout an.

1. Fügen Sie Dimensionen, Metriken und Filter hinzu.

   Scrollen Sie in den Komponentenlisten oder verwenden Sie das Feld **search** , um Komponenten zu finden. Ziehen Sie Komponenten per Drag-and-Drop in den Tabellenbereich oder doppelklicken Sie auf einen Komponentennamen in der Liste, um die Komponente automatisch zum Tabellenbereich hinzuzufügen.

   Doppelklicken Sie auf eine Komponente, um sie einem Standardabschnitt der Tabelle hinzuzufügen.

   - Dimension-Komponenten werden zum Bereich Zeile oder zum Bereich Spalte hinzugefügt, wenn Sie bereits eine Dimension in den Spalten haben.
   - Datumskomponenten werden dem Abschnitt Spalte hinzugefügt.
   - Filterkomponenten werden dem Abschnitt Filter hinzugefügt.

1. Ordnen Sie die Elemente im Tabellenbereich an, um das Layout Ihres Datenblocks anzupassen.

   Ziehen Sie Komponenten per Drag-and-Drop in den Tabellenbereich, um Komponenten neu anzuordnen, oder klicken Sie mit der rechten Maustaste auf einen Komponentennamen und wählen Sie im Optionsmenü die Option aus.

   Wenn Sie Komponenten zur Tabelle hinzufügen, wird eine Vorschau des Datenblocks an der Stelle des Datenblocks im Arbeitsblatt angezeigt. Das Layout der Datenblock-Vorschau wird automatisch aktualisiert, wenn Sie Elemente in der Tabelle hinzufügen, verschieben oder entfernen.

   ![](./assets/image10.png)

1. Klicken Sie auf **Finish**.

   Eine Verarbeitungsmeldung wird angezeigt, während die Analysedaten abgerufen werden.

   ![](./assets/image11.png)

   Report Builder ruft die Daten ab und zeigt den abgeschlossenen Datenblock im Arbeitsblatt an.

   ![](./assets/image12.png)
