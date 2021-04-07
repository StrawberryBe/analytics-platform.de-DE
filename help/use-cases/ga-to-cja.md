---
title: Einrichten des Google Analytics Berichte in Customer Journey Analytics
description: null
translation-type: tm+mt
source-git-commit: 9bbc625aca9e0b8384b3e95d79fd695fda863f0b
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---


# Einrichten des Google Analytics Berichte in Customer Journey Analytics

Einrichten des Google Cloud Datenspeicherung Connector,

Google Tag Manager konfigurieren

BigQuery Export-Schema (https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

1. GA-Sitzungen in große Abfrage in Ereignis konvertieren
1. Exportieren von Google Analytics-Ereignissen in die Google Cloud-Datenspeicherung
1. Importieren von GCS-Ereignissen in Adobe Experience Platform und Zuordnen zu XDM-Schema

## Voraussetzungen

* Zugang zu Adobe Experience Platform
* Zugriff auf universelle Google Analytics (Google Analytics 360) oder Google Analytics 4 (kostenlose Version oder Google Analytics 360)
* Zugang zum Customer Journey Analytics

## Daten von Google Analytics mit Adobe Experience Platform verbinden

Wie Sie Daten zu Google Analytics in Adobe Experience Platform importieren, hängt davon ab, welche Version von Google Analytics Sie verwenden:

| Bei Verwendung von ... | Sie benötigen diese Lizenz auch... | Und tun Sie das... |
| --- | --- | --- |
| **Universelle Google Analytics** | Google Analytics 360 | Führen Sie die Schritte 1 - x der unten stehenden Anweisungen aus. |
| **Google Analytics 4** | Kostenlose GA-Version oder Google Analytics 360 | In den Anweisungen unten ist Schritt x nicht erforderlich. |

Die folgenden Anweisungen basieren auf universellen Google Analytics.

1. Verbinden Sie Ihre Google Analytics-Daten mit BigQuery und
Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3416092?hl=en).
1. (Nur Universeller Analytics-Kunden) Transformieren Sie Google Analytics-Sitzungen in BigQuery in Ereignis.
Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3437618?hl=en).
1. Exportieren Sie Google Analytics-Ereignis in die Google Cloud-Datenspeicherung.
Weitere Informationen finden Sie unter [diese Anweisungen](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089).
