---
title: Datumsbereich erstellen
description: Erstellen Sie einen Datumsbereich für die Verwendung in Berichte.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 10%

---


# Datumsbereich erstellen

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Mehr Infos...](/help/getting-started/cja-aa.md)

Sie können einen benutzerdefinierten Datumsbereich mit einer der beiden folgenden Methoden erstellen:

* Direkt in einem Workspace-Projekt, indem Sie auf`+`&quot; neben der Liste der Datumsbereichskomponenten auf der linken Seite
* Innerhalb des Datumsbereichsmanagers

So erstellen Sie einen Datumsbereich im Datumsbereich-Manager:

1. Anmelden bei [analytics.adobe.com](https://analytics.adobe.com) mit Ihren AdobeID-Anmeldeinformationen.
1. Navigieren zu [!UICONTROL Komponenten] > [!UICONTROL Datumsbereiche].
1. Klicken Sie auf [!UICONTROL hinzufügen] , um das modale Fenster zu öffnen, das einen Datumsbereich erstellt.

## Erstellen eines modalen Datumsbereichsfensters

Das modale Fenster verfügt über vier Felder, die Sie bearbeiten können:

* **Datumsbereich**: Der Datumsbereich, den Sie für diese Komponente festlegen möchten.
* **Titel**: Der Name, den Sie für diese Komponente verwenden möchten. Der Titel wird in Workspace-Projekten verwendet.
* **Beschreibung**: Die Beschreibung, die Sie für diese Komponente benötigen. Die Beschreibung wird angezeigt, wenn Sie auf die ![i](../assets/i.png) Symbol.
* **Tags**: Verwenden Sie Tags, um Ihre Datumsbereiche zu organisieren. Ein Datumsbereich kann zu mehreren Tags gehören.

## Auswählen eines Datumsbereichs

Wenn Sie im modalen Fenster auf den Datumsbereich klicken, stehen Ihnen mehrere Optionen zur Verfügung:

* **Kalender**: Wählen Sie den Beginn und das Enddatum aus.
* **Rollierende Datumswerte verwenden**: Aktivieren Sie dieses Kontrollkästchen, wenn sich der Datumsbereich im Laufe der Zeit ändern soll. Aktivieren Sie dieses Kontrollkästchen nicht, wenn der Datumsbereich statisch bleiben soll.
* **Vorgabe auswählen**: Verwenden Sie diese Dropdownliste, wenn Sie einen benutzerdefinierten Datumsbereich möchten, der auf einem Bereich basiert, der standardmäßig von der Adobe Angebot wird. Wenn Sie eine Vorgabe auswählen, können Sie den Datumsbereich weiter an Ihre Anforderungen anpassen. Sie hat keine Auswirkungen auf die Vorgabe, die von der Adobe Angebot wird.

## Rollierende Datumsbereiche

Wenn Sie einen rollierenden Datumsbereich wünschen, können Sie ihn beim Rollen anpassen. Sie können steuern, wann Beginns- und Enddaten unabhängig voneinander laufen.

* **Beginn des Datums**: Wählen Sie aus, ob das Datum am Anfang eines Zeitraums, am Ende eines Zeitraums oder an einem bestimmten Tag Beginn wird.
* **Der zu verwendende Zeitraum**: Legen Sie fest, wie oft der Datumsbereich rolliert. Sie können es jeden Tag, jede Woche, jeden Monat, jedes Quartal oder jedes Jahr rollen lassen.
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
