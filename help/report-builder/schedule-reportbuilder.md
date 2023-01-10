---
title: Planung von Arbeitsmappen mit Report Builder in Customer Journey Analytics
description: Beschreibt die Verwendung der Planungsfunktion in Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
source-git-commit: 4c48aa3413ff3c2d3b29e7fc1ca4c73a80c0972d
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 0%

---


# Arbeitsmappen planen

Nachdem Sie die Arbeitsmappe gespeichert und die Analyse abgeschlossen haben, können Sie sie mithilfe der Planungsfunktion einfach für andere in Ihrem Team freigeben. Mit der Funktion Planung können Sie einen Zeitplan erstellen, der die Daten in der Arbeitsmappe automatisch aktualisiert und die Excel-Arbeitsmappe .xlsx als Anhang an Ihre angegebene Zielgruppe zu einem bestimmten Zeitpunkt per E-Mail sendet. Durch die Einrichtung eines Zeitplans erhalten die Empfänger regelmäßige Aktualisierungen automatisch. Sie können auch die Planungsfunktion verwenden, um die Arbeitsmappe einmal auszuführen, ohne automatische Aktualisierungen zu planen.

Sie können für eine Arbeitsmappe mehrere Zeitpläne erstellen. Sie können beispielsweise eine Arbeitsmappe täglich an Ihr Team senden und die Arbeitsmappe einmal wöchentlich an Ihren Manager senden, indem Sie zwei verschiedene Zeitpläne erstellen.

Mit der Planungsfunktion können Sie außerdem den Kennwortschutz für eine Arbeitsmappe einrichten und zuvor geplante Arbeitsmappen bearbeiten.

