---
description: Erfahren Sie, wie Sie die Ergebnisse von A/B-Tests im Bereich CJA-Experimentierung analysieren können.
title: Experimentationsbereich
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 69331f1ad3699c4a01d782fe11d4f2212c703190
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 7%

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

Das empfohlene Datenschema besteht darin, dass sich die Experimentdaten in einem Objekt-Array befinden, das die Experiment- und Variantendaten in zwei separaten Dimensionen enthält. Wenn sich Ihre Experimentdaten in einer einzigen Dimension mit Experiment- und Variantendaten in einer getrennten Zeichenfolge befinden, können Sie die [substring](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=en#) -Einstellung in Datenansichten, um sie zur Verwendung im Bereich in zwei aufzuteilen.

Nachdem Ihre Experimentdaten [erfasst](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) nach Adobe Experience Platform, [Erstellen einer Verbindung in CJA](/help/connections/create-connection.md) zu einem oder mehreren Experimentdatensätzen hinzufügen.

## Schritt 2: Hinzufügen von Kontextbezeichnungen in Datenansichten

In den Einstellungen für CJA-Datenansichten können Administratoren [Kontextbezeichnungen](/help/data-views/component-settings/overview.md) zu einer Dimension oder Metrik und CJA-Diensten wie [!UICONTROL Experimentieren] -Bedienfeld können diese Beschriftungen für ihre Zwecke verwenden. Für das Experimentierfeld werden zwei vordefinierte Beschriftungen verwendet:

* [!UICONTROL Experiment]
* [!UICONTROL Variante]

Wählen Sie in Ihrer Datenansicht, die Experimentdaten enthält, zwei Dimensionen aus: eine mit den Experimentierungsdaten und eine mit den Variantendaten. Benennen Sie diese Dimensionen dann mit dem **[!UICONTROL Experiment]** und **[!UICONTROL Variante]** Beschriftungen.

![Kontextbezeichnung](../assets/context-label.png)

Ohne diese Beschriftungen funktioniert das Experiment-Bedienfeld nicht, da keine Experimente zum Arbeiten vorhanden sind.

## Schritt 3: Konfigurieren des Experimentfensters

1. Ziehen Sie in CJA Workspace das Experimentierfeld in ein Projekt.

![Experimentbereich](../assets/experiment.png)

>[!IMPORTANT]
>Wenn die erforderliche Einrichtung in CJA-Datenansichten nicht abgeschlossen wurde, erhalten Sie eine entsprechende Nachricht, bevor Sie fortfahren können.

1. Konfigurieren Sie die Einstellungen für die Bedienfeldeingabe.

   | Einstellung | Definition |
   | --- | --- |
   | **[!UICONTROL Experiment]** | Eine Reihe von Varianten eines Erlebnisses, die Endbenutzern bereitgestellt wurden, um zu bestimmen, welches Erlebnis dauerhaft am besten beibehalten werden sollte. Ein Experiment besteht aus zwei oder mehr Varianten, von denen eine als Kontrollvariante gilt. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die mit dem  **[!UICONTROL Experiment]** und die Experimentdaten der letzten drei Monate. |
   | **[!UICONTROL Kontrollvariante]** | Eine von zwei oder mehr Änderungen am Erlebnis eines Endbenutzers, die verglichen werden, um die bessere Alternative zu ermitteln. Eine Variante muss als Kontrolle ausgewählt werden, und nur eine Variante kann als Kontrollvariante betrachtet werden. Diese Einstellung wird vorab mit den Dimensionen gefüllt, die mit dem  **[!UICONTROL Variante]** -Beschriftung in Datenansichten. Mit dieser Einstellung werden die Variantendaten abgerufen, die mit diesem Experiment verknüpft sind. |
   | **[!UICONTROL Erfolgsmetriken]** | Die Metrik(en), mit der/denen ein Benutzer Varianten vergleicht. Die Variante mit dem wünschenswertesten Ergebnis für die Konversionsmetrik (egal ob am höchsten oder am niedrigsten) wird zur &quot;Variante mit der besten Leistung&quot;eines Experiments erklärt. Sie können bis zu 5 Metriken hinzufügen. |
   | **[!UICONTROL Normalisierungsmetrik]** | Grundlage ([!UICONTROL Personen], [!UICONTROL Sitzungen]oder [!UICONTROL Veranstaltungen]), auf dem ein Test ausgeführt wird. Beispielsweise kann ein Test die Konversionsraten verschiedener Varianten vergleichen, bei denen **[!UICONTROL Konversionsrate]** berechnet als **[!UICONTROL Konversionen pro Sitzung]** oder **[!UICONTROL Konversionen pro Person]**. |
   | **[!UICONTROL Datumsbereich]** | Der Datumsbereich wird automatisch auf Grundlage des ersten Treffers festgelegt, der in Customer Journey Analytics für das ausgewählte Experiment empfangen wurde. Dies kann geändert werden, um den Datumsbereich bei Bedarf auf einen spezifischeren Zeitraum zu beschränken oder zu erweitern. |

1. Klicken Sie auf **[!UICONTROL Erstellen]**.

## Schritt 4: Interpretieren der Bedienfeldausgabe

Das Bedienfeld &quot;Experimentierung&quot;liefert umfangreiche Daten und Visualisierungen, die Ihnen helfen, die Leistung Ihrer Experimente besser zu verstehen. Ein globaler Filter wird hinzugefügt, um Personen oder Sitzungen zu berücksichtigen, die mehreren Varianten ausgesetzt sind. Dieser Filter kann nicht bearbeitet oder entfernt werden. Oben im Bedienfeld wird eine Zusammenfassungszeile angezeigt, die Sie an die ausgewählten Bedienfeldeinstellungen erinnert. Sie können das Bedienfeld jederzeit bearbeiten, indem Sie oben rechts auf den Stift zum Bearbeiten klicken.

Sie erhalten auch eine Textzusammenfassung, die anzeigt, ob das Experiment schlüssig ist oder nicht, und das Ergebnis zusammenfasst. Die Fazit beruht auf der statistischen Bedeutung. (Siehe &quot;Statistische Methode&quot;unten.) Die Variante mit der besten Performance wird nur für ein schlüssiges Experiment bereitgestellt und basierend auf der Konversionsrate der signifikanten Varianten ausgewählt. Sie können Zusammenfassungszahlen für die Variante mit der besten Performance mit der höchsten Steigerung und Konfidenz anzeigen.

Die Textzusammenfassungs- und Zusammenfassungsnummern werden nur für die erste Erfolgsmetrik generiert, die in der Bereichseingabe ausgewählt wurde.

>[!NOTE]
>
>Steigerung und Konfidenz sind auch erweiterte berechnete Metrikfunktionen in Customer Journey Analytics, sodass Sie Ihre eigenen Steigerungs- und Konfidenzmetriken erstellen können.

![Experimentausgabe](../assets/exp-output1.png)

Für jede ausgewählte Erfolgsmetrik wird eine Freiformtabelle und ein Konversionsraten-Trend angezeigt:

![Experimentausgabe](../assets/exp-output2.png)

Die [!UICONTROL Linie] gibt Ihnen das Diagramm [!UICONTROL Kontrolle] versus [!UICONTROL Kontrollvariante] Leistung:

![Experimentausgabe](../assets/exp-output3.png)
>[!NOTE]
>
>In diesem Bedienfeld wird die Analyse von A/A-Tests derzeit nicht unterstützt.

## Statistische Methode

Zu folgen.
