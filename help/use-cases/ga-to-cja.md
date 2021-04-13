---
title: So erhalten Sie Daten zu Google Analytics in Adobe Experience Platform zur Analyse in Customer Journey Analytics (CJA)
description: 'Erläutert, wie Sie Customer Journey Analytics (CJA) zum Erfassen Ihrer Google Analytics- und Firebase-Daten in Adobe Experience Platform einsetzen. '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 793b2ce4ec8a487f6c4290fe2eff00879fcca13d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 2%

---


# Daten zu Google Analytics in Adobe Experience Platform importieren

Dieser Verwendungsfall konzentriert sich darauf, wie Sie Ihre Google Analytics-Daten als Datensatz in Adobe Experience Platform erfassen. (Dies gilt sowohl für historische als auch für Live-Daten.) Anschließend können Sie beide Datensätze kombinieren, um eine geräteübergreifende Ansicht der Journey zu erzielen.

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

## 1. Daten Ihrer Google Analytics mit BigQuery verbinden

Beachten Sie, dass die folgenden Anweisungen auf universellen Google Analytics basieren.

Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3416092?hl=en).

## 2. Transformieren von Google Analytics in Ereignis in BigQuery

>[!IMPORTANT]
>
>Dieser Schritt gilt nur für Kunden von Universal Analytics

GA-Daten speichern jeden Datensatz in ihren Daten als Benutzersitzung und nicht als einzelne Ereignis. Durch die Datenumwandlung sind die Daten mit Adobe Experience Platform kompatibel.

Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3437618?hl=en).

Sie müssen eine SQL-Abfrage erstellen, um die universellen Analytics-Daten in ein Experience-Platform-kompatibles Format umzuwandeln. Ansicht dieses Videos für Anweisungen:

>[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3. Exportieren Sie Google Analytics-Ereignis im JSON-Format in die Google Cloud-Datenspeicherung und speichern Sie sie in einem Behälter

Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

## 4. Daten aus der Google Cloud-Datenspeicherung in Experience Platform bringen

Ansicht dieses Videos für Anweisungen:

>[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5. Importieren von GCS-Ereignissen in Adobe Experience Platform und Zuordnen zu XDM-Schema

BigQuery Export-Schema (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
