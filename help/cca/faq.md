---
title: Häufig gestellte Fragen zu Cross-Channel Analytics
description: Häufig gestellte Fragen zu Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
hide: true
hidefromtoc: true
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 66%

---

# Häufig gestellte Fragen

## Wie kann ich CCA verwenden, um zu sehen, wie Personen von einem Kanal zum anderen wechseln?

Sie können eine Flussvisualisierung mit der Dimension „Datensatz-ID“ verwenden.

1. Melden Sie sich bei [analytics.adobe.com](https://analytics.adobe.com) an und erstellen Sie ein leeres Arbeitsbereich-Projekt.
2. Klicken Sie auf der linken Seite auf die Registerkarte „Visualisierungen“ und ziehen Sie eine Flussvisualisierung in die Arbeitsfläche auf der rechten Seite.
3. Klicken Sie auf die Registerkarte „Komponenten“ auf der linken Seite und ziehen Sie die Dimension „Datensatz-ID“ an die mittlere Position mit der Bezeichnung „Dimension oder Element“.
4. Dieser Flussbericht ist interaktiv. Klicken Sie auf einen der Werte, um den Fluss auf nachfolgende oder vorherige Seiten zu erweitern. Verwenden Sie das Kontextmenü, um Spalten zu erweitern oder zu reduzieren. Im selben Flussbericht können auch verschiedene Dimensionen verwendet werden.

Wenn Sie die Datensatz-ID-Dimensionselemente umbenennen möchten, können Sie einen Lookup-Datensatz verwenden.

## Wie weit reicht die Rekordzahl der CCA zurück?

Das Lookback-Fenster für die Neuzuweisung hängt von der gewünschten Häufigkeit der [Wiederholung](replay.md) der Daten ab. Wenn Sie beispielsweise die CCA so einrichten, dass Daten einmal wöchentlich wiederholt werden, umfasst das Lookback-Fenster für die Neuzuweisung sieben Tage. Wenn Sie CCA so einrichten, dass Daten jeden Tag wiederholt werden, umfasst das Lookback-Fenster für die Neuzuweisung einen Tag.

## Wie werden freigegebene Geräte gehandhabt?

In einigen Situationen ist es möglich, dass sich mehrere Personen von demselben Gerät aus anmelden. Beispiele dafür sind freigegebene Geräte zu Hause, freigegebene PCs in einer Bibliothek oder ein Terminal in einem Einzelhandelsgeschäft.

Die vorübergehende ID setzt die beständige ID außer Kraft, sodass freigegebene Geräte als separate Personen betrachtet werden (auch wenn sie von demselben Gerät stammen).

## Wie behandelt CCA Situationen, in denen eine einzelne Person mehrere beständige IDs hat?

In einigen Fällen kann eine einzelne benutzende Person mit mehreren beständigen IDs verknüpft sein. Dazu gehören beispielsweise Personen, die Browser-Cookies häufig löschen oder den privaten bzw. Inkognito-Modus des Browsers verwenden.

Die Anzahl der beständigen IDs ist für die vorübergehende ID irrelevant. Ein einzelner Benutzer kann zu einer beliebigen Anzahl von Geräten gehören, ohne dass sich dies auf die Fähigkeit von CCA auswirkt, Zuordnungen geräteübergreifend vorzunehmen.

## Wie lange dauert es, bis der neu zugewiesene Datensatz verfügbar wird, nachdem ich mein Adobe-Kontoteam mit den gewünschten Informationen kontaktiert habe?

Die Echtzeit-Zuordnung ist etwa eine Woche nach der Aktivierung von Cross-Channel Analytics durch Adobe verfügbar. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Kleine Datensätze (weniger als 1 Million Ereignisse pro Tag) dauern in der Regel einige Tage, während große Datensätze (1 Milliarde Ereignisse pro Tag) eine Woche oder länger dauern können.

## Was ist der Unterschied zwischen der geräteübergreifenden Analyse (eine Funktion in Adobe Analytics) und der kanalübergreifenden Analyse?

[Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) ist eine Funktion, die speziell für das herkömmliche Adobe Analytics entwickelt wurde und Ihnen hilft, zu verstehen, wie Benutzende geräteübergreifend arbeiten. Sie bietet zwei Workflows zum Verknüpfen von Gerätedaten: die feldbasierte Zuordnung und das Gerätediagramm.

[Kanalübergreifende Analyse](/help/cca/overview.md) ist eine für Customer Journey Analytics spezifische Funktion, mit der Sie verstehen können, wie Benutzer auf beiden Geräten und Kanälen arbeiten. Sie verschlüsselt die Personen-ID eines Datensatzes neu, sodass dieser Datensatz nahtlos mit anderen Datensätzen kombiniert werden kann. Diese Funktion funktioniert im Design ähnlich wie das feldbasierte Stitching der geräteübergreifenden Analyse, aber die Implementierung unterscheidet sich von der unterschiedlichen Datenarchitektur zwischen Adobe Analytics und Customer Journey Analytics.

## Wie handhabt Cross-Channel Analytics DSGVO- und CCPA-Anforderungen?

Adobe handhabt DSGVO- und CCPA -Anforderungen gemäß den nationalen und internationalen Gesetzen. Adobe bietet den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de) für Datenzugriffs- und Löschanfragen. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

