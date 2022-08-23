---
source-git-commit: 99b190e1afe7068d11fd9d53c5be72008958a9c2
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---
# Einführung in die statistische Methode im Experimentierbereich von CJA

In diesem Artikel werden die statistischen Berechnungen beschrieben, die vom Experimentierungs-Panel in CJA verwendet werden. CJA verwendet erweiterte statistische Methoden zur Berechnung **Konfidenz** ist jederzeit gültig, sodass Sie Ihre Experimente so lange ausführen können, wie Sie möchten, und Ihre Ergebnisse kontinuierlich überwachen können.

In diesem Artikel wird beschrieben, wie A/B-Tests funktionieren. Außerdem erhalten Sie eine intuitive Einführung in die Funktionsweise von Adobe. ***Beliebige zeitgültige Konfidenzsequenzen***. Für erfahrene Benutzer sind die technischen Details und Referenzen am Ende enthalten.

## A/B-Tests und -Kausalität

A/B-Tests werden bei der Bewertung der Kausalauswirkungen bestimmter Arten von &quot;Interventionen&quot;häufig als &quot;Goldstandard&quot;bezeichnet. Es handelt sich um randomisierte Prüfungen, was im Rahmen von Online-Tests bedeutet, dass wir einige zufällig ausgewählte Benutzer einer bestimmten Variante einer Website, Nachricht oder E-Mail und einem anderen zufällig ausgewählten Benutzergruppe für andere Benutzer aussetzen. **Variante** oder **Behandlung**. Nach der Exposition messen wir dann das Ergebnis **Metrik(en)** interessiert uns (z.B. das Öffnen von E-Mails, Abonnements oder Käufen).

Wie in der Abbildung unten dargestellt, bedeutet die Tatsache, dass wir zufällig Benutzern jeder Variantengruppe zugewiesen haben, dass die Gruppen im Durchschnitt dieselben Merkmale aufweisen. Daher kann jeder Unterschied bei den Ergebnissen so interpretiert werden, dass er auf die Unterschiede in den erhaltenen Varianten zurückzuführen ist, d.h. wir können eine **kausal** Verbindung zwischen unseren Interventionen und den Ergebnissen, die uns interessieren. Auf diese Weise können Sie bei der Optimierung Ihrer Geschäftsziele rigorose, erklärbare, datengesteuerte Entscheidungen treffen. A/B-Tests sind daher ein wesentlicher Bestandteil des Toolkits jedes modernen Personalisierungsexperten.

<p style="text-align:center;"><img width="75%" src="img/causal-inference-cartoon.png" alt="kausal-inf"></p>


Eine wichtige Frage ist nun, ob beobachtete Unterschiede &quot;reale Auswirkungen&quot;sind oder aus Zufälligkeit entstehen. Wenn es nur einen kleinen Unterschied in den Ergebnismetriken zwischen Gruppen gibt, könnte dies zufällig beobachtet werden, während größere Unterschiede eher &quot;real&quot;sind. Der technische Begriff hier ist, dass unsere Messungen *schätzungen* der tatsächlichen Werte des Mittelwerts für jede Variantengruppe. Statistische Inferenztechniken geben uns Möglichkeiten, die Unsicherheit in unseren Schätzungen zu quantifizieren - hier sind die Konzepte von **p-Werte** und **Konfidenzintervalle** auftauchen, aber um diese zu verstehen, sollten wir zunächst die statistischen Fehler verstehen.

## Statistische Tests und Fehlerkontrolle

Mit vielen statistischen Erkennungsmethoden sollen zwei Fehlertypen bekämpft werden: **Falsch positive Werte** (Fehler vom Typ I) und **Falsch Negative** (Fehler vom Typ II). Diese sind in der folgenden Tabelle dargestellt.


<p style="text-align:center;"><img width="50%" src="img/contingency_table_stats_errors.png" alt="ContingencyTable"></p>


Eine Falsch-Positiv-Hypothese ist eine falsche Ablehnung der Nullhypothese, obwohl sie tatsächlich wahr ist. Im Zusammenhang mit Online-A/B-Tests bedeutet dies, dass wir (fälschlicherweise) zu dem Schluss kommen, dass die geschäftliche Ergebnismetrik zwischen verschiedenen Variantenarmen unterschiedlich ist, obwohl sie tatsächlich identisch war. Bevor wir das Experiment durchführen, wählen wir normalerweise einen Schwellenwert aus *α*. Nachdem das Experiment ausgeführt wurde, wird die *p*-value berechnet wird und wir lehnen den null ab, wenn *p &lt; α*. Ein häufig verwendeter Schwellenwert ist *α*= 0,05, was bedeutet, dass wir auf lange Sicht erwarten, dass 5 von 100 Experimenten falsch-positive Ergebnisse sind.

