---
title: Was ist Dimensionspersistenz in Customer Journey Analytics?
description: Dimension Persistenz ist eine Kombination aus Zuordnung und Ablauf. Zusammen bestimmen sie, wie oder ob Dimensionswerte von einem Ereignis zum nächsten bestehen.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
translation-type: tm+mt
source-git-commit: ffeada325825545ae0ab43f176e5d301cd1761ee
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 9%

---

# Persistenz

Dimension Persistenz ist eine Kombination aus Zuordnung und Ablauf. Zusammen bestimmen sie, wie oder ob Dimensionswerte von einem Ereignis zum nächsten bestehen. Die Persistenz der Dimension wird für eine Dimension innerhalb der Data-Ansichten konfiguriert und ist rückwirkend und nicht zerstörerisch für die Daten, auf die sie angewendet wird. Die Persistenz der Dimension ist eine sofortige Datenumwandlung, die auf eine Dimension angewendet wird, die vor dem Filtern oder anderen Analysen-Vorgängen in Berichte stattfindet.

* Standardmäßig ist für einen Dimensionswert keine Persistenz aktiviert.
* Wenn ein Zuordnungsmodell für eine Dimension aktiviert ist, wird standardmäßig ein Ablauf von [!UICONTROL Sitzung] verwendet.

## Zuordnung

Die Zuordnung wendet eine Transformation auf den zugrunde liegenden Wert an, den Sie verwenden. Zu den unterstützten Zuordnungsmodellen gehören:

* Zuletzt verwendet
* Original
* Alle

### [!UICONTROL Neueste ] Zuweisung

Die neueste Zuordnung bleibt der letzte in der Dimension vorhandene Wert (nach Zeitstempel). Alle nachfolgenden Werte, die innerhalb derselben Sitzung auftreten, ersetzen den zuvor bestehenden Wert. Beachten Sie, dass leere Werte vor der Anwendung der Persistenz durch &quot;Kein Wert&quot; ersetzt werden, wenn für diese Dimension &quot;Kein Wert behandeln&quot;ausgewählt wurde. Im Folgenden finden Sie ein Beispiel vor und nach der Zuordnung [!UICONTROL Zuletzt verwendete] unter der Annahme, dass eine [!UICONTROL Sitzung] für den Ablauf verwendet wird und alle Ereignis innerhalb einer [!UICONTROL Sitzung] auftreten:

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| Datensatzwerte |  | C | B |  | A |
| Zuletzt verwendete Zuteilung |  | C | B | B | A |

###  Originalzuordnung

Die ursprüngliche Zuordnung behält den ursprünglichen Wert (nach Zeitstempel) bei, der innerhalb der Dimension für einen Ablaufzeitraum vorhanden ist. Im Folgenden finden Sie ein Beispiel vor und nach der [!UICONTROL Original]-Zuordnung:

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| Datensatzwerte |  | C | B |  | A |
| Ursprüngliche Zuordnung |  | C | C | C | C |

###  Allzuweisung

Diese Dimensionszuordnung kann sowohl auf Array- als auch auf Einzelwertdimensionen angewendet werden. Es funktioniert ähnlich wie das Zuordnungsmodell [!UICONTROL Beitrag] für Metriken. Ein wichtiger Unterschied besteht darin, dass Dimensionen mit der Zuordnung &quot;Alle&quot;in Filterdefinitionen verwendet werden können. Angenommen, in einem Zeichenfolgenfeld befinden sich 5 Ereignis, wobei die Zuordnung auf &quot;Alle&quot;und der Ablauf auf 5 Minuten eingestellt ist:

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| Datensatzwerte | A | B | C |  | A |
| after-persistence | A | A,B | A,B,C | A,B,C | A,B,C |

## Gültigkeit

[!UICONTROL Mit ] Ablauf können Sie das Persistenzfenster für eine Dimension angeben.

Es gibt vier Möglichkeiten, einen Dimensionswert ablaufen zu lassen:

* Sitzung (Standard): Läuft nach einer bestimmten Sitzung ab.
* Person: Läuft am Ende des Berichte-Fensters ab.
* Zeit: Sie können den Dimensionswert so einstellen, dass er nach einem bestimmten Zeitraum (bis zu 90 Tagen) abläuft. Diese Ablaufoption ist nur für die Zuordnungsmodelle &quot;Original&quot;und &quot;Zuletzt verwendet&quot;verfügbar. Bei Verwendung der zeitbasierten Ablaufzeit werden Werte vor dem Beginn des Berichte-Fensters (bis zu 90 Tage) berücksichtigt.
* Metrik: Sie können eine der definierten Metriken als Ablaufdatum für diese Dimension angeben (z. B. eine &quot;Kauf&quot;-Metrik). Dieser Ablauf ist nur für die Zuordnungsmodelle &quot;Original&quot;und &quot;Zuletzt verwendet&quot;verfügbar.

### Was ist der Unterschied zwischen Zuordnung und Zuordnung?

**Zuordnung**: Denken Sie an die Zuordnung als Datenumwandlung zur Dimension. Die Zuordnung erfolgt vor dem Filtern. Wenn Sie einen Filter erstellen, wird die transformierte Dimension als Schlüssel verwendet.

**Zuordnung**: Wie verteilt ich die Gutschrift einer Metrik auf die Dimension, auf die sie angewendet wird? Die Zuordnung ist keine Datenumwandlung, wird während der Datenaggregation angewendet und hat keinen Einfluss darauf, welche Daten mithilfe eines Filters eingeschlossen werden.
