---
title: Referenz - Basisfunktionen
description: 'Mit dem Generator für berechnete Metriken können Sie statistische und mathematische Funktionen anwenden, um erweiterte berechnete Metriken zu erstellen. '
translation-type: tm+mt
source-git-commit: b521079bb9b3828ec3487b635366f5442f6fc4bd

---


# Referenz - Basisfunktionen

Mit dem Generator für berechnete Metriken können Sie statistische und mathematische Funktionen anwenden, um erweiterte berechnete Metriken zu erstellen.

Im Folgenden werden die Funktionen und ihre Definitionen alphabetisch aufgelistet.

> [!NOTE] Wenn [!DNL metric] als Argument in einer Funktion angegeben ist, sind auch andere Ausdrücke von Metriken zulässig. Beispiel: [!DNL MAXV(metrics)] ermöglicht auch [!DNL MAXV(PageViews + Visits).]

## Vergleich zwischen Tabellenfunktionen und Zeilenfunktionen

Eine Tabellenfunktion ist eine Funktion, bei der die Ausgabe für jede Tabellenzeile gleich ist. Bei einer Zeilenfunktion ist die Ausgabe für jede Tabellenzeile unterschiedlich.

## Absolutwert (Zeile)

Liefert den Absolutwert einer Zahl. Der Absolutwert einer Zahl ist die Zahl ohne Vorzeichen.

