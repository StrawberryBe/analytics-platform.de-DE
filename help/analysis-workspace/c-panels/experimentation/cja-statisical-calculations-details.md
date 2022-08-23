---
source-git-commit: c95e01a80f3f3ddcabfee171ee357a5cf9e81e53
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---
# Statistische Berechnungen im Experimentierbereich von CJA: Details

Auf dieser Seite werden die detaillierten statistischen Berechnungen dokumentiert, die im Experimentierbereich von CJA verwendet werden. Sie ist für technische Anwender gedacht.


## Konversionsrate

Konversionsrate oder **mean**, *μ<sub>ν</sub>* für jede Variante *ν* in einem Experiment definiert wird als Verhältnis der Summe der Metrik zur Anzahl der Einheiten, die dieser Metrik zugewiesen sind, *N<sub>ν</sub>*:
<p style="text-align:center;"><img width="15%" src="img/mean_definition.png" alt="metric-average"></p>
Hier,

- *Y<sub>iν</sub>* der Wert der Metrik für jede Einheit *i*, die einer bestimmten Variante zugewiesen wurde *ν*.
- Summe über Einheiten *i* hängt von der Auswahl der Normalisierungsmetrik ab.
   - Wenn *Personen* die Normalisierungsmetrik ist, ist jede Einheit eine eindeutige Person/ein eindeutiges Profil.
   - Wenn *Sitzungen* die Normalisierungsmetrik ist, ist jede Einheit eine eindeutige Sitzung.
   - Wenn *Veranstaltungen* die Normalisierungsmetrik ist, ist jede Einheit ein eindeutiges Ereignis.

Im Allgemeinen sollte diese Normalisierungsmetrik so gewählt werden, dass sie Ihrer Unabhängigkeit entspricht. Wenn das Verhalten eines Benutzers in einer Sitzung unabhängig von seinem Verhalten in einer anderen Sitzung ist, ist Sitzungen eine vernünftige Normalisierungsmetrik.

Wo immer nötig, wird die Standardabweichung der Stichprobe mit dem Ausdruck verwendet


<p style="text-align:center;"><img width="30%" src="img/stdev_definition.png" alt="metric-average"></p>


## Steigerung

Die Steigerung zwischen einer Variante  *ν* und der Kontrollvariante  *ν<sub>0</sub>* ist das relative &quot;Delta&quot;in Konversionsraten, definiert als
<p style="text-align:center;"><img width="15%" src="img/lift_definition.png" alt="metric-average"></p>
wobei die einzelnen Konversionsraten wie oben definiert sind.


## Konfidenzsequenzen

