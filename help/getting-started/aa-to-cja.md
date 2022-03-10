---
title: Entwicklung von Adobe Analytics zu Customer Journey Analytics
description: Schritte zum Konvertieren von Adobe Analytics-Daten in Customer Journey Analytics-Daten
role: Admin
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5e3f0aa0-ba24-48c8-948c-ebb5c270f34d
source-git-commit: cd48a91ca3affc39cf71451bdd8a44ca7669523b
workflow-type: tm+mt
source-wordcount: '1242'
ht-degree: 88%

---

# Entwicklung von Adobe Analytics zu Customer Journey Analytics

Wenn sich Ihr Unternehmen weiterentwickelt, Customer Journey Analytics zu verwenden, sollten Sie diese Schritte durchsuchen, um Ihre Daten vorzubereiten und sich der wichtigen Unterschiede zwischen den beiden Technologien bewusst zu werden. Dieser Artikel richtet sich an eine Administrator-Zielgruppe.

## Vorbereiten Ihrer Daten

Die Vorbereitung Ihrer Adobe Analytics-Daten auf einen nahtlosen Wechsel zu Customer Journey Analytics ist für die Datenintegrität und die Konsistenz der Berichte von entscheidender Bedeutung.

### 1. Identitäten erfassen

Die vielleicht wichtigste Komponente beim Verständnis einer Customer Journey ist, zu wissen, wer bei jedem Schritt der Kunde ist. Customer Journey Analytics verfügt über eine Kennung auf allen Kanälen und für alle entsprechenden Daten, die es ermöglicht, mehrere Quellen in CJA zusammenzufügen.
Beispiele für Identitäten sind Kunden-ID, Konto-ID oder E-Mail-ID. Für jede ID gilt Folgendes unabhängig von der Identität (es kann auch mehrere Identitäten geben):

* Die ID ist vorhanden oder kann zu allen Datenquellen hinzugefügt werden, die Sie in CJA integrieren möchten
* Die ID wird in jeder Datenzeile angegeben
* Die ID enthält keine persönlich identifizierbare Informationen. Wenden Sie Hashing auf alle sensiblen Elemente an.
* Die ID verwendet dasselbe Format für alle Quellen (gleiche Länge, gleiche Hashing-Methode usw.)

In Datensätzen wie Adobe Analytics ist möglicherweise nicht in jeder Datenzeile eine Identität vorhanden, aber eine sekundäre Identität schon. In diesem Fall kann die kanalübergreifende Analyse (früher als „feldbasierte Zuordnung“ bezeichnet) verwendet werden, um die Lücke zwischen Zeilen zu schließen, wenn ein Kunde nur durch seine ECID identifiziert wird und wenn eine Identität erfasst wird (z. B. bei der Authentifizierung eines Kunden). [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=de)

### 2. Variablen anpassen

Die einfachste Methode zur Umwandlung von Adobe Analytics-Daten in Customer Journey Analytics-Daten besteht darin, eine [globale Report Suite](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=de) in die Experience Platform mit [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de). Dieser Connector ordnet Ihre Adobe Analytics-Variablen direkt einem XDM-Schema und -Datensatz in Experience Platform zu, die wiederum problemlos mit Customer Journey Analytics verbunden werden können.

Eine vollständige globale Report Suite ist nicht in jedem Fall für eine Implementierung möglich. Wenn Sie planen, mehrere Report Suites in Customer Journey Analytics zu importieren, müssen Sie die Variablen in diesen Report Suites vorab angleichen.

Beispielsweise kann eVar1 in Report Suite 1 auf [!UICONTROL Seite] verweisen. In Report Suite 2 kann eVar 1 auf [!UICONTROL Interne Kampagne] verweisen. Wenn diese Variablen in Customer Journey Analytics importiert werden, werden sie in einer gemeinsamen eVar1-Dimension vermischt, was zu möglicherweise verwirrenden und ungenauen Berichten führt.

Wenn Sie den Wechsel zu einer globalen Report Suite aufgrund von Problemen mit [!UICONTROL Eindeutige Werte überschritten] oder [!UICONTROL Geringer Traffic] vermieden haben, beachten Sie, dass es in CJA keine [Kardinalitätsbeschränkungen für eine Dimension](/help/components/dimensions/high-cardinality.md) gibt. Dadurch können alle eindeutigen Werte angezeigt und gezählt werden.

### 3. Marketing-Kanäle (erneut) konfigurieren

Herkömmliche Einstellungen für Marketing-Kanäle in Adobe Analytics funktionieren in CJA nicht auf die gleiche Weise. Dies hat zwei Gründe:

* Die Verarbeitungsstufe für die in Adobe Experience Platform aufgenommenen Adobe Analytics-Daten

* Der Berichtscharakter von Customer Journey Analytics

Adobe hat [aktualisierte Best Practices für die Implementierung von Marketing-Kanälen](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=de) veröffentlicht. Diese aktualisierten Empfehlungen helfen Ihnen dabei, die bereits in Adobe Analytics vorhandenen Funktionen mit Attribution IQ optimal zu nutzen. Diese werden Ihnen auch bei der Umstellung auf Customer Journey Analytics helfen.

### 4. Entscheidung zwischen Analytics-Quell-Connector und Experience Platform SDKs