```
ABS(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die Metrik, deren Absolutbetrag gewünscht ist. |

## Spaltenmaximum

Gibt den größten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MAXV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet.

```
MAXV(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Eine Metrik, die ausgewertet werden soll. |

## Spaltenminimum

Gibt den kleinsten Wert in einem Satz aus Dimensionselementen für eine Metrikspalte zurück. MINV wird vertikal innerhalb einer einzelnen Spalte (Metrik) über Dimensionselemente hinweg ausgewertet.

```
MINV(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Eine Metrik, die ausgewertet werden soll. |

## Spaltensumme

Addiert alle numerischen Werte für eine Metrik innerhalb einer Spalte (über die Elemente einer Dimension hinweg).

```
SUM(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die Metrik, für die Sie den Gesamtwert oder die Summe ermitteln möchten. |

## Anzahl (Tabelle)

Gibt die Zahl oder Anzahl der Werte für eine Metrik innerhalb einer Spalte zurück, die ungleich null sind (die Anzahl berichteter eindeutiger Elemente innerhalb einer Dimension).

```
COUNT(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die Metrik, die gezählt werden soll. |

## Exponent (Zeile)

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | The exponent applied to the base *e*. |

## Potenzierung

Potenzierungsoperator

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (y-mal)
</pre>

## Arithmetisches Mittel (Tabelle)

Gibt das arithmetische Mittel (oder den Durchschnitt) für eine Metrik in einer Spalte zurück.

```
MEAN(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die Metrik, deren Durchschnitt gewünscht ist. |

## Medianwert (Tabelle)

Gibt den Medianwert für eine Metrik in einer Spalte zurück. Der Medianwert ist die Zahl in der Mitte eines Zahlensatzes, d. h. die Hälfte der Zahlen hat Werte größer oder gleich dem Medianwert und die Hälfte ist kleiner oder gleich dem Medianwert.

```
MEDIAN(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die Metrik, deren Mittelwert gewünscht ist. |

## Modulo

Der Rest von col1 / col2, unter Verwendung der Euclidean Division.

Gibt den Rest zurück, nachdem x durch y geteilt wurde.

```
x = floor(x/y) + modulo(x,y)
```

Der Rückgabewert hat das gleiche Zeichen wie die Eingabe (oder ist Null).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

Um immer eine positive Zahl zu erhalten, verwenden Sie

```
modulo(modulo(x,y)+y,y)
```

## Perzentil (Tabelle)

Gibt den k. Perzentil der Werte für eine Metrik zurück. Mit dieser Funktion können Sie einen Akzeptanzschwellenwert festlegen. Sie können beispielsweise Dimensionselemente untersuchen, die über dem 90. Perzentil liegen.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Metrik</i> </td> 
   <td colname="col2"> Die metrische Spalte, die die relative Position definiert. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> Der Prozentwert im Bereich von 0 bis 100. </td> 
  </tr> 
 </tbody> 
</table>

## Quartil (Tabelle)

Gibt das Quartil der Werte für eine Metrik zurück. Anhand von Quartilen können Sie beispielsweise die oberen 25 % der Produkte finden, die den meisten Umsatz generieren. MINV, MEDIAN und MAXV geben denselben Wert wie QUARTILE zurück, wenn Quartil 0 (null), 2 bzw. 4 entspricht.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>Metrik</i> </td> 
   <td colname="col2"> Die Metrik, deren Quartalswert gewünscht ist. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Gibt an, welcher *Wert zurückgegeben werden soll. </td> 
  </tr> 
 </tbody> 
</table>

*If *quart* = 0, QUARTILE returns the minimum value. Wenn *quart* = 1 ist, gibt QUARTILE das zweite Quartil (25. Perzentil) zurück. Wenn *quart* = 2 ist, gibt QUARTILE das zweite Quartil (50. Perzentil) zurück. Wenn *quart* = 3 ist, gibt QUARTILE das zweite Quartil (75. Perzentil) zurück. Wenn *quart* = 4 ist, gibt QUARTILE den Höchstwert zurück.

## Rund

Gibt die nächste Ganzzahl für einen Wert zurück. Beispiel: Wenn Sie keine Währungsdezimalzahlen für den Umsatz in Berichte aufnehmen möchten und ein Produkt einen Umsatz von 569,34 US-Dollar aufweist, können Sie mit der Formel Rund(*Umsatz*) den Umsatz bis zum nächsten Dollar runden (in diesem Fall 569 US-Dollar). Ein Berichte im Wert von 569,51 US-Dollar wird auf den nächsten Dollar gerundet oder 570 US-Dollar.

```
ROUND(metric)
```

| Argument | Beschreibung |
|---|---|
| *Anzahl* | Die Metrik, die gerundet werden soll. |

Das Runden ohne Ziffer-Parameter entspricht dem Runden mit einem Ziffer-Parameter von 0, also dem Runden auf die nächste Ganzzahl. Bei der Verwendung eines Ziffer-Parameters wird ein Wert mit der angegebenen Zahl rechts vom Dezimaltrennzeichen zurückgegeben. Falls der Ziffer-Parameter negativ ist, werden Nullen links vom Dezimaltrennzeichen zurückgegeben.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Zeilenanzahl

Gibt die Anzahl der Zeilen in einer bestimmten Spalte zurück (die Anzahl berichteter eindeutiger Elemente innerhalb einer Dimension). „Individuelle Werte überschritten“ wird als 1 gezählt.

## Zeilenmaximum

Das Maximum der Spalten in jeder Zeile.

## Zeilenminimum

Das Minimum der Spalten in jeder Zeile.

## Zeilensumme

Die Summe der Spalten in jeder Zeile.

## Quadratwurzel (Zeile)

Gibt die positive Quadratwurzel einer Zahl zurück. Die Quadratwurzel einer Zahl ist der Wert der Zahl hoch 1/2.

```
SQRT(metric)
```

| Argument | Beschreibung |
|---|---|
| *Anzahl* | Die Metrik, deren Quadratwurzel gewünscht ist. |

## Standardabweichung (Tabelle)

Gibt die Standardabweichung (oder die Quadratwurzel der Schwankung) basierend auf einer Beispieldatenpopulation zurück.

Die Gleichung für STDEV lautet:

![](assets/std_dev.png)

wobei x das Beispielmittel (*Metrik*) und *n* die Stichprobengröße ist.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Beschreibung</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> Metrik</i></b> </td> 
   <td> <p> Die Metrik, deren Standardabweichung gewünscht ist. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Schwankung (Tabelle)

Gibt die Schwankung basierend auf einer Beispieldatenpopulation zurück.

Die Gleichung für VARIANCE lautet:

![](assets/variance_eq.png)

wobei x das Beispielmittel, MEAN(*metric*) und *n* die Stichprobengröße ist.

```
VARIANCE(metric)
```

| Argument | Beschreibung |
|---|---|
| *Metrik* | Die Metrik, deren Varianz gewünscht ist. |

Um eine Varianz zu berechnen, betrachten Sie eine ganze Spalte mit Zahlen. Aus dieser Liste von Zahlen berechnen Sie zunächst den Durchschnitt. Sobald Sie den Durchschnitt erreicht haben, durchlaufen Sie jeden Eintrag und führen Sie folgende Schritte durch:

1. Ziehen Sie den Durchschnitt von der Zahl ab.

2. Quadrieren Sie das Ergebnis.

3. Fügen Sie diesen Wert zum Gesamtergebnis hinzu.

Nachdem Sie die gesamte Spalte durchlaufen haben, haben Sie eine einzige Summe. Dividieren Sie dann diese Summe durch die Anzahl der Elemente in der Spalte. Diese Zahl ist die Varianz für die Spalte. Es ist eine einzige Zahl. Er wird jedoch als Zahlenspalte angezeigt.

Beispiel: Sie haben eine Spalte mit drei Elementen:

1

2

3

Der Durchschnitt dieser Spalte ist 2. Die Varianz für die Spaltet lautet dann ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3. In Ad-hoc-Analysen sieht dies wie folgt aus:

1 2/3

2 2/3

3 2/3
