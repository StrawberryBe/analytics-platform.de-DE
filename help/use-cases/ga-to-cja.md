---
title: Daten zu Google Analytics in Adobe Experience Platform importieren
description: 'Erläutert, wie Sie Customer Journey Analytics (CJA) zum Erfassen Ihrer Google Analytics- und Firebase-Daten in Adobe Experience Platform einsetzen. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: de822eb00a5e205889b4fa96f729845ad4c7e356
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 1%

---


# Daten zu Google Analytics in Adobe Experience Platform importieren

Dieser Verwendungsfall konzentriert sich darauf, wie Sie Ihre Google Analytics-Daten als Datensatz in Adobe Experience Platform erfassen. Wir erklären Ihnen, wie Sie sowohl historische als auch Live-Daten erfassen. Anschließend können Sie beide Datensätze in Customer Journey Analytics kombinieren, um eine geräteübergreifende Ansicht der Journey zu erzielen.

Die Datensätze in der Experience Platform bestehen aus zwei Elementen: ein Schema und die tatsächlichen Datensätze im Datensatz. Das Schema (wir nennen es das Erlebnisdatenmodell oder kurz XDM) ähnelt den Spalten des Datensatzes und entspricht dem Entwurf oder den Regeln, die die Daten selbst beschreiben. Innerhalb der Plattform bietet Adobe zwei Typen von Schemas:

* Vordefinierte Schema, mit denen Sie Ihre Google Analytics-Daten automatisch zuordnen können (als Erlebnis-Ereignis-Schema bezeichnet)
* Benutzerspezifische Schema, die Sie erstellen und die Google Analytics-Daten einfach zuordnen können

Einer der leistungsfähigsten Aspekte des Datenmodells von Adobe ist, dass es Ihnen ermöglicht, alle Interaktionsdaten Ihrer Kunden in ein gemeinsames Schema zu standardisieren - das macht es wesentlich einfacher, die Daten in CJA zusammenzufügen.

## Voraussetzungen

Um diese Aufgaben ausführen zu können, benötigen Sie die folgenden Zugriffsrechte:

* Zugang zu Adobe Experience Platform
* Zugriff auf universelle Google Analytics (Google Analytics 360) oder Google Analytics 4 (kostenlose Version oder Google Analytics 360)
* Zugriff auf Customer Journey Analytics und dessen [Administratorberechtigungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=de-DE#admin-access-permissions).

Wie Sie Daten zu Google Analytics in Adobe Experience Platform importieren, hängt davon ab, welche Version von Google Analytics Sie verwenden:

| Bei Verwendung von ... | Sie benötigen diese Lizenz auch... | Und tun Sie das... |
| --- | --- | --- |
| **Universal Analytics** | Google Analytics 360 | Führen Sie die Schritte 1 bis 3 der folgenden Anweisungen aus. |
| **Google Analytics 4** | Kostenlose GA-Version oder Google Analytics 360 | Führen Sie die Schritte 1 und 3 der folgenden Anweisungen aus. Schritt 2 ist nicht erforderlich. |

## Verlaufsdaten (Aufstockung) erfassen

### 1. Daten Ihrer Google Analytics mit BigQuery verbinden

Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3416092?hl=en). Beachten Sie, dass diese Anweisungen auf universellen Google Analytics basieren.

### 2. Transformieren von Google Analytics in Ereignis in BigQuery und Exportieren in die Google Cloud-Datenspeicherung

>[!IMPORTANT]
>
>Dieser Schritt gilt nur für Kunden von Universal Analytics

GA-Daten speichern jeden Datensatz in ihren Daten als Benutzersitzung und nicht als einzelne Ereignis. Sie müssen eine SQL-Abfrage erstellen, um die universellen Analytics-Daten in ein Experience-Platform-kompatibles Format umzuwandeln. Sie wenden die Funktion &quot;unest&quot;auf das Feld &quot;Treffer&quot;im GA-Schema an. Im Folgenden finden Sie das SQL-Beispiel, das Sie verwenden können:

`SELECT
*,
timestamp_seconds(`` + hit.time) AS `` 
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
`visitStartTimetimestampyour_bq_table_2021_04_*`,
UNNEST(hits) AS hit 
)`

Speichern Sie nach Abschluss der Abfrage die vollständigen Ergebnisse in einer BigQuery-Tabelle.

Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/7029846?hl=en&amp;ref_topic=9359001#zippy=%2Cold-export-schema%2Cuse-this-script-to-migrate-existing-bigquery-datasets-from-the-old-export-schema-to-the-new-one%2Cscript-migration-scriptsql), die Anweisungen zur SQL-Abfrage enthalten.

Im folgenden Video wird auch der nächste Schritt erläutert, der darin besteht, die Google Analytics-Ereignis in die Google Cloud-Datenspeicherung im JSON-Format zu exportieren. Klicken Sie einfach auf **Export > Export nach GCS**. Dort können die Daten nach Adobe Experience Platform gezogen werden.

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Daten aus der Google Cloud-Datenspeicherung in Experience Platform importieren und XDM-Schema zuordnen

Wählen Sie in der Experience Platform **[!UICONTROL Quellen]** und suchen Sie die Option **[!UICONTROL Google Cloud-Datenspeicherung]**. Von hier aus müssen Sie nur den Datensatz finden, den Sie aus BigQuery gespeichert haben.

Beachten Sie:

* Stellen Sie sicher, dass Sie das JSON-Format auswählen.
* Sie können einen vorhandenen Datensatz auswählen oder einen neuen Datensatz erstellen (empfohlen).
* Stellen Sie sicher, dass Sie dasselbe Schema für Daten zu Verlaufsdaten und Live-Streaming-Google Analytics auswählen, auch wenn diese sich in separaten Datensätzen befinden. Anschließend können Sie die Datensätze in einer [CJA-Verbindung](/help/connections/combined-dataset.md) zusammenführen.