## Was passiert, wenn das Feld „Persistent ID“ in einem oder mehreren Ereignissen leer ist?

Wenn das Feld `Persistent ID` bei einem Ereignis in einem Datensatz, der mit feldbasierter Zuordnung verknüpft ist, leer ist, füllt CCA die `Stitched ID` für dieses Ereignis auf eine dieser zwei Arten aus:

* Wenn das Feld `Transient ID` nicht leer ist, verwendet CCA den Wert in `Transient ID` als `Stitched ID`.
* Wenn das Feld `Transient ID` leer ist, lässt CCA auch das Feld `Stitched ID` leer. In diesem Fall sind die Felder `Persistent ID`, `Transient ID` und `Stitched ID` für das Ereignis alle leer. Diese Ereignistypen werden aus jeder Customer Journey Analytics-Verbindung mit dem Datensatz, der zugeordnet wird, entfernt, in dem `Stitched ID` wurde als `Person ID`.

## Wie vergleichen sich Metriken in Customer Journey Analytics-zugeordneten Datensätzen mit ähnlichen Metriken in nicht zugeordneten Datensätzen in Customer Journey Analytics und mit dem herkömmlichen Adobe Analytics?

Bestimmte Metriken in Customer Journey Analytics ähneln den Metriken in Adobe Analytics, andere unterscheiden sich jedoch je nach dem, was Sie vergleichen. In der folgenden Tabelle werden verschiedene häufig verwendete Metriken verglichen:

| **Vom Customer Journey Analytics zugeordnete Daten** | **Aufgepasste Daten vom Customer Journey Analytics** | **Traditionelles Adobe Analytics** | **Analytics Ultimate mit CDA** |
| ----- | ----- | ----- | ----- |
| **Personen** = Anzahl der einzelnen `Person ID`s, für die `Stitched ID` als `Person ID` ausgewählt ist. Je nach Ergebnis des Zuordnungsprozesses kann **Personen** größer oder kleiner als **Unique Visitors** im herkömmlichen Adobe Analytics sein. | **Personen** = Anzahl der einzelnen `Person ID`s basierend auf der Spalte, die als `Person ID` ausgewählt wurde. **Personen** in Adobe Source Connector-Datensätzen ähnelt **Unique Visitors** im traditionellen Adobe Analytics `endUserIDs._experience.aaid.id` ausgewählt wird als `Person ID` in Customer Journey Analytics. | **Unique Visitors** = Anzahl der eindeutigen Personen-IDs. **Unique Visitors** ist möglicherweise nicht identisch mit der Anzahl der eindeutigen **ECID** s. | Siehe [Personen](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=de). |
| **Sitzungen**: Wird basierend auf den Sitzungseinstellungen in der Datenansicht des Customer Journey Analytics definiert. Der Zuordnungsprozess kann einzelne Sitzungen von mehreren Geräten zu einer einzelnen Sitzung kombinieren. | **Sitzungen**: Definiert anhand der Sitzungseinstellungen, die in der Datenansicht des Customer Journey Analytics angegeben sind. | **Besuche**: Siehe [Besuche](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=de). | **Besuche**: Wird basierend auf den Sitzungseinstellungen definiert, die in der [Virtual Report Suite von CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=de) angegeben sind. |
| **Veranstaltungen** = Anzahl der Zeilen in den zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch die oben stehenden häufig gestellten Fragen zu Zeilen mit einem leeren `Persistent ID`. | **Veranstaltungen** = Anzahl der Zeilen in den nicht zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch, dass bei Ereignissen, die eine leere `Person ID` in den nicht zugewiesenen Daten im Data Lake der Experience Platform sind diese Ereignisse nicht in Customer Journey Analytics enthalten. | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). |

Andere Metriken können in Customer Journey Analytics und im herkömmlichen Adobe Analytics ähnlich sein. Beispielsweise die Gesamtzahl für Adobe Analytics [benutzerspezifische Ereignisse](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=de) 1-100 ist im Allgemeinen zwischen dem herkömmlichen Adobe Analytics und dem herkömmlichen Customer Journey Analytics vergleichbar (ob zugeordnet oder nicht zugeordnet). [Funktionsunterschiede](/help/getting-started/aa-vs-cja/cja-aa.md)), z. B. die Deduplizierung zwischen Customer Journey Analytics und traditionellem Adobe Analytics kann zu Diskrepanzen zwischen den beiden Produkten führen.

## Kann CCA Identity Map-Felder verwenden?

Nein, CCA kann derzeit keine Identity Map-Felder verwenden.
