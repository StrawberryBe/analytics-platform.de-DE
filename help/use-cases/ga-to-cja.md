---
title: Einrichten des Google Analytics Berichte in Customer Journey Analytics
description: null
translation-type: tm+mt
source-git-commit: 1324ad5768a7ab215431b9447d9519367dfe17a0
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 1%

---


# Einrichten des Google Analytics Berichte in Customer Journey Analytics



## Voraussetzungen

* Zugang zu Adobe Experience Platform
* Zugriff auf universelle Google Analytics (Google Analytics 360) oder Google Analytics 4 (kostenlose Version oder Google Analytics 360)
* Zugang zum Customer Journey Analytics

## 1. Daten von Google Analytics mit Adobe Experience Platform verbinden

Wie Sie Daten zu Google Analytics in Adobe Experience Platform importieren, hängt davon ab, welche Version von Google Analytics Sie verwenden:

| Bei Verwendung von ... | Sie benötigen diese Lizenz auch... | Und tun Sie das... |
| --- | --- | --- |
| **Universelle Google Analytics** | Google Analytics 360 | Führen Sie die Schritte 1 - x der unten stehenden Anweisungen aus. |
| **Google Analytics 4** | Kostenlose GA-Version oder Google Analytics 360 | In den Anweisungen unten ist Schritt x nicht erforderlich. |

Die folgenden Anweisungen basieren auf universellen Google Analytics.

1. Verbinden Sie Ihre Google Analytics-Daten mit BigQuery und
Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3416092?hl=en).

1. (Nur Universeller Analytics-Kunden) Transformieren Sie Google Analytics-Sitzungen in BigQuery in Ereignis.
Dadurch sind die Daten mit Adobe Experience Platform kompatibel. Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3437618?hl=en).

   Details: In BigQuery werden Ihre GA-Daten als Tabelle angezeigt:

   ![](assets/ga-bigquery.png)
Sie müssen eine SQL-Abfrage erstellen, um die universellen Analytics-Daten in ein Experience-Platform-kompatibles Format umzuwandeln. Ansicht dieses Videos für Anweisungen:

   >[!VIDEO](https://video.tv.adobe.com/v/332634)

1. Exportieren Sie Google Analytics-Ereignis im JSON-Format in die Google Cloud-Datenspeicherung und speichern Sie sie in einem Behälter.
Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).

1. Daten aus der Google Cloud-Datenspeicherung in die Experience Platform übernehmen
Ansicht dieses Videos für Anweisungen:

   >[!VIDEO](https://video.tv.adobe.com/v/332641)

1. Importieren von GCS-Ereignissen in Adobe Experience Platform und Zuordnen zu XDM-Schema

BigQuery Export-Schema (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

