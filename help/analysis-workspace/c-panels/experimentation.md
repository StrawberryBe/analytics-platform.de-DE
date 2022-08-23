---
description: Erfahren Sie, wie Sie die Ergebnisse von A/B-Tests im Bereich CJA-Experimentierung analysieren können.
title: Experimentationsbereich
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 15ef6bfc1d6600b3795310c208ad46c6f6b52254
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 5%

---

# Experimentationsbereich

>[!NOTE]
>
>Diese Funktion wird derzeit [eingeschränkt getestet](/help/release-notes/releases.md).

Die **[!UICONTROL Experimentieren]** -Bedienfeld können Analysten verschiedene Varianten von Benutzererlebnissen, Marketing- oder Messaging miteinander vergleichen, um zu ermitteln, welches die beste Lösung für ein bestimmtes Ergebnis ist. Sie können die Steigerung und Konfidenz jedes A/B-Experiments von jeder beliebigen Experimentierplattform aus bewerten - online, offline, aus Adobe-Lösungen, Adobe Journey Optimizer und sogar aus eigenen BYO-Daten.

>[!IMPORTANT]
>
>An dieser Stelle [Adobe Analytics für Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=de) (A4T)-Daten, die über den Analytics Source Connector in Adobe Experience Platform importiert wurden **cannot** im [!UICONTROL Experimentieren] Bereich. Wir erwarten für 2023 eine Lösung dieses Problems.

## Zugriffssteuerung

Das Experimentierfeld ist für alle Customer Journey Analytics (CJA) verfügbar. Es sind keine Administratorrechte oder anderen Berechtigungen erforderlich. Die Einrichtung (Schritte 1 und 2 unten) erfordert jedoch Aktionen, die nur Administratoren durchführen können.

## Schritt 1: Verbindung zu Testdatensätzen erstellen

Nachdem Ihre Experimentdaten [erfasst](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=de) nach Adobe Experience Platform, [Erstellen einer Verbindung in CJA](/help/connections/create-connection.md) zu einem oder mehreren Experimentdatensätzen hinzufügen.

## Schritt 2: Hinzufügen von Kontextbezeichnungen in Datenansichten

In den Einstellungen für CJA-Datenansichten können Administratoren [Kontextbezeichnungen](/help/data-views/component-settings/overview.md) zu einer Dimension oder Metrik und CJA-Diensten wie [!UICONTROL Experimentieren] -Bedienfeld können diese Beschriftungen für ihre Zwecke verwenden. Für das Experimentierfeld werden zwei vordefinierte Beschriftungen verwendet:

* [!UICONTROL Experiment]
* [!UICONTROL Variante]

Wählen Sie in Ihrer Datenansicht, die Experimentdaten enthält, zwei Dimensionen aus: eine mit den Experimentierungsdaten und eine mit den Variantendaten. Benennen Sie diese Dimensionen dann mit dem **[!UICONTROL Experiment]** und **[!UICONTROL Variante]** Beschriftungen.

![Kontextbezeichnung](assets/context-label.png)

Ohne diese Beschriftungen funktioniert das Experiment-Bedienfeld nicht, da keine Experimente zum Arbeiten vorhanden sind.

## Schritt 3: Konfigurieren des Experimentfensters

1. Ziehen Sie in CJA Workspace das Experimentierfeld in ein Projekt.

![Experimentbereich](assets/experiment.png)

>[!IMPORTANT]
>Wenn die erforderliche Einrichtung in CJA-Datenansichten nicht abgeschlossen wurde, erhalten Sie eine entsprechende Nachricht, bevor Sie fortfahren können.

