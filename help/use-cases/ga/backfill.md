---
title: Erfassen von Google Analytics-Verlaufsdaten in Adobe Experience Platform
description: Erläutert die Verwendung von Customer Journey Analytics (CJA) zur Aufnahme Ihrer Google Analytics-Daten in Adobe Experience Platform.
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: f65f13d696ad2045f58ccb5c9ef7fed45eb9d68c
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 9%

---


# Erfassen von Google Analytics-Verlaufsdaten in Adobe Experience Platform

Auf dieser Seite wird beschrieben, wie Sie Ihre Google Analytics historische Daten in Adobe Experience Platform als Datensatz erfassen und so in einer Datenansicht in Customer Journey Analytics auf diesen Datensatz verweisen können. Sie können die Schritte auf dieser Seite mit [Live-Google Analytics-Implementierung konfigurieren](streaming.md), wodurch ein sich wiederholender Datensatz generiert wird. Kombinieren Sie diesen historischen Datensatz mit dem Datensatz Ihrer aktuellen Implementierung, um eine nahtlose Ansicht der Daten im Customer Journey Analytics mit aktuellen und aufgestockten Daten zu erhalten.

## Voraussetzungen

Um diese Aufgaben ausführen zu können, benötigen Sie die folgenden Zugriffsrechte:

* Zugriff auf Adobe Experience Platform
* Zugriff auf Google Analytics (GA Standard oder GA 360)
* [Administratorzugriff](/help/getting-started/cja-access-control.md) Customer Journey Analytics

## Einrichten eines BigQuery-Exports

Die Datenstruktur in universellen Analytics-Eigenschaften unterscheidet sich von der Datenstruktur in den Eigenschaften von Google Analytics 4. Richten Sie einen BigQuery-Export basierend auf dem Eigenschaftstyp ein, aus dem Sie Daten exportieren möchten:

* [Einrichten eines BigQuery-Exports für eine Universal Analytics-Eigenschaft](https://support.google.com/analytics/answer/3416092)
* [Einrichten eines BigQuery-Exports für eine Google Analytics 4-Eigenschaft](https://support.google.com/analytics/answer/9823238)

### Zusätzliche Anforderungen für universelle Analytics-Eigenschaften

>[!NOTE]
>
>Dieser Abschnitt gilt nur für universelle Analytics-Eigenschaften. Wenn Sie aus einer GA4-Eigenschaft exportieren, können Sie mit [Daten in Google Cloud Platform exportieren](#export-gcp).

In den universellen Analytics-Eigenschaften werden die einzelnen Datensätze in den Daten als Benutzersitzung und nicht als einzelne Ereignisse gespeichert. Es ist eine SQL-Abfrage erforderlich, um die universellen Analytics-Daten in ein mit Adobe Experience Platform kompatibles Format umzuwandeln. Wenden Sie die `UNNEST` -Funktion `hits` im GA-Schema und speichern Sie es als BigQuery-Tabelle.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

```sql
SELECT
   *,
   timestamp_seconds(`visitStartTime` + hit.time) AS `timestamp` 
FROM
   (
      SELECT
         fullVisitorId,
         visitNumber,
         visitId,
         visitStartTime,
         trafficSource,
         socialEngagementType,
         channelGrouping,
         device,
         geoNetwork,
         hit 
      FROM
         `example_bq_table_*`,
         UNNEST(hits) AS hit 
   )
```

## Daten in Google Cloud Platform exportieren {#export-gcp}

Navigieren Sie in Google Cloud Platform zu **Exportieren > Exportieren in GCS**. Sobald sich die Daten im Google Cloud-Speicher befinden, können sie in Adobe Experience Platform abgerufen werden.

## Importieren Sie die Daten aus Google Cloud Storage in Experience Platform

1. Wählen Sie in Adobe Experience Platform **[!UICONTROL Quellen]** auf der linken Seite.
1. Suchen Sie unter dem Katalog nach **[!UICONTROL Google Cloud Storage]** -Option. Klicken **[!UICONTROL Daten hinzufügen]**.

>[!VIDEO](https://video.tv.adobe.com/v/332676)

>[!TIP]
>
>Wenn Sie sowohl historische als auch Live-Streaming-Google Analytics-Daten importieren möchten, stellen Sie sicher, dass Sie dasselbe Schema für beide Datensätze verwenden. Sie können die Datensätze in einer Customer Journey Analytics mithilfe einer [Kombinierter Datensatz](/help/connections/combined-dataset.md).

Sie können die GA-Ereignisdaten einem vorhandenen Datensatz zuordnen, den Sie zuvor erstellt haben, oder einen Datensatz mit einem beliebigen XDM-Schema erstellen. Nachdem Sie das Schema ausgewählt haben, wendet Experience Platform maschinelles Lernen an, um jedes der Felder in den Daten von Google Analytics automatisch Ihrem [XDM-Schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de#ui) vor-zuzuordnen.

![Schema Map](../assets/schema-map.png)

Nachdem Sie die Zuordnung der Felder zu Ihrem XDM-Schema abgeschlossen haben, können Sie diesen Import auf wiederkehrender Basis planen und während des Aufnahmevorgangs eine Fehlervalidierung anwenden. Diese Validierung stellt sicher, dass es keine Probleme mit den importierten Daten gibt.

## Erforderliche XDM-Felder

Bestimmte XDM-Felder in Platform benötigen das richtige Format, damit Daten korrekt verarbeitet werden können.

* **`timestamp`**: Erstellen Sie ein spezielles berechnetes Feld in der Benutzeroberfläche des Experience Platform-Schemas. Klicken **[!UICONTROL Berechnetes Feld hinzufügen]** und die `timestamp` in einer `date` Funktion:

   `date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

   Speichern Sie das berechnete Feld in der Zeitstempeldatenstruktur im Schema:

   ![Zeitstempel](../assets/timestamp.png)

* **`_id`**: Dieses Feld muss einen Wert enthalten - CJA spielt keine Rolle, was der Wert ist. Sie können dem Feld &quot;1&quot;hinzufügen:

   ![ID](../assets/_id.png)

## Nächste Schritte

* Wenn Sie aktuelle Daten haben, die Sie in Adobe Experience Platform streamen möchten, lesen Sie [Streaming für Google Analytics-Daten einrichten](streaming.md).
* Wenn Sie mit der Berichterstellung für aufgestockte Daten beginnen möchten, lesen Sie [Verbindung erstellen](/help/connections/create-connection.md).
