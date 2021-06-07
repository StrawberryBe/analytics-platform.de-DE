---
title: Datumsbereich erstellen
description: Erstellen Sie einen Datumsbereich für die Verwendung in Berichten.
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 8%

---

# Datumsbereich erstellen

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Weitere Informationen...](/help/getting-started/cja-aa.md)

Sie können einen benutzerdefinierten Datumsbereich mit einer der beiden folgenden Methoden erstellen:

* Direkt in einem Workspace-Projekt durch Klicken auf die Schaltfläche &quot;`+`&quot;neben der Liste der Datumsbereichskomponenten auf der linken Seite
* Innerhalb des Datumsbereichsmanagers

So erstellen Sie einen Datumsbereich im Datumsbereich-Manager:

1. Melden Sie sich mit Ihren Adobe ID-Anmeldeinformationen bei [analytics.adobe.com](https://analytics.adobe.com) an.
1. Navigieren Sie zu [!UICONTROL Komponenten] > [!UICONTROL Datumsbereiche].
1. Klicken Sie auf die Schaltfläche [!UICONTROL Hinzufügen] , um das modale Fenster zu öffnen, das einen Datumsbereich erstellt.

## Erstellen eines modalen Datumsbereichsfensters

Das modale Fenster verfügt über vier Felder, die Sie bearbeiten können:

* **Datumsbereich**: Der Datumsbereich, den Sie für diese Komponente wünschen.
* **Titel**: Der Name, den Sie für diese Komponente benötigen. Der Titel wird in Workspace-Projekten verwendet.
* **Beschreibung**: Die Beschreibung, die Sie für diese Komponente benötigen. Die Beschreibung wird beim Klicken auf das Symbol ![i](../assets/i.png) angezeigt.
* **Tags**: Organisieren Sie Ihre Datumsbereiche mithilfe von Tags. Ein Datumsbereich kann mehreren Tags angehören.

## Datumsbereich auswählen

Beim Klicken auf den Datumsbereich im modalen Fenster haben Sie mehrere Optionen:

* **Kalender**: Wählen Sie das Start- und Enddatum aus.
* **Rollierende Datumswerte** verwenden: Aktivieren Sie dieses Kontrollkästchen, wenn Sie möchten, dass sich der Datumsbereich im Laufe der Zeit ändert. Aktivieren Sie dieses Kontrollkästchen nicht, wenn Ihr Datumsbereich statisch bleiben soll.
* **Vorgabe auswählen**: Verwenden Sie dieses Dropdown-Menü, wenn Sie einen benutzerdefinierten Datumsbereich wünschen, der auf einem von Adobe standardmäßig angebotenen Bereich basiert. Wenn Sie eine Vorgabe auswählen, können Sie den Datumsbereich entsprechend Ihren Anforderungen weiter anpassen. Die von Adobe angebotene Vorgabe wird dadurch nicht beeinflusst.

## Rollierende Datumsbereiche

Wenn Sie einen rollierenden Datumsbereich wünschen, können Sie den Rollout anpassen. Sie können steuern, wann die Start- und Enddaten unabhängig voneinander rollierend sind.

* **Wenn das Datum beginnt**: Wählen Sie aus, ob das Datum am Anfang eines Zeitraums, am Ende eines Zeitraums beginnt, oder verwenden Sie einen festen Tag.
* **Der zu verwendende** Zeitraum: Wählen Sie aus, wie oft der Datumsbereich rolliert. Sie können es täglich, jede Woche, jeden Monat, jedes Quartal oder jedes Jahr rollen lassen.
* **Versatz**: Wählen Sie den Versatz des Datumsbereichs aus. Sie können Tage, Wochen, Monate, Quartale oder Jahre hinzufügen oder subtrahieren.

## Rollierende Datumsbeispiele

Einige Datumsbereiche können in bestimmten Berichten nützlich sein.

Jahr bis Datum:

```text
Start: Start of current year
End: End of current day
```

Letzten Donnerstag bis Donnerstag:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Haushaltsjahr (z. B. wenn ein Geschäftsjahr im Dezember beginnt)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```
