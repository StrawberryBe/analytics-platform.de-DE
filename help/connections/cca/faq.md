---
title: Häufig gestellte Fragen zu Cross-Channel Analytics
description: Häufig gestellte Fragen zu Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: 5eede8eeb5d7e8632dc0d7d580f01ccc7ac8106c
workflow-type: tm+mt
source-wordcount: '1067'
ht-degree: 58%

---

# Häufig gestellte Fragen

## Wie kann ich kanalübergreifende Analyse verwenden, um zu sehen, wie Personen von einem Kanal zum anderen wechseln?

Sie können eine Flussvisualisierung mit der Dimension „Datensatz-ID“ verwenden.

1. Melden Sie sich bei [analytics.adobe.com](https://analytics.adobe.com) an und erstellen Sie ein leeres Arbeitsbereich-Projekt.
2. Klicken Sie auf der linken Seite auf die Registerkarte „Visualisierungen“ und ziehen Sie eine Flussvisualisierung in die Arbeitsfläche auf der rechten Seite.
3. Klicken Sie links auf die Registerkarte &quot;Komponenten&quot;und ziehen Sie die Dimension &quot;Datensatz-ID&quot;an die mittlere Position mit der Bezeichnung &quot;Dimension oder Element&quot;.
4. Dieser Flussbericht ist interaktiv. Klicken Sie auf einen der Werte, um den Fluss auf nachfolgende oder vorherige Seiten zu erweitern. Verwenden Sie das Kontextmenü, um Spalten zu erweitern oder zu reduzieren. Im selben Flussbericht können auch verschiedene Dimensionen verwendet werden.

Wenn Sie die Datensatz-ID-Dimensionselemente umbenennen möchten, können Sie einen Lookup-Datensatz verwenden.

## Wie weit zurück werden Besucher in der kanalübergreifenden Analyse neu zugewiesen?

Das Lookback-Fenster für die Neuzuweisung hängt von der gewünschten Häufigkeit der [Wiederholung](replay.md) der Daten ab. Wenn Sie beispielsweise die kanalübergreifende Analyse so einrichten, dass Daten einmal wöchentlich wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung sieben Tage. Wenn Sie die kanalübergreifende Analyse so einrichten, dass Daten täglich wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung einen Tag.

## Wie werden freigegebene Geräte gehandhabt?

In einigen Situationen ist es möglich, dass sich mehrere Personen von demselben Gerät aus anmelden. Beispiele dafür sind freigegebene Geräte zu Hause, freigegebene PCs in einer Bibliothek oder ein Terminal in einem Einzelhandelsgeschäft.

Die vorübergehende ID setzt die beständige ID außer Kraft, sodass freigegebene Geräte als separate Personen betrachtet werden (auch wenn sie von demselben Gerät stammen).

## Wie behandelt die kanalübergreifende Analyse Situationen, in denen eine einzelne Person über viele beständige IDs verfügt?

In einigen Fällen kann ein einzelner Benutzer mit vielen beständigen IDs verknüpft sein. Dazu gehören beispielsweise Personen, die Browser-Cookies häufig löschen oder den privaten bzw. Inkognito-Modus des Browsers verwenden.

Die Anzahl der beständigen IDs ist für die vorübergehende ID irrelevant. Ein einzelner Benutzer kann zu einer beliebigen Anzahl von Geräten gehören, ohne dass sich dies auf die Fähigkeit der kanalübergreifenden Analyse auswirkt, Zuordnungen geräteübergreifend vorzunehmen.

## Wie lange dauert es, bis der neu zugewiesene Datensatz verfügbar ist, nachdem ich meinen Account-Manager mit den gewünschten Informationen kontaktiert habe?

Die Echtzeit-Zuordnung ist ca. eine Woche nach der Adobe verfügbar und ermöglicht die kanalübergreifende Analyse. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Bei kleinen Datensätzen (weniger als 1 Million Ereignisse pro Tag) dauert es in der Regel einige Tage, während große Datensätze (1 Milliarde Ereignisse pro Tag) eine Woche oder länger benötigen können.

## Was ist der Unterschied zwischen der geräteübergreifenden Analyse (eine Funktion in herkömmlicher Analytics) und der kanalübergreifenden Analyse?

[Geräteübergreifende Analyse](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) ist eine Funktion, die speziell für den herkömmlichen Adobe Analytics entwickelt wurde und Ihnen hilft, zu verstehen, wie Benutzer geräteübergreifend arbeiten. Es bietet zwei Workflows zum Verknüpfen von Gerätedaten: feldbasiertes Stitching und das Gerätediagramm.

[Kanalübergreifende Analyse](../overview.md) ist eine CJA-spezifische Funktion, mit der Sie verstehen können, wie Benutzer auf beiden Geräten und Kanälen arbeiten. Es ist die Personen-ID eines Datensatzes, sodass dieser Datensatz nahtlos mit anderen Datensätzen kombiniert werden kann. Diese Funktion funktioniert im Design ähnlich wie das feldbasierte Stitching der geräteübergreifenden Analyse, aber die Implementierung unterscheidet sich von der anderen Datenarchitektur zwischen herkömmlichem Analytics und CJA.

## Wie handhabt Cross-Channel Analytics DSGVO- und CCPA-Anforderungen?

Adobe handhabt DSGVO- und CCPA -Anforderungen gemäß den nationalen und internationalen Gesetzen. Adobe bietet den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de) für Datenzugriffs- und Löschanfragen. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

