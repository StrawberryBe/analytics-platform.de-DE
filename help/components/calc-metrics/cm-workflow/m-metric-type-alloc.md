---
description: Informationen
title: Metriktyp und Attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 100%

---

# Metriktyp und Attribution

Wenn Sie das Zahnradsymbol neben einer Metrik auswählen, können Sie den Metriktyp und das Attributionsmodell angeben.

## Metriktyp

![](assets/cm_type_alloc.png)

| Metriktyp | Definition |
|---|---|
| Standard | Diese Metriken sind dieselben, die auch in der Standard-[!DNL Analytics]-Berichterstellung verwendet werden. Wenn eine Formel aus einer einzelnen Standardmetrik besteht, zeigt sie die gleichen Daten wie das nicht berechnete Metrikgegenstück an. Standardmetriken eignen sich zum Erstellen berechneter Metriken, die speziell für die einzelnen Einzelposten gelten. Beispiel: [Bestellungen]/[Besuche] teilt die Bestellungen für diesen Einzelposten durch die Anzahl der Besuche für den Posten. |
| Gesamt | Verwenden Sie den Gesamtwert für den Berichtszeitraum in jedem Einzelposten. Wenn eine Formel aus einer einzelnen Gesamtmetrik besteht, zeigt sie dieselbe Gesamtzahl für jeden Einzelposten an. Gesamtmetriken eignen sich für die Erstellung berechneter Metriken, die mit den Gesamtdaten der Site verglichen werden. Beispiel: [Bestellungen]/[Gesamtbesuche] zeigt den Anteil der Bestellungen für ALLE Site-Besuche und nicht nur die Besuche für den speziellen Zeileneintrag. |

## Attribution

>[!IMPORTANT]
>Eine vollständige Liste der nicht standardmäßigen Attributionsmodelle und unterstützten Lookback-Fenster finden Sie unter [Attributionsmodelle und Lookback-Fenster](/help/analysis-workspace/attribution/models.md).
