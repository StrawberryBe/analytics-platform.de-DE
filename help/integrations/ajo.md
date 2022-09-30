---
title: Integrieren von Adobe Journey Optimizer mit Customer Journey Analytics
description: Einbinden von AJO generierter Daten und Analysieren mit Analysis Workspace in CJA.
source-git-commit: b24ad572ca36bbafffcd242fe257a2113977392d
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 4%

---


# Integrieren von Adobe Journey Optimizer mit Customer Journey Analytics

[Adobe Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=de) hilft Ihnen bei der Bereitstellung von vernetzten, kontextbezogenen und personalisierten Erlebnissen. Dadurch können Ihre Kunden beim nächsten Schritt auf der Journey ihrer Kunden unterstützt werden.

Sie können von Journey Optimizer generierte Daten importieren, um eine erweiterte Analyse in Customer Journey Analytics durchzuführen, indem Sie die folgenden Schritte ausführen:

## Daten aus Journey Optimizer an Adobe Experience Platform senden

Adobe Experience Platform dient als zentrale Datenquelle und Verknüpfung zwischen Journey Optimizer und Customer Journey Analytics. Siehe [Erste Schritte mit Datensätzen](https://experienceleague.adobe.com/docs/journey-optimizer/using/data-management/datasets/get-started-datasets.html) Anweisungen zum Senden von Journey Optimizer-Daten an Platform as a Datensatz finden Sie im Journey Optimizer-Benutzerhandbuch .

## Erstellen einer Verbindung in Customer Journey Analytics

Sobald sich Journey Optimizer-Daten in Adobe Experience Platform befinden, können Sie [Verbindung erstellen](/help/connections/create-connection.md) basierend auf Ihrem Journey Optimizer-Datensatz. Wählen Sie den Datensatz aus, den Sie an Platform gesendet haben.

## Konfigurieren der Datenansicht für Journey Optimizer-Dimensionen und -Metriken

Nachdem eine Verbindung erstellt wurde, können Sie eine oder mehrere [Datenansichten](/help/data-views/create-dataview.md) um die gewünschten Dimensionen und Metriken zu konfigurieren, die in Customer Journey Analytics verfügbar sind.

Sie können die folgenden Metriken in einer Datenansicht erstellen, um eine ungefähre Parität mit ähnlichen Metriken in Journey Optimizer zu erreichen. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichtsmanager finden Sie Einzelheiten zur Anpassung von Dimensionen und Metriken.

| Metrik | Beschreibung | Datenansichtseinstellungen |
| --- | --- | --- |
| Absprünge | Die Anzahl der Bounce-Nachrichten | Schema String-Element verwenden `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Ausschlusswerte einschließen: Wenn ein Kriterium erfüllt ist<br>Gleich: `bounce`<br>Gleich: `denylist` |
| Fehler | Die Anzahl der fehlerhaften Nachrichten | Schema String-Element verwenden `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `error` |
| Ausgeschlossen sind | Die Anzahl der ausgeschlossenen Nachrichten | Schema String-Element verwenden `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `exclude` |
| Abonnementkündigungen | Anzahl der Abmeldungen | Schema String-Element verwenden `_experience.customerJourneyManagement.messageInteraction.interactionType` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `unsubscribe` |
| Klicks | Anzahl der Klicks in Nachrichten | Schema String-Element verwenden `_experience.customerJourneyManagement.messageInteraction.interactionType` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `click` |
| Öffnungen | Anzahl geöffneter Nachrichten | Schema String-Element verwenden `_experience.customerJourneyManagement.messageInteraction.interactionType` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `open` |
| Spam-Beschwerden | Anzahl der Beschwerden wegen Spam | Schema String-Element verwenden `_experience.customerJourneyManagement.messageInteraction.interactionType` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `spam_complaint` |
| Nachrichten wurden erfolgreich gesendet | Die Anzahl der erfolgreich gesendeten Nachrichten | Schema String-Element verwenden `_experience.customerJourneyManagement.messageDeliveryfeedback.feedbackStatus` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `sent` |
| Synchronisierungsfehler | Die Gesamtzahl der Nachrichten, die nicht synchronisiert werden konnten | Schema String-Element verwenden `_experience.customerJourneyManagement.messageDeliveryfeedback.messageFailure.category` mit den folgenden Einstellungen:<br>Komponententyp: Metrik<br>Ausschlusswerte einschließen: Gleich `sync` |

{style=&quot;table-layout:auto&quot;}

## Berechnete Metriken mit Journey Optimizer-Metriken konfigurieren

Nachdem Sie die gewünschten Dimensionen und Metriken für den Journey Optimizer-Datensatz konfiguriert haben, können Sie auch [Berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md) für weitere Einblicke in diese Daten. Diese berechneten Metriken basieren auf den oben genannten Metriken, die im Data View Manager erstellt wurden.

| Berechnete Kennzahl | Beschreibung | Formel |
| --- | --- | --- |
| Gesamtzahl der gesendeten Nachrichten | Gesamtzahl der gesendeten, erfolgreichen oder fehlgeschlagenen Nachrichten | `[Messages successfully sent]` + `[Bounces]` + `[Sync failures]` |

{style=&quot;table-layout:auto&quot;}

## Unterschiede bei der Berichterstellung zwischen Journey Optimizer und Customer Journey Analytics

Datendiskrepanzen zwischen Produkten liegen in der Regel zwischen 1 und 2 %. Größere Diskrepanzen zwischen Produkten können möglicherweise auf Folgendes zurückgeführt werden:

* Die Verarbeitungszeit für eingehende Daten kann sich von Produkt zu Produkt leicht unterscheiden, insbesondere bei Daten, die innerhalb der letzten zwei Stunden erfasst wurden. Verwenden Sie Datumsbereiche mit Ausnahme von heute, um Diskrepanzen im Zusammenhang mit der Verarbeitungszeit zu vermeiden.
* Die berechnete Metrik &quot;Gesamtzahl der gesendeten Nachrichten&quot;enthält nicht die Metrik &quot;Weitere Zustellversuche&quot;. Daten für die Metrik &quot;Weitere Zustellversuche&quot;sind nicht im Datensatz enthalten und zeigen möglicherweise niedrigere Zahlen in CJA-Berichten im Vergleich zu AJO-Berichten an. Wiederholungsdaten werden jedoch in die Metrik &quot;Nachrichten erfolgreich gesendet&quot;oder &quot;Absprünge&quot;konvertiert. Verwenden Sie Datumsbereiche in einer Woche oder älter, um Diskrepanzen bei der Metrik &quot;Gesamtzahl der gesendeten Nachrichten&quot;zwischen Produkten zu vermeiden.
