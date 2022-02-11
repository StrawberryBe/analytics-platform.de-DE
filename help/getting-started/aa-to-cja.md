---
title: Migration von Adobe Analytics zu Customer Journey Analytics
description: Schritte für die Migration von Adobe Analytics zu Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 868cd819148b29436fbd92cf220c8bc4cb9e0725
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 5%

---


# Vorbereiten der Migration von Adobe Analytics zu Customer Journey Analytics

Bevor Sie Ihre Daten von Adobe Analytics zu Customer Journey Analytics migrieren, sollten Sie diese Überlegungen durchlesen, um Ihre Daten vorzubereiten und sich der kritischen Unterschiede zwischen den beiden Technologien bewusst zu werden.

## Daten vorbereiten

Die Vorbereitung Ihrer Adobe Analytics-Daten auf einen nahtlosen Wechsel zu Customer Journey Analytics ist für die Datenintegrität und die Konsistenz der Berichte von entscheidender Bedeutung.

### 1. Identitäten erfassen

Die vielleicht wichtigste Komponente beim Verständnis einer Journey ist, zu wissen, wer bei jedem Schritt der Kunde ist. Customer Journey Analytics: Eine Kennung, die über alle Kanäle hinweg vorhanden ist, und die entsprechenden Daten ermöglichen die Zuordnung mehrerer Quellen in Customer Journey Analytics.
Beispiele für Identitäten sind Kunden-ID, Konto-ID oder E-Mail-ID. Stellen Sie unabhängig von der Identität (und es kann mehrere IDs geben) sicher, dass Sie Folgendes für jede ID beachten:

* Existiert oder kann zu allen Datenquellen hinzugefügt werden, die in CJA integriert werden sollen
* Wird in jeder Datenzeile gefüllt
* Enthält keine PII. Wenden Sie Hashing auf alle sensiblen Elemente an.
* Verwendet dasselbe Format für alle Quellen (gleiche Länge, gleiche Hashing-Methode usw.)

In Datensätzen wie Adobe Analytics ist möglicherweise nicht in jeder Datenzeile eine Identität vorhanden, aber eine sekundäre Identität schon. In diesem Fall kann die kanalübergreifende Analyse (früher als &quot;feldbasierte Zuordnung&quot;bezeichnet) verwendet werden, um die Lücke zwischen Zeilen zu schließen, wenn ein Kunde nur durch seine ECID identifiziert wird und wenn eine Identität erfasst wird (z. B. bei der Authentifizierung eines Kunden). [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=de)

### 2. Anpassen der Variablen

Die einfachste Migration von Adobe Analytics-Daten in Customer Journey Analytics besteht darin, eine globale Report Suite mithilfe der [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de). Dieser Connector ordnet Ihre Adobe Analytics-Variablen direkt einem XDM-Schema und -Datensatz in AEP zu, die wiederum einfach mit CJA verbunden werden können.

Eine vollständige globale Report Suite ist möglicherweise nicht immer für eine Implementierung machbar. Wenn Sie planen, mehrere Report Suites in Customer Journey Analytics zu integrieren, müssen Sie vorab planen, die Variablen über diese Report Suites hinweg anzugleichen.

Beispielsweise kann eVar 1 in Report Suite 1 auf [!UICONTROL Seite] verweisen. In Report Suite 2 kann eVar 1 auf [!UICONTROL Interne Kampagne]. Wenn diese Variablen in Customer Journey Analytics integriert werden, werden sie in eine einzige eVar1-Dimension gemischt, was zu möglicherweise verwirrenden und ungenauen Berichten führt.

Wenn Sie aufgrund von Problemen mit dem [!UICONTROL Individuelle Werte überschritten] oder [!UICONTROL Geringer Traffic], wissen, dass CJA keine [Kardinalitätsbeschränkungen für eine Dimension](/help/components/dimensions/high-cardinality.md). Dadurch können alle eindeutigen Werte angezeigt und gezählt werden.

### 3. (Erneut) Konfigurieren Ihrer Marketing-Kanäle

Die herkömmlichen Adobe Analytics-Marketingkanaleinstellungen führen in Customer Journey Analytics nicht dasselbe aus. Dies hat zwei Gründe:

* Verarbeitungsstufe für die in Adobe Experience Platform erfassten Adobe Analytics-Daten und

* Berichtscharakter des Customer Journey Analytics