1. Konfigurieren Sie die Einstellungen für die Bedienfeldeingabe.

   | Einstellung | Definition |
   | --- | --- |
   | **[!UICONTROL Experiment]** | Eine Reihe von Varianten eines Erlebnisses, die Endbenutzern bereitgestellt wurden, um zu bestimmen, welches Erlebnis dauerhaft am besten beibehalten werden sollte. Ein Experiment besteht aus zwei oder mehr Varianten, von denen eine als Kontrollvariante gilt. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die mit dem  **[!UICONTROL Experiment]** und die Experimentdaten der letzten drei Monate. |
   | **[!UICONTROL Kontrollvariante]** | Eine von zwei oder mehr Änderungen am Erlebnis eines Endbenutzers, die verglichen werden, um die bessere Alternative zu ermitteln. Eine Variante muss als Kontrolle ausgewählt werden, und nur eine Variante kann als Kontrollvariante betrachtet werden. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die mit dem  **[!UICONTROL Variante]** -Beschriftung in Datenansichten. Mit dieser Einstellung werden die Variantendaten abgerufen, die mit diesem Experiment verknüpft sind. |
   | **[!UICONTROL Erfolgsmetriken]** | Die Metrik(en), mit der/denen ein Benutzer Varianten vergleicht. Die Variante mit dem wünschenswertesten Ergebnis für die Konversionsmetrik (egal ob am höchsten oder am niedrigsten) wird zur &quot;Variante mit der besten Leistung&quot;eines Experiments erklärt. Sie können bis zu 5 Metriken hinzufügen. |
   | **[!UICONTROL Normalisierungsmetrik]** | Grundlage ([!UICONTROL Personen], [!UICONTROL Sitzungen]oder [!UICONTROL Veranstaltungen]), auf dem ein Test ausgeführt wird. Beispielsweise kann ein Test die Konversionsraten verschiedener Varianten vergleichen, bei denen **[!UICONTROL Konversionsrate]** berechnet als **[!UICONTROL Konversionen pro Sitzung]** oder **[!UICONTROL Konversionen pro Person]**. |
   | **[!UICONTROL Datumsbereich]** | Der Datumsbereich wird basierend auf dem ersten Treffer, der in Customer Journey Analytics für das ausgewählte Experiment empfangen wurde, automatisch festgelegt. Sie können den Datumsbereich bei Bedarf auf einen spezifischeren Zeitraum beschränken oder erweitern. |

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

## Schritt 4: Interpretieren der Bedienfeldausgabe

Das Bedienfeld &quot;Experimentierung&quot;liefert umfangreiche Daten und Visualisierungen, die Ihnen helfen, die Leistung Ihrer Experimente besser zu verstehen. Oben im Bedienfeld wird eine Zusammenfassungszeile angezeigt, die Sie an die ausgewählten Bedienfeldeinstellungen erinnert. Sie können das Bedienfeld jederzeit bearbeiten, indem Sie oben rechts auf den Stift zum Bearbeiten klicken.

Sie erhalten auch eine Textzusammenfassung, die anzeigt, ob das Experiment schlüssig ist oder nicht, und das Ergebnis zusammenfasst. Die Fazit beruht auf der statistischen Bedeutung. (Siehe &quot;Statistische Methode&quot;unten.) Sie können Zusammenfassungszahlen für die Variante mit der besten Performance mit der höchsten Steigerung und Konfidenz anzeigen.

>[!NOTE]
>
>Steigerung und Konfidenz sind ebenfalls [erweiterte berechnete Metrikfunktionen](/help/components/calc-metrics/cm-adv-functions.md) in Customer Journey Analytics verwenden, sodass Sie Ihre eigenen Steigerungs- und Konfidenzmetriken erstellen können.

![Experimentausgabe](assets/exp-output1.png)

Für jede ausgewählte Erfolgsmetrik wird eine Freiformtabelle und ein Konversionsraten-Trend angezeigt:

![Experimentausgabe](assets/exp-output2.png)

Die [!UICONTROL Linie] gibt Ihnen das Diagramm [!UICONTROL Kontrolle] versus [!UICONTROL Kontrollvariante] Leistung:

![Experimentausgabe](assets/exp-output3.png)

>[!NOTE]
>
>In diesem Bedienfeld wird die Analyse von A/A-Tests derzeit nicht unterstützt.

## Statistische Methode der Adobe

