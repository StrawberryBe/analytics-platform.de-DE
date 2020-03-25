---
title: Referenz - erweiterte Funktionen
description: Greifen Sie auf diese Funktionen zu, indem Sie in der Dropdown-Liste Funktionen die Option „Erweitert anzeigen“ wählen.
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Referenz - erweiterte Funktionen

Access these functions by checking **[!UICONTROL Show Advanced]** in the **[!UICONTROL Functions]** drop-down list.

## Vergleich zwischen Tabellenfunktionen und Zeilenfunktionen

Eine Tabellenfunktion ist eine Funktion, bei der die Ausgabe für jede Tabellenzeile gleich ist. Bei einer Zeilenfunktion ist die Ausgabe für jede Tabellenzeile unterschiedlich.

## Was bedeutet der Parameter „Include-Zeros“? 

Er sagt, ob Nullen in die Berechnung einbezogen werden sollen. Manchmal bedeutet Null &quot;nichts&quot;, aber manchmal ist es wichtig.

Wenn Sie z. B. eine Umsatzmetrik haben und dem Bericht dann eine Metrik für die Ansichten der Seite hinzufügen, gibt es plötzlich mehr Zeilen für Ihren Umsatz, die alle null sind. Dies soll sich sicherlich nicht auf Berechnungen für arithmetisches Mittel, Minimum, Quartil usw. Berechnungen, die Sie für die Umsatzspalte haben. In diesem Fall würden Sie den Parameter include-zeros überprüfen.

Wenn Sie hingegen zwei Metriken haben, die Sie interessieren, ist es möglicherweise nicht fair zu sagen, dass eine Metrik einen höheren Durchschnitt oder einen höheren Mindestwert hat, weil einige ihrer Zeilen Nullen waren. Daher würden Sie den Parameter nicht auf Nullen überprüfen.

## UND

Gibt den Wert des Arguments zurück. Verwenden Sie NOT, um sicherzustellen, dass ein Wert nicht mit einem bestimmten Wert übereinstimmt.

> [!NOTE] 0 (null) bedeutet „Falsch“ und jeder andere Wert „Wahr“.

```
AND(logical_test1,[logical_test2],...)
```

| Argument | Beschreibung |
|---|---|
| *logical_test1* | Erforderlich. Wert, der als TRUE oder FALSE bestimmt werden kann. |
| *logical_test2* | Optional. Zusätzliche Bedingungen, die Sie als TRUE oder FALSE auswerten möchten |

## Ungefährer Distinct Count (Dimension)

Gibt den ungefähren Distinct Count für die Elemente der ausgewählten Dimension zurück. Diese Funktion verwendet die HyperLogLog (HLL)-Methode zur ungefähren Bestimmung des Distinct Count.  Sie ist entsprechend eingestellt, um zu garantieren, dass der Wert zu 95 % der Zeit 5 % des tatsächlichen Werts beträgt.

```
Approximate Count Distinct (dimension)
```

| Argument |  |
|---|---|
| *Dimension* | Die Dimension, für die Sie die ungefähre Elementanzahl ermitteln möchten. |

## Beispielanwendungsfall 

Ungefährer Distinct Count (Kunden-ID-eVar) ist ein typischer Anwendungsfall für diese Funktion.

Definition für eine neue berechnete „Ungefähre Kunden“-Metrik:

![](assets/approx-count-distinct.png)

So könnte die „Ungefähre Kunden“-Metrik für Berichte verwendet werden:

![](assets/approx-customers.png)

## Individuelle Werte überschritten 

