---
title: Bericht zu Google Analytics-Daten in Customer Journey Analytics
description: Zeigt nützliche Berichte zu Google Analytics-Daten in Customer Journey Analytics an
exl-id: a7ac3c8d-c0d9-4fc2-80d7-c2b388250586
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: 39e7ae1f77e00dfe58c7f9e9711d18a1cd4fc0ac
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 98%

---

# Bericht zu Google Analytics-Daten in Customer Journey Analytics

Nachdem Sie nun [die Daten zu Google Analytics in Experience Platform und Customer Journey Analytics (CJA)](/help/use-cases/ga-to-cja.md) eingebunden haben, zeigen wir Ihnen einige nützliche Szenarien für das Reporting dieser Daten.

## Visualisieren von Web-Daten und App-Daten als kombinierte Datensätze

Dieses Venn-Diagramm zeigt die Überschneidung der Benutzer auf Ihrer Website (aus Ihren Google Analytics-Daten) und in Ihrer mobilen App (aus Ihren Firebase-Daten) sowie in Ihrem Callcenter. Sie können auch die leistungsstärksten Produkte sehen – nicht nur im Web, sondern auch in der mobilen App. Sie können sogar den Gesamtumsatz aus beiden mithilfe einer berechneten Metrik abrufen. Beachten Sie, dass die Top-Produkte eine andere Geschichte erzählen, wenn Sie sich den kombinierten Umsatz ansehen. Ohne die kombinierten Datensätze hätten Sie nie gewusst, dass die „Twill Cap“ eine solch starke Leistung erbringt.

![](assets/combined-datasets.png)

## Identifizieren Sie die Gründe für die Anrufe und reduzieren Sie das Anrufvolumen.

Um sicherzustellen, dass Sie bereits viele Anrufe erhalten haben, können Sie die Zeit, die Sie in unserem Callcenter verbracht haben, über die letzten 2 Monate hinweg als Trend verfolgen. Der steigende Trend ist leicht zu erkennen. Das ist beunruhigend, denn jede Minute, die Ihre Callcenter-Mitarbeiter am Telefon verbringen, kostet Sie Geld. Das kann sich auf jeden Fall auf Ihren Gewinn auswirken.

Schauen wir uns die wichtigsten Gründe an, die zu einem Anstieg der Anrufe in das Callcenter geführt haben. Beachten Sie, dass „Kreditkarte verweigert“, „Kreditkarte entfernen“ und „Beschädigtes Produkt“ die Hauptgründe sind. Dies kann bereits Hinweise auf Möglichkeiten zur Verbesserung des Online-Erlebnisses geben. Sie können auch einen Trend für diese Anrufgründe verfolgen und sehen, welche am meisten zum Gesamtanstieg beigetragen haben. Interessant ist, dass Kunden mit „Beschädigtes Produkt“ mehr als 3 Minuten pro Anruf verbracht haben.

![](assets/call-volume.png)

Schauen wir uns weiter an, welche Produkte die meisten Anrufe in Ihrem Callcenter verursachen und wie viele Kunden diese Anrufe getätigt haben. Das Blasendiagramm zeigt an, dass 20.000 Personen angerufen haben, mehr als 4 Stunden 30 Minuten damit verbracht haben und 33 Einheiten des Produkts „Kurzärmliges Herren-T-Shirt“ zurückgegeben haben.

Wir können diesen Einblick aufschlüsseln und sehen, warum diese Personen das Produkt zurückgegeben haben, indem wir die Dimension „Anrufgrund“ hinzuziehen. Wie Sie sehen, ist der Grund für die vielen Anrufe zu diesem Produkt „Beschädigtes Produkt“. Der nächste Schritt besteht darin, sich mit der Abteilung der Qualitätskontrolle in Verbindung zu setzen und herauszufinden, warum die Kunden beschädigte T-Shirts erhalten haben.

![](assets/call-reason.png)

Schauen wir uns nun an, welche Website-Seiten die eingehenden Anrufe im Callcenter verursacht haben. Auf diese Weise erfahren Sie, wo die Erlebnisse auf der Website hinter den Erwartungen zurückbleiben, und helfen Ihren Produkt-Managern, diese Herausforderungen zu lösen.

Wir tun dies durch:

* Verwenden einer berechneten Metrik, um die Daten nur bezüglich Sitzungen zu filtern, die mit einem Callcenter-Aufruf endeten.
* Verwenden des „Teilnahme“-Modells im [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html#cja-workspace) von Customer Journey Analytics.

Sie können leicht erkennen, welche Seiten am häufigsten an einer Sitzung teilnehmen, die zu einem Aufruf führt. Sie können sehen, dass die Seiten „Warenkorb“ und „Checkout-Informationen“ zu den meisten Anrufen führten. Da Sie auch die Daten der Mobile App „Firebase“ eingeschlossen haben, können Sie sogar Seitenfehler und App-Abstürze sehen, die die Anrufe generieren. Dies ist ein wirklich wichtiger Datenpunkt, wenn Sie großartige Erlebnisse im Web und in der Mobile App bereitstellen möchten.

![](assets/contributing-pages.png)

Und schließlich können Sie mithilfe der Kohortentabelle in Analysis Workspace leicht nachvollziehen, wie lange es normalerweise dauert, bis Benutzer unser Callcenter anrufen, nachdem sie die Website besucht haben. Hier können Sie sehen, dass die durchschnittliche Zeit zwischen 3 und 4 Wochen liegt.

![](assets/cohort.png)

## Erweiterte Marketing-Attribution verwenden

Mit CJA können Sie ausgefeilte Attributionsmodelle für Ihre Cross-Channel-Daten verwenden. Im folgenden Beispiel sehen Sie einen Vergleich der Anwendung von Erstkontakt, Letztkontakt, U-förmig und algorithmischer Attribution von Umsatz mit den Channel Grouping-Dimensionen von Google Analytics.

![](assets/mktg-attribution.png)

Mithilfe einer berechneten Metrik können Sie diese Attribution auf Ihren Web-Umsatz und den Umsatz mit Mobile Apps anwenden und sogar die Produktretouren abziehen. Infolgedessen können Sie für jeden Marketing-Kanal den tatsächlichen Nettoumsatz sehen.

![](assets/calc-metric.png)

Mit Attribution IQ können Sie Ihre Daten auch einfach filtern. Sie können die Attribution auch für bestimmte Benutzergruppen anzeigen, z. B. nur für Benutzer, die mehr als ein Gerät verwenden.

![](assets/filter.png)

Schließlich können Sie Ihren Umsatz im Web und über Mobile Apps auch Ihren Google-Anzeigeninhalten zuordnen. Sie werden feststellen, dass Sie mit der Mobile App durch unsere Online-Google-Anzeigen mehr Umsatz erzielt haben als im Web. Indem Sie Anzeigen nach Web- und Mobile App-Umsatz sortieren, erhalten Sie ein ganz anderes Bild davon, welches Ihre leistungsstärksten Google-Anzeigen waren.

![](assets/google-ad.png)

Ohne CJA hätten Sie nicht wissen können, dass Ihre Online-Anzeigen Auswirkungen auf Produkte hatten, die über Ihre Mobile App gekauft wurden. Jetzt können Sie sehen, dass der Umsatz der Mobile App durch Google Ads zusätzliche 14.000 $ ausmacht, im Vergleich zum 5.000 $ vom Internet allein.

![](assets/google-ad2.png)
