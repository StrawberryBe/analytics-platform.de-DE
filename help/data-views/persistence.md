---
title: Was ist Dimensionspersistenz in Customer Journey Analytics?
description: Die Dimensionspersistenz ist eine Kombination aus Zuordnung und Ablauf. Zusammengenommen bestimmen sie, wie oder ob Dimensionswerte von einem Ereignis zum nächsten bestehen bleiben.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
source-git-commit: ab81c7fff2b7e942491fd417cfa115dd428f222d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 84%

---

# Persistenz

Die Dimensionspersistenz ist eine Kombination aus Zuordnung und Ablauf. Zusammengenommen bestimmen sie, wie oder ob Dimensionswerte von einem Ereignis zum nächsten bestehen bleiben. Die Dimensionspersistenz wird für eine Dimension innerhalb der Datenansichten konfiguriert. Sie ist rückwirkend und nicht zerstörerisch für die Daten, auf die sie angewendet wird. Die Dimensionspersistenz ist eine sofortige Datenumwandlung, die auf eine Dimension angewendet wird und vor dem Filtern oder anderen Analysevorgängen im Reporting stattfindet.

* Standardmäßig ist für einen Dimensionswert keine Persistenz aktiviert.
* Wenn ein Zuordnungsmodell für eine Dimension aktiviert ist, wird standardmäßig ein Ablaufdatum der [!UICONTROL Sitzung] verwendet.

## Zuordnung

Die Zuordnung wendet eine Umwandlung auf den zugrunde liegenden Wert an, den Sie verwenden. Die unterstützten Zuordnungsmodelle umfassen:

* Zuletzt verwendet
* Original
* Alle

### [!UICONTROL Zuletzt verwendete] Zuordnung

Die neueste Zuordnung behält den neuesten (nach Zeitstempel) Wert bei, der in der Dimension vorhanden ist. Alle nachfolgenden Werte, die innerhalb derselben Sitzung auftreten, ersetzen den zuvor beibehaltenen Wert. Beachten Sie, dass, wenn für diese Dimension &quot;Kein Wert behandeln&quot;ausgewählt wurde, die leeren Werte durch &quot;Kein Wert&quot;ersetzt werden, bevor die Persistenz angewendet wird. Im Folgenden finden Sie ein Beispiel vor und nach der [!UICONTROL zuletzt verwendeten] Zuordnung unter der Annahme, dass für den Ablauf eine [!UICONTROL Sitzung] verwendet wird und alle Ereignisse innerhalb ein und derselben [!UICONTROL Sitzung] auftreten:

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| Datensatzwerte |  | C | B |  | A |
| Zuletzt verwendete Zuordnung |  | C | B | B | A |

### [!UICONTROL Originale] Zuordnung

Die ursprüngliche Zuordnung behält den ursprünglichen Wert (nach Zeitstempel) bei, der innerhalb der Dimension für einen Ablaufzeitraum vorhanden ist. Im Folgenden finden Sie ein Beispiel vor und nach der [!UICONTROL originalen] Zuordnung:

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| Datensatzwerte |  | C | B |  | A |
| Originale Zuordnung |  | C | C | C | C |

### Zuordnung [!UICONTROL Alle]

Diese Dimensionszuordnung kann sowohl auf Array-basierte als auch auf Einzelwertdimensionen angewendet werden. Es funktioniert ähnlich wie das Zuordnungsmodell [!UICONTROL Teilnahme] für Metriken. Ein wichtiger Unterschied besteht darin, dass Dimensionen mit der Zuordnung „Alle“ in Filterdefinitionen verwendet werden können. Angenommen, in einem Zeichenfolgenfeld befinden sich 5 Ereignisse, wobei die Zuordnung auf „Alle“ und die Gültigkeitsdauer auf 5 Minuten eingestellt ist:

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| Datensatzwerte | A | B | C |  | A |
| after-persistence | A | A,B | A,B,C | A,B,C | A,B,C |

## Gültigkeit

[!UICONTROL Gültigkeit] ermöglicht, die Persistenzdauer für eine Dimension anzugeben.

Es gibt vier Möglichkeiten, einen Dimensionswert ablaufen zu lassen:

* Sitzung (Standard): Läuft nach einer bestimmten Sitzung ab.
* Person: Läuft am Ende des Reporting-Fensters ab.
* Zeit: Sie können den Wert der Dimension so einstellen, dass er nach einem bestimmten Zeitraum (bis zu 90 Tage) abläuft. Diese Ablaufoption ist nur für die Zuordnungsmodelle „Original“ und „Zuletzt verwendet“ verfügbar. Bei Verwendung der zeitbasierten Gültigkeit werden Werte berücksichtigt, die vor dem Beginn des Berichtsfensters (bis zu 90 Tage) liegen.
* Metrik: ermöglicht Ihnen, eine der definierten Metriken als Ablaufdatum für diese Dimension anzugeben (z. B. eine Kaufmetrik). Diese Art des Ablaufens ist nur für die Zuordnungsmodelle „Original“ und „Zuletzt verwendet“ verfügbar.

### Was ist der Unterschied zwischen Zuordnung und Attribution?

**Zuordnung**: Stellen Sie sich eine Zuordnung als eine Datenumwandlung zur Dimension vor. Die Zuordnung erfolgt vor dem Filtern. Wenn Sie einen Filter erstellen, wird die umgewandelte Dimension als Schlüssel verwendet.

**Attribution**: Wie verteile ich die Gutschrift einer Metrik auf die Dimension, auf die sie angewendet wird? Die Attribution ist keine Datenumwandlung, sie wird während der Datenaggregation angewendet und hat keinen Einfluss darauf, welche Daten mithilfe eines Filters eingeschlossen werden.