## Was passiert, wenn das Feld „Persistent ID“ in einem oder mehreren Ereignissen leer ist?

Wenn das Feld `Persistent ID` bei einem Ereignis in einem Datensatz, der mit feldbasierter Zuordnung verknüpft ist, leer ist, füllt die kanalübergreifende Analyse die `Stitched ID` für dieses Ereignis auf eine dieser zwei Arten aus:

* Wenn das Feld `Transient ID` nicht leer ist, verwendet die kanalübergreifende Analyse den Wert in `Transient ID` als `Stitched ID`.
* Wenn das Feld `Transient ID` leer ist, lässt die kanalübergreifende Analyse auch das Feld `Stitched ID` leer. In diesem Fall `Persistent ID`, `Transient ID`und `Stitched ID` leer sind. Diese Ereignistypen werden aus jeder CJA-Verbindung mit dem Datensatz, der zugeordnet wird, entfernt, in dem `Stitched ID` wurde als `Person ID`.

## Wie stellt sich ein Vergleich zwischen Metriken in zugeordneten CJA-Datensätzen und ähnlichen Metriken in nicht zugeordneten CJA-Datensätzen und mit dem herkömmlichen Adobe Analytics dar?

Bestimmte Metriken in CJA ähneln den Metriken in herkömmlichem Analytics, andere unterscheiden sich jedoch davon, je nachdem was Sie vergleichen. In der folgenden Tabelle werden verschiedene häufig verwendete Metriken verglichen:

| **Zugeordnete CJA-Daten** | **Nicht zugeordnete CJA-Daten** | **Traditionelles Adobe Analytics** | **Analytics Ultimate mit CDA** |
| ----- | ----- | ----- | ----- |
| **Personen** = Anzahl der einzelnen `Person ID`s, für die `Stitched ID` als `Person ID` ausgewählt ist. Je nach Ergebnis des Zuordnungsprozesses kann **Personen** größer oder kleiner als **Unique Visitors** im herkömmlichen Adobe Analytics sein. | **Personen** = Anzahl der einzelnen `Person ID`s basierend auf der Spalte, die als `Person ID` ausgewählt wurde. **Personen** in Adobe Source Connector-Datensätzen ähnelt **Unique Visitors** im traditionellen Adobe Analytics `endUserIDs._experience.aaid.id` ausgewählt wird als `Person ID` in CJA. | **Unique Visitors** = Anzahl unterschiedlicher Besucher-IDs. **Unique Visitors** darf nicht mit der Anzahl der einzelnen **ECID** s. | Siehe [Personen](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=de). |
| **Sitzungen**: Wird basierend auf den Sitzungseinstellungen in der CJA-Datenansicht definiert. Der Zuordnungsprozess kann einzelne Sitzungen von mehreren Geräten zu einer einzelnen Sitzung kombinieren. | **Sitzungen**: Definiert anhand der Sitzungseinstellungen, die in der CJA-Datenansicht angegeben sind. | **Besuche**: Siehe [Besuche](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=de). | **Besuche**: Dies wird anhand der Sitzungseinstellungen definiert, die in der Variablen [CDA Virtual Report Suite](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=de). |
| **Ereignisse** = Anzahl der Zeilen in den zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im traditionellen Adobe Analytics. Beachten Sie jedoch die oben stehenden häufig gestellten Fragen zu Zeilen mit einem leeren `Persistent ID`. | **Ereignisse** = Anzahl der Zeilen in den nicht zugeordneten Daten in CJA. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im traditionellen Adobe Analytics. Beachten Sie jedoch, dass bei Ereignissen, die eine leere `Person ID` in den nicht zugewiesenen Daten im Data Lake der Experience Platform sind diese Ereignisse nicht in CJA enthalten. | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

Andere Metriken können in CJA und im herkömmlichen Adobe Analytics ähnlich sein. Beispielsweise die Gesamtzahl für Adobe Analytics [benutzerspezifische Ereignisse](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=de) 1-100 ist im Allgemeinen zwischen dem herkömmlichen Adobe Analytics und CJA vergleichbar (ob zugeordnet oder nicht zugeordnet). [Funktionsunterschiede](/help/getting-started/aa-vs-cja/cja-aa.md)), z. B. die Deduplizierung zwischen CJA und dem herkömmlichen Adobe Analytics, kann zu Diskrepanzen zwischen den beiden Produkten führen.

## Kann die kanalübergreifende Analyse Identitätszuordnungsfelder verwenden?

Nein, die kanalübergreifende Analyse kann derzeit keine Identitätszuordnungsfelder verwenden.
