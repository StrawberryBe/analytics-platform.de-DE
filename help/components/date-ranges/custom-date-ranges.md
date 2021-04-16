---
description: Erstellen Sie benutzerdefinierte Datumsbereiche in Analysis Workspace und speichern Sie sie als Zeitkomponenten.
keywords: Analysis Workspace
title: Benutzerdefinierte Datumsbereiche erstellen
feature: Grundlagen zu Reports & Analysen
uuid: c8873d41-454d-4f22-ad1f-38cacec5a3bc
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
translation-type: tm+mt
source-git-commit: 3c10451d5a70e4f733634efb9648da843e4c0db1
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 98%

---

# Benutzerdefinierte Datumsbereiche erstellen

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Weitere Informationen ...](/help/getting-started/cja-aa.md)

Erstellen Sie benutzerdefinierte Datumsbereiche in Analysis Workspace und speichern Sie sie als Zeitkomponenten.

**[!UICONTROL Komponenten]** > **[!UICONTROL Neuer Datumsbereich]**

Ein Datumsbereich wird auf der Bereichsebene angewendet. Klicken Sie, um einen Datumsbereich zu Ihrem Projekt hinzuzufügen, auf **Bedienfelder** > *`<select panel>`* und legen Sie einen neuen Datumsbereich fest.

## Datumsbereich für „Vor zwei Monaten“ 

Der folgende benutzerdefinierte Datumsbereich zeigt den Bereich vor zwei Monaten mit einer Visualisierung der Zusammenfassungsänderung, die eine Trend-Entwicklung anzeigt.

![](assets/date-range-two-months-ago.png)

Der benutzerdefinierte Datumsbereich wird in Ihrem Projekt oben auf dem Komponentenbereich für den [!UICONTROL Datumsbereich] angezeigt:

![](assets/date-range-panel-two-months-ago.png)

Sie können diesen benutzerdefinierten Datumsbereich auf eine Spalte neben einem benutzerdefinierten, monatlichen rollierenden Datumsbereich ziehen und die Voreinstellung für den letzten Monat für den Vergleich nutzen. Fügen Sie eine Visualisierung der Sammeländerung hinzu und wählen Sie die Gesamtsummen der einzelnen Spalten aus, um eine Trendentwicklung zu zeigen:

![](assets/date-range-two-months-table.png)

## Verwenden eines 7-Tage-Datumsbereichs

Ein Datumsbereich wird auf der Bereichsebene angewendet. Klicken Sie, um einen Datumsbereich zu Ihrem Projekt hinzuzufügen, auf **Aktionen** > **Bereich hinzufügen** und geben Sie einen neuen Datumsbereich an.

Im Datumsbereich-Builder können Sie einen benutzerdefinierten Datumsbereich erstellen, der zusammen mit anderen Datumsbereichen im Komponentenbereich angezeigt wird.

Sie können z. B. einen Datumsbereich erstellen, der ein rollierendes Zeitfenster von 7 Tagen anzeigt, das vor einer Woche endet:

![](assets/create_date_range.png)

Verwenden Sie *`rolling daily`*.

* Die Starteinstellung lautet *`current day minus 14 days`*.

* Die Endeinstellung lautet *`current day minus 7 days`*.

Dieser Datumsbereich kann eine Komponente sein, die Sie auf eine beliebige Freiformtabelle ziehen können.
