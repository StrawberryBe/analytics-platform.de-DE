---
description: Erfahren Sie, wie Sie die Ergebnisse von A/B-Tests im Bedienfeld „Experimentieren“ von CJA analysieren können.
title: Experimentier-Bedienfeld
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 3c4e2ccd9a3a1d8daf4ace79103b35aead79e432
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 100%

---

# Experimentier-Bedienfeld

>[!NOTE]
>
>Diese Funktion wird derzeit [eingeschränkt getestet](/help/release-notes/releases.md).

Im Bedienfeld **[!UICONTROL Experimentieren]** können Analysten verschiedene Varianten von Anwendererlebnissen, Marketing oder Messaging miteinander vergleichen, um zu ermitteln, welches die beste Lösung für ein bestimmtes Ergebnis ist. Sie können den Anstieg und die Konfidenz eines jeden A/B-Experiments von jeder beliebigen Experimentierplattform aus bewerten – online, offline, aus Adobe-Lösungen, über Adobe Journey Optimizer und sogar aus eigenen BYO (bring-your-own)-Daten.

>[!IMPORTANT]
>
>Aktuell können Daten aus [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=de) (A4T), die über Analytics Source Connector in Adobe Experience Platform importiert wurden, **nicht** im Bedienfeld [!UICONTROL Experimentieren] analysiert werden. Wir erwarten, dass dieses Problem 2023 gelöst wird.

## Zugriffssteuerung

Das Bedienfeld „Experimentieren“ kann von allen Anwendern von Customer Journey Analytics (CJA) genutzt werden. Es sind keine Administratorrechte oder anderen Berechtigungen erforderlich. Die Einrichtung (Schritte 1 und 2 unten) erfordert jedoch Aktionen, die nur Administratoren durchführen können.

## Schritt 1: Einrichten der Verbindung zu Experimentier-Datensätzen

Wenn Ihre Experimentierdaten in Adobe Experience Platform [erfasst](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=de) sind, können Sie zu einem oder mehreren Testdatensätzen [in CJA eine Verbindung einrichten](/help/connections/create-connection.md).

## Schritt 2: Hinzufügen von Kontextbezeichnungen in Datenansichten

In den Einstellungen für Datenansichten in CJA können Administratoren [Kontextbeschriftungen](/help/data-views/component-settings/overview.md) zu einer Dimension oder Metrik hinzufügen, und CJA-Services wie das Bedienfeld [!UICONTROL Experimentieren] können diese Beschriftungen für ihre Zwecke verwenden. Für das Bedienfeld „Experimentieren“ werden zwei vordefinierte Beschriftungen verwendet:

* [!UICONTROL Experimentierexperiment]
* [!UICONTROL Experimentiervariante]

Wählen Sie in Ihrer Datenansicht, die Experimentierdaten enthält, zwei Dimensionen aus: eine mit den Experimentierdaten und eine mit den Variantendaten. Geben Sie diesen Dimensionen dann die Beschriftungen **[!UICONTROL Experiment]** und **[!UICONTROL Variante]**.

![Kontextbeschriftung](assets/context-label.png)

Ohne diese Beschriftungen funktioniert das Bedienfeld „Experiment“ nicht, da keine Experimente vorhanden sind, mit denen gearbeitet werden kann.

## Schritt 3: Konfigurieren des Bedienfelds „Experiment“

1. Ziehen Sie in CJA Workspace das Bedienfeld „Experimentieren“ in ein Projekt.

![Bedienfeld „Experimentieren“](assets/experiment.png)

>[!IMPORTANT]
>Wenn die erforderliche Einrichtung in den Datenansichten in CJA nicht abgeschlossen wurde, erhalten Sie eine entsprechende Nachricht, bevor Sie fortfahren können.

