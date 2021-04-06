---
title: Algorithmische Attribution
description: Details zum algorithmischen Attributionsmodell.
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 82%

---

# Algorithmische Attribution

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Weitere Informationen ...](/help/getting-started/cja-aa.md)

>[!NOTE]
>
>**[!UICONTROL Algorithmische]** Zuordnung wird derzeit nur eingeschränkt getestet. Weitere Informationen finden Sie unter [Adobe Analytics feature release](https://docs.adobe.com/content/help/de-DE/analytics/landing/an-releases.html).

Das algorithmische [Attributionsmodell](models.md) in Analysis Workspace unterscheidet sich von anderen Modellen insofern, als es mithilfe statistischer Verfahren Gewichtungen über die Dimensionselemente in Ihrem Bericht oder Ihrer Freiform-Tabelle verteilt. Wie alle anderen Zuordnungsmodelle in Analysis Workspace kann es für jede Dimension oder Metrik verwendet werden. Es unterstützt unbegrenzte Filter und Aufschlüsselungen und verteilt 100 % der Konversionen auf die Dimension(en) in der Tabelle (auch als &quot;Bruchzuordnung&quot;bezeichnet).

Der für die Zuordnung verwendete Algorithmus basiert auf der Harsanyi-Dividende aus der kooperativen Spieltheorie. Die Harsanyi-Dividende ist eine Verallgemeinerung der Shapley-Wertlösung (die nach Lloyd Shapley, einem Nobelpreisträger für Ökonomie, benannt wurde) zur Verteilung von Gutschriften unter den Spielern in einem Spiel mit ungleichen Beiträgen zum Ergebnis.

Auf hoher Ebene betrachtet die Attributionsberechnung der Konversionsgewichtung für jeden Touchpoint jeden Marketing-Touchpoint innerhalb eines Lookback-Fensters als eine Koalition von Akteuren, auf die ein Überschuss gleichmäßig verteilt werden muss. Die Überschusshöhe jeder Koalition wird nach dem Überschuss bestimmt, der zuvor von jeder Unterkoalition (oder zuvor teilnehmenden Dimensionselementen) rekursiv erzeugt wurde. Weitere Einzelheiten finden Sie in den Originalarbeiten von John Harsanyi und Lloyd Shapley:

* Shapley, Lloyd S. (1953). Ein Wert für N-Personen-Spiele. *Beiträge zur Spieltheorie, 2 (28)*, 307-317.
* Harsanyi, John C. (1963). Ein vereinfachtes Verhandlungsmodell für das N-Personen-Kooperationsspiel. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>Das Ergebnis der algorithmischen Attribution unterscheidet sich nur dann von anderen Modellen, wenn innerhalb des angegebenen Lookback-Fensters mehrere Touchpoints vorhanden sind. Konversionen mit einem einzigen Touchpoint erhalten eine Gewichtung von 100 % unabhängig vom Attributionsmodell.
