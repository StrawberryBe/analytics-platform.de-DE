---
title: So erhalten Sie Daten zu Google Analytics in Adobe Experience Platform zur Analyse in Customer Journey Analytics (CJA)
description: 'Erläutert, wie Sie Customer Journey Analytics (CJA) zum Erfassen Ihrer Google Analytics- und Firebase-Daten in Adobe Experience Platform einsetzen. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 58842436ab3388ba10ad0df0b35c78f68b02f0a3
workflow-type: tm+mt
source-wordcount: '1030'
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
| **Universelle Google Analytics** | Google Analytics 360 | Führen Sie die Schritte 1 bis 5 der folgenden Anweisungen aus |
| **Google Analytics 4** | Kostenlose GA-Version oder Google Analytics 360 | Führen Sie die Schritte 1 und 3-5 der folgenden Anweisungen aus. Schritt 2 ist nicht erforderlich. |

## Verlaufsdaten erfassen

### 1. Daten Ihrer Google Analytics mit BigQuery verbinden

Beachten Sie, dass die folgenden Anweisungen auf universellen Google Analytics basieren. Sie gelten für historische Daten. Anweisungen zum Live-Streaming finden Sie unter Live-Streaming-Daten in AEP übertragen.

Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3416092?hl=en).

### 2. Transformieren von Google Analytics in Ereignis in BigQuery

>[!IMPORTANT]
>
>Dieser Schritt gilt nur für Kunden von Universal Analytics

GA-Daten speichern jeden Datensatz in ihren Daten als Benutzersitzung und nicht als einzelne Ereignis. Sie müssen eine SQL-Abfrage erstellen, um die universellen Analytics-Daten in ein Experience-Platform-kompatibles Format umzuwandeln. Sie wenden die Funktion &quot;unest&quot;auf das Feld &quot;Treffer&quot;im GA-Schema an. Im Folgenden finden Sie das SQL-Beispiel, das Sie verwenden können:

`SQL sample`

Speichern Sie nach Abschluss der Abfrage die vollständigen Ergebnisse in einer BigQuery-Tabelle.

Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3437618?hl=en).

Oder Ansicht dieses Videos:

>[!VIDEO](https://video.tv.adobe.com/v/332634)

### 3. Exportieren Sie Google Analytics-Ereignis im JSON-Format in die Google Cloud-Datenspeicherung und speichern Sie sie in einem Behälter

Als Nächstes importieren Sie die Google Analytics-Ereignis in die Google Cloud-Datenspeicherung im JSON-Format. Dann bringen Sie es in die Experience Platform.

Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

### 4. Daten aus der Google Cloud-Datenspeicherung in Experience Platform bringen

Wählen Sie in der Experience Platform **[!UICONTROL Quellen]** und suchen Sie die Option **[!UICONTROL Google Cloud-Datenspeicherung]**. Von hier aus müssen Sie nur den Datensatz finden, den Sie vor Big Abfrage gespeichert haben.

Ansicht dieses Videos für Anweisungen:

>[!VIDEO](https://video.tv.adobe.com/v/332641)

### 5. Importieren von GCS-Ereignissen in Adobe Experience Platform und Zuordnen zu XDM-Schema

Als Nächstes können Sie die GA-Ereignis-Daten einem vorhandenen Datensatz zuordnen, den Sie zuvor erstellt haben, oder Sie können ein neues Dataset mit dem gewünschten XDM-Schema erstellen. Nachdem Sie das Schema ausgewählt haben, wendet die Experience Platform maschinelles Lernen an, um die Google Analytics-Daten automatisch Ihrem eigenen Schema zuzuordnen.

Zuordnungen lassen sich leicht ändern, und Sie können sogar abgeleitete oder berechnete Felder aus den Daten der Google Analytics erstellen. Nachdem Sie die Zuordnung der Felder zu Ihrem XDM-Schema abgeschlossen haben, können Sie diesen Import wiederholt planen und während des Erfassungsvorgangs eine Fehlerüberprüfung anwenden. Dadurch wird sichergestellt, dass keine Probleme mit den importierten Daten auftreten.

## Daten zu Live-Streaming-Google Analytics einbeziehen

Sie können auch Live-Streaming-Ereignis von Google Tag Manager direkt nach Adobe Experience Platform erfassen.

### hinzufügen benutzerspezifische Variablen

Nach der Anmeldung beim Google Tag-Manager-Konto müssen Sie benutzerspezifische Konstantenvariablen hinzufügen, die sich auf die Adobe der Organisations-ID und der DataSet-IDs beziehen. Sie haben vermutlich bereits Variablen im Google Tag-Manager, die an Google Analytics gesendet werden, wie z. B. die E-Mail des Kunden, der Kundenname, die Sprache und der Status des angemeldeten Kunden. Sie müssen fünf neue benutzerdefinierte Variablen definieren:

* Adobe Experience Cloud-Organisations-ID
* DCS Streaming-Endpunkt
* Experience Platform DataSet-ID
* Schema
* Zeitstempel der Seite.

Durch das Abrufen dieser Werte wird sichergestellt, dass alle Google Analytics-Daten an den richtigen Datensatz gesendet werden und das richtige Schema haben. Wenn Sie Ihren Experience Cloud-Org oder eine der anderen soeben erwähnten Variablen nicht kennen, kann Ihr Kundenbetreuer Ihnen bei der Verfolgung helfen.

Nachdem Sie diese benutzerspezifischen Variablen definiert haben, können wir einen Trigger einrichten, der alle Daten, die Sie bereits an Google Analytics senden, auch an die Experience Platform sendet.

### Einrichten eines Triggers im Google Tag-Manager

In diesem Beispiel wurde der Trigger &quot;Kontoerstellung&quot;definiert, wobei `pageUrl equals account-creation` verwendet wird. Durch Hinzufügen von Informationen zu diesem Trigger können Sie sicherstellen, dass Daten sowohl an Google Analytics als auch an AEP gesendet werden, wenn der Benutzer sich authentifiziert und die Seite zur Kontoerstellung geladen hat.

Anleitungen finden Sie in diesem Video in der Ansicht:

>[!VIDEO](https://video.tv.adobe.com/v/332668)

### Nächste Schritte

Sobald die Adobe Experience Platform mit dem Empfang der Live-Google Analytics-Daten begonnen hat und Sie die historischen Google Analytics-Daten von BigQuery aufgestockt haben, können Sie in CJA springen und

1. [Erstellen Sie Ihre erste ](/help/connections/create-connection.md) Verbindung, die die GA-Daten mit all Ihren anderen Kundendaten verbindet, indem Sie eine gemeinsame Kunden-ID verwenden.
1. Führen Sie eine fantastische Analyse in Workspace durch, z. B. ...

*Ist dies der Punkt, an dem dieses Thema anhalten sollte, oder müssen wir im Detail auf die Verbindung eingehen?*