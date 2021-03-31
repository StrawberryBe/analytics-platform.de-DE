---
title: Was ist Persistenz im Customer Journey Analytics?
description: Dimension Persistenz ist eine Kombination aus Zuordnung und Ablauf. Gemeinsam bestimmen sie, welche Dimensionswerte beibehalten werden.
translation-type: tm+mt
source-git-commit: 09f49cff89d69ae630e917243425967dbf56a9ed
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 72%

---


# Persistenz

Dimension Persistenz ist eine Kombination aus Zuordnung und Ablauf. Gemeinsam bestimmen sie, welche Dimensionswerte beibehalten werden. Adobe empfiehlt dringend, dass Sie innerhalb Ihres Unternehmens besprechen, wie mehrere Werte für jede Dimension verarbeitet werden (Zuordnung) und wann Dimensionswerte die Speicherung der Daten beenden (Ablauf).

* Standardmäßig verwendet ein Dimensionswert die letzte Zuordnung. Neue Werte überschreiben persistente Werte.
* Standardmäßig verwendet ein Dimensionswert einen Ablauf von [!UICONTROL Sitzung].

## Zuordnung

Legt fest, wie CJA Gutschriften für ein Erfolgsereignis zuweist, wenn eine Variable mehrere Ereignis vor dem Ereignis erhält. Folgende Werte werden unterstützt:

* Zuletzt verwendet: Der letzte eVar-Wert erhält immer die Gutschrift für Erfolgsereignisse, bis diese eVar abläuft.
* Ausgangswert: Der erste eVar-Wert erhält immer die Gutschrift für Erfolgsereignisse, bis diese eVar abläuft.
* Instanz: ??

Hinweis: Beim Wechsel zu oder von linearen Werten wird unterbunden, dass historische Daten angezeigt werden. Das Mischen von Zuweisungstypen in der Berichterstellungsoberfläche kann zu falsch angegebenen Daten in Berichten führen. Bei einer linearen Zuweisung etwa könnte der Umsatz auf eine Reihe unterschiedlicher eVar-Werte aufgeschlüsselt werden. Nach dem Zurücksetzen auf die „Zuletzt“-Zuweisung würden 100 % des Umsatzes dem aktuellsten Einzelwert zugewiesen. Diese Zuweisung kann dazu führen, dass Benutzer die falschen Schlüsse ziehen.

Um die Wahrscheinlichkeit von Missverständnissen bei der Berichterstellung zu verringern, macht Analytics die historischen Daten für die Oberfläche nicht verfügbar. Wenn Sie sich entscheiden, die gegebene eVar wieder auf die ursprüngliche Zuweisungseinstellung zurückzusetzen, können diese angesehen werden – allerdings sollten Sie die eVar-Zuweisungseinstellungen nicht ändern, bloß um auf historische Daten zugreifen zu können. Adobe empfiehlt, eine neue eVar zu nutzen, wenn neue Zuweisungseinstellungen für bereits aufgezeichnete Daten gewünscht werden, statt die Zuweisungseinstellung einer eVar zu verändern, die bereits eine erhebliche Menge historischer Daten aufgebaut hat.

## Gültigkeit

Dimensionen laufen nach dem von Ihnen angegebenen Zeitraum ab. Nachdem der Dimensionswert abgelaufen ist, erhält er keine Gutschrift mehr für eine Metrik. Dimensionen können auch so konfiguriert werden, dass sie bei Metriken ablaufen. Beispiel: Wenn Sie eine interne Werbeaktion haben, die am Ende eines Besuchs abläuft, werden für diese interne Werbeaktionen nur Einkäufe oder Registrierungen gezählt, die während des Besuchs erfolgten, in der sie aktiviert wurde.

Es gibt zwei Möglichkeiten für den Ablauf einer eVar:

Sie können die eVar so einstellen, dass sie nach einem bestimmten Zeitraum oder Ereignis abläuft.
Sie können das Ablaufen einer eVar erzwingen, indem Sie sie zurücksetzen (z. B. wenn eine Variable für einen anderen Zweck eingesetzt werden soll).
Wenn Sie beispielsweise den Ablauf einer eVar von 30 auf 90 Tage ändern, bleiben die erfassten eVar-Werte für die Dauer des neu eingestellten Ablaufzeitraums (in diesem Fall 90 Tage) erhalten. Das System prüft lediglich die aktuelle Ablaufeinstellung und den letzten festgelegten Zeitstempel des erfassten eVar-Werts, um den Ablauf zu bestimmen. Nur die Option Zurücksetzen bewirkt ein unmittelbares Ablaufen von Werten.

Ein weiteres Beispiel: Wenn eine eVar im Mai dazu dienen soll, interne Werbeaktionen widerzuspiegeln (wobei sie nach 21 Tagen ablaufen soll) und im Juni dann eingesetzt wird, um interne Keywords zu erfassen, müssen Sie am 1. Juni ihren Ablauf erzwingen oder die Variable zurücksetzen. Dies wird dazu beitragen, die Werte der internen Werbung aus den Berichten vom Juni herauszuhalten.