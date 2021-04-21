---
title: Bericht zu Google Analytics-Daten in Customer Journey Analytics
description: Zeigt nützliche Berichte zu Google Analytics-Daten in Customer Journey Analytics an
translation-type: tm+mt
source-git-commit: a4e95424ee304869e76a0532b7240290a3f13418
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 0%

---


# Bericht zu Google Analytics-Daten in Customer Journey Analytics

Nachdem Sie nun [die Daten der Google Analytics in Experience Platform und Customer Journey Analytics (CJA)](/help/use-cases/ga-to-cja.md) eingebunden haben, zeigen wir Ihnen einige nützliche Szenarien für den Berichte dieser Daten.

## Visualisieren von Webdaten und App-Daten als kombinierte Datensätze

Dieses Venn-Diagramm zeigt die Überschneidung der Benutzer auf Ihrer Website (aus Ihren Google Analytics-Daten) und in Ihrer mobilen App (aus Ihren Firebase-Daten) sowie in Ihrem Call-Center. Sie können auch die leistungsstärksten Produkte sehen - nicht nur im Web, sondern auch in der mobilen App. Sie können sogar den Gesamtumsatz aus beiden mithilfe einer berechneten Metrik abrufen. Beachten Sie, dass die Top-Produkte eine andere Geschichte erzählen, wenn Sie sich den kombinierten Umsatz ansehen. Ohne die kombinierten Datensätze hätten Sie nie gewusst, dass die &quot;Twill Cap&quot; eine solch starke Leistung erbringt.

![](assets/combined-datasets.png)

## Identifizieren Sie die Gründe für den Anruf und reduzieren Sie das Anrufvolumen.

Um sicherzustellen, dass Sie bereits viele Anrufe erhalten haben, können Sie die Zeit, die Sie in unserem Call-Center verbracht haben, über die letzten 2 Monate hinweg als Trend verfolgen. Der steigende Trend ist leicht zu erkennen. Das ist beunruhigend, denn jede Minute, die Ihre Call-Center-Reps am Telefon kosten Sie Geld. Das kann sich auf jeden Fall auf Ihren Gewinn auswirken.

Schauen wir uns die wichtigsten Gründe an, die zu einem Anstieg der Anrufe in das Call-Center geführt haben. Beachten Sie, dass &quot;Kreditkarte verweigert&quot;, &quot;Kreditkarte entfernen&quot;und &quot;Beschädigtes Produkt&quot;die Hauptgründe sind. Dies kann bereits Hinweise zur Verbesserung des Online-Erlebnisses liefern. Sie können auch einen Trend für diese Anrufgründe verfolgen und sehen, welche am meisten zur Gesamt-Spitze beigetragen haben. Interessant ist, dass Kunden mit &quot;Beschädigtes Produkt&quot;mehr als 3 Minuten pro Anruf verbracht haben.

![](assets/call-volume.png)

Schauen wir uns noch einmal an, welche Produkte die meisten Anrufe an Ihr Call Center verursachen und wie viele Kunden diese Anrufe getätigt haben. Das Punktdiagramm zeigt an, dass 20.000 Personen angerufen haben, mehr als 4 Stunden 30 Minuten verbracht haben und 33 Einheiten des Produkts &quot;Herren&#39;s short Sleeve Tee&quot; zurückgegeben haben.

Wir können diese Erkenntnis unterbrechen und sehen, warum diese Leute das Produkt zurückgegeben haben, indem wir die Dimension &quot;Call Reason&quot;ziehen. Wie Sie sehen können, ist der Grund, warum dieses Produkt so viele Anrufe erhält, &quot;beschädigtes Produkt&quot;. Der nächste Schritt wäre, sich an die Abteilung Qualitätssicherung zu wenden und zu sehen, warum Kunden beschädigte T-Shirts erhalten haben.

![](assets/call-reason.png)

Schauen wir uns nun an, welche Webseiten zu den eingehenden Anrufen im Call Center geführt haben. Auf diese Weise erfahren Sie, wo die Erlebnisse auf der Website hinter den Erwartungen zurückbleiben, und helfen Ihren Produktmanagern, diese Herausforderungen zu lösen.

Wir tun dies

* Verwenden einer berechneten Metrik, um die Daten auf nur Sitzungen zu filtern, die mit einem Call-Center-Aufruf endeten.
* Verwenden des &quot;Participation&quot;-Modells in CJAs [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#cja-workspace).

Sie können leicht erkennen, welche Seiten am häufigsten an einer Sitzung teilnehmen, die zu einem Aufruf führt. Sie können sehen, dass die Seiten &quot;Warenkorb&quot;und &quot;Kassengangsinformationen&quot;die meisten Anrufe verursacht haben. Da Sie auch die Daten der mobilen Firebase-App eingeschlossen haben, können Sie sogar Seitenfehler und App-Abstürze sehen, die die Aufrufe generieren. Dies ist ein wirklich wichtiger Datenpunkt, wenn Sie großartige Web- und mobile App-Erlebnisse bereitstellen möchten.

![](assets/contributing-pages.png)

Mit der Kohortentabelle in Analysis Workspace können Sie außerdem nachvollziehen, wie lange es in der Regel dauert, bis die Benutzer nach dem Besuch der Website unser Call-Center aufrufen. Hier können Sie sehen, dass die durchschnittliche Zeit zwischen 3 und 4 Wochen liegt.

![](assets/cohort.png)

## Erweiterte Marketingzuordnung verwenden

Mit CJA können Sie ausgefeilte Zuordnungsmodelle für Ihre Daten über mehrere Kanal hinweg verwenden. Im folgenden Beispiel sehen Sie einen Vergleich der Anwendung von Last touch, first touch, u-förmig und algorithmischer Zuordnung von Umsatz zu den Google Analytics Kanal Grouping-Dimensionen.

![](assets/mktg-attribution.png)

Mithilfe einer berechneten Metrik können Sie diese Zuordnung auf Ihren Webumsatz, den Umsatz mobiler Apps und sogar die Produktrückgaben anwenden. Infolgedessen können Sie für jeden Marketing-Kanal den tatsächlichen Nettoumsatz sehen.

![](assets/calc-metric.png)

Mit Attribution IQ können Sie Ihre Daten auch einfach filtern. Sie können die Zuordnung nur für bestimmte Benutzergruppen anzeigen, z. B. für Benutzer, die mehr als ein Gerät verwenden.

![](assets/filter.png)

Schließlich können Sie Ihren Web- und App-Umsatz auch Ihren Google-Anzeigeninhalten zuordnen. Sie werden feststellen, dass Sie mehr Umsatz aus der mobilen App gewonnen haben, die von unseren Online-Google-Anzeigen angetrieben wird, als aus dem Internet. Indem Sie Anzeigen nach Web- und App-Umsatz sortieren, erhalten Sie ein ganz anderes Bild davon, was Ihre leistungsstärksten Google-Anzeigen waren.

![](assets/google-ad.png)

Ohne CJA hätten Sie nicht wissen können, dass Ihre Online-Anzeigen Auswirkungen auf Produkte haben, die Sie in Ihrer mobilen App gekauft haben. Jetzt können Sie sehen, dass der Umsatz von mobilen Apps aus Google Ads zusätzliche 14 bis 5.000 $ im Vergleich zum Internet ausmacht.

![](assets/google-ad2.png)