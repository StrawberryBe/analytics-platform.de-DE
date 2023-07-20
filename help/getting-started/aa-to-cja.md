---
title: Weiterentwicklung von Adobe Analytics
description: Schritte zum Umwandeln von Adobe Analytics-Daten in Customer Journey Analytics-Daten
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: a49ef8b35b9d5464df2c5409339b33eacb90cd9c
workflow-type: tm+mt
source-wordcount: '1461'
ht-degree: 75%

---

# Weiterentwicklung von Adobe Analytics

Wenn sich Ihr Unternehmen entschließt, Customer Journey Analytics zu verwenden, sollten Sie sich mit diesen Schritten vertraut machen, um Ihre Daten vorzubereiten, und über die wichtigen Unterschiede zwischen den beiden Technologien Bescheid wissen. Dieser Artikel richtet sich an Administratoren.

## Vorbereiten Ihrer Daten

Die Vorbereitung Ihrer Adobe Analytics-Daten auf einen nahtlosen Wechsel zu Customer Journey Analytics ist für die Datenintegrität und die Konsistenz der Berichte von entscheidender Bedeutung.

### 1. Identitäten erfassen {#identities}

Die vielleicht wichtigste Komponente beim Verständnis einer Customer Journey ist, zu wissen, wer bei jedem Schritt der Kunde ist. Customer Journey Analytics: Eine kanalübergreifende Kennung und die entsprechenden Daten ermöglichen die Zuordnung mehrerer Quellen innerhalb des Customer Journey Analytics.
Beispiele für Identitäten sind Kunden-ID, Konto-ID oder E-Mail-ID. Für jede ID gilt Folgendes unabhängig von der Identität (es kann auch mehrere Identitäten geben):

* ID existiert oder kann zu allen Datenquellen hinzugefügt werden, die Sie in Customer Journey Analytics integrieren möchten
* Die ID wird in jeder Datenzeile angegeben
* Die ID enthält keine persönlich identifizierbare Informationen. Wenden Sie Hashing auf alle sensiblen Elemente an.
* Die ID verwendet dasselbe Format für alle Quellen (gleiche Länge, gleiche Hashing-Methode usw.)

In Datensätzen wie Adobe Analytics ist möglicherweise nicht in jeder Datenzeile eine Identität vorhanden, aber eine sekundäre Identität schon. In diesem Fall kann Cross-Channel-Analyse (früher als „feldbasierte Zuordnung“ bezeichnet) verwendet werden, um die Lücke zwischen Zeilen zu schließen, wenn ein Kunde nur durch seine ECID identifiziert wird und wenn eine Identität erfasst wird (z. B. bei der Authentifizierung eines Kunden). [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=de)

### 2. Variablen anpassen {#variables}

Die einfachste Methode zur Umwandlung von Adobe Analytics-Daten in Customer Journey Analytics-Daten besteht darin, eine [globale Report Suite](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=de) in die Experience Platform mit [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de). Dieser Connector ordnet Ihre Adobe Analytics-Variablen direkt einem XDM-Schema und -Datensatz in Experience Platform zu, die wiederum einfach mit Customer Journey Analytics verbunden werden können.

Eine vollständige globale Report Suite ist nicht in jedem Fall für eine Implementierung möglich. Wenn Sie planen, mehrere Report Suites in Customer Journey Analytics zu integrieren, haben Sie zwei Möglichkeiten:

* Planen Sie im Voraus, damit Sie die Variablen in diesen Report Suites in Einklang bringen können. Beispielsweise kann eVar1 in Report Suite 1 auf [!UICONTROL Seite] verweisen. In Report Suite 2 kann eVar1 auf [!UICONTROL Interne Kampagne] verweisen. Wenn diese Variablen in den Customer Journey Analytics aufgenommen werden, werden sie in eine einzige eVar1-Dimension gemischt, was zu möglicherweise verwirrenden und ungenauen Berichten führt.

