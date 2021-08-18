---
title: Best Practices für die Attribution
description: Was sind die Best Practices bei der Entscheidung über ein Attributionsmodell?
source-git-commit: 0e0d77425edeceb3ede6d2d7ca81846b30179607
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---


# Best Practices für die Attribution

Das Auswählen des richtigen Attributionsmodells für Ihre Organisation hängt von einer Reihe von Überlegungen ab. In diesem Artikel werden eine Methodik und einige allgemeine Best Practices untersucht.

## Schritt 1: Sondierungsanalyse

>[!NOTE]
>Diese Analyse muss durchgeführt werden, bevor Sie ein Attributionsmodell auswählen.

Diese Phase besteht zunächst aus dem Verständnis des Kundenverhaltens und der Definition von Konversionsmetriken. Basierend auf den Konversionsmetriken können Tools wie Analysis Workspace und das Abrufen von Datenquellen aus mehreren Kanälen (z. B. Impressionsdaten) Ihr Verständnis von

* Wie viele Kunden greifen vor der Konvertierung auf verschiedene Marketing-Kanäle zu?
* Der Anteil/die Verteilung dieser Verhaltensweisen.

Wenn beispielsweise 50 % der Kunden vor der Konvertierung drei Kanäle berühren, besteht dann eine Interaktion zwischen diesen drei Kanälen?
Sie können dann eine Ober- und Unterstrichanalyse durchführen, um Ihr Verständnis zu erweitern.

### Analyse des oberen Trichters

Die Upper-Trichter-Analyse analysiert Kanäle, die verwendet werden, um Marken- oder Produktbewusstsein zu schaffen. Das Ziel der meisten TV-Anzeigen ist beispielsweise das Markenbewusstsein. Sie können das Attributionsmodell [&quot;Zeitverfall&quot;](/help/analysis-workspace/attribution/models.md) verwenden, da Benutzer Ihre TV-Anzeige im Laufe der Zeit vergessen werden.

### Analyse des unteren Trichters

In dieser Analyse wird davon ausgegangen, dass die Menschen bereits über Ihre Marke wissen und Sie möchten, dass sie konvertieren. Verwenden Sie E-Mail- oder Push-Benachrichtigungen oder Facebook-Anzeigen.

## Schritt 2: Regelbasierte Attribution

Dieser Schritt dient der Validierung Ihrer Hypothesen.

**Beispiel 1**

Nehmen wir einmal an, Ihre Hypothese lautet &quot;Mein Erstkontaktkanal hat einen größeren Einfluss auf die Konversion als mein Letztkontakt-Kanal. Anschließend verwenden Sie das Attributionsmodell [&quot;Umgekehrt J-förmig&quot;](/help/analysis-workspace/attribution/models.md), um diese Hypothese zu testen. Mit diesem Modell werden 60 % des Guthabens dem Erstkontaktpunkt gutgeschrieben.

**Beispiel 2**

Ihre Hypothese könnte sein: &quot;In unserer Branche (z. B. der Reisebranche) beträgt das Attributionsfenster 60 oder 90 Tage, nicht 30 Tage, da Kunden vor dem Kauf eines Produkts viel recherchieren. Anschließend ändern Sie Ihr [Lookback-Fenster](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#lookback-windows) in 90 Tage.

## Schritt 3: Algorithmische Attribution verwenden

Da es sehr schwierig ist, eine große Anzahl möglicher Hypothesen und Kombinationen zu validieren, können Sie [algorithmische Attribution](/help/analysis-workspace/attribution/algorithmic.md) verwenden, um diese Arbeit integrierten Algorithmen zu überlassen. Wenn Sie bereits das perfekte Attributionsmodell gefunden haben, das all Ihre Fragen beantwortet und perfekt passt, dann müssen Sie diesen Schritt offensichtlich nicht tun.

## Sonstige Aspekte

* Möglicherweise müssen Sie die Dienste eines Datenwissenschaftlers verwenden, anstatt sich allein auf Analysis Workspace zu verlassen.