1. Konfigurieren Sie die Einstellungen für die Bedienfeldeingabe.

   | Einstellung | Definition |
   | --- | --- |
   | **[!UICONTROL Experiment]** | Eine Reihe von Varianten eines Erlebnisses, die Endbenutzern präsentiert wurden, um zu ermitteln, welche am besten dauerhaft beibehalten werden sollte. Ein Experiment besteht aus zwei oder mehr Varianten, von denen eine als Kontrollvariante gilt. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die in den Datenansichten mit der Beschriftung **[!UICONTROL Experiment]** gekennzeichnet wurden, sowie mit den Experimentdaten der letzten drei Monate. |
   | **[!UICONTROL Kontrollvariante]** | Eine von zwei oder mehr Änderungen im Erlebnis eines Endbenutzers, die verglichen werden, um die bessere Alternative zu ermitteln. Eine Variante muss als Kontrolle ausgewählt werden und nur eine Variante kann als Kontrollvariante betrachtet werden. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die in den Datenansichten mit der Beschriftung **[!UICONTROL Variante]** gekennzeichnet wurden. Mit dieser Einstellung werden die Variantendaten abgerufen, die mit diesem Experiment verknüpft sind. |
   | **[!UICONTROL Erfolgsmetriken]** | Die Metrik(en), die ein Anwender verwendet, um Varianten zu vergleichen. Die Variante mit dem wünschenswertesten Ergebnis für die Konversionsmetrik (egal ob am höchsten oder am niedrigsten) wird zur „Variante mit der besten Performance“ eines Experiments erklärt. Sie können bis zu 5 Metriken hinzufügen. |
   | **[!UICONTROL Normalisierungsmetrik]** | Grundlage ([!UICONTROL Personen], [!UICONTROL Sitzungen] oder [!UICONTROL Ereignisse]) für die Ausführung eines Tests. Beispielsweise kann ein Test die Konversionsraten verschiedener Varianten vergleichen, bei denen die **[!UICONTROL Konversionsrate]** als **[!UICONTROL Konversionen pro Sitzung]** oder **[!UICONTROL Konversionen pro Person]** berechnet wird. |
   | **[!UICONTROL Datumsbereich]** | Der Datumsbereich wird basierend auf dem ersten Treffer, der in Customer Journey Analytics für das ausgewählte Experiment empfangen wurde, automatisch festgelegt. Sie können den Datumsbereich bei Bedarf auf einen spezifischeren Zeitraum beschränken oder erweitern. |

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

## Schritt 4: Interpretieren der Bedienfeldausgabe

Das Bedienfeld „Experimentieren“ liefert umfangreiche Daten und Visualisierungen, die Ihnen helfen, die Performance Ihrer Experimente besser zu verstehen. Oben im Bedienfeld wird eine Zusammenfassungszeile angezeigt, die Sie an die ausgewählten Bedienfeldeinstellungen erinnert. Sie können das Bedienfeld jederzeit bearbeiten, indem Sie oben rechts auf den Stift zum Bearbeiten klicken.

Sie erhalten auch eine Textzusammenfassung, die anzeigt, ob das Experiment schlüssig ist oder nicht, und die das Ergebnis zusammenfasst. Das Fazit beruht auf der statistischen Signifikanz. (Siehe unten unter „Statistische Methodik“.) Sie können Zusammenfassungszahlen für die Variante mit der besten Performance mit dem höchsten Anstieg und der höchsten Konfidenz anzeigen.

>[!NOTE]
>
>Anstieg und Konfidenz sind ebenfalls [erweiterte Funktionen für die berechnete Metrik](/help/components/calc-metrics/cm-adv-functions.md) in Customer Journey Analytics. Sie können also Ihre eigenen Metriken zu Anstieg und Konfidenz erstellen.

![Experimentausgabe](assets/exp-output1.png)

Für jede ausgewählte Erfolgsmetrik wird eine Freiformtabelle und ein Konversionsraten-Trend angezeigt:

![Experimentausgabe](assets/exp-output2.png)

Das [!UICONTROL Liniendiagramm] zeigt Ihnen die Performance von [!UICONTROL Kontrolle] im Vergleich zur [!UICONTROL Kontrollvariante]:

![Experimentausgabe](assets/exp-output3.png)

>[!NOTE]
>
>Die Analyse von A/A-Tests wird aktuell von diesem Bedienfeld nicht unterstützt.

## Statistische Methodik von Adobe