Anleitungen finden Sie in diesem Video in der Ansicht:

>[!VIDEO](https://video.tv.adobe.com/v/332676)

Sie können die GA-Ereignis-Daten zu einem vorhandenen Datensatz zuordnen, den Sie zuvor erstellt haben, oder einen neuen Datensatz erstellen, wobei Sie das gewünschte XDM-Schema verwenden. Nachdem Sie das Schema ausgewählt haben, wendet die Experience Platform maschinelles Lernen an, um jedes der Felder in den Daten des Google Analytics automatisch Ihrem [XDM-Schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=en#ui) zuzuordnen.

![](assets/schema-map.png)

Zuordnungen lassen sich leicht ändern, und Sie können sogar abgeleitete oder berechnete Felder aus den Daten der Google Analytics erstellen. Nachdem Sie die Zuordnung der Felder zu Ihrem XDM-Schema abgeschlossen haben, können Sie diesen Import wiederholt planen und während des Erfassungsvorgangs eine Fehlerüberprüfung anwenden. Dadurch wird sichergestellt, dass keine Probleme mit den importierten Daten auftreten.

**Berechnetes Feld &quot;Zeitstempel&quot;**

Für das Feld `timestamp` Schema in den Daten zu Google Analytics müssen Sie ein spezielles berechnetes Feld in der Benutzeroberfläche des Experience Platform Schema erstellen. Klicken Sie auf **[!UICONTROL Hinzufügen berechnetes Feld]** und schließen Sie die `timestamp`-Zeichenfolge in eine `date`-Funktion wie die folgende ein:

`date(timestamp, "yyyy-MM-dd HH:mm:ssZ")`

Anschließend müssen Sie dieses berechnete Feld in der Zeitstempeldatenstruktur im Schema speichern:

![](assets/timestamp.png)

**berechnetes Feld &#39;_id&#39;**

Das Schema `_id` muss einen Wert enthalten - CJA spielt keine Rolle, was der Wert ist. Sie können dem Feld einfach eine &quot;1&quot;hinzufügen:

![](assets/_id.png)

## Daten zu Live-Streaming-Google Analytics einbeziehen

Sie können auch Live-Streaming-Ereignis von Google Tag Manager direkt nach Adobe Experience Platform erfassen.

### 1. hinzufügen benutzerspezifische Variablen

Nachdem Sie sich beim Google Tag-Manager-Konto angemeldet haben, müssen Sie einige benutzerspezifische Konstantenvariablen zur Adobe hinzufügen. Sie haben vermutlich bereits Variablen im Google Tag-Manager, die an Google Analytics gesendet werden, wie z. B. die E-Mail des Kunden, der Kundenname, die Sprache und der Status des angemeldeten Kunden. Sie müssen fünf neue benutzerdefinierte Variablen definieren:

* Adobe Experience Cloud-Organisations-ID
* DCS Streaming-Endpunkt
* Experience Platform DataSet-ID
* Schema
* Zeitstempel der Seite

Durch das Abrufen dieser Werte wird sichergestellt, dass alle Google Analytics-Daten an den richtigen Datensatz gesendet werden und das richtige Schema haben. Wenn Sie Ihren Experience Cloud-Org oder eine der anderen soeben erwähnten Variablen nicht kennen, kann Ihr Kundenbetreuer Ihnen bei der Verfolgung helfen.

Nachdem Sie diese benutzerspezifischen Variablen definiert haben, können wir einen Trigger einrichten, der alle Daten, die Sie bereits an Google Analytics senden, auch an die Experience Platform sendet.

### 2. Einrichten eines Triggers im Google Tag-Manager

In diesem Beispiel wurde der Trigger &quot;Kontoerstellung&quot;definiert, wobei `pageUrl equals account-creation` verwendet wird. Durch Hinzufügen von Informationen zu diesem Trigger können Sie sicherstellen, dass Daten sowohl an Google Analytics als auch an AEP gesendet werden, wenn der Benutzer sich authentifiziert und die Seite zur Kontoerstellung geladen hat.

Sie können auch auf [Dateneinbettung und Google Tag-Manager](https://experienceleague.adobe.com/docs/platform-learn/comprehensive-technical-tutorial/module9/data-ingestion-using-google-tag-manager-and-google-analytics.html?lang=en#module9) verweisen.

Anleitungen finden Sie in diesem Video in der Ansicht:

>[!VIDEO](https://video.tv.adobe.com/v/332668)

## Erstellen einer Verbindung in CJA mit dem Google Analytics-Datensatz

Sobald das Adobe Experience Platform mit dem Empfang der Daten zu den Live-Google Analytics begonnen hat und Sie die Daten zu den historischen Google Analytics von BigQuery aufgestockt haben, sind Sie bereit, in CJA zu springen und [Ihre erste Verbindung ](/help/connections/create-connection.md) zu erstellen. Diese Verbindung verbindet die GA-Daten mit allen anderen Kundendaten mit einer gemeinsamen Kunden-ID.

## Nächste Schritte

* Ansicht von Daten auf der Grundlage von Google Analytics erstellen
Als Nächstes erstellen Sie in CJA eine Data Ansicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#cja-dataviews), basierend auf der Verbindung, die die Google Analytics-Daten enthält.[

* Führen Sie eine erstaunliche Analyse in [Workspace](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/home.html?lang=en#cja-workspace) durch. Später finden Sie einige Anwendungsfälle für Berichte.