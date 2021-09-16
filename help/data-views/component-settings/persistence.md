---
title: Einstellungen der Persistenz-Komponente
description: Bestimmen Sie, wie oder ob Dimensionswerte von einem Ereignis zum nächsten beibehalten werden.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 23%

---


# Einstellungen der Persistenz-Komponente

Persistenz ist die Fähigkeit eines bestimmten Dimensionswerts, sich mit einer Metrik über das Ereignis hinaus zu beziehen, für das sie festgelegt wurde. Es wird eine Kombination aus Zuordnung und Gültigkeit verwendet.

* **** Mit der Zuordnung können Sie festlegen, welcher Wert beibehalten wird, wenn mehrere Dimensionselemente gleichzeitig in einer Spalte beibehalten werden können.
* **** Mit Ablauf können Sie festlegen, wie lange ein Dimensionselement über das Ereignis hinaus bestehen bleibt, für das es festgelegt ist.

Persistenz ist nur für Dimensionen verfügbar und rückwirkend für die Daten, auf die sie angewendet wird. Es handelt sich um eine sofortige Datenumwandlung, die vor der Anwendung von Filtern oder anderen Analysevorgängen erfolgt.

![Persistenz](../assets/persistence.png)

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Persistenz festlegen] | Aktivieren Sie die Persistenz für die Dimension. Wenn die Persistenz nicht aktiviert ist, bezieht sich die Dimension nur auf Metriken, die im selben Ereignis vorhanden sind. Diese Einstellung ist standardmäßig aktiviert. |
| [!UICONTROL Zuordnung] | Hier können Sie das Zuordnungsmodell angeben, das für eine Dimension für Persistenz verwendet wird. Die Optionen sind: [!UICONTROL Zuletzt verwendet], [!UICONTROL Original], [!UICONTROL Instanz], [!UICONTROL Alle]. |
| [!UICONTROL Ablauf] | Hier können Sie das Persistenzfenster für eine Dimension angeben. Optionen sind: [!UICONTROL Sitzung] (Standard), [!UICONTROL Person], [!UICONTROL Benutzerdefinierte Zeit], [!UICONTROL Metrik]. Möglicherweise brauchen Sie die Option, dass die Dimension bei einem Kauf ablaufen soll (z. B. interne Suchbegriffe oder andere Merchandising-Verwendungsfälle). Die maximale Ablaufzeit beträgt 90 Tage. Wenn Sie eine Zuordnung von [!UICONTROL Alle] auswählen, ist nur die Gültigkeit [!UICONTROL Sitzung] oder [!UICONTROL Person] verfügbar. |

## Zuordnungseinstellungen

Details zu den verfügbaren Zuordnungseinstellungen.

* **Zuletzt verwendet**: behält den aktuellsten (nach Zeitstempel) Wert bei, der in der Dimension vorhanden ist. Alle nachfolgenden Werte, die innerhalb des Ablaufzeitraums der Dimension auftreten, ersetzen den zuvor beibehaltenen Wert. Wenn &quot;Kein Wert als Wert behandeln&quot;für diese Dimension unter [Keine Wertoptionen](no-value-options.md) aktiviert ist, überschreiben leere Werte zuvor persistente Werte. Betrachten Sie beispielsweise die folgende Tabelle mit der Zuordnung [!UICONTROL Zuletzt verwendete] und dem Ablauf [!UICONTROL Sitzung] :

   | Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
   | --- | --- | --- | --- | --- | --- |
   | Datensatzwerte |  | C | B |  | A |
   | Zuletzt verwendete Zuordnung |  | C | B | B | A |

* **Original**: Behält den ursprünglichen Wert nach Zeitstempel bei, der innerhalb der Dimension für die Dauer des Ablaufzeitraums vorhanden ist. Wenn diese Dimension einen Wert hat, wird sie nicht überschrieben, wenn bei einem nachfolgenden Ereignis ein anderer Wert angezeigt wird. Betrachten Sie beispielsweise die folgende Tabelle mit der Zuordnung [!UICONTROL Original] und dem Ablauf [!UICONTROL Sitzung]:

   | Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
   | --- | --- | --- | --- | --- | --- |
   | Datensatzwerte |  | C | B |  | A |
   | Originale Zuordnung |  | C | C | C | C |

* **Alle**: Funktioniert ähnlich wie das   Beitragsattributionsmodell für Metriken. Behält alle Werte gleich bei, damit jeder Wert in der Berichterstellung vollständig für die Metrik angerechnet wird. Betrachten Sie beispielsweise die folgende Tabelle mit der Zuordnung [!UICONTROL Alle] und dem Ablauf [!UICONTROL Sitzung]:

   | Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
   | --- | --- | --- | --- | --- | --- |
   | Datensatzwerte | A | B | C |  | A |
   | Zuordnung Alle | A | A,B | A,B,C | A,B,C | A,B,C |

## Gültigkeit Einstellungen

Details zu den verfügbaren Ablaufeinstellungen.

* **Sitzung**: Läuft nach einer bestimmten Sitzung ab. Standardgültigkeitsfenster.
* **Person**: Läuft am Ende des Berichtsfensters ab.
* **Zeit**: Sie können den Dimensionswert so einstellen, dass er nach einem bestimmten Zeitraum (bis zu 90 Tage) abläuft. Diese Ablaufoption ist nur für die Zuordnungsmodelle „Original“ und „Zuletzt verwendet“ verfügbar. Bei Verwendung der zeitbasierten Gültigkeit werden Werte berücksichtigt, die vor dem Beginn des Berichtsfensters (bis zu 90 Tage) liegen.
* **Metrik**: Wenn diese Metrik in einem Treffer angezeigt wird, laufen Sie den beibehaltenen Wert in der Dimension sofort ab. Sie können jede beliebige Metrik als Ablaufende für diese Dimension verwenden. Diese Ablaufoption ist nur für die Zuordnungseinstellungen Original und Zuletzt verwendet verfügbar.
