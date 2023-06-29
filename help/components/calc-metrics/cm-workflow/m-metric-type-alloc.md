---
description: Informationen
title: Metriktyp und Attribution
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 7f3412dc852ccae1ad5e122c200da5567ba89e87
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 37%

---

# Metriktyp und Attribution

Wenn Sie das Zahnradsymbol neben einer Metrik auswählen, können Sie den Metriktyp und das Attributionsmodell angeben.

## Metriktyp

So legen Sie den Metriktyp beim Erstellen einer berechneten Metrik fest:

1. Wählen Sie das Zahnradsymbol neben der Metrik aus, deren Typ Sie auswählen möchten.

   ![](assets/cm_type_alloc.png)

1. Wählen Sie aus den folgenden Optionen:

   | Metriktyp | Definition |
   |---|---|
   | Standard | Diese Metriken sind dieselben, die auch in der Standard-[!DNL Analytics]-Berichterstellung verwendet werden. Wenn eine Formel aus einer einzelnen Standardmetrik besteht, zeigt sie die gleichen Daten wie das nicht berechnete Metrikgegenstück an. Standardmetriken eignen sich zum Erstellen berechneter Metriken, die speziell für die einzelnen Einzelposten gelten. Beispiel: [Bestellungen] / [Sitzungen] nimmt Bestellungen für diesen Zeileneintrag und teilt ihn durch die Anzahl der Sitzungen für diesen Zeileneintrag. |
   | Gesamtsumme | Verwenden Sie in jedem Zeileneintrag die Gesamtsumme für den Berichtszeitraum. Wenn eine Formel aus einer einzelnen Gesamtmetrik bestand, wird für jeden Zeileneintrag dieselbe Gesamtsumme angezeigt. Gesamtmetriken sind nützlich für die Erstellung berechneter Metriken, die mit den Gesamtdaten der Site vergleichen. Beispiel: [Bestellungen] / [Sitzungen insgesamt] zeigt den Anteil der Bestellungen für ALLE Sitzungen auf Ihrer Site, nicht nur die Sitzungen für den jeweiligen Zeileneintrag. |

## Attribution

Informationen zur Attribution in Customer Journey Analytics finden Sie unter [Einstellungen der Attribution-Komponente](/help/data-views/component-settings/attribution.md).
