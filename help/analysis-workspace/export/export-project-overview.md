---
description: Machen Sie sich mit den verschiedenen Methoden vertraut, die für den Export aus Analysis Workspace verfügbar sind.
keywords: Analysis Workspace
title: Übersicht über die Exportzweck-Projektdaten
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: a2b2c6bca0557521ac7b6bcf635f467ca41731b7
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# Exportübersicht

Sie können Customer Journey Analytics-Berichte aus Analysis Workspace exportieren. Möglicherweise möchten Sie Customer Journey Analytics-Berichte aus verschiedenen Gründen exportieren, z. B. aus Drittanbieter-Tools oder aus Kombination mit externen Daten.

In den folgenden Abschnitten werden die unterstützten Dateitypen, die verschiedenen für den Export verfügbaren Methoden und die Vorteile jeder Methode beschrieben.

## Unterstützte Dateitypen

Sie können Customer Journey Analytics-Berichte als PDF-, CSV- oder JSON-Datei exportieren.

* **PDF:** Bietet eine einfache Möglichkeit, visuelle Daten für Interessengruppen freizugeben. PDF-Dateien enthalten alle angezeigten (sichtbaren) Tabellen und Visualisierungen im Projekt.

* **CSV:** Ermöglicht die Anzeige von Rohdaten in einer Tabellenkalkulationsanwendung, z. B. Excel. CSV-Dateien enthalten Textdaten.

* **JSON:** Bietet ein offenes Standarddateiformat für die Datenfreigabe.

## Ausfuhrmethoden

Beim Exportieren aus Analysis Workspace stehen verschiedene Methoden zur Verfügung. Überlegen Sie bei der Auswahl einer Exportmethode, was Sie exportieren möchten und wer darauf zugreifen muss.

| Exportmethode | Vorteile |
|---------|----------|
| [Herunterladen auf die Workstation](/help/analysis-workspace/export/download-send.md) | Verwenden Sie diese Methode, wenn Sie: <ul><li>Laden Sie Projekte auf Ihre persönliche Workstation herunter.</li><li>Downloads sind nur für Ad Hoc (können nicht geplant werden).</li> <li>Laden Sie insgesamt 50.000 Zeilen herunter.</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [An andere Benutzer senden](/help/analysis-workspace/export/t-schedule-report.md) | Verwenden Sie diese Methode, wenn Sie: <ul><li>E-Mail exportierte Customer Journey Analytics-Daten an andere Benutzer in Ihrer Organisation.</li><li>Kann ad hoc oder nach einem Zeitplan sein.</li> <li>Beinhaltet insgesamt 50.000 Zeilen.</li> <!--true?--> |
| [Senden an eine Cloud-Anwendung](/help/analysis-workspace/export/export-cloud.md) | Verwenden Sie diese Methode, wenn Sie: <ul><li>Exportieren Sie in einen freigegebenen Speicherort, z. B. Google Cloud Platform, Microsoft Azure, Amazon S3, Snowflake oder Adobe Experience Platform Data Landing Zone.</li><li>Kann ad hoc oder nach einem Zeitplan sein.</li><li>Speichern Sie größere Mengen von Customer Journey Analytics-Daten.</li><li>Exportieren Sie vollständige Tabellen mit Tausenden oder Millionen von Zeilen.<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}

