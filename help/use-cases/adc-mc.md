---
title: Marketing-Kanal mit Analytics Data Connector in CJA importieren
description: Verwenden Sie die richtigen Analytics Data Connector-Einstellungen, um die Verarbeitungsregeln für Marketing Kanal in Adobe Experience Platform zu importieren.
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 7%

---


# Marketing-Kanal mit Analytics Data Connector in CJA importieren

Wenn Ihr Unternehmen den [Analytics Data Connector](https://docs.adobe.com/content/help/de-DE/experience-platform/sources/connectors/adobe-applications/analytics.html) verwendet, um Report Suite-Daten in CJA zu importieren, können Sie eine Verbindung in CJA konfigurieren, um Berichte über die Dimensionen des Marketing-Kanals zu erstellen.

## Voraussetzungen

* Report Suite-Daten müssen bereits mit dem [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) in Adobe Experience Platform importiert werden.
* Verarbeitungsregeln für Marketing Kanal müssen bereits eingerichtet sein. Siehe [Verarbeitungsregeln für Marketing-Kanal](https://docs.adobe.com/content/help/de-DE/analytics/components/marketing-channels/c-rules.html) im Handbuch zu Analytics-Komponenten.

## Marketing Kanal Schema-Elemente

Wenn Sie Analytics Data Connector für eine gewünschte Report Suite verwenden, wird ein XDM-Schema für Sie erstellt. Dieses Schema enthält alle Analytics-Dimensionen und -Metriken als Rohdaten. Diese Rohdaten enthalten keine Zuordnung oder Persistenz. Stattdessen durchläuft jeder Treffer die Verarbeitungsregeln von Marketing Kanal und zeichnet die erste übereinstimmende Regel auf. Beim Erstellen einer Ansicht in CJA geben Sie Zuordnung und Persistenz an.

1. [Erstellen Sie eine ](/help/connections/create-connection.md) Verbindung, die einen Datensatz enthält, der auf dem Analytics Data Connector basiert.
2. [Erstellen Sie eine ](/help/data-views/create-dataview.md) Datenansicht mit den folgenden Dimensionen:
   * **`channel.typeAtSource`**: Entspricht der  [Marketingkanal-](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) Dimension.
   * **`channel._id`**: Entspricht den Details zum  [Marketing-Kanal](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. Weisen Sie jeder Dimension das gewünschte Zuordnungsmodell und die gewünschte Persistenz zu. Wenn Sie sowohl die First Touch- als auch die Last Touch-Dimension verwenden möchten, ziehen Sie jede Marketing Kanal-Dimension mehrmals in den Komponentenbereich. Weisen Sie jeder Dimension das gewünschte Zuordnungsmodell und die gewünschte Persistenz zu. Adobe empfiehlt außerdem, jeder Dimension einen Anzeigenamen zuzuweisen, um die Verwendung in Workspace zu vereinfachen.
4. Erstellen Sie die Daten-Ansicht.

Die Dimensionen Ihrer Marketing-Kanal stehen jetzt in Analysis Workspace zur Verfügung.

## Unterschiede in der Verarbeitung und Architektur

>[!IMPORTANT]
>
>Es gibt mehrere grundlegende Datenunterschiede zwischen Report Suite-Daten und Plattformdaten. Adobe empfiehlt dringend, die Verarbeitungsregeln für Marketing Kanal Ihrer Report Suite anzupassen, um eine ordnungsgemäße Datenerfassung in der Plattform zu erleichtern.


Da die Dimensionen des First Touch- und Last Touch-Kanals im Wesentlichen die gleiche Dimension mit verschiedenen Zuordnungsmodellen aufweisen, können Sie ähnliche Dimensionen neu erstellen, wenn [eine Data Ansicht](/help/data-views/create-dataview.md) erstellt wird. Sie können mehrere Dimensionen erstellen, die auf demselben Schema basieren und ihnen unterschiedliche Zuordnungsmodelle und Persistenz bieten.

## Unterschiede zwischen

