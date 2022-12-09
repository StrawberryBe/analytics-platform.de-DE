---
title: Kanalübergreifende Journey-Analyse
description: Analysieren und extrahieren Sie Einblicke aus Kundeninteraktionen über die Customer Journey.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: dbb7edae43fdc970cacf5863ecd13df75deaefad
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 100%

---

# Kanalübergreifende Journey-Analyse

Verschaffen Sie sich einen zentralen Überblick über das Kundenverhalten über verschiedene Kanäle hinweg, indem Sie Daten aus verschiedenen Web-, Mobile- und Offline-Eigenschaften vereinheitlichen. Beispielsweise können Sie diese konsolidierte Ansicht verwenden, um Kundeninteraktionen auf Desktop- und Mobilgeräten zu analysieren, um das Kundenverhalten zu verstehen und Einblicke zu gewinnen, um digitale Kundenerlebnisse zu optimieren. Sie können auch kanalübergreifend Kundeninteraktionen analysieren, einschließlich digitaler und Offline-Kanäle wie Support-Interaktionen und In-Store-Käufe, um die Customer Journey besser zu verstehen und zu optimieren.

## Architektur

![Kanalübergreifende Architektur](../assets/cross-channel-architecture.svg)

## Implementierungsschritte

1. [Erstellen Sie Schemata](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) für aufzunehmende Daten.
1. [Erstellen Sie Datensätze](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=de) für aufzunehmende Daten.
1. [Erfassen von Daten in Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=de).
1. Verwenden Sie eine gemeinsame Namespace-ID für alle Datensätze oder verwenden Sie [Cross-Channel-Analyse](/help/connections/cca/overview.md), um Personen miteinander zu verknüpfen. Beachten Sie, dass Customer Journey Analytics derzeit für die Zuordnung weder das Experience Platform-Profil noch die Identitäts-Services verwendet.
1. Führen Sie eine benutzerdefinierte Datenvorbereitung durch, um sicherzustellen, dass ein gemeinsamer Schlüssel aus Zeitreihendaten in Customer Journey Analytics aufgenommen werden kann.
1. Weisen Sie Suchdaten eine primäre ID zu, die mit einem Feld in den Ereignisdaten verknüpft werden kann. Zählt bei der Lizenzierung als Zeilen.
1. Legen Sie dieselbe primäre ID für Profildaten als primäre ID der Ereignisdaten fest.
1. Konfigurieren Sie eine Datenverbindung, um Daten aus Experience Platform in Customer Journey Analytics aufzunehmen.
1. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) für die Verbindung, um die spezifischen Dimensionen und Metriken auszuwählen, die in die Ansicht aufgenommen werden sollen. Die Einstellungen für Attribution und Zuordnung werden auch in der Datenansicht konfiguriert. Diese Einstellungen werden zur Berichtszeit berechnet.
1. Erstellen Sie ein Projekt, um Dashboards und Berichte in Analysis Workspace zu konfigurieren.

## Zu beachten

Beachten Sie bei der Erstellung dieses Workflows die folgenden Punkte.

* Für die kanalübergreifende Analyse von Daten ist für jeden Datensatz derselbe ID-Namespace erforderlich.
* Für den Vereinigungsprozess verschiedener Datensätze ist ein gemeinsamer primärer Personen-/Entitätsschlüssel für die Datensätze erforderlich.
* Sekundäre schlüsselbasierte Vereinigungen werden derzeit nicht unterstützt.
* Der feldbasierte Identitätszusammenfügungsprozess ermöglicht die Neuzuweisung von Identitäten in Zeilen basierend auf nachfolgenden vorübergehenden ID-Datensätzen, z. B. einer Authentifizierungs-ID. Dies ermöglicht die Auflösung unterschiedlicher Datensätze in einer zentralen ID für die Analyse auf der Personenebene und nicht auf Geräte- oder Cookie-Ebene.
* Objekte und Attribute desselben XDM-Felds werden in Customer Journey Analytics zu einer Dimension zusammengeführt. Um mehrere Attribute aus verschiedenen Datensätzen mit derselben Customer Journey Analytics-Dimension zusammenzuführen, sollten die Datensätze auf dasselbe XDM-Feld oder Schema verweisen.
