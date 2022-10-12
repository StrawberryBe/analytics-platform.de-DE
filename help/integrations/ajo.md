---
title: Integrieren von Adobe Journey Optimizer in Customer Journey Analytics
description: Binden Sie die von AJO generierten Daten ein und analysieren Sie diese mit Analysis Workspace in CJA.
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: ht
source-wordcount: '664'
ht-degree: 100%

---


# Integrieren von Adobe Journey Optimizer in Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=de) hilft Ihnen bei der Bereitstellung von vernetzten, kontextbezogenen und personalisierten Erlebnissen. Dadurch können Ihre Kundinnen und Kunden leichter zum nächsten Schritt ihrer Customer Journey gelangen.

Sie können von Journey Optimizer generierte Daten importieren, um eine erweiterte Analyse in Customer Journey Analytics durchzuführen, indem Sie die folgenden Schritte ausführen:

## Senden von Daten aus Journey Optimizer an Adobe Experience Platform

Adobe Experience Platform dient als zentrale Datenquelle und Bindeglied zwischen Journey Optimizer und Customer Journey Analytics. Eine schrittweise Anleitung zum Senden von Journey Optimizer-Daten an Platform als Datensatz finden Sie unter [Erste Schritte mit Datensätzen](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html?lang=de) im Journey Optimizer-Benutzerhandbuch.

## Erstellen einer Verbindung in Customer Journey Analytics

Sobald sich Journey Optimizer-Daten in Adobe Experience Platform befinden, können Sie eine [Verbindung erstellen](/help/connections/create-connection.md), die auf Ihrem Journey Optimizer-Datensatz basiert. Wählen Sie den Datensatz aus, den Sie an Platform gesendet haben.

## Konfigurieren der Datenansicht für Journey Optimizer-Dimensionen und -Metriken

Sobald eine Verbindung erstellt wurde, können Sie eine oder mehrere [Datenansichten](/help/data-views/create-dataview.md) erstellen, um die gewünschten Dimensionen und Metriken zu konfigurieren, die in Customer Journey Analytics verfügbar sind.

Sie können die folgenden Metriken in einer Datenansicht erstellen, um eine ungefähre Übereinstimmung mit ähnlichen Metriken in Journey Optimizer zu erreichen. Einzelheiten zur Anpassung von Dimensionen und Metriken finden Sie unter [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichts-Manager.

| Metrik | Beschreibung | Datenansichtseinstellungen |
| --- | --- | --- |
| Bounces | Die Anzahl der Nachrichten, die zurückgeschickt wurden | Verwenden Sie das Schema-Zeichenfolgenelement `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Werte einschließen/ausschließen: Wenn ein Kriterium erfüllt ist<br>Gleich: `bounce`<br>Gleich: `denylist` |
| Fehler | Die Anzahl der fehlerhaften Nachrichten | Verwenden Sie das Schema-Zeichenfolgenelement `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Werte einschließen/ausschließen: Gleich `error` |
| Ausschlüsse | Die Anzahl der ausgeschlossenen Nachrichten | Verwenden Sie das Schema-Zeichenfolgenelement `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Werte einschließen/ausschließen: Gleich `exclude` |
| Abonnementkündigungen | Anzahl der Abmeldungen | Verwenden Sie das Schema-Zeichenfolgenelement `_experience.customerJourneyManagement.messageInteraction.interactionType` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Werte einschließen/ausschließen: Gleich `unsubscribe` |
| Klicks | Anzahl der Klicks in Nachrichten | Verwenden Sie das Schema-Zeichenfolgenelement `_experience.customerJourneyManagement.messageInteraction.interactionType` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Werte einschließen/ausschließen: Gleich `click` |
| Öffnungen | Anzahl geöffneter Nachrichten | Verwenden Sie das Schema-Zeichenfolgenelement `_experience.customerJourneyManagement.messageInteraction.interactionType` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Werte einschließen/ausschließen: Gleich `open` |
| Spam-Beschwerden | Anzahl der Beschwerden wegen Spam | Verwenden Sie das Schema-Zeichenfolgenelement `_experience.customerJourneyManagement.messageInteraction.interactionType` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Werte einschließen/ausschließen: Gleich `spam_complaint` |
| Erfolgreich gesendete Nachrichten | Die Anzahl der erfolgreich gesendeten Nachrichten | Verwenden Sie das Schema-Zeichenfolgenelement `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Werte einschließen/ausschließen: Gleich `sent` |
| Synchronisierungsfehler | Die Gesamtzahl der Nachrichten, die nicht synchronisiert werden konnten | Verwenden Sie das Schema-Zeichenfolgenelement `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Werte einschließen/ausschließen: Gleich `sync` |

{style=&quot;table-layout:auto&quot;}

## Konfigurieren von berechneten Metriken mit Journey Optimizer-Metriken

Nachdem Sie die gewünschten Dimensionen und Metriken für den Journey Optimizer-Datensatz konfiguriert haben, können Sie auch [Berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md) für weitere Einblicke in diese Daten konfigurieren. Diese berechneten Metriken basieren auf den oben genannten Metriken, die im Datenansichts-Manager erstellt wurden.

| Berechnete Metrik | Beschreibung | Formel |
| --- | --- | --- |
| Gesamtzahl der gesendeten Nachrichten | Gesamtzahl der (erfolgreich oder nicht erfolgreich) gesendeten Nachrichten | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Unterschiede bei der Berichterstellung zwischen Journey Optimizer und Customer Journey Analytics

Datendiskrepanzen zwischen Produkten liegen in der Regel zwischen 1 und 2 %. Größere Diskrepanzen zwischen Produkten lassen sich möglicherweise auf Folgendes zurückführen:

* Die Verarbeitungszeit für eingehende Daten kann sich von Produkt zu Produkt leicht unterscheiden, insbesondere bei Daten, die innerhalb der letzten zwei Stunden erfasst wurden. Verwenden Sie Datumsbereiche, die den heutigen Tag ausschließen, um Abweichungen wegen der Verarbeitungszeit zu vermeiden.
* Die berechnete Metrik „Gesamtzahl der gesendeten Nachrichten“ enthält nicht die Metrik „Weitere Zustellversuche“. Die Daten für die Metrik „Weitere Zustellversuche“ sind nicht im Datensatz enthalten, wodurch die Zahlen in den CJA-Berichten möglicherweise niedriger sind als in den AJO-Berichten. Die Daten für weitere Zustellversuche werden jedoch in die Metrik „Erfolgreich gesendete Nachrichten“ oder „Bounces“ einbezogen. Verwenden Sie Datumsbereiche, die eine Woche oder älter sind, um die Diskrepanzen zwischen den Produkten bei der Metrik „Gesamtzahl der gesendeten Nachrichten“ zu minimieren.
