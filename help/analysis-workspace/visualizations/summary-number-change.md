---
description: Verwenden Sie die Visualisierungen "Zusammenfassungsnummer"und "Ändern", um wichtige Datenpunkte in einem Projekt anzuzeigen.
title: Sammelnummer und Sammeländerung
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
translation-type: tm+mt
source-git-commit: 9733d6471e6f1c886fd27b702654349d6760870c
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 56%

---


# Sammelnummer und Sammeländerung

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Mehr Infos...](/help/getting-started/cja-aa.md)

## Visualisierung für Zusammenfassungsnummer {#summary-number}

Verwenden Sie die Visualisierung der Zusammenfassungsnummer, um eine große Zahl hervorzuheben, die für ein Projekt wichtig ist. Diese Visualisierung verhält sich wie folgt:

* Wenn keine Zelle ausgewählt ist, wird die gesamte Spalte ausgewählt.
* Wenn eine einzelne Zelle ausgewählt ist, wird die Zusammenfassung für diese Zelle angezeigt.
* Wenn mehr als eine Zelle ausgewählt ist, wird die zuerst ausgewählte Zelle angezeigt.
* Wenn die Spalte ausgewählt ist, wird der erste Zellenwert in der Spalte verwendet.

![Zusammenfassungszahl](assets/summary-number.png)

Klicken Sie auf **Visualisierungseinstellungen** oben rechts hinein, um die Einstellungen für die Zusammenfassungsnummer zu konfigurieren:

| Einstellung | Definition |
|--- |--- |
| Prozentsatz | Zeigt Prozentwerte anstelle von Rohdaten an. |
| Legende sichtbar | Zeigt Informationen zur angezeigten Metrik an. |
| Wert abkürzen | Sie können Werte kürzen und bis zu 3 Dezimalstellen anzeigen. |
| Wert zusammenfassen nach | Wählen Sie aus, ob die Werte für &quot;max&quot;, &quot;min&quot;, &quot;mittel&quot;, &quot;median&quot;oder &quot;sum&quot;für eine Auswahl von Daten angezeigt werden sollen. |

## Visualisierung für Zusammenfassungsänderung:{#summary-change}

Verwenden Sie die Visualisierung der Zusammenfassungsänderung, um das Delta (Änderung) zwischen zwei Zahlen anzuzeigen. Die grüne und rote Farbe der Zusammenfassungsänderung können über [Benutzerdefinierte Ereignis-Polarität](https://docs.adobe.com/content/help/de-DE/analytics/admin/admin-tools/success-events/success-event.html) oder einer berechneten Metrik [Aufwärts-Trend anzeigen als](https://docs.adobe.com/content/help/de-DE/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html) auswählen.

Diese Visualisierung verhält sich wie folgt:

* Wenn keine Zelle ausgewählt ist, werden die ersten beiden Zellenwerte in der Spalte verglichen.
* Wenn eine Zelle ausgewählt ist, wird 0 angezeigt, weil der Zellenwert mit sich selbst verglichen wird.
* Wenn zwei Zellen ausgewählt sind, wird die erste ausgewählte Zelle als Numerator und die zweite als Denominator verwendet.
* Wenn mehr als zwei Zellen ausgewählt sind, werden nur die ersten beiden Zellen für den Vergleich berücksichtigt.
* Wenn ein Zellbereich ausgewählt ist, wird die erste Zelle mit den letzten im Bereich ausgewählten Zellen verglichen.
* Wenn die Spalte ausgewählt ist, wird der erste Wert mit sich selbst verglichen, sodass eine Änderung von 0 angezeigt wird.

![Zusammenfassungsänderung](assets/summary-change.png)

Klicken Sie auf **Visualisierungseinstellungen** oben rechts hinein, um die Einstellungen für die Zusammenfassungsänderung zu konfigurieren:

| Einstellung | Definition |
|--- |--- |
| Prozentsatz | Zeigt Prozentwerte anstelle von Rohdaten an. |
| Legende sichtbar | Zeigt Informationen zur angezeigten Metrik an. |
| Prozentsatzänderung anzeigen | Zeigt die prozentuale Änderung zwischen den 2 Zahlen an. |
| Rohdifferenz anzeigen | Zeigt den tatsächlichen Unterschied zwischen den beiden Zahlen. Mit dieser Option können Sie auch Werte kürzen und bis zu 3 Dezimalstellen anzeigen. |
