---
title: Aufnehmen von Daten aus Google Analytics in Adobe Experience Platform
description: 'Erläutert, wie Sie Customer Journey Analytics (CJA) nutzen können, um Ihre Google Analytics-Daten in Adobe Experience Platform aufzunehmen. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 100%

---


# Aufnehmen von Daten aus Google Analytics in Adobe Experience Platform

Dieser Verwendungsfall konzentriert sich darauf, wie Sie Ihre Google Analytics-Daten als Datensatz in Adobe Experience Platform aufnehmen. Wir erklären Ihnen, wie Sie sowohl Verlaufs- als auch Live-Daten aufnehmen können. Anschließend können Sie beide Datensätze in Customer Journey Analytics kombinieren, um eine geräteübergreifende Ansicht der Journey Ihres Benutzers zu erzielen.

Datensätze in Experience Platform bestehen aus zwei Elementen: einem Schema und den tatsächlichen Datensätzen im Datensatz. Das Schema (wir nennen es das Experience-Datenmodell oder kurz XDM) ähnelt den Spalten des Datensatzes und entspricht dem Blueprint oder den Regeln, die die Daten selbst beschreiben. Innerhalb von Platform bietet Adobe zwei Typen von Schemas:

* Vordefinierte Schemas, mit denen Sie Ihre Google Analytics-Daten automatisch zuordnen können (als Erlebnisereignis-Schemas bezeichnet)
* Benutzerspezifische Schemas, die Sie erstellen und denen Sie die Google Analytics-Daten einfach zuordnen können

Einer der leistungsfähigsten Aspekte des Datenmodells von Adobe ist, dass es Ihnen ermöglicht, alle Ihre Kundeninteraktionsdaten in einem gemeinsamen Schema zu standardisieren – das macht es wesentlich einfacher, die Daten in CJA zusammenzufügen.

## Voraussetzungen

Um diese Aufgaben ausführen zu können, benötigen Sie die folgenden Zugriffsrechte:

* Zugriff auf Adobe Experience Platform
* Zugriff auf Universal Google Analytics (Version Google Analytics 360) oder Google Analytics 4 (kostenlose Version oder Version Google Analytics 360)
* Zugriff auf Customer Journey Analytics und dessen [Administratorberechtigungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=de#admin-access-permissions).

Wie Sie Daten von Google Analytics in Adobe Experience Platform importieren, hängt davon ab, welche Version von Google Analytics Sie verwenden:

| Bei Verwendung von... | Sie benötigen auch diese Lizenz... | Führen Sie Folgendes aus... |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | Führen Sie die Schritte 1 bis 3 der folgenden Anweisungen aus |
| **Google Analytics 4** | Kostenlose GA-Version oder Google Analytics 360 | Führen Sie die Schritte 1 und 3 der folgenden Anweisungen aus. Schritt 2 ist nicht erforderlich. |

## Verlaufsdaten (Aufstockung) aufnehmen

### 1. Ihre Google Analytics-Daten mit BigQuery verbinden

Weitere Informationen finden Sie in [diesen Anweisungen](https://support.google.com/analytics/answer/3416092?hl=de). Beachten Sie, dass diese Anweisungen auf Universal Google Analytics basieren.

### 2. Transformieren von Google Analytics-Sitzungen in Ereignisse in BigQuery und Exportieren an den Google Cloud-Datenspeicherplatz

>[!IMPORTANT]
>
>Dieser Schritt gilt nur für Kunden von Universal Analytics

GA-Daten speichern jeden Datensatz in ihren Daten als Benutzersitzung und nicht als einzelne Ereignisse. Sie müssen eine SQL-Abfrage erstellen, um die Universal Analytics-Daten in ein mit Experience Platform kompatibles Format umzuwandeln. Sie wenden die Funktion „unnest“ auf das Feld „Treffer“ im GA-Schema an. Hier finden Sie das SQL-Beispiel, das Sie verwenden können:

```
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
         `your_bq_table_2021_04_*`,
         UNNEST(hits) AS hit 
   )
```

Speichern Sie nach Abschluss der Abfrage die vollständigen Ergebnisse in einer BigQuery-Tabelle.

Weitere Informationen finden Sie in [diesen Anweisungen](https://support.google.com/analytics/answer/7029846?hl=de&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql), die Anweisungen zur SQL-Abfrage enthalten.

Im folgenden Video wird auch der nächste Schritt erläutert, der darin besteht, die Google Analytics-Ereignisse im JSON-Format an den Google Cloud-Datenspeicherplatz zu exportieren. Klicken Sie einfach auf **Export > Export nach GCS**. Dort können die Daten in Adobe Experience Platform eingebracht werden.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Daten vom Google Cloud-Datenspeicherplatz in Experience Platform importieren und XDM-Schema zuordnen

Wählen Sie in Experience Platform **[!UICONTROL Quellen]** und suchen Sie die Option **[!UICONTROL Google Cloud-Datenspeicherplatz]**. Von hier aus müssen Sie nur den Datensatz finden, den Sie aus BigQuery gespeichert haben.

Beachten Sie:

* Stellen Sie sicher, dass Sie das JSON-Format auswählen.
* Sie können einen vorhandenen Datensatz auswählen oder einen neuen Datensatz erstellen (empfohlen).
* Stellen Sie sicher, dass Sie dasselbe Schema für Daten zu Verlaufsdaten von Google Analytics und Live-Streaming-Daten von Google Analytics auswählen, auch wenn diese sich in separaten Datensätzen befinden. Anschließend können Sie die Datensätze in einer [Customer Journey Analytics-Verbindung](/help/connections/combined-dataset.md) zusammenführen.

Anleitungen finden Sie in diesem Video:

>[!VIDEO](https://video.tv.adobe.com/v/332676)

Sie können die GA-Ereignisdaten einem vorhandenen Datensatz zuordnen, den Sie zuvor erstellt haben, oder einen neuen Datensatz erstellen, wobei Sie ein beliebiges XDM-Schema verwenden. Nachdem Sie das Schema ausgewählt haben, wendet Experience Platform maschinelles Lernen an, um jedes der Felder in den Daten von Google Analytics automatisch Ihrem [XDM-Schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de#ui) vor-zuzuordnen.

![](assets/schema-map.png)

Zuordnungen lassen sich leicht ändern, und Sie können sogar abgeleitete oder berechnete Felder aus den Daten von Google Analytics erstellen. Nachdem Sie die Zuordnung der Felder zu Ihrem XDM-Schema abgeschlossen haben, können Sie diesen Import wiederholt terminieren und während des Aufnahmevorgangs eine Fehlerüberprüfung anwenden. Dadurch wird sichergestellt, dass keine Probleme mit den importierten Daten auftreten.

**Berechnetes Feld „Zeitstempel“**

Für das Schemafeld `timestamp` in den Daten von Google Analytics müssen Sie ein spezielles berechnetes Feld in der Schema-Benutzeroberfläche von Experience Platform erstellen. Klicken Sie auf **[!UICONTROL Berechnetes Feld hinzufügen]** und schließen Sie die `timestamp`-Zeichenfolge in eine `date`-Funktion ein wie folgt:

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

Anschließend müssen Sie dieses berechnete Feld in der Zeitstempeldatenstruktur im Schema speichern:

![](assets/timestamp.png)

**berechnetes Feld „_id“**

Das Schema `_id` muss einen Wert enthalten – welcher, spielt für CJA keine Rolle. Sie können einfach eine „1“ zu dem Feld hinzufügen:

![](assets/_id.png)

## Live-Streaming-Daten von Google Analytics aufnehmen

Sie können auch Live-Streaming-Ereignisse von Google Tag Manager direkt in Adobe Experience Platform erfassen.

### 1. Benutzerspezifische Variablen hinzufügen

Nachdem Sie sich beim Google Tag-Manager-Konto angemeldet haben, müssen Sie einige benutzerdefinierte konstante Variablen in Bezug auf Adobe hinzufügen. Sie haben vermutlich bereits Variablen im Google Tag-Manager, die an Google Analytics gesendet werden, wie z. B. die E-Mail-Adresse des Kunden, der Kundenname, die Sprache und der Anmeldestatus des Kunden. Sie müssen fünf neue benutzerdefinierte Variablen definieren:

* Organisations-ID für Adobe Experience Cloud
* DCS Streaming-Endpunkt
* Datensatz-ID in Experience Platform
* Referenz des Schemas
* Zeitstempel der Seite

Durch das Abrufen dieser Werte wird sichergestellt, dass alle Google Analytics-Daten an den richtigen Datensatz gesendet werden und das richtige Schema haben. Wenn Sie Ihre Experience Cloud-Org oder eine der anderen soeben erwähnten Variablen nicht kennen, kann Ihr Adobe Account Manager Ihnen beim Auffinden helfen.

Nachdem Sie diese benutzerspezifischen Variablen definiert haben, können wir einen Trigger einrichten, der alle Daten, die Sie bereits an Google Analytics senden, auch an Experience Platform sendet.

### 2. Einrichten eines Triggers in Google Tag Manager

In diesem Beispiel wurde der Trigger „Kontoerstellung“ definiert, wobei `pageUrl equals account-creation` verwendet wird. Durch Hinzufügen von Informationen zu diesem Trigger können Sie sicherstellen, dass Daten sowohl an Google Analytics als auch an AEP gesendet werden, wenn der Benutzer sich erfolgreich authentifiziert und die Seite zur Kontoerstellung geladen hat.

Sie können auch auf [Datenaufnahme und Google Tag-Manager](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=de#module9) zurückgreifen.

Anleitungen finden Sie in diesem Video:

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## Erstellen einer Verbindung in CJA mit dem Google Analytics-Datensatz

Sobald Adobe Experience Platform mit dem Empfang der Live-Daten von Google Analytics begonnen hat und Sie die historischen Google Analytics-Daten von BigQuery aufgestockt haben, sind Sie bereit, zu CJA zu wechseln und [Ihre erste Verbindung zu erstellen](/help/connections/create-connection.md). Diese Verbindung verbindet die GA-Daten mit allen anderen Kundendaten und verwendet dabei eine gemeinsame Kunden-ID.

## Nächste Schritte

* Erstellen Sie eine [Datenansicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=de#cja-dataviews) basierend auf der Verbindung, die Google Analytics-Daten enthält.

* Führen Sie eine äußerst aussagekräftige [Analyse in Workspace](/help/use-cases/ga-to-cja-reporting.md) durch.