Um eine leicht verständliche und sichere statistische Einflussnahme zu ermöglichen, hat die Adobe eine statistische Methode eingeführt, die auf [Immer gültige Konfidenzsequenzen](https://doi.org/10.48550/arXiv.2103.06476).

Eine Konfidenzsequenz ist ein &quot;sequenzielles&quot;Analogon eines Konfidenzintervalls. Um zu verstehen, was eine Konfidenzsequenz ist, stellen Sie sich vor, Ihre Experimente hundertmal zu wiederholen und eine Schätzung der durchschnittlichen Geschäftsmetrik (z. B. Öffnungsrate einer E-Mail) und der zugehörigen 95-%-Konfidenzsequenz für *Jeder neue Benutzer* , der in das Experiment eintritt. Eine Konfidenzsequenz von 95 % enthält den Wert &quot;true&quot;der Geschäftsmetrik in 95 der 100 Experimente, die Sie ausgeführt haben. (Ein Konfidenzintervall von 95 % konnte nur einmal pro Versuch berechnet werden, um die gleiche 95-%-Garantie zu erhalten. nicht bei jedem neuen Benutzer). Konfidenzsequenzen ermöglichen es Ihnen daher, Experimente kontinuierlich zu überwachen, ohne die Falsch-Positiv-Fehlerrate zu erhöhen, d. h. sie ermöglichen einen &quot;Peeking&quot; bei Ergebnissen.

### Interpretation der Ergebnisse

1. **Experiment ist abgeschlossen**: Jedes Mal, wenn Sie den Experimentbericht anzeigen, analysiert Adobe die Daten, die bis zu diesem Zeitpunkt im Experiment gesammelt wurden, und deklariert einen Versuch als &quot;Fazit&quot;, wenn das jederzeit gültige Konfidenzniveau einen Schwellenwert von 95 % für *mindestens* der Varianten (mit einer Bonferonni-Korrektur, wenn mehr als zwei Arme vorhanden sind, zur Korrektur für mehrere Hypothesentests).

2. **Beste Variante**: Wenn ein Experiment für schlüssig erklärt wird, wird die Variante mit der höchsten Konversionsrate als die &quot;Variante mit der besten Performance&quot;gekennzeichnet. Beachten Sie, dass diese Variante entweder die Kontroll- oder die Baseline-Variante sein muss oder eine der Varianten, die die 95%-ige, jederzeit gültige Konfidenzschwelle überschreiten (wobei Bonferonni-Korrekturen vorgenommen werden).

3. **Konversionsrate**: Die angezeigte Konversionsrate ist ein Verhältnis zwischen dem Erfolgsmetrikwert und dem normalisierenden Metrikwert. Beachten Sie, dass dies manchmal größer als 1 sein kann, wenn die Metrik nicht binär ist (1 oder 0 für jede Einheit im Experiment)

4. **Steigerung**: Die Zusammenfassung des Experimentberichts zeigt die Steigerung im Vergleich zur Grundlinie, die einen Messwert für die prozentuale Verbesserung der Konversionsrate einer bestimmten Variante gegenüber der Grundlinie darstellt. Genau bestimmt ist dies der Leistungsunterschied zwischen einer bestimmten Variante und der Grundlinie, geteilt durch die Leistung der Grundlinie, in Prozent ausgedrückt.

5. **Konfidenz**: Die angezeigte &quot;Anytime Valid Confidence&quot;ist ein probabilistischer Messwert dafür, wie viele Beweise dafür vorliegen, dass eine bestimmte Variante mit der Kontrollvariante identisch ist. Eine höhere Konfidenz deutet auf weniger Anzeichen für die Annahme hin, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Leistung aufweisen. Genauer gesagt ist das angezeigte Vertrauen eine Wahrscheinlichkeit (ausgedrückt als Prozentsatz), dass wir einen kleineren Unterschied bei den Konversionsraten zwischen einer bestimmten Variante und der Kontrolle beobachtet hätten, wenn in Wirklichkeit kein Unterschied bei den zugrunde liegenden tatsächlichen Konversionsraten besteht. Im Hinblick auf *p*-Werte, ist die angezeigte Konfidenz 1 - *p*-Wert.

Beachten Sie jedoch, dass bei einer vollständigen Beschreibung der Ergebnisse alle verfügbaren Nachweise berücksichtigt werden sollten (d. h. Versuchsaufbau, Stichprobengrößen, Konversionsraten, Konfidenz usw.) und nicht nur die endgültige Erklärung. Selbst wenn ein Ergebnis noch nicht &quot;schlüssig&quot;ist, können überzeugende Beweise dafür vorliegen, dass sich eine Variante von einer anderen unterscheidet (Konfidenzintervalle sind beispielsweise nahezu nicht überlappend). Idealerweise sollte die Entscheidungsfindung durch alle statistischen Daten, die auf einem kontinuierlichen Spektrum interpretiert werden, informiert werden.
