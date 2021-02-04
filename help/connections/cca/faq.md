---
title: Häufig gestellte Fragen zur kanalübergreifenden Analyse
description: Häufig gestellte Fragen zur kanalübergreifenden Analyse
translation-type: ht
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: ht
source-wordcount: '460'
ht-degree: 100%

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