Wie Count() und RowCount() unterliegt auch &quot;Ungefährer Zähler Distinct()&quot;den Beschränkungen [für](https://marketing.adobe.com/resources/help/en_US/reference/metrics_uniques_high_numbers.html)&quot;Eindeutige Werte überschritten&quot;. Wenn die Grenze &quot;Individuelle Werte überschritten&quot;innerhalb eines bestimmten Monats für eine Dimension erreicht wird, wird der Wert als 1 Dimensionselement gezählt.

## Vergleich von Count-Funktionen 

Approximate Count Distinct() ist eine Verbesserung gegenüber den Funktionen Count() und RowCount(), da die erstellte Metrik in jedem Dimensionsbericht verwendet werden kann, um eine ungefähre Anzahl von Elementen für eine separate Dimension zu rendern. Beispiel: Anzahl der Kunden-IDs, die in einem Mobilgerätetypbericht verwendet werden.

Diese Funktion ist geringfügig weniger genau als Count() und RowCount(), da sie die HLL-Methode verwendet, während Count() und RowCount() exakte Zählungen sind.

## Arkuskosinus (Zeile)

Gibt den Arkuskosinus (oder umgekehrten Kosinus) einer Metrik zurück. Der Arkuskosinus ist der Winkel, dessen Kosinus „Zahl“ ist. Der Ergebniswinkel wird im Bogenmaß (Radiant) im Wertebereich von 0 (Null) bis pi (Pi) angegeben. Möchten Sie ein Ergebnis aus dem Bogenmaß (Radiant) in Grad umrechnen, müssen Sie es mit 180/PI( ) multiplizieren.

```
ACOS(metric)
```

| Argument |  |
|---|---|
| *Metrik* | Der Kosinus des gewünschten Winkels von -1 bis 1. |

## Arkussinus (Zeile)

Gibt den Arkussinus oder auch umgekehrten Sinus einer Zahl zurück. Der Arkussinus ist der Winkel, dessen Sinus „Zahl“ ist. Der als Ergebnis zurückgegebene Winkel wird im Bogenmaß (Radiant) mit einem Wert zwischen -pi/2 und pi/2 ausgegeben. Soll ein Arkussinus in Grad ausgedrückt werden, müssen Sie das jeweilige Ergebnis mit 180/PI( ) multiplizieren.

```
ASIN(metric) 
```

| Argument |  |
|---|---|
| *Metrik* | Der Kosinus des gewünschten Winkels von -1 bis 1. |

## Arkustangens (Zeile)

Gibt den Arkustangens oder auch umgekehrten Tangens einer Zahl zurück. Der Arkustangens ist der Winkel, dessen Tangens „Zahl“ ist. Der als Ergebnis zurückgegebene Winkel wird im Bogenmaß (Radiant) mit einem Wert zwischen -pi/2 und pi/2 ausgegeben. Soll ein Arkustangens in Grad ausgedrückt werden, müssen Sie das jeweilige Ergebnis mit 180/PI( ) multiplizieren.

```
ATAN(metric)
```

| Argument |  |
|---|---|
| *Metrik* | Der Kosinus des gewünschten Winkels von -1 bis 1. |

## Exponentielle Regression: Vorhersage für Y (Zeile)

Berechnet die prognostizierten y-Werte (metric_Y) anhand der bekannten x-Werte (metric_X) mittels der Methode der kleinsten Quadrate für die Berechnung der Ausgleichsgeraden basierend auf .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Cdf-T

Gibt den Prozentsatz von Werten in studentischer t-Verteilung mit n Freiheitsgraden zurück, die einen z-Wert unter x aufweisen.

```
cdf_t( -∞, n ) = 0 
cdf_t(  ∞, n ) = 1 
cdf_t( 3, 5 ) ? 0.99865 
cdf_t( -2, 7 ) ? 0.0227501 
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Gibt den Prozentsatz von Werten in einer normalen Verteilung zurück, die einen z-Wert unter x aufweisen.

```
cdf_z( -∞ ) = 0 
cdf_z( ∞ ) = 1 
cdf_z( 0 ) = 0.5 
cdf_z( 2 ) ? 0.97725 
cdf_z( -3 ) ? 0.0013499 
 
```

## Nächsthöhere ganze Zahl (Ceiling) (Zeile)

Gibt die kleinste Ganzzahl zurück, die nicht kleiner als ein angegebener Wert ist. Beispiel: Wenn Sie keine Währungsdezimalzahlen für den Umsatz in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel CEILING(*Umsatz*) den Umsatz bis zum nächsten Dollar aufrunden (in diesem Fall 570 US-Dollar).

```
CEILING(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die Metrik, die gerundet werden soll. |

## Kosinus (Zeile)

Gibt den Kosinus eines Winkels zurück. Liegt der Winkel im Gradmaß vor, müssen Sie ihn durch Multiplizieren mit PI( )/180 in das Bogenmaß umwandeln.

```
COS(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Der Winkel in Radiant, dessen Kosinus gewünscht ist. |

## Kubikwurzel

Gibt die positive Kubikwurzel einer Zahl zurück. Die Kubikwurzel einer Zahl ist der Wert dieser Zahl hoch 1/3.

```
CBRT(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die Metrik, deren Kubikwurzel gewünscht ist. |

## Zusammengefasst

Gibt die Summe von x für die letzten N Zeilen zurück (entsprechend der Reihenfolge der Dimension unter Verwendung von Hashwerten für zeichenfolgenbasierte Felder).

Wenn N &lt;= 0, werden alle vorherigen Zeilen verwendet. Da sie nach der Dimension geordnet ist, ist sie nur bei Dimensionen mit einer natürlichen Reihenfolge wie Datum oder Pfadlänge nützlich.

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) | 
|------+------+--------------+--------------| 
| May  | $500 | $500         | $500         | 
| June | $200 | $700         | $700         | 
| July | $400 | $1100        | $600         | 
 
```

## Kumulativer Durchschnitt

Gibt den Durchschnitt der letzten N Zeilen zurück.

Wenn N &lt;= 0, werden alle vorherigen Zeilen verwendet. Da sie nach der Dimension geordnet ist, ist sie nur bei Dimensionen mit einer natürlichen Reihenfolge wie Datum oder Pfadlänge nützlich.

> [!NOTE] Mit Quotenmetriken, wie Umsatz/Besucher, funktioniert dies nicht so, wie Sie es vielleicht erwarten: Es wird der Quotendurchschnitt ermittelt, anstatt dass der Umsatz über die letzten N und die Besucher über die letzten N summiert und anschließend geteilt werden. Verwenden Sie stattdessen

```
cumul(revenue)/cumul(visitor)
```

## Gleich

Gibt Elemente mit einer exakten Entsprechung für numerische oder Zeichenfolgenwerte wieder.

## Exponentielle Regression: Korrelationskoeffizient (Tabelle)

Gibt den Korrelationskoeffizienten *r* zwischen zwei Metrikspalten (*metric_A* und *metric_B*) für die Regressionsgleichung zurück.

```
CORREL.EXP(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## Exponentielle Regression: Konstante (Tabelle)

Gibt die Konstante *b* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) zurück für

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Exponentielle Regression: Steigung (Tabelle)

Gibt die Steigung *a* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) zurück für.

```
SLOPE.EXP(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Nächstniedrigere ganze Zahl (Floor) (Zeile)

Gibt die größte Ganzzahl zurück, die nicht größer als ein angegebener Wert ist. Beispiel: Wenn Sie keine Währungsdezimalzahlen für den Umsatz in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel FLOOR(*Umsatz*) den Umsatz bis zum nächsten Dollar abrunden (in diesem Fall 569 US-Dollar).

```
FLOOR(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die Metrik, die gerundet werden soll. |

## Größer als

Gibt Elemente zurück, deren numerische Anzahl größer als der eingegebene Wert ist.

## Größer gleich

Gibt Elemente zurück, deren numerische Anzahl größer als der eingegebene Wert ist oder damit übereinstimmt.

## Hyperbelkosinus (Zeile)

Gibt den Hyperbelkosinus einer Zahl zurück.

```
COSH(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Der Winkel in Radiant, dessen hyperbolischer Kosinus berechnet werden soll. |

## Hyperbelsinus (Zeile)

Gibt den Hyperbelsinus einer Zahl zurück.

```
SINH(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Der Winkel in Radiant, dessen hyperbolischer Sinus berechnet werden soll. |

## Hyperbeltangens (Zeile)

Gibt den Hyperbeltangens einer Zahl zurück.

```
TANH(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Der Winkel in Radianten, für den Sie die hyperbolische Bindung finden möchten. |

## WENN (Zeile)

Die IF-Funktion gibt einen Wert zurück, wenn eine angegebene Bedingung TRUE ergibt, und einen anderen, wenn diese Bedingung FALSE ergibt.

```
IF(logical_test, [value_if_true], [value_if_false])
```

| Argument | Beschreibung |
|---|---|
| *logical_test* | Erforderlich. Wert, der als TRUE oder FALSE bestimmt werden kann. |
| *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.) |
| *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.) |

## Kleiner als

Gibt Elemente zurück, deren numerische Anzahl kleiner als der eingegebene Wert ist.

## Kleiner gleich

Gibt Elemente zurück, deren numerische Anzahl kleiner als der eingegebene Wert ist oder damit übereinstimmt.

## Lineare Regression: Korrelationskoeffizient

Y = a X + b. Gibt den Korrelationskoeffizienten zurück.

## Lineare Regression: Konstante

Y = a X + b. Gibt b zurück.

## Lineare Regression: Vorhersage für Y

Y = a X + b. Gibt Y zurück.

## Lineare Regression: Steigung

Y = a X + b. Gibt a zurück.

## Logarithmus zur Basis 10 (Zeile)

Gibt den Logarithmus zur Basis 10 zurück.

```
LOG10(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die positive reale Zahl, dessen Logarithmus zur Basis 10 gewünscht ist. |

## Logistische Regression: Korrelationskoeffizient (Tabelle)

Gibt den Korrelationskoeffizienten *r* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für die Regressionsgleichung [!DNL Y = a ln(X) + b] zurück. Dies wird mit der Gleichung CORREL berechnet.

```
CORREL.LOG(metric_X,metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## Logistische Regression: Konstante (Tabelle)

Gibt die Konstante *b* als die Regression der kleinsten Quadrate zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für die Regressionsgleichung [!DNL Y = a ln(X) + b] zurück. Dies wird mit der Gleichung INTERCEPT berechnet.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Logistische Regression: Vorhersage für Y (Zeile)

Berechnet die prognostizierten [!DNL y]-Werte (metric_Y) anhand der bekannten [!DNL x]-Werte (metric_X) mittels der Methode der kleinsten Quadrate für die Berechnung der Ausgleichsgeraden mit [!DNL Y = a ln(X) + b]. Dies wird mit der Gleichung ESTIMATE berechnet.

In der Regressionsanalyse berechnet diese Funktion die prognostizierten [!DNL y]-Werte (*metric_Y*) anhand der bekannten [!DNL x]-Werte (*metric_X*) mithilfe des Logarithmus zur Berechnung der Ausgleichsgraden für die Regressionsgleichung [!DNL Y = a ln(X) + b]. Die [!DNL a]-Werte entsprechen den jeweiligen x-Werten und [!DNL b] ist eine Konstante.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Logistische Regression: Steigung (Tabelle)

Gibt die Steigung *a* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für die Regressionsgleichung [!DNL Y = a ln(X) + b] zurück. Dies wird mit der Gleichung SLOPE berechnet.

```
SLOPE.LOG(metric_A, metric_B)
```

| Argument | Beschreibung |
|---|---|
| *metric_A* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_B* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Natürlicher Logarithmus

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die positive reale Zahl, dessen natürlicher Logarithmus gewünscht ist. |

## NICHT

Gibt 1 zurück, wenn die Zahl 0 ist, oder 0, wenn eine andere Zahl zurückgegeben wird.

```
NOT(logical)
```

| Argument | Beschreibung |
|---|---|
| *logisch* | Erforderlich. Ein Wert oder Ausdruck, der als TRUE oder FALSE bestimmt werden kann. |

Die Verwendung von NOT erfordert das Wissen, ob die Ausdruck (&lt;, >, =, &lt;> usw.) 0- oder 1-Werte zurückgeben.

## Ungleich

Gibt alle Elemente zurück, die keine exakte Übereinstimmung mit dem eingegebenen Wert enthalten.

## Oder (Zeile)

Gibt TRUE zurück, wenn ein Argument TRUE ist, oder FALSE, wenn alle Argumente FALSE sind.

> [!NOTE] 0 (null) bedeutet „Falsch“ und jeder andere Wert „Wahr“.

```
OR(logical_test1,[logical_test2],...)
```

| Argument | Beschreibung |
|---|---|
| *logical_test1* | Erforderlich. Wert, der als TRUE oder FALSE bestimmt werden kann. |
| *logical_test2* | Optional. Zusätzliche Bedingungen, die Sie als TRUE oder FALSE auswerten möchten |

## Pi

Gibt die Konstante PI (3,14159265358979) mit 15 Stellen zurück.

```
PI()
```

Die Funktion [!DNL PI]weist keine Argumente auf.

## Potenzregression: Korrelationskoeffizient (Tabelle)

Gibt den Korrelationskoeffizienten *r* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = b*X] zurück.

```
CORREL.POWER(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## Potenzregression: Konstante (Tabelle)

Gibt die Konstante *b* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = b*X] zurück.

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Potenzregression: Vorhersage für Y (Zeile)

Berechnet die prognostizierten [!DNL y]-Werte ([!DNL metric_Y]) anhand der bekannten [!DNL x]-Werte ([!DNL metric_X]) mittels der Methode der kleinsten Quadrate für die Berechnung der Ausgleichsgeraden für [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Potenzregression: Steigung (Tabelle)

Gibt die Steigung ** zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = b*X]a zurück.

```
SLOPE.POWER(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Quadratische Regression: Korrelationskoeffizient (Tabelle)

Gibt den Korrelationskoeffizienten *r* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y=(a*X+b)]**** zurück.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## Quadratische Regression: Konstante (Tabelle)

Gibt die Konstante *b* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y=(a*X+b)]**** zurück.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Quadratische Regression: Vorhersage für Y (Zeile)

Berechnet die prognostizierten [!DNL y]-Werte (metric_Y) anhand der bekannten [!DNL x]-Werte (metric_X) mittels der Methode der kleinsten Quadrate für die Berechnung der Ausgleichsgeraden mit [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| Argument | Beschreibung |
|---|---|
| *metric_A* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_B* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |

## Quadratische Regression: Steigung (Tabelle)

Gibt die Steigung *a* zwischen zwei Metrikspalten (*metric_X* und metric_Y) für [!DNL Y=(a*X+b)]**** zurück.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Reziproke Regression: Korrelationskoeffizient (Tabelle)

Gibt den Korrelationskoeffizienten *r* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = a/X+b] zurück.

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | A metric that you would like to correlate with *metric_Y*. |
| *metric_Y* | A metric that you would like to correlate with *metric_X*. |

## Reziproke Regression: Konstante (Tabelle)

Gibt die Konstante *b* zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = a/X+b] zurück.

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Reziproke Regression: Vorhersage für Y (Zeile)

Berechnet die prognostizierten [!DNL y]-Werte (metric_Y) anhand der bekannten [!DNL x]-Werte (metric_X) mittels der Methode der kleinsten Quadrate für die Berechnung der Ausgleichsgeraden mit [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Reziproke Regression: Steigung (Tabelle)

Gibt die Steigung ** zwischen zwei Metrikspalten (*metric_X* und *metric_Y*) für [!DNL Y = a/X+b]a zurück.

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| Argument | Beschreibung |
|---|---|
| *metric_X* | Eine Metrik, der abhängiger Datenstatus zugewiesen werden soll. |
| *metric_Y* | Eine Metrik, der unabhängiger Datenstatus zugewiesen werden soll. |

## Sinus (Zeile)

Gibt den Sinus eines Winkels zurück. Liegt der Winkel im Gradmaß vor, müssen Sie ihn durch Multiplizieren mit PI( )/180 in das Bogenmaß umwandeln.

```
SIN(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Der Winkel in Radiant, dessen Sinus gewünscht ist. |

## t-Transformation

Alias für z-Transformation, also die Abweichung vom arithmetischen Mittel geteilt durch die Standardabweichung.

## t-Test

Führt einen m-seitigen t-Test mit einem t-Wert von Spalte und n Freiheitsgraden durch.

Die Signatur lautet `t_test( x, n, m )`. Darunter wird einfach `m*cdf_t(-abs(x),n)` aufgerufen. (Dies entspricht der z-Test-Funktion, die wie folgt lautet `m*cdf_z(-abs(x))`.

Hier gibt `m` die Anzahl der Seiten und `n` die Freiheitsgrade an. Hierbei sollte es sich um Ziffern handeln (im gesamten Bericht konstant, d. h. die Werte sollten nicht von Zeile zu Zeile variieren).

`X` ist die t-Test-Statistik. Hierbei handelt es sich häufig um eine auf einer Metrik basierende Formel (z. B. z-Wert), die in jeder Zeile bewertet wird.

Der Rückgabewert ist die Wahrscheinlichkeit, mit der die Teststatistik x in Anbetracht der Freiheitsgrade und der Anzahl der Schwänze angezeigt wird.

**Beispiele:**

1. Verwenden Sie ihn zum Auffinden von Ausreißern:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Kombinieren Sie ihn mit `if`, um sehr hohe oder niedrige Absprungraten zu ignorieren und alle weiteren Besuche zu zählen:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangens

Gibt den Tangens eines Winkels zurück. Liegt der Winkel im Gradmaß vor, müssen Sie ihn durch Multiplizieren mit PI( )/180 in das Bogenmaß umwandeln.

```
TAN (metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Der Winkel in Radiant, dessen Tangens gewünscht ist. |

## z-Transformation (Zeile)

Gibt die z-Transformation oder Normaltransformation basierend auf einer normalen Verteilung zurück. Der Z-Wert ist die Anzahl der Standardabweichungen, die eine Beobachtung vom arithmetischen Mittel ergibt. Ein Z-Wert von 0 (null) bedeutet, dass der Wert mit dem arithmetischen Mittel identisch ist. Ein Z-Wert kann positiv oder negativ sein, was angibt, ob er über oder unter dem Mittelwert liegt und wie viele Standardabweichungen vorliegen.

Die Gleichung für den Z-Wert lautet:

![](assets/z_score.png)

wobei [!DNL x] der Rohwert, [!DNL μ] das arithmetische Mittel der Population und [!DNL σ] die Standardabweichung der Population ist.

> [!NOTE] [!DNL μ] (Mu) und[!DNL σ] (Sigma) werden automatisch aus der Metrik berechnet.

z-Transformation (Metrik)

<table id="table_AEA3622A58F54EA495468A9402651E1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Metrik</i> </td> 
   <td colname="col2"> <p> Gibt den Wert seines ersten Nicht-Null-Arguments aus. </p> </td> 
  </tr> 
 </tbody> 
</table>

## z-Test

Führt einen n-seitigen Z-Test mit Z-Wert von A durch.

Gibt die Wahrscheinlichkeit zurück, mit der die aktuelle Zeile zufällig in der Spalte angezeigt wird.

> [!NOTE] Dabei wird von einer Normalverteilung der Werte ausgegangen.

