---
title: Häufig gestellte Fragen zu Cross-Channel Analytics
description: Häufig gestellte Fragen zu Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: f181584603d62b09ebc8538759d47fb1e03b007a
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 91%

---

# Häufig gestellte Fragen

## Wie kann ich kanalübergreifende Analyse verwenden, um zu sehen, wie Personen von einem Kanal zum anderen wechseln?

Sie können eine Flussvisualisierung mit der Dimension „Datensatz-ID“ verwenden.

1. Melden Sie sich bei [analytics.adobe.com](https://analytics.adobe.com) an und erstellen Sie ein leeres Arbeitsbereich-Projekt.
2. Klicken Sie auf der linken Seite auf die Registerkarte „Visualisierungen“ und ziehen Sie eine Flussvisualisierung in die Arbeitsfläche auf der rechten Seite.
3. Klicken Sie auf den Tab „Komponenten“ auf der linken Seite und ziehen Sie die Dimension „Datensatz-ID“ an die mittlere Position mit der Bezeichnung „Dimension oder Element“.
4. Dieser Flussbericht ist interaktiv. Klicken Sie auf einen der Werte, um den Fluss auf nachfolgende oder vorherige Seiten zu erweitern. Verwenden Sie das Kontextmenü, um Spalten zu erweitern oder zu reduzieren. Im selben Flussbericht können auch verschiedene Dimensionen verwendet werden.

Wenn Sie die Datensatz-ID-Dimensionselemente umbenennen möchten, können Sie einen Lookup-Datensatz verwenden.

## Wie weit zurück werden Besucher in der kanalübergreifenden Analyse neu zugewiesen?

Das Lookback-Fenster für die Neuzuweisung hängt von der gewünschten Häufigkeit der [Wiederholung](replay.md) der Daten ab. Wenn Sie beispielsweise die kanalübergreifende Analyse so einrichten, dass Daten einmal wöchentlich wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung 7 Tage. Wenn Sie die kanalübergreifende Analyse so einrichten, dass Daten jeden Tag wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung 1 Tag.

## Wie werden freigegebene Geräte gehandhabt?

In einigen Situationen ist es möglich, dass sich mehrere Personen von demselben Gerät aus anmelden. Beispiele dafür sind freigegebene Geräte zu Hause, freigegebene PCs in einer Bibliothek oder ein Terminal in einem Einzelhandelsgeschäft.

Die vorübergehende ID setzt die beständige ID außer Kraft, sodass freigegebene Geräte als separate Personen betrachtet werden (auch wenn sie von demselben Gerät stammen).

## Wie werden in der kanalübergreifenden Analyse Situationen behandelt, in denen eine einzelne Person über eine große Anzahl von beständigen IDs verfügt?

In bestimmten Situationen kann ein einzelner Benutzer mit einer großen Anzahl von beständigen IDs verknüpft sein. Dazu gehören beispielsweise Personen, die Browser-Cookies häufig löschen oder den privaten bzw. Inkognito-Modus des Browsers verwenden.

Die Anzahl der beständigen IDs ist für die vorübergehende ID irrelevant. Ein einzelner Benutzer kann zu einer beliebigen Anzahl von Geräten gehören, ohne dass sich dies auf die Fähigkeit der kanalübergreifenden Analyse auswirkt, Zuordnungen geräteübergreifend vorzunehmen.

## Wie lange dauert es, bis der neu zugewiesene Datensatz verfügbar ist, nachdem ich meinen Account-Manager mit den gewünschten Informationen kontaktiert habe?

Die Echtzeit-Zuordnung ist ca. 1 Woche, nachdem Adobe Cross-Channel Analytics aktiviert hat, verfügbar. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Bei kleinen Datensätzen (weniger als 1 Million Ereignisse pro Tag) dauert es in der Regel einige Tage, während große Datensätze (1 Milliarde Ereignisse pro Tag) eine Woche oder länger benötigen können.

## Wie handhabt Cross-Channel Analytics DSGVO- und CCPA-Anforderungen?

Adobe handhabt DSGVO- und CCPA -Anforderungen gemäß den nationalen und internationalen Gesetzen. Adobe bietet den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de) für Datenzugriffs- und Löschanfragen. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

## Was passiert, wenn das Feld „Persistent ID“ in einem oder mehreren Ereignissen leer ist?