* Verwenden Sie die Funktion der [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) zum Zuordnen von Variablen. Es ist zwar einfacher, wenn alle Report Suites denselben Variablenaufbau verwenden, dies ist aber nicht erforderlich, wenn Sie die neue [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de#mapping)-Funktion von Experience Platform verwenden. Damit können Sie eine Variable anhand ihres zugeordneten Werts referenzieren, der sich auf der Ebene des Datenstroms (oder der Eigenschaft) befindet.

Wenn Sie aufgrund von Problemen mit dem [!UICONTROL Individuelle Werte überschritten] oder [!UICONTROL Geringer Traffic], wissen, dass der Customer Journey Analytics keine [Kardinalitätsbeschränkungen für eine Dimension](/help/components/dimensions/high-cardinality.md). Dadurch können alle eindeutigen Werte angezeigt und gezählt werden.

Im Folgenden finden Sie ein Anwendungsbeispiel für das [Kombinieren von Report Suites mit verschiedenen Schemata](/help/use-cases/aa-data/combine-report-suites.md).

### 3. Marketing-Kanäle (erneut) konfigurieren {#marketing-channels}

Die herkömmlichen Marketingkanaleinstellungen von Adobe Analytics führen in Customer Journey Analytics nicht dasselbe aus. Dies hat zwei Gründe:

* Die Verarbeitungsstufe für die in Adobe Experience Platform aufgenommenen Adobe Analytics-Daten

* Der Berichtscharakter von Customer Journey Analytics

Adobe hat [aktualisierte Best Practices für die Implementierung von Marketing-Kanälen](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=de) veröffentlicht. Diese aktualisierten Empfehlungen helfen Ihnen dabei, die bereits in Adobe Analytics vorhandenen Funktionen mit Attribution IQ optimal zu nutzen. Diese werden Ihnen auch bei der Umstellung auf Customer Journey Analytics helfen.

### 4. Entscheiden Sie, ob Sie Analytics-Quell-Connector oder Experience Platform SDKs verwenden möchten {#connector-vs-sdk}

Adobe Analytics-Kunden können ihre Report Suites in Adobe Experience Platform und Customer Journey Analytics einfach über den Analytics-Quell-Connector nutzen. Informationen zur Verwendung des Analytics-Quell-Connectors finden Sie in der Schnellstartanleitung zum [Daten aus Adobe Analytics erfassen und in Customer Journey Analytics verwenden](../data-ingestion/analytics.md). Siehe auch [Erstellen einer Adobe Analytics-Quellverbindung in der Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de), um weitere Informationen zu erhalten.

Im Zuge der Weiterentwicklung der [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de)-Datenerfassung werden Sie wahrscheinlich entweder auf das [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=de) oder das [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=de) mit dem Adobe Experience Platform Edge Network migrieren. Während eine typische Implementierung der SDKs Daten an Adobe Analytics sendet, gibt es eine neue Möglichkeit, Daten direkt an Adobe Experience Platform zu senden. Diese Daten können dann in Customer Journey Analytics aufgenommen werden, während gleichzeitig die an Adobe Analytics gesendeten Daten beibehalten werden.

Diese Methode erweitert die Möglichkeiten für die Datenerfassung deutlich: Die Anzahl der Felder ist nicht mehr beschränkt und es besteht keine Notwendigkeit mehr, Datenelemente Props, eVars und Ereignissen wie in Analytics zuzuordnen. Sie können unbegrenzte Schemaelemente verschiedener Typen verwenden und sie mithilfe von Customer Journey Analytics auf verschiedene Weise darstellen [Datenansichten](/help/data-views/data-views.md). Die Geschwindigkeit der Datenverfügbarkeit steigt, wenn die Daten direkt an Adobe Experience Platform gesendet werden, da die Zeit für die Datenverarbeitung über Adobe Analytics entfällt.

**Vorteile der Verwendung von Experience Platform-SDKs:**

* Flexibles Schema zur Definition von erforderlichen Feldern
* Nicht von der Adobe Analytics-Nomenklatur abhängig (Prop, eVar, Ereignis usw.)
* Keine Längenbeschränkung (100 Zeichen für Props)
* Schnellere Datenverfügbarkeit in Adobe Experience Platform für [Anwendungsfälle der Echtzeit-Personalisierung](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/configure-personalization-destinations.html?lang=de)
* [Erstanbieter-Geräte-IDs](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=de) für eine genauere Besucheridentifizierung

**Nachteile der Verwendung von Experience Platform-SDKs**

Die folgenden Adobe Analytics-Funktionen oder -Komponenten werden nicht unterstützt:

* Bot-Filterung
* Geo-, Domain-, Gerätesuche
* Messung von Streaming-Medien
* Livestream oder Livestream-Trigger

## Einige wichtige Unterschiede

### Machen Sie sich vertraut mit der Verarbeitung zur Berichtslaufzeit {#report-time}

Das Reporting in Adobe Analytics beruht auf einer erheblichen Datenvorverarbeitung, um Ergebnisse zu generieren, wie die Persistenz in [!UICONTROL eVars]. Im Gegensatz dazu führt Customer Journey Analytics (CJA) diese Berechnungen zur Berichtslaufzeit aus.

[!UICONTROL Berichtszeitverarbeitung] eröffnet die Möglichkeit, rückwirkende Einstellungen anzuwenden und mehrere Versionen der Variablenpersistenz zu erstellen, ohne die Art der Erfassung der zugrunde liegenden Daten ändern zu müssen.

Diese Änderung führt zu gewissen Unterschieden in der Verwendung von Daten zur Berichtserstellung, insbesondere bei Variablen, die länger gültig sind. Sie können beurteilen, wie sich die Verarbeitung zur Berichtslaufzeit auf Ihr Reporting auswirken kann, indem Sie eine [Virtual Report Suite](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=de) verwenden.

### Identifizieren Sie wichtige Segmente und berechnete Metriken {#segments-calcmetrics}

Adobe Analytics-Segmente (namens [!UICONTROL Filter] in Customer Journey Analytics) und berechnete Metriken nicht mit Customer Journey Analytics kompatibel sind. In vielen Fällen können diese Komponenten in Customer Journey Analytics mithilfe der neuen Schemata und verfügbaren Daten neu erstellt werden.

Um den Wechsel zwischen den Systemen für Benutzer so reibungslos wie möglich zu gestalten, führen Sie folgende Maßnahmen aus:

1. Identifizieren Sie die wichtigsten dieser Komponenten.

2. Dokumentieren Sie ihre Definitionen

3. Identifizieren, welche Felder in den Daten benötigt werden, um sie in Customer Journey Analytics zu replizieren als [Filter](/help/components/filters/filters-overview.md) und [Berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md).

Hier sind einige Videos, die Ihnen dabei helfen:

* [Verschieben von Adobe Analytics-Segmenten nach Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=de)

* [Verschieben der berechneten Metriken von Adobe Analytics nach Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/components/calc-metrics/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=de)

### Weitere Überlegungen

* Mithilfe der Vorteile von Customer Journey Analytics-Datenansichten haben Sie bei der Definition von Metriken und Dimensionen innerhalb von Customer Journey Analytics deutlich mehr Flexibilität. Sie können beispielsweise den Wert einer Dimension als Definition einer Metrik verwenden. [Weitere Informationen](/help/use-cases/data-views/data-views-usecases.md)

* Wenn Sie einen benutzerdefinierten Kalender in Adobe Analytics definiert haben, haben Sie ähnliche [benutzerdefinierte Kalenderfunktionen](/help/components/date-ranges/custom-date-ranges.md) innerhalb von Customer Journey Analytics. Sie müssen sicherstellen, dass Ihr Kalender korrekt definiert ist.

* In Customer Journey Analytics können Sie eine benutzerdefinierte maximale Wartezeit für Besuche/Sitzungen definieren sowie eine Metrik festlegen, durch die eine neue Sitzung gestartet wird. Sie können Datenansichten mit verschiedenen Sitzungsdefinitionen erstellen, um Einblicke zu erhalten, die weit darüber hinausgehen, was in Adobe Analytics möglich war. Diese Funktion kann besonders für Datensätze im Mobile-Bereich von Nutzen sein.

* Erwägen Sie die Bereitstellung eines Datenwörterbuchs für Ihre Benutzer – oder erweitern Sie das SDR, um den Experience Platform-Feldnamen für Schemaelemente einzuschließen.

## Nächste Schritte

Wenn Sie nach dem Wechsel zu Customer Journey Analytics Abweichungen feststellen, können Sie Ihre ursprünglichen Adobe Analytics-Daten mit den Adobe Analytics-Daten vergleichen, die sich jetzt in Customer Journey Analytics befinden. [Weitere Informationen](/help/troubleshooting/compare.md)
