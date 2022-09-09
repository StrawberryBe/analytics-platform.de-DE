---
title: Migrieren von Daten von Google Analytics zu Customer Journey Analytics
description: Erfahren Sie mehr über den übergeordneten Workflow zum Verschieben von Daten von Google Analytics in Adobe Experience Platform und zum Anzeigen von Berichten in Customer Journey Analytics.
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Migrieren von Daten von Google Analytics zu Customer Journey Analytics

Wenn Sie mit Customer Journey Analytics noch nicht vertraut sind, kann es sein, dass Ihr Unternehmen über vorhandene Daten auf einer anderen Analytics-Plattform verfügt, z. B. über Google Analytics. Sie können diese übergreifenden Schritte ausführen, um diese Daten in Adobe Experience Platform zu verschieben und so Berichte in Customer Journey Analytics anzuzeigen.

Workflows werden sowohl für historische Daten als auch für die aktuelle Datenerfassung bereitgestellt. Je nach Datenanforderungen Ihres Unternehmens können Sie einen oder beide Workflows ausführen.

## Einbinden von historischen Daten aus Google Analytics in Adobe Experience Platform

Die Erfassung historischer (Aufstockungsdaten) Daten umfasst den Export von Daten aus Google und den Import dieser Daten in Adobe Experience Platform. Siehe [Google Analytics-Daten in Adobe Experience Platform erfassen](backfill.md).

Sobald Sie historische Daten erfolgreich in Platform integriert haben, können Sie entweder [Streaming aktueller Daten konfigurieren](streaming.md)oder sofort mit der Berichterstellung für aufgestockte Daten in CJA von [Verbindung erstellen](/help/connections/create-connection.md).

## Vorhandene Google Analytics-Implementierung für Adobe Experience Platform konfigurieren {#configure}

Zur Erfassung aktueller (Streaming-)Daten müssen Daten an Adobe Experience Edge gesendet werden, der diese Daten dann an Adobe Experience Platform weiterleitet. Siehe [Einrichten von Streaming-Google Analytics-Daten in Adobe Experience Platform](streaming.md).

## Konfigurieren einer Verbindung und Datenansicht in CJA

Nachdem Sie historische Daten erfolgreich erfasst und/oder die Datenerfassung in Adobe Experience Platform konfiguriert haben, können Sie [Verbindung erstellen](/help/connections/create-connection.md) , damit Customer Journey Analytics auf diese Daten verweisen kann.

Verwenden Sie die Verbindung, um eine oder mehrere [Datenansichten](/help/data-views/create-dataview.md) zur Verwendung in Analysis Workspace.

## Berichte erstellen

Nachdem Sie Dimensionen und Metriken in einer Datenansicht konfiguriert haben, können Sie mit der Erstellung der gewünschten Berichte mit Analysis Workspace beginnen. Siehe [Bericht zu Google Analytics-Daten in Customer Journey Analytics](report.md).
