---
title: Streaming-Google Analytics-Daten in Adobe Experience Platform konfigurieren
description: Erfahren Sie, wie Sie Ihre Implementierung einrichten, um eine Google-Datenschicht in Adobe Experience Platform zu senden.
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 2%

---

# Streaming-Google Analytics-Daten in Adobe Experience Platform konfigurieren

Auf dieser Seite wird beschrieben, wie Sie Ihre Live-Google Analytics-Daten in Adobe Experience Platform erfassen und so auf diesen Datensatz in einer Datenansicht in Customer Journey Analytics verweisen können. Sie können die Schritte auf dieser Seite mit [Erfassen von Google Analytics-Verlaufsdaten in Adobe Experience Platform](backfill.md), wodurch ein Datensatz mit historischen Daten generiert wird. Kombinieren Sie einen Streaming-Datensatz mit einem Aufstockungsdatensatz, um eine nahtlose Ansicht vergangener und vorhandener Daten in Customer Journey Analytics zu erhalten.

Die Konfiguration der Datenerfassung umfasst die folgenden Schritte:

1. Implementierung [Tags für Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=de). Siehe [Schnellstartanleitung](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) , um eine grundlegende Implementierung einzurichten und auszuführen.
1. Installieren Sie die [Google Data Layer-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/google-data-layer/overview.html). Diese Erweiterung dient als Alternative zur Installation der Web SDK-Erweiterung, die speziell auf eine Google-Datenschicht ausgerichtet ist.
1. [Erstellen eines Datenspeichers](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html) in der Adobe Experience Platform-Datenerfassung. Konfigurieren Sie den Datenspeicher, um Daten an Adobe Experience Platform zu senden. Sie müssen derzeit jedes Google-Datenschichtobjekt einem entsprechenden XDM-Feld hier zuordnen. Adobe plant, diesen Zuordnungs-Workflow in Zukunft zu vereinfachen.

Nachdem Sie die gewünschten Tags auf Ihrer Site implementiert und veröffentlicht haben, können Sie mit dem [Verbindung erstellen](/help/connections/create-connection.md), dann [Datenansicht erstellen](/help/data-views/create-dataview.md).