Die Adobe wurde veröffentlicht. [aktualisierte Best Practices für die Implementierung von Marketingkanälen](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=en). Diese aktualisierten Empfehlungen helfen Ihnen dabei, die bereits in Adobe Analytics vorhandenen Funktionen mit Attribution IQ optimal zu nutzen. Sie werden Sie auch bei der Umstellung auf den Customer Journey Analytics erfolgreich einrichten.

### 4. Entscheiden Sie sich für die Verwendung von Analytics Data Connector oder Experience Platform SDKs

As [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) sich die Datenerfassung weiterentwickelt, migrieren Sie wahrscheinlich entweder zum Adobe Experience Platform Web SDK oder zum Adobe Experience Platform Mobile SDK mit dem Adobe Experience Platform Edge Network. Während eine typische Implementierung der SDKs Daten an Adobe Analytics sendet, bietet sich eine neue Möglichkeit, Daten direkt an Adobe Experience Platform zu senden. Sie kann dann in Customer Journey Analytics aufgenommen werden, während gleichzeitig die an Adobe Analytics gesendeten Daten gepflegt werden.

Diese Methode erweitert die Möglichkeiten für die Datenerfassung deutlich: Die Anzahl der Felder oder die Notwendigkeit, Datenelemente Props, eVars und Ereignissen wie in Analytics zuzuordnen, ist nicht mehr beschränkt. Sie können unbegrenzte Schemaelemente verschiedener Typen verwenden und sie mithilfe von CJA auf verschiedene Weise darstellen [Datenansichten](/help/data-views/data-views.md). Die Geschwindigkeit der Datenverfügbarkeit steigt, wenn sie direkt an Adobe Experience Platform gesendet wird, da die Zeit für die Datenverarbeitung über Adobe Analytics entfernt wird.

**Vorteile der Verwendung von Experience Platform SDKs**

* Flexibles Schema zur Definition von erforderlichen Feldern
* Nicht von der Adobe Analytics-Nomenklatur abhängig (Eigenschaft, eVar, Ereignis usw.)
* Keine Längenbeschränkung (100 Zeichen für Props)
* Schnellere Datenverfügbarkeit in Adobe Experience Platform

**Nachteile der Verwendung von Experience Platform SDKs**

Die folgenden Adobe Analytics-Komponenten werden nicht unterstützt:

* Marketing-Kanäle
* Bot-Filterung
* Geo, Domäne, Gerätesuche
* Analytics for Target (A4T)

## Vorbereitung auf kritische Unterschiede

### Bequem mit der Berichtszeitverarbeitung

Die Berichterstellung in Adobe Analytics beruht auf einer erheblichen Menge an Datenvorverarbeitung, um Ergebnisse wie die Persistenz zu generieren, die in eVars angezeigt wird. Customer Journey Analytics führt diese Berechnungen zur Berichtslaufzeit aus.

Die Berichtszeitverarbeitung bietet die Möglichkeit, rückwirkende Einstellungen anzuwenden und mehrere Versionen der Variablenpersistenz zu erstellen, ohne die Art der Erfassung der zugrunde liegenden Daten ändern zu müssen.

Diese Verschiebung führt zu gewissen Unterschieden in der Berichtserstellung von Daten, insbesondere bei Variablen mit einem langen Ablauffenster. Sie können damit beginnen zu bewerten, wie sich die Berichtszeitverarbeitung auf Ihre Berichterstellung auswirken kann, indem Sie eine [Virtual Report Suite](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html).

### kritische Segmente und berechnete Metriken identifizieren

Adobe Analytics-Segmente (in Customer Journey Analytics als Filter bezeichnet) und berechnete Metriken sind nicht mit Customer Journey Analytics kompatibel. In vielen Fällen können diese Komponenten in Customer Journey Analytics mithilfe der neuen Schemata und verfügbaren Daten neu erstellt werden.

Planen Sie die Umstellung so reibungslos wie möglich für Benutzer beim Übergang zwischen den Systemen, indem Sie

1. Ermittlung der wichtigsten Komponenten.

1. ihre Definitionen dokumentieren und

1. Identifizieren, welche Felder in den Daten erforderlich sind, um sie in Customer Journey Analytics als [Filter](/help/components/filters/filters-overview.md) und [Berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md).

Hier sind einige Videos, die Sie führen:

* [Verschieben von Adobe Analytics-Segmenten in Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en)

* [Verschieben der berechneten Metriken von Adobe Analytics nach Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en)
