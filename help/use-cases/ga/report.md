---
title: Bericht zu Google Analytics-Daten in Customer Journey Analytics
description: Zeigt nützliche Berichte zu Google Analytics-Daten in Customer Journey Analytics an
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 17b9e14e58f5bd2f4ec995de54989b00c26076f2
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 35%

---

# Bericht zu Google Analytics-Daten in Customer Journey Analytics

Sobald Ihnen Daten in Customer Journey Analytics zur Verfügung stehen, bieten die folgenden Beispiele nützliche Szenarien für die Berichterstellung zu diesen Daten.

## Visualisieren von Web-Daten und App-Daten als kombinierte Datensätze

Dieses Venn-Diagramm zeigt die Überschneidung der Benutzer auf Ihrer Website (aus Ihren Google Analytics-Daten) und in Ihrer mobilen App (aus Ihren Firebase-Daten) sowie in Ihrem Callcenter. Sie können auch die leistungsstärksten Produkte sehen – nicht nur im Web, sondern auch in der mobilen App. Sie können sogar den Gesamtumsatz aus beiden mithilfe einer berechneten Metrik abrufen. Beachten Sie, dass die Top-Produkte eine andere Geschichte erzählen, wenn Sie sich den kombinierten Umsatz ansehen. Ohne die kombinierten Datensätze hätten Sie nie gewusst, dass die „Twill Cap“ eine solch starke Leistung erbringt.

![Kombinierte Datensätze](../assets/combined-datasets.png)

## Identifizieren Sie die Gründe für die Anrufe und reduzieren Sie das Anrufvolumen.

Sie können einen Trend für die in den letzten zwei Monaten verbrachte Callcenter-Zeit erstellen, um das Aufrufvolumen zu ermitteln. Das folgende Beispiel zeigt diese Daten in der Trendansicht der letzten zwei Monate. Das folgende Beispiel zeigt einen zunehmenden Trend, der sich auf die Organisationskosten auswirken kann.

![Aufrufvolumen](../assets/call-volume.png)

Die Verwendung der Dimension &quot;Anrufgrund&quot;kann auf Möglichkeiten hinweisen, das Web-Erlebnis zu verbessern, wodurch verhindert wird, dass Besucher von vornherein aufrufen. Das obige Beispiel zeigt, dass die durchschnittliche Anrufzeit von fast 3 Minuten pro Anruf bei &quot;beschädigtem Produkt&quot;liegt, was Ihrer Organisation eine präzise Möglichkeit gibt, das Kundenerlebnis zu verbessern und die Anrufzentakosten zu senken.

Sie können sehen, welche Produkte die meisten Aufrufe an Ihr Callcenter verursachen und wie viele Kunden diese Aufrufe getätigt haben. Das Punktdiagramm zeigt, dass 20.000 Personen angerufen, mehr als 4 Stunden 30 Minuten verbracht und 33 Einheiten des Produkts &quot;Men&#39;s short Sleeve Tee&quot;zurückgegeben haben.

![Grund für den Anruf](../assets/call-reason.png)

Wenn Sie eine Dimensionsaufschlüsselung von &quot;Anrufgrund&quot;anwenden, zeigt das Beispiel das Dimensionselement &quot;Beschädigtes Produkt&quot;. Der nächste Schritt besteht darin, sich mit der Abteilung der Qualitätskontrolle in Verbindung zu setzen und herauszufinden, warum die Kunden beschädigte T-Shirts erhalten haben.

Sie können sehen, welche Website-Seiten Anrufe zum Callcenter geleitet haben. Dieser Bericht informiert Sie darüber, wo auf der Website weniger optimale Erlebnisse vorhanden sind, und hilft Ihren Produktmanagern bei der Lösung dieser Herausforderungen. Im folgenden Beispiel wird eine berechnete Metrik verwendet, um die Daten nach nur Sitzungen zu filtern, die mit einem Callcenter-Aufruf endeten. Außerdem wird das &quot;Beteiligungsmodell&quot;in CJA verwendet. [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=de#cja-workspace).

Das folgende Beispiel zeigt, dass die Seiten &quot;Warenkorb&quot;und &quot;Checkout-Informationen&quot;die meisten Aufrufe auslösen.

![Beiträge zu Seiten](../assets/contributing-pages.png)

In der Kohortentabelle können Sie sehen, wie lange es normalerweise dauert, bis Benutzer das Callcenter nach einem Besuch der Website aufrufen. Das folgende Beispiel zeigt, dass die durchschnittliche Zeit für diesen Beispieldatensatz zwischen drei und vier Wochen liegt.

![Kohorte](../assets/cohort.png)

## Erweiterte Marketing-Attribution verwenden

Mit CJA können Sie komplexe Attributionsmodelle für kanalübergreifende Daten verwenden. Im folgenden Beispiel sehen Sie einen Vergleich der Anwendung von Erstkontakt, Letztkontakt, U-förmig und algorithmischer Attribution von Umsatz mit den Channel Grouping-Dimensionen von Google Analytics.

![Marketing-Attribution](../assets/mktg-attribution.png)

Mithilfe einer berechneten Metrik können Sie diese Attribution auf Ihren Web-Umsatz und den Umsatz mit Mobile Apps anwenden und sogar die Produktretouren abziehen. Infolgedessen können Sie für jeden Marketing-Kanal den tatsächlichen Nettoumsatz sehen.

![Berechnete Metrik](../assets/calc-metric.png)

Mit Attribution IQ können Sie auch Ihre Daten filtern. Sie können die Attribution auch für bestimmte Benutzergruppen anzeigen, z. B. nur für Benutzer, die mehr als ein Gerät verwenden.

![Filter](../assets/filter.png)

Sie können Ihren Web- und App-Umsatz auch Ihren Google-Anzeigeninhalten zuordnen. Das Beispiel dieses Datensatzes erzielte mehr Umsatz aus der mobilen App, die von Online-Google-Anzeigen gesteuert wurde, als aus dem Internet. Durch Sortieren von Anzeigen nach Web- und App-Umsatz erhalten Sie ein anderes Bild davon, was Ihre leistungsstärksten Google-Anzeigen waren.

![Google-Anzeige](../assets/google-ad.png)

Durch die Kombination von Datensätzen in CJA können Sie in diesem Beispiel sehen, dass Online-Anzeigen Auswirkungen auf Produkte hatten, die in Ihrer mobilen App gekauft wurden. Die folgende Visualisierung zeigt, dass der Umsatz mobiler Apps durch Google Ads einen zusätzlichen Umsatz von 14 bis 15 Milliarden US-Dollar darstellt, verglichen mit dem Internet allein.

![Google und 2](../assets/google-ad2.png)
