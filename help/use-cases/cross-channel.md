---
title: Kanalübergreifende Journey-Analyse
description: Analysieren und extrahieren Sie Einblicke aus Kundeninteraktionen über die Customer Journey.
source-git-commit: a6c6620a4f4118755509e534d7d6a12bf08b4b67
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 6%

---


# Kanalübergreifende Journey-Analyse

Verschaffen Sie sich einen zentralen Überblick über das Kundenverhalten über verschiedene Kanäle hinweg, indem Sie Daten aus verschiedenen Web-, Mobile- und Offline-Eigenschaften vereinheitlichen. Beispielsweise können Sie diese konsolidierte Ansicht verwenden, um Kundeninteraktionen auf Desktop- und Mobilgeräten zu analysieren, um das Kundenverhalten zu verstehen und Einblicke zu gewinnen, um digitale Kundenerlebnisse zu optimieren. Sie können auch kanalübergreifend Kundeninteraktionen analysieren, einschließlich digitaler und Offline-Kanäle wie Support-Interaktionen und In-Store-Käufe, um die Journey der Kunden besser zu verstehen und zu optimieren.

## Architektur

![Kanalübergreifende Architektur](assets/cross-channel-architecture.svg)

## Implementierungsschritte

1. [Erstellen Sie ](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) Schemata für aufzunehmende Daten.
1. [Erstellen Sie ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) Datensätze für aufzunehmende Daten.
1. [Erfassen von Daten in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html).
1. Verwenden Sie eine gemeinsame Namespace-ID für alle Datensätze oder verwenden Sie [Cross-Channel-Analyse](/help/connections/cca/overview.md), um Personen miteinander zu verknüpfen. Beachten Sie, dass Customer Journey Analytics derzeit das Experience Platform-Profil oder die Identitätsdienste nicht zum Zuordnen verwendet.
1. Führen Sie eine benutzerdefinierte Datenvorbereitung durch, um sicherzustellen, dass ein gemeinsamer Schlüssel aus Zeitreihendaten in Customer Journey Analytics erfasst werden kann.
1. Weisen Sie Suchdaten eine primäre ID zu, die mit einem Feld in den Ereignisdaten verknüpft werden kann. Zählt bei der Lizenzierung als Zeilen.
1. Legen Sie dieselbe primäre ID für Profildaten als primäre ID der Ereignisdaten fest.
1. Konfigurieren Sie eine Datenverbindung, um Daten von Experience Platform zu Customer Journey Analytics zu erfassen.
1. [Erstellen Sie eine ](/help/data-views/create-dataview.md) Datenansicht in der Verbindung, um die spezifischen Dimensionen und Metriken auszuwählen, die in die Ansicht aufgenommen werden sollen. Die Einstellungen für Attribution und Zuordnung werden auch in der Datenansicht konfiguriert. Diese Einstellungen werden zur Berichtszeit berechnet.
1. Erstellen Sie ein Projekt, um Dashboards und Berichte in Analysis Workspace zu konfigurieren.

## Zu beachten

Beachten Sie bei der Erstellung dieses Workflows die folgenden Punkte.

* Für die kanalübergreifende Analyse von Daten ist für jeden Datensatz derselbe ID-Namespace erforderlich.
* Für den Vereinigungsprozess verschiedener Datensätze ist ein gemeinsamer Primärschlüssel/Entitätsschlüssel für die Datensätze erforderlich.
* Sekundären wichtige Gewerkschaften werden derzeit nicht unterstützt.
* Der feldbasierte Identitätszusammenfügungsprozess ermöglicht die Neuzuweisung von Identitäten in Zeilen basierend auf nachfolgenden vorübergehenden ID-Datensätzen, z. B. einer Authentifizierungs-ID. Dies ermöglicht die Auflösung unterschiedlicher Datensätze zu einer einzelnen ID für die Analyse auf der Personenebene und nicht auf Geräte- oder Cookie-Ebene.
* Objekte und Attribute desselben XDM-Felds werden in Customer Journey Analytics zu einer Dimension zusammengeführt. Um mehrere Attribute aus verschiedenen Datensätzen mit derselben Customer Journey Analytics-Dimension zusammenzuführen, sollten die Datensätze auf dasselbe XDM-Feld oder Schema verweisen.
