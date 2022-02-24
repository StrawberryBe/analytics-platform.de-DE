---
title: Häufig gestellte Fragen zu Attribution
description: Erhalten Sie Antworten auf häufig gestellte Fragen zur Attribution.
feature: Attribution
exl-id: 3153d8c9-4ca8-4189-8a2f-511a87e8ac17
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '306'
ht-degree: 100%

---

# Häufig gestellte Fragen zu Attribution

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=de). [Weitere Informationen...](/help/getting-started/cja-aa.md)

**Was bedeutet der Zeileneintrag „Keine“ bei Verwendung von Attribution?**

Das Zeilenelement „Keine“ ist ein Sammelobjekt, der alle Konversionen darstellt, die ohne Touchpoints im Lookback-Fenster stattgefunden haben. Versuchen Sie, einen längeren Zeitraum in Ihr Berichtsfenster aufzunehmen.

**Warum sehe ich manchmal Daten außerhalb meines Berichtsfensters, wenn ich Attributionsmodelle verwende?**

Diese zusätzlichen Daten sind auf das Lookback-Fenster des Besucherberichts zurückzuführen. Weitere Informationen finden Sie unter [Daten, die außerhalb des Berichtsfensters angezeigt werden](https://helpx.adobe.com/de/analytics/kb/data-appearing-outside-reporting-window.html) in der Analytics-KB. Adobe wird diese zusätzlichen Zeilen in einer künftigen Version herausfiltern.

**Wann sollte ich eine Rückmeldung zur Besuchszuordnung oder zur Besucherattribution verwenden?**

Die Auswahl des Attributions-Lookbacks hängt von Ihrem Anwendungsfall ab. Wenn Konversionen in der Regel länger als einen Besuch dauern, wird ein Besucher-Lookback empfohlen. Das Erstellen einer Datenansicht mit einer Definition eines längeren Besuchs ist ebenfalls eine mögliche Lösung.

**Worin unterscheiden sich Props und eVars bei der Verwendung von Attribution?**

Die Attribution wird zur Laufzeit des Berichts neu berechnet. Es gibt also keinen Unterschied zwischen einer Prop oder einer eVar (oder einer anderen Dimension) hinsichtlich des Attributionsmodells. Eigenschaften können mit jedem Lookback-Fenster oder Attributionsmodell bestehen bleiben und die eVar-Zuordnungs-/Ablaufeinstellungen werden ignoriert.

**Welche Dimensionen und Metriken werden nicht unterstützt?**

Das Attributionsbedienfeld unterstützt alle Dimensionen. Nicht unterstützte Metriken:

* Unique Visitors
* Besuche
* Vorfälle
* Seitenansichten
* A4T-Metriken
* Besuchszeitmetriken
* Absprünge
* Absprungrate
* Einstiege
* Ausstiege
* Nicht gefundene Seiten
* Suchvorgänge
* Einzelseitenbesuche
* Einzelzugriff

**Wie funktioniert die Attribution mit Filtern?**

Die Attribution wird immer vor dem Filtern ausgeführt und globale Filter werden ausgeführt, bevor andere Berichtsfilter angewendet werden.
