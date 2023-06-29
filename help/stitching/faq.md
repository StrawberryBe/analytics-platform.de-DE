---
title: Häufig gestellte Fragen zur Zuordnung
description: Häufig gestellte Fragen zum Stitching
solution: Customer Journey Analytics
feature: Stitching
source-git-commit: 34566535589c84c96a8d7a47988cd155b743674e
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 35%

---

# Häufig gestellte Fragen

Im Folgenden finden Sie einige häufig gestellte Fragen zum Stitching:

+++**Wie kann ich das Stitching verwenden, um zu sehen, wie Benutzer von einem Kanal zum anderen wechseln?**

Sie können eine Flussvisualisierung mit der Dimension „Datensatz-ID“ verwenden.

1. Anmelden bei [Customer Journey Analytics](https://analytics.adobe.com) und erstellen Sie ein leeres Workspace-Projekt.
2. Wählen Sie die **[!UICONTROL ** Visualisierungen **]** auf der linken Seite ein und ziehen Sie eine **[!UICONTROL ** Fluss **]** Visualisierung zur Arbeitsfläche auf der rechten Seite.
3. Wählen Sie die **[!UICONTROL ** Komponenten **]** auf der linken Seite ein und ziehen Sie die Dimension **[!UICONTROL ** Datensatz-ID **]** zum zentralen Ort mit der Bezeichnung **[!UICONTROL ** Dimension oder Element **]**.
4. Dieser Flussbericht ist interaktiv. Um die Flüsse auf nachfolgende oder vorherige Seiten zu erweitern, wählen Sie einen der Werte aus. Verwenden Sie das Kontextmenü, um Spalten zu erweitern oder zu reduzieren. Im selben Flussbericht können auch verschiedene Dimensionen verwendet werden.

Wenn Sie die Datensatz-ID-Dimensionselemente umbenennen möchten, können Sie einen Lookup-Datensatz verwenden.

+++

+++**Wie weit reicht die Zuordnung von wiedergegebenen Besuchern zurück?**

Das Lookback-Fenster für die Neuzuweisung hängt von der gewünschten Häufigkeit der [Wiederholung](explained.md) der Daten ab. Wenn Sie beispielsweise die Zuordnung so einrichten, dass Daten einmal wöchentlich wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung sieben Tage. Wenn Sie die Zuordnung so einrichten, dass Daten täglich wiederholt werden, beträgt das Lookback-Fenster für die Neuzuweisung einen Tag.

+++

+++**Wie werden freigegebene Geräte gehandhabt?**

In einigen Situationen ist es möglich, dass sich mehrere Personen von demselben Gerät aus anmelden. Beispiele dafür sind freigegebene Geräte zu Hause, freigegebene PCs in einer Bibliothek oder ein Terminal in einem Einzelhandelsgeschäft.

Die vorübergehende ID setzt die beständige ID außer Kraft, sodass freigegebene Geräte als separate Personen betrachtet werden (auch wenn sie von demselben Gerät stammen).

+++

+++**Wie behandelt das Stitching Situationen, in denen eine einzelne Person über viele beständige IDs verfügt?**

In einigen Fällen kann eine einzelne benutzende Person mit mehreren beständigen IDs verknüpft sein. Ein Beispiel ist eine Person, die häufig die Cookies des Browsers löscht oder den privaten/Inkognito-Modus des Browsers verwendet.

Die Anzahl der beständigen IDs ist für die vorübergehende ID irrelevant. Ein einzelner Benutzer kann zu einer beliebigen Anzahl von Geräten gehören, ohne die Fähigkeit von Customer Journey Analytics zu beeinträchtigen, Geräte zuzuordnen.

+++

+++**Wie lange dauert es, bis der neu zugewiesene Datensatz verfügbar wird, nachdem ich mein Adobe-Kontoteam mit den gewünschten Informationen kontaktiert habe?**

Die Echtzeit-Zuordnung ist ca. eine Woche nach der Adobe verfügbar, die das Stitching ermöglicht. Die Verfügbarkeit der Aufstockung hängt von der Menge der vorhandenen Daten ab. Bei kleinen Datensätzen (weniger als 1 Million Ereignisse pro Tag) dauert es in der Regel einige Tage, während große Datensätze (1 Milliarde Ereignisse pro Tag) eine Woche oder länger benötigen können.

+++

+++**Was ist der Unterschied zwischen geräteübergreifender Analyse (eine Funktion in herkömmlichem Analytics) und kanalübergreifender Analyse?**

[Geräteübergreifende Analyse](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) ist eine Funktion, die speziell für den herkömmlichen Adobe Analytics entwickelt wurde und Ihnen hilft, zu verstehen, wie Benutzer geräteübergreifend arbeiten. Sie bietet zwei Workflows zum Verknüpfen von Gerätedaten: die feldbasierte Zuordnung und das Gerätediagramm.

Die kanalübergreifende Analyse ist ein für Customer Journey Analytics spezifisches Anwendungsbeispiel, in dem Sie verstehen können, wie Benutzer auf Geräten und Kanälen arbeiten. Er ordnet die Personen-ID eines Datensatzes zu, sodass dieser Datensatz nahtlos mit anderen Datensätzen kombiniert werden kann. Diese Funktion funktioniert im Design ähnlich wie die geräteübergreifende feldbasierte Zuordnung für Analysen, aber die Implementierung unterscheidet sich aufgrund der unterschiedlichen Datenarchitektur zwischen herkömmlichem Analytics und Customer Journey Analytics. Siehe [Stitching](overview.md) und [Cross-Channel-Analyse](../use-cases/cross-channel/cross-channel.md) Anwendungsbeispiel für weitere Informationen.

+++**Wie verarbeitet die Zuordnung DSGVO- und CCPA-Anfragen?**

Adobe verarbeitet DSGVO- und CCPA-Anfragen gemäß den nationalen und internationalen Rechtsvorschriften. Adobe bietet den [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=de) für Datenzugriffs- und Löschanfragen. Die Anfragen gelten sowohl für die ursprünglichen als auch die neu zugewiesenen Datensätze.

+++

+++**Was passiert, wenn das Feld „Persistent ID“ in einem oder mehreren Ereignissen leer ist?**

Wenn das Feld &quot;Persistente ID&quot;bei einem Ereignis in einem Datensatz, der zugeordnet wird, leer ist, wird die zugeordnete ID für dieses Ereignis auf zwei Arten ermittelt:

* Wenn das Feld für die Übergangs-ID nicht leer ist, verwendet Customer Journey Analytics den Wert in der Übergangs-ID als zugeordnete ID.
* Wenn das Feld für die Verlaufs-ID leer ist, bleibt in Customer Journey Analytics auch die zugeordnete ID leer. In diesem Fall sind die beständige ID, die vorübergehende ID und die zugeordnete ID im Ereignis leer. Diese Ereignistypen werden aus jeder Customer Journey Analytics-Verbindung mit dem Datensatz, der zugeordnet wird, entfernt, wobei die zugeordnete ID als Personen-ID ausgewählt wurde.

+++

+++**Wie vergleichen sich Metriken in Customer Journey Analytics-zugeordneten Datensätzen mit ähnlichen Metriken in nicht zugeordneten Datensätzen in Customer Journey Analytics und mit Adobe Analytics?**

Bestimmte Metriken in Customer Journey Analytics ähneln den Metriken in herkömmlichem Analytics, andere unterscheiden sich jedoch je nach dem, was Sie vergleichen. In der folgenden Tabelle werden verschiedene häufig verwendete Metriken verglichen:

| **Vom Customer Journey Analytics zugeordnete Daten** | **Aufgepasste Daten vom Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate mit CDA** |
| ----- | ----- | ----- | ----- |
| **Personen** = Zählung unterschiedlicher Personen-IDs, bei denen die zugeordnete ID als Personen-ID ausgewählt wird. Je nach Ergebnis des Zuordnungsprozesses kann **Personen** größer oder kleiner als **Unique Visitors** im herkömmlichen Adobe Analytics sein. | **Personen** = Zählung unterschiedlicher Personen-IDs basierend auf der Spalte, die als Personen-ID ausgewählt wurde. **Personen** in Adobe Source Connector-Datensätzen ähnelt **Unique Visitors** im traditionellen Adobe Analytics `endUserIDs._experience.aaid.id` wird als Personen-ID in Customer Journey Analytics verwendet. | **Unique Visitors** = Anzahl unterschiedlicher Besucher-IDs. **Unique Visitors** ist möglicherweise nicht identisch mit der Anzahl der eindeutigen **ECID** s. | Siehe [Personen](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=de). |
| **Sitzungen**: Wird basierend auf den Sitzungseinstellungen in der Datenansicht des Customer Journey Analytics definiert. Der Zuordnungsprozess kann einzelne Sitzungen von mehreren Geräten zu einer einzelnen Sitzung kombinieren. | **Sitzungen**: Definiert anhand der Sitzungseinstellungen, die in der Datenansicht des Customer Journey Analytics angegeben sind. | **Besuche**: Siehe [Besuche](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=de). | **Besuche**: Wird basierend auf den Sitzungseinstellungen definiert, die in der [Virtual Report Suite von CDA](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=de) angegeben sind. |
| **Veranstaltungen** = Anzahl der Zeilen in den zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch die oben stehenden häufig gestellten Fragen zu Zeilen mit einer leeren beständigen ID. | **Veranstaltungen** = Anzahl der Zeilen in den nicht zugeordneten Daten in Customer Journey Analytics. Diese Metrik liegt normalerweise nahe bei **Vorfälle** im herkömmlichen Adobe Analytics. Beachten Sie jedoch, dass, wenn Ereignisse in den nicht zugewiesenen Daten im Experience Platform Data Lake eine leere Personen-ID enthalten, diese Ereignisse nicht in Customer Journey Analytics enthalten sind. | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). | **Vorfälle**: Siehe [Vorfälle](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=de). |

Andere Metriken können in Customer Journey Analytics und Adobe Analytics ähnlich sein. Beispielsweise die Gesamtzahl für Adobe Analytics [benutzerspezifische Ereignisse](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=de) 1-100 ist zwischen dem traditionellen Adobe Analytics und dem Customer Journey Analytics vergleichbar (ob zugeordnet oder nicht zugeordnet). [Funktionsunterschiede](/help/getting-started/aa-vs-cja/cja-aa.md)), z. B. die Deduplizierung zwischen Customer Journey Analytics und Adobe Analytics, kann zu Diskrepanzen zwischen den beiden Produkten führen.

+++

+++**Kann Customer Journey Analytics Identity Map-Felder verwenden?**

Nein, Customer Journey Analytics können derzeit keine Identity Map-Felder zum Stitching verwenden.

+++