Unterdessen bedeutet ein Falsch Negativ, dass wir die Null-Hypothese nicht zurückweisen, wenn sie tatsächlich falsch ist. Für A/B-Tests bedeutet dies, dass wir die Null-Hypothese nicht ablehnen (erinnern Sie sich daran, dass die Null-Hypothese besagt, dass die geschäftliche Ergebnismetrik zwischen verschiedenen Variantenarmen identisch ist), obwohl sie tatsächlich anders ist. Um diesen Fehlertyp zu steuern, müssen wir im Allgemeinen genügend Benutzer in unserem Experiment haben, um eine bestimmte **Leistung**, definiert als 1-*β* (d. h. eins abzüglich der Wahrscheinlichkeit eines Fehlers vom Typ II).

Die meisten statistischen Erkennungsverfahren erfordern, dass Sie Ihre Stichprobengröße vorzeitig anhand der zu bestimmenden Effektgröße sowie Ihrer Fehlertoleranz (*α* und *β*). Die Methodik von Adobe ist jedoch so konzipiert, dass Sie Ihre Ergebnisse kontinuierlich für jede Stichprobengröße betrachten können.



## Statistische Methode der Adobe: _Immer gültige Konfidenzsequenzen_

Um eine leicht verständliche und sichere statistische Einflussnahme zu ermöglichen, hat die Adobe eine statistische Methode eingeführt, die auf [_Immer gültige Konfidenzsequenzen_](https://doi.org/10.48550/arXiv.2103.06476).

Eine Konfidenzsequenz ist ein &quot;sequenzielles&quot;Analogon eines Konfidenzintervalls. Um zu verstehen, was eine Konfidenzsequenz ist, stellen Sie sich vor, Ihre Experimente hundertmal zu wiederholen und eine Schätzung der durchschnittlichen Geschäftsmetrik (z. B. Öffnungsrate einer E-Mail) und der zugehörigen 95-%-Konfidenzsequenz für *Jeder neue Benutzer* , der in das Experiment eintritt. Eine Konfidenzsequenz von 95 % enthält den Wert &quot;true&quot;der Geschäftsmetrik in 95 der 100 Experimente, die Sie ausgeführt haben. (Ein Konfidenzintervall von 95 % konnte nur einmal pro Versuch berechnet werden, um die gleiche 95-%-Garantie zu erhalten. nicht bei jedem neuen Benutzer). Konfidenzsequenzen ermöglichen es Ihnen daher, Experimente kontinuierlich zu überwachen, ohne die Falsch-Positiv-Fehlerrate zu erhöhen, d. h. sie ermöglichen einen &quot;Peeking&quot; bei Ergebnissen.

Der Unterschied zwischen Konfidenzsequenzen und Konfidenzintervallen für ein einzelnes Experiment ist in der nachstehenden Animation dargestellt:

<p style="text-align:center;"><img width="75%" src="img/confidence-sequence-evolution-comparison.gif" alt="CSGIF"></p>


Wir stellen fest, dass Konfidenzsequenzen den Schwerpunkt von A/B-Tests auf *Schätzung* anstatt Hypothesentests durchzuführen, d. h., sich auf eine genaue Schätzung des Unterschieds der Mittel zwischen den Behandlungen zu konzentrieren, anstatt zu entscheiden, ob eine Nullhypothese basierend auf einem Schwellenwert von statistischer Bedeutung abgelehnt werden soll oder nicht.

In ähnlicher Weise wie die Beziehung zwischen p$-Werten (oder Konfidenz) und Konfidenzintervallen besteht jedoch auch eine Beziehung zwischen Konfidenzsequenzen und beliebigen gültigen p$-Werten (oder jeder beliebigen gültigen Konfidenz). Angesichts der Vertrautheit von Mengen wie der Konfidenz bietet CJA in seinen Berichten jederzeit gültige Konfidenz an.

Die theoretischen Grundlagen von Konfidenzsequenzen stammen aus der Studie von Sequenzen von zufälligen Variablen, die als Martingales bekannt sind. Im Folgenden finden Sie einige wichtige Ergebnisse für erfahrene Leser, aber die Möglichkeiten für Praktiker sind klar:


> Konfidenzsequenzen können als &quot;sichere&quot;sequenzielle Analoga von Konfidenzintervallen interpretiert werden: Sie können die Daten in Ihrem A/B-Test jederzeit ansehen und interpretieren und sicher stoppen oder die Experimente fortsetzen. Die entsprechende &quot;Anytime Valid Confidence&quot;(oder *p*-value) ist auch sicher zu interpretieren.

Da die statistische Methode &quot;jederzeit gültig&quot;ist, ist sie konservativer als eine Methode mit festgelegtem Horizont, die bei demselben Stichprobenumfang angewendet wird. Das bedeutet, dass die &quot;anytime valid&quot; *p*-Werte überschreiten im Allgemeinen den entsprechenden festgelegten Horizont. *p*-Werte (d. h. die jederzeit gültige Konfidenz ist kleiner)

## Interpretation der Ergebnisse

1. **Experiment ist abgeschlossen**: Jedes Mal, wenn Sie den Experimentbericht anzeigen, analysiert Adobe die Daten, die bis zu diesem Zeitpunkt im Experiment gesammelt wurden, und deklariert einen Versuch als &quot;Fazit&quot;, wenn das jederzeit gültige Konfidenzniveau einen Schwellenwert von 95 % für *mindestens* der Varianten (mit einer Bonferonni-Korrektur, wenn mehr als zwei Arme vorhanden sind, zur Korrektur für mehrere Hypothesentests).

2. **Beste Variante**: Wenn ein Experiment für schlüssig erklärt wird, wird die Variante mit der höchsten Konversionsrate als die &quot;Variante mit der besten Performance&quot;gekennzeichnet. Beachten Sie, dass diese Variante entweder die Kontroll- oder die Baseline-Variante sein muss oder eine der Varianten, die die 95%-ige, jederzeit gültige Konfidenzschwelle überschreiten (wobei Bonferonni-Korrekturen vorgenommen werden).

3. **Konversionsrate**: Die angezeigte Konversionsrate ist ein Verhältnis zwischen dem Erfolgsmetrikwert und dem normalisierenden Metrikwert. Beachten Sie, dass dies manchmal größer als 1 sein kann, wenn die Metrik nicht binär ist (1 oder 0 für jede Einheit im Experiment)

4. **Steigerung**: Die Zusammenfassung des Experimentberichts zeigt die Steigerung im Vergleich zur Grundlinie, die einen Messwert für die prozentuale Verbesserung der Konversionsrate einer bestimmten Variante gegenüber der Grundlinie darstellt. Genau bestimmt ist dies der Leistungsunterschied zwischen einer bestimmten Variante und der Grundlinie, geteilt durch die Leistung der Grundlinie, in Prozent ausgedrückt.

5. **Konfidenz**: Die angezeigte &quot;Anytime Valid Confidence&quot;ist ein probabilistischer Messwert dafür, wie viele Beweise dafür vorliegen, dass eine bestimmte Variante mit der Kontrollvariante identisch ist. Eine höhere Konfidenz deutet auf weniger Anzeichen für die Annahme hin, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Leistung aufweisen. Genauer gesagt ist das angezeigte Vertrauen eine Wahrscheinlichkeit (ausgedrückt als Prozentsatz), dass wir einen kleineren Unterschied bei den Konversionsraten zwischen einer bestimmten Variante und der Kontrolle beobachtet hätten, wenn in Wirklichkeit kein Unterschied bei den zugrunde liegenden tatsächlichen Konversionsraten besteht. Im Hinblick auf *p*-Werte, ist die angezeigte Konfidenz 1 - *p*-Wert.

Beachten Sie jedoch, dass bei einer vollständigen Beschreibung der Ergebnisse alle verfügbaren Nachweise berücksichtigt werden sollten (d. h. Versuchsaufbau, Stichprobengrößen, Konversionsraten, Konfidenz usw.) und nicht nur die endgültige Erklärung. Selbst wenn ein Ergebnis noch nicht &quot;schlüssig&quot;ist, können überzeugende Beweise dafür vorliegen, dass sich eine Variante von einer anderen unterscheidet (Konfidenzintervalle sind beispielsweise nahezu nicht überlappend). Idealerweise sollte die Entscheidungsfindung durch alle statistischen Daten, die auf einem kontinuierlichen Spektrum interpretiert werden, informiert werden.