>[!VIDEO](https://video.tv.adobe.com/v/3413079/?quality=12&learn=on)

## Arbeitsmappe planen

Verwenden Sie die Schaltfläche Aufgabe planen im Report Builder-Hub, um schnell einen Zeitplan zu erstellen, damit Sie eine Excel-Arbeitsmappe (.xlsx) automatisch an eine Einzelperson oder eine Gruppe verteilen können.

1. Klicken Sie im Report Builder-Hub auf die Schaltfläche Planen .

   ![](./assets/schedule-button.png){width="55%"}

1. Klicken Sie oben links auf Arbeitsmappe planen oder auf die Plusschaltfläche , um eine neue geplante Arbeitsmappe zu erstellen.

   ![ALT-Beschreibung](./assets/schedule-workbook.png){width="55%"}

   Im Planungsfenster werden einige vordefinierte Informationen zur Arbeitsmappe angezeigt, z. B. der Arbeitsmappenname und das letzte Änderungsdatum der Arbeitsmappe.

   ![ALT-Beschreibung](./assets/schedule-pane.png){width="55%"}

1. (Optional) Geben Sie einen Dateinamen ein.

   Der Dateiname der Arbeitsmappe entspricht standardmäßig dem Namen der Arbeitsmappe. Sie können ihn jedoch bei Bedarf ändern. Wenn Sie dieselbe Arbeitsmappe an mehrere Zielgruppen senden und sie für eine bestimmte Zielgruppe etwas benutzerfreundlicher benennen möchten, können Sie den Namen ändern.

1. (Optional) Wählen Sie **Zeitstempel an Dateinamen anhängen**.

   Sie können einen Zeitstempel an den Dateinamen anhängen, um das Datum der Aktualisierung der Arbeitsmappe anzugeben. Dies ist hilfreich, um schnell zu sehen, welche Version einer Arbeitsmappe an einem bestimmten Datum gesendet wurde. Die **Dateinamenvorschau** zeigt an, wie der Dateiname der Arbeitsmappe in der E-Mail angezeigt wird, wenn die Arbeitsmappe verteilt wird. Das Zeitstempelformat ist JJJ-MM-TT.

1. (Optional) Wählen Sie **.zip-Komprimierung** , um die Datei zu komprimieren und einen Kennwortschutz für die Datei einzurichten.

   Wenn Sie diese Auswahl treffen, werden Sie aufgefordert, ein Kennwort einzugeben, um die Datei zu öffnen. Dies ist hilfreich, wenn Sie Bedenken hinsichtlich der Datensicherheit haben und die Arbeitsmappe mit einem Kennwort geschützt werden möchten. Zum Schutz der Datei mit einem Kennwort müssen Sie Folgendes auswählen: **.zip-Komprimierung**. Das Kennwort muss mindestens 8 Zeichen lang sein und eine Zahl sowie ein Sonderzeichen enthalten.

   ![ALT-Beschreibung](./assets/zip-compression.png){width="55%"}

1. Eingabe **Empfänger**. Sie können den Namen einer in Ihrem Unternehmen anerkannten Person eingeben oder eine E-Mail-Adresse einer Person innerhalb oder außerhalb Ihres Unternehmens eingeben.

1. Geben Sie die **Betreff** der E-Mail und eine Beschreibung für Ihre Empfänger. Der Betreff verwendet standardmäßig den Namen der Arbeitsmappen-Datei. Sie können den Betreff jedoch bei Bedarf ändern. Sie können Details im Beschreibungsabschnitt hinzufügen.

   ![ALT-Beschreibung](./assets/recipients-subject.png){width="55%"}

1. Richten Sie die Planungsoptionen ein, um das Datum und die Uhrzeit festzulegen, zu dem die Arbeitsmappe per E-Mail an Ihre Empfänger gesendet werden soll.

   Wählen Sie das Start- und Enddatum und die Zeitrahmen aus. Dies kann das heutige Datum oder ein Datum in der Zukunft sein.

   Wählen Sie die **Häufigkeit** aus dem Dropdown-Menü. Sie können die Häufigkeit auf stündlich, täglich, wöchentlich, monatlich oder jährlich an einem bestimmten Tag einstellen. Sie können beispielsweise einen Zeitplan einrichten, um die Arbeitsmappe am ersten Sonntagabend des Monats zu senden, sodass Ihre Empfänger die E-Mail am Montagmorgen in ihrem Posteingang haben.

   ![ALT-Beschreibung](./assets/frequency.png){width="55%"}

1. Nachdem Sie den Zeitplan festgelegt haben, klicken Sie auf **Planmäßig senden**.

   ![ALT-Beschreibung](./assets/send-on-schedule.png){width="55%"}

   Unten im Report Builder-Hub wird ein Bestätigungstoast angezeigt, und die geplante Arbeitsmappe wird auf der Registerkarte Arbeitsmappen aufgeführt.

   ![ALT-Beschreibung](./assets/confirmation-toast.png){width="55%"}

## Arbeitsmappe nur einmal senden

Sie können die Arbeitsmappe auch nur einmal versenden.

1. Deaktivieren **Planungsoptionen anzeigen**

   ![ALT-Beschreibung](./assets/send-now.png){width="40%"}

1. Klicken Sie auf **Jetzt senden**.

## Geplante Arbeitsmappen anzeigen und bearbeiten

Sie können alle geplanten Arbeitsmappen an einem Ort auf der Registerkarte Arbeitsmappen anzeigen und verwalten.

1. Klicken Sie im Bereich Planung des Report Builder-Hub auf die Registerkarte Arbeitsmappen . Verwenden Sie diese Ansicht, um eine Liste aller geplanten Arbeitsmappen anzuzeigen.

1. Wählen Sie eine Arbeitsmappe aus. Es werden verschiedene Tools angezeigt, mit denen Sie die Arbeitsmappe bearbeiten, den Zeitplan ändern, den Zeitplan anhalten und neu starten oder den Zeitplan löschen können.

   ![ALT-Beschreibung](./assets/edit-icons.png){width="55%"}

* (Optional) Klicken Sie auf das Stiftsymbol, um den Arbeitsmappen-Zeitplan zu bearbeiten.

* (Optional) Klicken Sie auf das Uhrensymbol, um einen Verlauf jeder geplanten Aufgabe anzuzeigen.

* (Optional) Klicken Sie auf das Pausensymbol, um den Verteilungszeitplan anzuhalten und neu zu starten. Dies ist hilfreich, wenn Sie die Arbeitsmappe ändern müssen, bevor die Arbeitsmappe gesendet wird. Klicken Sie erneut auf das Pausensymbol , wenn Sie die Distribution neu starten möchten.

* (Optional) Klicken Sie auf den Papierkorb, um den Zeitplan zu löschen.

## Status geplanter Aufgaben überprüfen

In der Verlaufsansicht können Sie den Status jeder geplanten Aufgabe überprüfen. Es gibt eine separate Zeile, die die Statusänderung für jede geplante Aufgabe dokumentiert. Im folgenden Beispiel wird die Variable *Neuer Stundenplan* wurde am 5. Januar um 15:04 Uhr eröffnet. Bis 15:05 Uhr wurde er erfolgreich aktualisiert und an Empfänger gesendet. die nächste Arbeitsmappe, *Ungültige Arbeitsmappe* während des Aktualisierungsprozesses einen Fehler aufgetreten ist. Wenn eine Arbeitsmappe nicht gesendet werden konnte, hilft Ihnen der Tab Verlauf bei der Fehlerbehebung, indem er anzeigt, wo im Prozess der Fehler aufgetreten ist. In diesem Fall ist dies wahrscheinlich auf einen Datenblockfehler zurückzuführen, der die Arbeitsmappe daran hinderte, erfolgreich zu aktualisieren. Dies ist möglicherweise eine fehlende Komponente.

Ein grünes Häkchen bedeutet, dass die Arbeitsmappe erfolgreich gesendet wurde. Ein Ausrufezeichen in einem roten Dreieck zeigt an, dass ein Fehler aufgetreten ist.

Sie können auswählen, welche Spalten im Tab Verlauf angezeigt werden sollen, indem Sie rechts neben der Suchleiste auf das Spalteneinstellungssymbol klicken.

![ALT-Beschreibung](./assets/history.png){width="55%"}

Sie können den Verlauf so filtern, dass nur der eines einzelnen geplanten Arbeitsmappen angezeigt wird. Gehen Sie dazu in den Tab Arbeitsmappen , wählen Sie die Arbeitsmappe aus und klicken Sie auf das Verlaufssymbol .

Sie können den Verlauf einer bestimmten Arbeitsmappe auch auf der Registerkarte Arbeitsmappen anzeigen. Wählen Sie auf der Registerkarte Arbeitsmappen die Arbeitsmappe aus und klicken Sie auf das Verlaufssymbol.

![ALT-Beschreibung](./assets/history2.png){width="55%"}

Der Arbeitsmappen-Filter wird dann oben im Verlauf angezeigt. Um den Verlauf aller geplanten Aufgaben erneut anzuzeigen, klicken Sie auf das x neben dem Filter.

![ALT-Beschreibung](./assets/history3.png){width="55%"}



