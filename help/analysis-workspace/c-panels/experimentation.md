---
description: Erfahren Sie, wie Sie die Ergebnisse von A/B-Tests im Bereich CJA-Experimentierung analysieren können.
title: Experimentationsbereich
feature: Panels
source-git-commit: 2c217c7d31819ac8eb27d2d1010e0df787601e21
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# Experimentationsbereich

>[!NOTE]
>
>Diese Funktion wird derzeit [eingeschränkt getestet](/help/release-notes/releases.md).

Die **[!UICONTROL Experimentieren]** -Bedienfeld können Sie verschiedene Varianten von Benutzererlebnissen, Marketing- oder Messaging miteinander vergleichen, um zu bestimmen, welches am besten zu einem bestimmten Ergebnis führt. Sie können die Steigerung und Konfidenz jedes A/B-Experiments von jeder beliebigen Experimentierplattform aus bewerten - online, offline, aus Adobe-Lösungen, Adobe Journey Optimizer und sogar aus eigenen BYO-Daten.

>[!IMPORTANT]
>
>An dieser Stelle [Adobe Analytics für Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=de) (A4T) Daten können nicht im [!UICONTROL Experimentieren] Bereich.

## Zugriffssteuerung

Das Experimentierungsfenster steht allen Customer Journey Analytics (CJA) zur Verfügung. Es sind keine Administratorrechte oder anderen Berechtigungen erforderlich. Für das Setup sind jedoch Beschriftungen in Datenansichten erforderlich, die nur Administratoren zuweisen können.

## Terminologie

* **Experiment**: Bei einem Experiment handelt es sich um eine Reihe von Varianten eines Erlebnisses, die Endbenutzern zur Verfügung gestellt wurden, um zu ermitteln, welche Erlebnisse am besten dauerhaft beibehalten werden sollten. Ein Experiment besteht aus zwei oder mehr Varianten, von denen eine als Kontrollvariante betrachtet wird.

* **Variante**: Eine von zwei oder mehr Änderungen am Erlebnis eines Endbenutzers, die verglichen werden, um die bessere Alternative zu ermitteln. Eine Variante muss als Kontrolle ausgewählt werden, und nur eine Variante kann als Kontrollvariante betrachtet werden.

* **Kontrolle**: Eine bestimmte Variante, die den Status quo oder den Standardstatus eines Benutzererlebnisses darstellt. Mit welchen anderen Varianten wird verglichen.

* **Normalisierungsmetrik**: Die Basis (Sitzungen oder Personen), auf der ein Test ausgeführt wird. Beispielsweise kann ein Test die Konversionsraten verschiedener Varianten vergleichen, bei denen die Konversionsrate als Konversionen pro Sitzung oder Konversionen pro Person berechnet wird.

* **Konversionsmetrik**: Die Metrik, mit der ein Benutzer Varianten vergleicht. Die Variante mit dem wünschenswertesten Ergebnis für die Konversionsmetrik (egal ob am höchsten oder am niedrigsten) wird zum &quot;Gewinner&quot;eines Experiments erklärt.

## Schritt 1: Verbindung zu Testdatensätzen erstellen

Nachdem Ihre Experimentdaten [erfasst](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) nach Adobe Experience Platform, [Erstellen einer Verbindung in CJA](/help/connections/create-connection.md) zu einem oder mehreren Experimentdatensätzen hinzufügen.

## Schritt 2: Hinzufügen von Kontextbezeichnungen in Datenansichten

In den Einstellungen für CJA-Datenansichten können Administratoren [Kontextbezeichnungen](/help/data-views/component-settings/overview.md) zu einer Dimension oder Metrik und CJA-Diensten wie [!UICONTROL Experimentieren] -Bedienfeld können diese Beschriftungen für ihre Zwecke verwenden. Für das Experimentierfeld werden zwei vordefinierte Beschriftungen verwendet:

* [!UICONTROL Experiment]
* [!UICONTROL Variante]

Wählen Sie in Ihrer Datenansicht, die Experimentdaten enthält, zwei Dimensionen aus: eine mit den Experimentierungsdaten und eine mit den Variantendaten. Benennen Sie diese Dimensionen dann mit dem **[!UICONTROL Experiment]** und **[!UICONTROL Variante]** Beschriftungen.

![Kontextbezeichnung](assets/context-label.png)

Ohne diese Beschriftungen funktioniert das Experiment-Bedienfeld nicht.

## Schritt 3: Konfigurieren des Experimentfensters

1. Ziehen Sie in CJA Workspace das Experimentierfeld in ein Projekt.

![Experimentbereich](assets/experiment.png)




