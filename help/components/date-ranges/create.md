---
title: Datumsbereich erstellen
description: Erstellen Sie einen Datumsbereich für die Verwendung in Berichte.
translation-type: tm+mt
source-git-commit: 2452490cc2f147cfd87540a68be2d0c219d8744f

---


# Datumsbereich erstellen

Sie können einen benutzerdefinierten Datumsbereich mit einer der beiden folgenden Methoden erstellen:

* Direkt in einem Arbeitsflächenprojekt durch Klicken auf die Schaltfläche &#39;`+`&#39; neben der Liste der Datumsbereichskomponenten links
* Innerhalb des Datumsbereichsmanagers

So erstellen Sie einen Datumsbereich im Datumsbereich-Manager:

1. Melden Sie sich mit Ihren AdobeID-Anmeldeinformationen bei [analytics.adobe.com](https://analytics.adobe.com) an.
1. Navigieren Sie zu [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Klicken Sie auf die [!UICONTROL Add] Schaltfläche, um das modale Fenster zu öffnen, das einen Datumsbereich erstellt.

## Erstellen eines modalen Datumsbereichsfensters

Das modale Fenster verfügt über vier Felder, die Sie bearbeiten können:

* **Datumsbereich**: Der Datumsbereich, den Sie für diese Komponente festlegen möchten.
* **Titel**: Der Name, den Sie für diese Komponente verwenden möchten. Der Titel wird in Workspace-Projekten verwendet.
* **Beschreibung**: Die Beschreibung, die Sie für diese Komponente benötigen. Die Beschreibung wird beim Klicken auf das ![i](../assets/i.png) -Symbol angezeigt.
* **Tags**: Verwenden Sie Tags, um Ihre Datumsbereiche zu organisieren. Ein Datumsbereich kann zu mehreren Tags gehören.

## Auswählen eines Datumsbereichs

Wenn Sie im modalen Fenster auf den Datumsbereich klicken, stehen Ihnen mehrere Optionen zur Verfügung:

* **Kalender**: Wählen Sie den Beginn und das Enddatum aus.
* **rollierende Daten** verwenden: Aktivieren Sie dieses Kontrollkästchen, wenn sich der Datumsbereich im Laufe der Zeit ändern soll. Aktivieren Sie dieses Kontrollkästchen nicht, wenn der Datumsbereich statisch bleiben soll.
* **Vorgabe** auswählen: Verwenden Sie dieses Dropdownmenü, wenn Sie einen benutzerdefinierten Datumsbereich möchten, der auf einem von Adobe standardmäßig Angebot Datumsbereich basiert. Wenn Sie eine Vorgabe auswählen, können Sie den Datumsbereich weiter an Ihre Anforderungen anpassen. Die Vorgabe, die Adobe Angebot verwendet, bleibt davon unberührt.

## Rollierende Datumsbereiche

Wenn Sie einen rollierenden Datumsbereich wünschen, können Sie ihn beim Rollen anpassen. Sie können steuern, wann Beginns- und Enddaten unabhängig voneinander laufen.

* **Beginn** des Datums: Wählen Sie aus, ob das Datum am Anfang eines Zeitraums, am Ende eines Zeitraums oder an einem bestimmten Tag Beginn wird.
* **Der zu verwendende** Zeitraum: Legen Sie fest, wie oft der Datumsbereich rolliert. Sie können es jeden Tag, jede Woche, jeden Monat, jedes Quartal oder jedes Jahr rollen lassen.
* **Versatz**: Wählen Sie den Versatz des Datumsbereichs. Sie können Tage, Wochen, Monate, Quartale oder Jahre hinzufügen oder abziehen.

## Beispiele für rollierende Datumswerte

Einige Datumsbereiche können in bestimmten Berichten nützlich sein.

Aktuell:

```text
Start: Start of current year
End: End of current day
```

Letzter Donnerstag bis Donnerstag:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Haushaltsjahr (z. B. wenn ein Haushaltsjahr im Dezember Beginn ist)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
