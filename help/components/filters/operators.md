---
title: Filteroperatoren
description: Bestimmen Sie, wie eine Komponente mit einem Wert in einem Filter interagiert.
source-git-commit: 1334e1edb36583ba978936fecbff2657e63a94bf
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 20%

---

# Filteroperatoren

Mit dem Filter-Builder können Sie Werte mithilfe ausgewählter Operatoren vergleichen und beschränken. Es gibt zwei Kategorien von Benutzern: [!UICONTROL Standard] und [!UICONTROL Distinct Count].

## Standardoperatoren

| Operator | Beschreibung |
| gleich | Gibt Elemente zurück, die exakt mit einem numerischen oder Zeichenfolgenwert übereinstimmen. Verwenden Sie bei Verwendung von Platzhalterzeichen den Operator &quot;stimmt überein mit&quot;. |
| ist nicht gleich | Gibt alle Elemente zurück, die nicht die exakte Übereinstimmung mit dem eingegebenen Wert enthalten.  Verwenden Sie bei Verwendung von Platzhalterzeichen den Operator &quot;stimmt nicht überein mit&quot;. |
| enthält | Gibt Elemente zurück, die mit den Unterzeichenfolgen der eingegebenen Werte vergleichbar sind. Wenn die Regel für eine Zeichenfolgendimension beispielsweise `"Search"` enthält, stimmt sie mit allen Seiten überein, die die Unterzeichenfolge `"Search"` enthalten, einschließlich `"Search Results"`, `"Search"` und `"Searching"`. Bei diesem Operator wird zwischen Groß- und Kleinschreibung unterschieden. |
| enthält nicht | Alle Elemente, die dem eingegebenen Wert entsprechen, werden aus den Ergebnissen ausgeschlossen. Wenn die Regel für eine Zeichenfolgendimension beispielsweise `"Search"` nicht enthält, werden alle Seiten ausgeschlossen, die die Unterzeichenfolge `"Search"` enthalten, einschließlich `"Search Results"`, `"Search"` und `"Searching"`. |
| enthält alle von | Gibt Elemente zurück, die alle Unterzeichenfolgen (durch ein Leerzeichen getrennt) in beliebiger Reihenfolge enthalten. Wenn Sie beispielsweise `"Search Results"` mit diesem Operator eingeben, stimmen `"Search Results"` und `"Results of Search"` überein, jedoch nicht `"Search"` oder `"Results"` unabhängig voneinander. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| enthält nicht alle von | Alle Elemente, die jedem eingegebenen Wert entsprechen, werden aus den Ergebnissen ausgeschlossen. Wenn Sie beispielsweise `"Search Results"` mit diesem Operator eingeben, werden `"Search Results"` und `"Results of Search"` ausgeschlossen, jedoch nicht `"Search"` oder `"Results"`. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| enthält beliebige von | Gibt Elemente zurück, die eines der angegebenen Unterzeichenfolgen enthalten. Wenn Sie beispielsweise `"Search Results"` mit diesem Operator eingeben, stimmen `"Search Results"`, `"Results of Search"`, `"Search"` und `"Results"` überein. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| enthält keinerlei von | Alle Elemente, die mit einer Unterzeichenfolge übereinstimmen, werden aus den Ergebnissen ausgeschlossen. Wenn Sie beispielsweise `"Search Results"` eingeben, werden `"Search Results"`, `"Results of Search"`, `"Search"` und `"Results"` ausgeschlossen. Dieser Operator unterstützt bis zu 100 durch Leerzeichen getrennte Wörter. |
| beginnt mit | Gibt Elemente zurück, die mit dem Zeichen oder der Zeichenfolge des eingegebenen Werts beginnen. |
| beginnt nicht mit | Gibt alle Elemente zurück, die nicht mit den Zeichen oder Zeichenfolgen der eingegebenen Werte beginnen. |
| endet mit | Gibt Elemente zurück, die mit dem Zeichen oder der Zeichenfolge des eingegebenen Werts enden. |
| endet nicht mit | Gibt alle Elemente zurück, die nicht mit den Zeichen oder Zeichenfolgen des eingegebenen Werts enden. |
| Übereinstimmungen | Gibt Elemente zurück, die genau auf Basis eines angegebenen numerischen oder Zeichenfolgenwerts übereinstimmen. Unterstützt Platzhalter mit einem Sternchen (`*`). Bei diesem Operator wird zwischen Groß- und Kleinschreibung unterschieden. Beispiel:<ul><li>`a*e` stimmt überein mit  `ae`,  `abcde`,  `adobe` und  `a whole sentence`.</li><li>`adob*` Treffer  `adobe`,  `adobe analytics`und  `adobo recipe`</li><li>`*dobe` stimmt überein mit  `dobe`,  `adobe` und  `cute little dobe`.</li></ul>|
| stimmt nicht überein mit | Alle Elemente, die mit der Zeichenfolge übereinstimmen, werden ausgeschlossen. Unterstützt Platzhalter mit einem Sternchen (`*`). |
| vorhanden | Gibt Elemente zurück, wenn der Wert nicht null ist. |
| existiert nicht | Gibt Elemente zurück, wenn der Wert null ist. |

## Distinct Count-Operatoren

Sie können nach einer bestimmten Anzahl von Elementen innerhalb einer Dimension segmentieren. Sie können beispielsweise Filter für Besucher erstellen, die mehr als 5 verschiedene Produkte oder Besuche angesehen haben, bei denen mehr als 5 verschiedene Seiten angezeigt wurden.

| Operator | Beschreibung |
| --- | --- |
| gleich | Gibt Dimensionselemente zurück, deren eindeutige Anzahl dem eingegebenen Wert entspricht. |
| ist nicht gleich | Gibt Dimensionselemente zurück, deren eindeutige Anzahl nicht dem eingegebenen Wert entspricht. |
| größer als | Gibt Dimensionselemente zurück, deren eindeutige Anzahl größer als der eingegebene Wert ist. |
| kleiner als | Gibt Dimensionselemente zurück, deren eindeutige Anzahl kleiner als der eingegebene Wert ist. |
| größer als oder gleich | Gibt Dimensionselemente zurück, deren eindeutige Anzahl größer als der eingegebene Wert ist oder damit übereinstimmt. |
| kleiner als oder gleich | Gibt Dimensionselemente zurück, deren eindeutige Anzahl kleiner als der eingegebene Wert ist oder damit übereinstimmt. |
