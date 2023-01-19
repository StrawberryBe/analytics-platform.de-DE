---
title: Datenerfassung – Übersicht
description: Hier erhalten Sie Informationen über die unterschiedlichen Arten der Datenaufnahme für Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 5de8c0daaa7eea0a9ab993d256e2b0a14f37301e
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 8%

---


# Datenerfassung – Übersicht

Sie haben eine Reihe von Möglichkeiten, Daten in Customer Journey Analytics aufzunehmen. Einige davon gehen davon aus, dass Sie herkömmliche Adobe Analytics-Daten verschieben möchten, andere gehen davon aus, dass Sie direkt in Adobe Experience Platform erfasste Daten verwenden.

>[!IMPORTANT]
>
>In allen Szenarien können Sie die gewünschten Daten _use_ im Customer Journey Analytics _erfasst_ in Adobe Experience Platform.


Die allgemeine Customer Journey Analytics-Architektur wird weiter oben in [Übersicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=de):

![Customer Journey Analytics](./assets/cja-architecture.png)

Der Datensatz in der obigen Architektur kann aus verschiedenen Quellen stammen: Batch-Daten, Streaming-Daten, Daten aus einer aktuellen Adobe Analytics-Bereitstellung, Daten aus der Verfolgung Ihrer Website/App mithilfe des Adobe Experience Platform Web/Mobile SDK oder Daten von einem Drittanbieter für Daten, für den Adobe einen Quell-Connector bereitstellt. Und Sie können viele dieser Datensätze haben.

In diesem Abschnitt der Dokumentation finden Sie Schnellstartanleitungen für eine Reihe von Szenarien.

## Daten aus herkömmlichem Adobe Analytics erfassen und verwenden

Sie haben Adobe Analytics bereits bereitgestellt und möchten diese Daten in Adobe Experience Platform erfassen und in Customer Journey Analytics mit Daten aus anderen Kanälen und Datenquellen kombinieren und analysieren.

Siehe [Daten aus herkömmlichem Adobe Analytics erfassen und verwenden](./analytics.md) für weitere Informationen.

## Daten über das Adobe Experience Platform Web SDK und das Edge Network erfassen und verwenden

Sie möchten Ihre Website mit Adobe-Technologie analysieren, möglicherweise aus einer anderen  migrieren oder das Besucherverhalten verfolgen. Sie möchten die Best Practices der Adobe für die Implementierung befolgen, bei der die Adobe Experience Platform SDK und das Edge Network zum Erfassen der Daten verwendet werden. Anschließend können Sie die erfassten Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Siehe [Daten über das Adobe Experience Platform Web SDK und das Edge Network erfassen und verwenden](./aepwebsdk.md) für weitere Informationen.

## Batch-Daten erfassen und verwenden

Ihnen stehen relevante Batch-Daten zur Verfügung, die Ihnen helfen, das Kundenverhalten besser zu verstehen und Kundeninteraktionen zu analysieren. Beispiele für solche Batch-Daten sind flache Dateien im CSV-, JSON- oder Parquet-Format aus einem CRM-System, einer Treueanwendung oder einer anderen Lösung, für die Adobe derzeit keinen Quell-Connector bereitstellt. Durch die Aufnahme dieser Batch-Daten in Adobe Experience Platform können Sie sie mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Siehe [Batch-Daten erfassen und verwenden](./batch.md) für weitere Informationen.

## Streaming-Daten erfassen und verwenden

Sie verfügen über eine relevante Datenquelle wie z. B. ein CRM-System, ein ERP-System oder eine andere Quelle mit Details, die Ihnen helfen, das Kundenverhalten besser zu verstehen und Kundeninteraktionen zu analysieren. Diese Datenquelle kann über HTTP oder eine öffentliche Cloud-Streaming-Infrastruktur kommunizieren, für die Adobe jedoch derzeit keinen Quell-Connector bereitstellt. Durch die Echtzeit-Erfassung dieser Streaming-Daten in Adobe Experience Platform können Sie diese Daten mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Siehe [Streaming-Daten erfassen und verwenden](./streaming.md) für weitere Informationen.

## Daten über Quell-Connectoren erfassen und verwenden

Sie verfügen über Daten aus einer Quelle, die von einem Quell-Connector unterstützt wird. Quell-Connectoren sind konfigurierbare Konfigurationen, mit denen Sie Daten aus Adobe, Erstanbieter- und Drittanbieteranwendungen in Adobe Experience Platform erfassen können. Siehe [Übersicht über Quell-Connectoren](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=de) für eine Übersicht der verfügbaren Quell-Connectoren. Mithilfe des Quell-Connectors können Sie einfach Daten aus der Quelle in Adobe Experience Platform erfassen und diese dann mit Daten aus anderen Kanälen und Datenquellen in Customer Journey Analytics verwenden, kombinieren und analysieren.

Siehe [Daten über Quell-Connectoren erfassen und verwenden](./sources.md) für weitere Informationen.