Die Konfidenzsequenz für eine einzelne Variante wird zwar nicht im Bereich CJA-Experimentierung angezeigt, aber *ν* ist von zentraler Bedeutung für die von der Adobe verwendete statistische Methodik und wird daher hier definiert (reproduziert aus [Waudby-Smith et al.](https://doi.org/10.48550/arXiv.2103.06476)).

> Angenommen, man möchte einen Zielparameter schätzen *Punkt* (wie die Konversionsrate einer Variante in einem Experiment). Anschließend lässt sich die Dichotomie zwischen einer Sequenz von &quot;festen&quot;Konfidenzintervallen (CIs) und einer zeiteinheitlichen Konfidenzsequenz (CS) wie folgt zusammenfassen:
<p style="text-align:center;"><img width="60%" src="img/ci_vs_cs.png" alt="metric-average"></p>

Mit anderen Worten: Für ein reguläres Konfidenzintervall garantiert die probabilistische Garantie, dass der Zielparameter innerhalb des Wertebereichs liegt. *Ċ<sub>t</sub>* ist nur bei einem einzelnen festen Wert von *n* , *n* Anzahl der Proben). Im Gegensatz zu einer Konfidenzsequenz wird garantiert, dass jederzeit/alle Werte der Stichprobengröße *t*, liegt der Wert &quot;true&quot;des Interaktionsparameters innerhalb der Grenzen *<SPAN STYLE="text-decoration:overline">C</SPAN><sub>t</sub>*.

Dies hat einige tief greifende Auswirkungen, die für Online-Tests sehr wichtig sind:
- Das CSS kann optional aktualisiert werden, sobald neue Daten verfügbar sind.
- Experimente können kontinuierlich überwacht, adaptiv angehalten oder fortgesetzt werden.
- Der Typ-I-Fehler wird zu allen Stoppzeiten gesteuert, einschließlich datenabhängiger Zeiten.

Adobe verwendet asymptotische Konfidenzsequenzen, die für eine einzelne Variante mit durchschnittlicher Schätzung verwendet werden *μ* hat das Formular

<p style="text-align:center;"><img width="45%" src="img/confidence_sequence_individual.png" alt="metric-average"></p>

Dabei wird:
- *N* die Anzahl der Einheiten für diese Variante
- *σ* ist ein Stichprobenschätzwert der Standardabweichung (zuvor definiert)
- *α* ist die gewünschte Fehlerrate des Typ-I-Fehlers (oder der Wahrscheinlichkeit einer Fehlabdeckung).
- *evaluate*<sup> 2</sup> ist eine Konstante, die die Stichprobengröße anpasst, bei der das CS am härtesten ist. Die Adobe hat sich für einen universellen Wert von *evaluate*<sup> 2</sup> = 10<sup>-2,8</sup>, was für die in Online-Experimenten angezeigten Konversionsraten geeignet ist.


## Konfidenz

Die von der Adobe verwendete Konfidenz ist eine &quot;jederzeit gültige&quot;Konfidenz, die durch Umkehrung der Konfidenzsequenz für den durchschnittlichen Behandlungseffekt erzielt wird.

Um genau zu sein: Wir stellen fest, dass in zwei Beispielen *t* Test auf den Unterschied zwischen den Mittelwerten zweier Varianten. Es gibt eine 1:1-Zuordnung zwischen der *p*-Wert für diesen Test und das Konfidenzintervall für die Differenz der Mittelwerte. Eine jederzeit gültige *p*-Wert kann durch Invertieren der (jederzeit gültigen) Konfidenzsequenz für die Schätzung des durchschnittlichen Behandlungseffekts abgerufen werden:
<p style="text-align:center;"><img width="22%" src="img/ate_definition.png" alt="metric-average"></p>

Der verwendete Schätzwert ist ein umgekehrter Tendenzgewichteter (IPW) Schätzer. Überlegen *N = N<sub>0</sub>* + *N<sub>1</sub>* Einheiten, die Variantenzuweisungen für jede Einheit $i$, gekennzeichnet durch *A<sub>i</sub>=0,1* wenn die Einheit der Variante ν=0,1 zugewiesen ist. Wenn die Benutzer mit einer festen Wahrscheinlichkeit (Tendenz) zugewiesen sind *BS<sub>0</sub>, (1-H<sub>0</sub>)* und ihre Ergebnismetrik lautet *Y<sub>i</sub>*, ist der IPW-Schätzer
<p style="text-align:center;"><img width="45%" src="img/ipw_definition.png" alt="metric-average"></p>

feststellen, dass *f* ist die Einflussfunktion Waudby-Smith et al. zeigte, dass die Konfidenzsequenz für diesen Schätzer:
<p style="text-align:center;"><img width="55%" src="img/cs_ate_definition1.png" alt="metric-average"></p>

Ersetzen der Zuweiswahrscheinlichkeit durch ihre empirischen Schätzungen: *BS<sub>0</sub> = N<sub>0</sub>/N*, kann der Varianzbegriff in Form von individuellen Mittelwerten für die Stichprobe ausgedrückt werden.  *μ<sub>{0,1}</sub>* und Standardabweichungsschätzungen,  *σ<sub>{0,1}</sub>* as:

<p style="text-align:center;"><img width="55%" src="img/cs_ate_var.png" alt="metric-average"></p>


daran erinnern, dass für einen regelmäßigen Hypothesentest mit Teststatistik *z = (μ<sub>1</sub> - μ<sub>0</sub>)/ σ<sub>p</sub>* besteht eine Korrespondenz zwischen p$-Werten und Konfidenzintervallen:

<p style="text-align:center;"><img width="55%" src="img/pvalue_ci_correspondence.png" alt="metric-average"></p>

where *ì* ist die kumulative Verteilung der normalen Normalwerte. Für jeden Zeitraum gültig *p*-Werte, in Anbetracht der Konfidenzsequenz für den oben definierten durchschnittlichen Behandlungseffekt, können wir diese Beziehung umkehren:
<p style="text-align:center;"><img width="75%" src="img/anytimevalid-pvalue.png" alt="metric-average"></p>

Schließlich wird die **jederzeit gültig *Konfidenz*** is
<p style="text-align:center;"><img width="22%" src="img/anytimevalid-confidence.png" alt="metric-average"></p>


## Definieren eines Experiments als abgeschlossen

Für ein Experiment mit zwei Armen zeigt das Fenster &quot;CJA-Experimentierung&quot;eine Meldung an, dass ein Experiment **schlüssig** wenn die jederzeit gültige Konfidenz 95 % überschreitet (d. h. die jederzeit gültige Gültigkeit *p*-Wert unter 5%).

Wenn mehr als zwei Varianten vorhanden sind, wird die Bonferonni-Korrektur angewendet. Für ein Experiment mit *K* und eine einzige Ausgangsbehandlung (Kontrolle), gibt es *K-1* unabhängige Hypothesentests. Die Bonferonni-Korrektur bedeutet, dass wir die Null-Hypothese ablehnen, dass die Kontrolle und eine bestimmte Variante über die gleichen Mittel verfügen, wenn die jederzeit gültige *p*-value unterhalb eines Schwellenwerts von 0,05/(K-1).


## Beste Leistung

Wenn ein Experiment als abgeschlossen erklärt wird, wird der Arm mit der besten Leistung angezeigt. Dies ist der Arm mit der besten Leistung (höchste Mittelwert- oder Konversionsrate), der zu dem Satz gehört, der die Kontrolle enthält, und allen Armen mit einer *p*-Wert unterhalb des Bonferonni-Schwellenwerts.