Um leicht verständliche und sichere statistische Rückschlüsse zu ermöglichen, hat Adobe eine statistische Methodik eingeführt, die auf [Immer gültige Konfidenzsequenzen](https://doi.org/10.48550/arXiv.2103.06476) basiert.

Eine Konfidenzsequenz ist ein „sequenzielles“ Analogon eines Konfidenzintervalls. Um zu verstehen, was eine Konfidenzsequenz ist, stellen Sie sich vor, Ihre Experimente hundertmal zu wiederholen und für *jeden neue Anwender*, der zum Experiment hinzukommt, eine Schätzung der durchschnittlichen Geschäftsmetrik (z. B. Öffnungsrate einer E-Mail) und der zugehörigen 95-%-Konfidenzsequenz durchzuführen. Eine Konfidenzsequenz von 95 % enthält in 95 der 100 Experimente, die Sie ausgeführt haben, den Wert „true“ der Geschäftsmetrik. (Ein Konfidenzintervall von 95 % kann nur einmal pro Experiment und nicht für jeden einzelnen neuen Anwender berechnet werden, um die gleiche 95-%-Garantie zu erhalten.) Konfidenzsequenzen ermöglichen es Ihnen daher, Experimente kontinuierlich zu überwachen, ohne die Falsch-Positiv-Fehlerrate zu erhöhen, d. h. sie ermöglichen einen Einblick in die Ergebnisse.

### Interpretation der Ergebnisse

1. **Experiment ist endgültig**: Jedes Mal, wenn Sie den Experimentbericht anzeigen, analysiert Adobe die Daten, die bis zu diesem Zeitpunkt im Experiment gesammelt wurden, und deklariert einen Versuch als „endgültig“, wenn das jederzeit gültige Konfidenzniveau einen Schwellenwert von 95 % für *mindestens eine* der Varianten überschreitet (mit Bonferonni-Korrektur, wenn mehr als zwei Arme vorhanden sind, als Korrektur für mehrere Hypothesentests).

2. **Variante mit der besten Performance**: Wenn ein Experiment als endgültig deklariert wird, wird die Variante mit der höchsten Konversionsrate als „Variante mit der besten Performance“ gekennzeichnet. Beachten Sie, dass diese Variante entweder die Kontroll- bzw. Baseline-Variante sein muss oder eine der Varianten, die die 95-%-ige, immer gültige Konfidenzschwelle überschreiten (mit Bonferonni-Korrekturen).

3. **Konversionsrate**: Die angezeigte Konversionsrate ist ein Verhältnis zwischen dem Wert der Erfolgsmetrik und dem Wert der Normalisierungsmetrik. Beachten Sie, dass dies manchmal größer als 1 sein kann, wenn die Metrik nicht binär ist (1 oder 0 für jede Einheit im Experiment)

4. **Anstieg**: Die Zusammenfassung des Experimentberichts zeigt den Anstieg im Vergleich zur Baseline und ist somit ein Messwert für die prozentuale Verbesserung der Konversionsrate einer bestimmten Variante gegenüber der Baseline. Genau bestimmt ist dies der Performance-Unterschied zwischen einer bestimmten Variante und der Baseline, geteilt durch die Performance der Baseline und ausgedrückt in Prozent.

5. **Konfidenz**: Die angezeigte „immer gültige Konfidenz“ ist ein wahrscheinlicher Messwert dafür, wie viele Nachweise dafür vorliegen, dass eine bestimmte Variante der Kontrollvariante entspricht. Eine höhere Konfidenz deutet auf weniger Nachweise hin, die die Annahme stützen, dass die Kontroll- und Nicht-Kontrollvariante die gleiche Performance aufweisen. Genauer gesagt ist die angezeigte Konfidenz eine Wahrscheinlichkeit (ausgedrückt als Prozentsatz), dass wir einen kleineren Unterschied bei den Konversionsraten zwischen einer bestimmten Variante und der Kontrollvariante beobachtet hätten, wenn in Wirklichkeit kein Unterschied bei den zugrunde liegenden tatsächlichen Konversionsraten besteht. Im Hinblick auf *p*-Werte ist die angezeigte Konfidenz 1 - *p*-Wert.

Beachten Sie jedoch, dass bei einer vollständigen Beschreibung der Ergebnisse alle verfügbaren Nachweise berücksichtigt werden sollten (d. h. Experimentaufbau, Stichprobengrößen, Konversionsraten, Konfidenz usw.) und nicht nur, ob das Experiment als endgültig deklariert ist oder nicht. Selbst wenn ein Ergebnis noch nicht „endgültig“ ist, können überzeugende Beweise dafür vorliegen, dass sich eine Variante von einer anderen unterscheidet (z. B. wenn sich Konfidenzintervalle nahezu nicht überlappen). Idealerweise sollte die Entscheidungsfindung unter Berücksichtigung aller statistischen Daten, die auf einem kontinuierlichen Spektrum interpretiert werden, erfolgen.
