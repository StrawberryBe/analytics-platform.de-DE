---
title: Häufig gestellte Fragen zur kanalübergreifenden Analyse
description: Häufig gestellte Fragen zur kanalübergreifenden Analyse
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
source-git-commit: 2be442915587780ce41f33b13e27b8cf44e239a6
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 46%

---

# Häufig gestellte Fragen

## Wie kann ich kanalübergreifende Analyse verwenden, um zu sehen, wie Personen von einem Kanal zum anderen wechseln?

Sie können eine Flussvisualisierung mit der Dimension „Datensatz-ID“ verwenden.

1. Melden Sie sich bei [analytics.adobe.com](https://analytics.adobe.com) an und erstellen Sie ein leeres Workspace-Projekt.
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

Die Echtzeit-Zuordnung ist ca. 1 Woche, nachdem Adobe die kanalübergreifende Analyse aktiviert hat, verfügbar. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Bei kleinen Datensätzen (weniger als 1 Million Ereignisse pro Tag) dauert es in der Regel einige Tage, während große Datensätze (1 Milliarde Ereignisse pro Tag) eine Woche oder länger benötigen können.

## Wie handhabt die kanalübergreifende Analyse DSGVO- und CCPA-Anforderungen?

Adobe handhabt DSGVO- und CCPA -Anforderungen gemäß den nationalen und internationalen Gesetzen. Adobe bietet den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de-DE) für Datenzugriffs- und Löschanfragen. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

## Was passiert, wenn das Feld &quot;Persistent ID&quot;in einem oder mehreren Ereignissen leer ist?

Wenn das Feld `Persistent ID` bei einem Ereignis in einem Datensatz, der mit feldbasiertem Stitching verknüpft ist, leer ist, füllt die kanalübergreifende Analyse die `Stitched ID` für dieses Ereignis auf zwei Arten aus:
* Wenn das Feld `Transient ID` nicht leer ist, verwendet die kanalübergreifende Analyse den Wert in `Transient ID` als `Stitched ID`.
* Wenn das Feld `Transient ID` leer ist, lässt die kanalübergreifende Analyse auch das Feld `Stitched ID` leer. In diesem Fall sind `Persistent ID`, `Transient ID` und `Stitched ID` beim Ereignis alle leer. Ereignisse wie diese werden aus CJA in jeder CJA-Verbindung mit dem zuzuordnenden Datensatz abgelegt, wobei `Stitched ID` als `Person ID` ausgewählt wurde.

## Wie vergleichen sich Metriken in mit CJA zugeordneten Datensätzen mit ähnlichen Metriken in nicht zugeordneten CJA-Datensätzen und mit dem herkömmlichen Adobe Analytics?

Bestimmte Metriken in CJA ähneln den Metriken in herkömmlichem Analytics, andere unterscheiden sich jedoch je nach dem, was Sie vergleichen. In der folgenden Tabelle werden verschiedene häufig verwendete Metriken verglichen:

| **CJA-zugeordnete Daten** | **Nicht zugeordnete CJA-Daten** | **Traditioneller Adobe Analytics** | **Analytics Ultimate mit CDA** |
| ----- | ----- | ----- | ----- |
| **Personen**  = Anzahl der einzelnen  `Person ID`s, für die  `Stitched ID` ausgewählt  `Person ID`ist. **** Je nach Ergebnis des Stitching-Prozesses können Personen höher oder kleiner als  **Unique** Visitors im herkömmlichen Adobe Analytics sein. | **Personen**  = Anzahl der einzelnen  `Person ID`Zeichen basierend auf der Spalte, die als  `Person ID`ausgewählt wurde. **** Die Datensätze von People in Adobe Analytics Connector (ADC) ähneln denen von  **Unique** Visitors im herkömmlichen Adobe Analytics, wenn  `endUserIDs. _experience. aaid.id` wie  `Person ID` in CJA ausgewählt ist. | **Unique Visitors**  = Anzahl unterschiedlicher Besucher-IDs. Beachten Sie, dass **Unique Visitors** möglicherweise nicht mit der Anzahl der eindeutigen **ECID** s übereinstimmt. | Siehe [Personen](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=en). |
| **Sitzungen**: Wird anhand der in der CJA-Datenansicht angegebenen Sitzungseinstellungen definiert. Der Stitching-Prozess kann einzelne Sitzungen von mehreren Geräten zu einer einzelnen Sitzung kombinieren. | **Sitzungen**: Wird anhand der in der CJA-Datenansicht angegebenen Sitzungseinstellungen definiert. | **Besuche**: Siehe  [Besuche](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=en). | **Besuche**: Wird basierend auf den Sitzungseinstellungen definiert, die in der  [Virtual Report Suite](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=en) der geräteübergreifenden Analyse angegeben sind. |
| **Ereignisse**  = Anzahl der Zeilen in den zugeordneten Daten in Customer Journey Analytics. Im Allgemeinen sollte dies im herkömmlichen Adobe Analytics nahe **Vorfälle** sein. Beachten Sie jedoch die oben stehenden häufig gestellten Fragen zu Zeilen mit einem leeren `Persistent ID`. | **Ereignisse**  = Anzahl der Zeilen in den nicht zugeordneten Daten in Customer Journey Analytics. Im Allgemeinen sollte dies im herkömmlichen Adobe Analytics nahe **Vorfälle** sein. Beachten Sie jedoch, dass, wenn Ereignisse in den nicht zugewiesenen Daten im AEP Data Lake ein leeres `Person ID` enthalten, diese Ereignisse in CJA abgelegt (nicht eingeschlossen) werden. | **Vorfälle**: Siehe  [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en). | **Vorfälle**: Siehe  [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en). |

Andere Metriken können in CJA und im herkömmlichen Adobe Analytics ähnlich sein. Beispielsweise sollte die Gesamtanzahl für Adobe Analytics [benutzerdefinierte Ereignisse](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=en) (Ereignisse 1-100) im Allgemeinen in der herkömmlichen Adobe Analytics und CJA sehr nahe liegen (ob zugeordnet oder nicht zugeordnet). Beachten Sie jedoch, dass dies möglicherweise nicht immer zutrifft, da [die Funktionen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-aa.html?lang=en) unterschiedlich sind, z. B. die Deduplizierung zwischen CJA und herkömmlichem Adobe Analytics.
