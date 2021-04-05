---
title: Was ist Dimensionspersistenz in Customer Journey Analytics?
description: Dimension Persistenz ist eine Kombination aus Zuordnung und Ablauf. Gemeinsam bestimmen sie, welche Dimensionswerte beibehalten werden.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
translation-type: tm+mt
source-git-commit: 16e43f5d938ac25445f382e5eba8fc12e0e67161
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 18%

---

# Persistenz

Dimension Persistenz ist eine Kombination aus Zuordnung und Ablauf. Gemeinsam bestimmen sie, welche Dimensionswerte beibehalten werden. Adobe empfiehlt dringend, dass Sie innerhalb Ihres Unternehmens besprechen, wie mehrere Werte für jede Dimension verarbeitet werden (Zuordnung) und wann Dimensionswerte die Speicherung der Daten beenden (Ablauf).

* Standardmäßig verwendet ein Dimensionswert [WAS?] zugeordnet.
* Standardmäßig verwendet ein Dimensionswert einen Ablauf von [!UICONTROL Sitzung].

## Zuordnung

Die Zuordnung wendet eine Transformation auf den zugrunde liegenden Wert an, den Sie verwenden. Zu den unterstützten Zuordnungsmodellen gehören:

* Zuletzt verwendet
* Original
* Alle
* Erste bekannt
* Zuletzt verwendet

### [!UICONTROL Neueste ] Zuweisung

Im Folgenden finden Sie ein Beispiel vor und nach der [!UICONTROL Zuletzt verwendete]-Zuordnung:

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| Originalwerte |  | C | B |  | A |
| Zuletzt verwendete Zuteilung |  | C | B | B | A |

###  Originalzuordnung

Im Folgenden finden Sie ein Beispiel vor und nach der [!UICONTROL Original]-Zuordnung:

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 3 | 2 | 1 | 6 | 7 |
| Originalwerte |  | C | B |  | A |
| Ursprüngliche Zuordnung |  | C | C | C | C |

###  Allzuweisung

Diese neue Dimensionszuordnung kann sowohl auf Array- als auch auf Einzelwertdimensionen angewendet werden. Es funktioniert ähnlich wie das Zuordnungsmodell [!UICONTROL Beitrag] für Metriken. Der Unterschied besteht darin, dass einzelne Werte im Feld an unterschiedlichen Punkten ablaufen können. Nehmen wir an, wir haben 5 Ereignis in einem Zeichenfolgenfeld, wobei die Zuordnung auf &quot;Alle&quot;und der Ablauf auf 5 Minuten eingestellt ist. Wir erwarten folgendes Verhalten:

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| Originalwerte | A | B | C |  | A |
| after-persistence | A | A,B | A,B,C | B,C | A,C |

Beachten Sie, dass der Wert von A so lange erhalten bleibt, bis er die 5-Minuten-Markierung erreicht, während B und C weiterhin bei Treffer 4 bleiben, da für diese Werte noch 5 Minuten vergangen sind. Beachten Sie, dass mit dieser Zuordnung aus einem Feld mit einem Wert eine Dimension mit mehreren Werten erstellt wird. Dieses Modell sollte auch bei Array-basierten Dimensionen unterstützt werden:

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 3 | 2 | 3 | 6 | 7 |
| Originalwerte | A,B | C | B,C |  | A |
| after-persistence | A,B | A,B,C | A,B,C | B,C | A,B,C |

### Zuordnungen von &quot;zuerst bekannt&quot;und &quot;Letzte bekannt&quot;

Diese beiden neuen Zuordnungsmodelle nehmen den ersten oder letzten beobachteten Wert für eine Dimension innerhalb eines bestimmten Persistenzbereichs (Sitzung, Person oder benutzerdefinierter Zeitraum mit Lookback) und wenden ihn auf alle Ereignis im angegebenen Bereich an. Beispiel: 

| Dimension | Treffer 1 | Treffer 2 | Treffer 3 | Treffer 4 | Treffer 5 |
| --- | --- | --- | --- | --- | --- |
| timestamp (min) | 1 | 2 | 3 | 6 | 7 |
| Originalwerte |  | C | B |  | A |
| first known | C | C | C | C | C |
| letzte bekannt | A | A | A | A | A |

Die ersten oder letzten bekannten Werte können nur auf eine Sitzung oder auf den Personensegment (Berichte-Fenster) oder auf einen benutzerdefinierten oder zeitbasierten Bereich angewendet werden (im Wesentlichen auf einen Personensegment mit einem Lookback-Fenster).

## Gültigkeit

[!UICONTROL Mit ] Ablauf können Sie das Persistenzfenster für eine Dimension angeben.

Es gibt vier Möglichkeiten, einen Dimensionswert ablaufen zu lassen:

* Sitzung (Standard): Läuft nach einer bestimmten Sitzung ab.
* Benutzer: ?
* Zeit: Sie können den Dimensionswert so einstellen, dass er nach einem bestimmten Zeitraum oder Ereignis abläuft.
* Metrik: Sie können eine der definierten Metriken als Ablaufdatum für diese Dimension angeben (z. B. eine &quot;Kauf&quot;-Metrik).
* Anpassen:

### Was ist der Unterschied zwischen Zuordnung und Zuordnung?

**Zuordnung**: Denken Sie an die Zuordnung als &quot;Datenumwandlung&quot;der Dimension. Die Zuordnung erfolgt vor dem Filtern. Wenn Sie einen Filter erstellen, wird die transformierte Dimension als Schlüssel verwendet.

**Zuordnung**: Wie verteilt ich die Gutschrift einer Metrik auf die Dimension, auf die sie angewendet wird? Die Zuordnung erfolgt nach dem Filtern.