Wenn das Feld `Persistent ID` bei einem Ereignis in einem Datensatz, der mit feldbasierter Zuordnung verknüpft ist, leer ist, füllt die kanalübergreifende Analyse die `Stitched ID` für dieses Ereignis auf eine dieser zwei Arten aus:
* Wenn das Feld `Transient ID` nicht leer ist, verwendet die kanalübergreifende Analyse den Wert in `Transient ID` als `Stitched ID`.
* Wenn das Feld `Transient ID` leer ist, lässt die kanalübergreifende Analyse auch das Feld `Stitched ID` leer. In diesem Fall sind `Persistent ID`, `Transient ID` und `Stitched ID` beim Ereignis leer. Ereignisse wie diese werden aus CJA in jeder CJA-Verbindung mit dem zuzuordnenden Datensatz abgelegt, wobei `Stitched ID` als `Person ID` ausgewählt wurde.

## Wie stellt sich ein Vergleich zwischen Metriken in zugeordneten CJA-Datensätzen und ähnlichen Metriken in nicht zugeordneten CJA-Datensätzen und mit dem herkömmlichen Adobe Analytics dar?

Bestimmte Metriken in CJA ähneln den Metriken in herkömmlichem Analytics, andere unterscheiden sich jedoch davon, je nachdem was Sie vergleichen. In der folgenden Tabelle werden verschiedene häufig verwendete Metriken verglichen:

| **Zugeordnete CJA-Daten** | **Nicht zugeordnete CJA-Daten** | **Traditionelles Adobe Analytics** | **Analytics Ultimate mit CDA** |
| ----- | ----- | ----- | ----- |
| **Personen** = Anzahl der einzelnen `Person ID`s, für die `Stitched ID` als `Person ID` ausgewählt ist. Je nach Ergebnis des Zuordnungsprozesses kann **Personen** größer oder kleiner als **Unique Visitors** im herkömmlichen Adobe Analytics sein. | **Personen** = Anzahl der einzelnen `Person ID`s basierend auf der Spalte, die als `Person ID` ausgewählt wurde. **Personen** in Adobe Source Connector-Datensätzen ähnelt **Unique Visitors** im traditionellen Adobe Analytics `endUserIDs. _experience. aaid.id` ausgewählt wird als `Person ID` in CJA. | **Unique Visitors** = Anzahl unterschiedlicher Besucher-IDs. Beachten Sie, dass **Unique Visitors** möglicherweise nicht mit der Anzahl der eindeutigen **ECID** s übereinstimmt. | Siehe [Personen](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=de). |
| **Sitzungen**: Wird anhand der in der CJA-Datenansicht angegebenen Sitzungseinstellungen definiert. Der Zuordnungsprozess kann einzelne Sitzungen von mehreren Geräten zu einer einzelnen Sitzung kombinieren. | **Sitzungen**: Wird anhand der in der CJA-Datenansicht angegebenen Sitzungseinstellungen definiert. | **Besuche**: Siehe [Besuche](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=de). | **Besuche**: Wird basierend auf den Sitzungseinstellungen definiert, die in der [Virtual Report Suite der geräteübergreifenden Analyse](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=de) angegeben sind. |
| **Ereignisse** = Anzahl der Zeilen in den zugeordneten Daten in Customer Journey Analytics. Im Allgemeinen sollte diese Anzahl nahe bei der der **Vorfälle** im herkömmlichen Adobe Analytics liegen. Beachten Sie jedoch die oben stehenden häufig gestellten Fragen zu Zeilen mit einem leeren `Persistent ID`. | **Ereignisse** = Anzahl der Zeilen in den nicht zugeordneten Daten in CJA. Im Allgemeinen sollte diese Anzahl nahe bei der der **Vorfälle** im herkömmlichen Adobe Analytics liegen. Beachten Sie jedoch, dass Ereignisse, die in den nicht zugeordneten Daten in AEP Data Lake ein leeres `Person ID` enthalten, in CJA abgelegt (nicht eingeschlossen) werden. | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

Andere Metriken können in CJA und im herkömmlichen Adobe Analytics ähnlich sein. Beispielsweise die Gesamtzahl für Adobe Analytics [benutzerspezifische Ereignisse](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=de) 1-100 sollte im Allgemeinen im herkömmlichen Adobe Analytics und CJA sehr nahe beieinander liegen (ob zugeordnet oder nicht zugeordnet). Beachten Sie jedoch, dass dies nicht immer der Fall ist, da [Funktionsunterschiede](/help/getting-started/aa-vs-cja/cja-aa.md)), z. B. die Deduplizierung zwischen CJA und herkömmlichem Adobe Analytics.

## Kann die kanalübergreifende Analyse Identitätszuordnungsfelder verwenden?

Nein, die kanalübergreifende Analyse kann derzeit keine identityMap-Felder verwenden.