Im Zuge der Weiterentwicklung der [Experience Edge](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de)-Datenerfassung werden Sie wahrscheinlich entweder auf das [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/web-sdk.html?lang=de) oder das [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=de) mit dem Adobe Experience Platform Edge Network migrieren. Während eine typische Implementierung der SDKs Daten an Adobe Analytics sendet, gibt es eine neue Möglichkeit, Daten direkt an Adobe Experience Platform zu senden. Diese Daten können dann in Customer Journey Analytics aufgenommen werden, während gleichzeitig die an Adobe Analytics gesendeten Daten beibehalten werden.

Diese Methode erweitert die Möglichkeiten für die Datenerfassung deutlich: Die Anzahl der Felder ist nicht mehr beschränkt und es besteht keine Notwendigkeit mehr, Datenelemente Props, eVars und Ereignissen wie in Analytics zuzuordnen. Sie können unbegrenzte Schemaelemente verschiedener Typen verwenden und sie mithilfe von CJA-[Datenansichten](/help/data-views/data-views.md) auf verschiedene Weise darstellen. Die Geschwindigkeit der Datenverfügbarkeit steigt, wenn die Daten direkt an Adobe Experience Platform gesendet werden, da die Zeit für die Datenverarbeitung über Adobe Analytics entfällt.

**Vorteile der Verwendung von Experience Platform-SDKs:**

* Flexibles Schema zur Definition von erforderlichen Feldern
* Nicht von der Adobe Analytics-Nomenklatur abhängig (Prop, eVar, Ereignis usw.)
* Keine Längenbeschränkung (100 Zeichen für Props)
* Schnellere Datenverfügbarkeit in Adobe Experience Platform

**Nachteile der Verwendung von Experience Platform-SDKs**

Die folgenden Adobe Analytics-Funktionen oder -Komponenten werden nicht unterstützt:

* Marketing-Kanäle
* Bot-Filterung
* Geo-, Domain-, Gerätesuche
* Analytics for Target (A4T)

## Einige wichtige Unterschiede

### Machen Sie sich vertraut mit der Verarbeitung zur Berichtslaufzeit

Das Reporting in Adobe Analytics beruht auf einer erheblichen Datenvorverarbeitung, um Ergebnisse zu generieren, wie die Persistenz in [!UICONTROL eVars]. Im Gegensatz dazu führt Customer Journey Analytics (CJA) diese Berechnungen zur Berichtslaufzeit aus.

[!UICONTROL Berichtszeitverarbeitung] eröffnet die Möglichkeit, rückwirkende Einstellungen anzuwenden und mehrere Versionen der Variablenpersistenz zu erstellen, ohne die Art der Erfassung der zugrunde liegenden Daten ändern zu müssen.


Diese Änderung führt zu gewissen Unterschieden in der Verwendung von Daten zur Berichtserstellung, insbesondere bei Variablen, die länger gültig sind. Sie können beurteilen, wie sich die Verarbeitung zur Berichtslaufzeit auf Ihr Reporting auswirken kann, indem Sie eine [Virtual Report Suite](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=de) verwenden.

### Identifizieren Sie wichtige Segmente und berechnete Metriken

Adobe Analytics-Segmente (in CJA als [!UICONTROL Filter] bezeichnet) und berechnete Metriken sind nicht mit Customer Journey Analytics kompatibel. In vielen Fällen können diese Komponenten in CJA mithilfe der neuen Schemata und verfügbaren Daten neu erstellt werden.

Um den Wechsel zwischen den Systemen für Benutzer so reibungslos wie möglich zu gestalten, führen Sie folgende Maßnahmen aus:

1. Identifizieren Sie die wichtigsten dieser Komponenten

1. Dokumentieren Sie ihre Definitionen

1. Ermitteln Sie, welche Felder in den Daten erforderlich sind, um sie in CJA als [Filter](/help/components/filters/filters-overview.md) und [Berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md) zu replizieren.

Hier sind einige Videos, die Ihnen dabei helfen:

* [Verschieben von Adobe Analytics-Segmenten nach Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=de)

* [Verschieben der berechneten Metriken von Adobe Analytics nach Customer Journey Analytics](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=de)

### Weitere Überlegungen

* Durch die CJA-Datenansichten haben Sie bei der Definition von Metriken und Dimensionen in Customer Journey Analytics deutlich mehr Flexibilität. Sie können beispielsweise den Wert einer Dimension als Definition einer Metrik verwenden. [Weitere Informationen](/help/data-views/data-views-usecases.md)

* Wenn Sie einen benutzerdefinierten Kalender in Adobe Analytics definiert haben, haben Sie ähnliche [benutzerdefinierte Kalenderfunktionen](/help/components/date-ranges/custom-date-ranges.md) innerhalb von CJA. Sie müssen sicherstellen, dass Ihr Kalender korrekt definiert ist.

* In Customer Journey Analytics können Sie eine benutzerdefinierte maximale Wartezeit für Besuche/Sitzungen definieren sowie eine Metrik festlegen, durch die eine neue Sitzung gestartet wird. Sie können Datenansichten mit verschiedenen Sitzungsdefinitionen erstellen, um Einblicke zu erhalten, die weit darüber hinausgehen, was in Adobe Analytics möglich war. Diese Funktion kann besonders für Datensätze im Mobile-Bereich von Nutzen sein.

## Nächste Schritte

Wenn Sie nach dem Wechsel zu CJA Datendiskrepanzen feststellen, können Sie Ihre ursprünglichen Adobe Analytics-Daten mit den Adobe Analytics-Daten vergleichen, die sich jetzt in Customer Journey Analytics befinden. [Weitere Informationen](/help/troubleshooting/compare.md)
