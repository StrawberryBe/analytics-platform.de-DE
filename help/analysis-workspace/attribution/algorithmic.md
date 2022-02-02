---
title: Algorithmische Attribution
description: Details zum algorithmischen Attributionsmodell.
feature: Attribution
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 84%

---

# Algorithmische Attribution

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=de). [Weitere Informationen...](/help/getting-started/cja-aa.md)

Im Folgenden finden Sie eine Videoübersicht zur algorithmischen Zuordnung:

>[!VIDEO](https://video.tv.adobe.com/v/36205/?quality=12)

Das algorithmische [Attributionsmodell](models.md) in Analysis Workspace unterscheidet sich von anderen Modellen insofern, als es mithilfe statistischer Verfahren Gewichtungen über die Dimensionselemente in Ihrem Bericht oder Ihrer Freiform-Tabelle verteilt. Wie alle anderen Attributionsmodelle in Analysis Workspace kann es für jede Dimension oder Metrik verwendet werden. Es unterstützt unbegrenzte Filter und Aufschlüsselungen und verteilt 100 % der Konversionen auf die Dimension(en) in der Tabelle (auch als &quot;Teilattribution&quot;bezeichnet).

Der für die Zuordnung verwendete Algorithmus basiert auf der Harsanyi-Dividende aus der kooperativen Spieltheorie. Die Harsanyi-Dividende ist eine Verallgemeinerung der Shapley-Wertlösung (die nach Lloyd Shapley, einem Nobelpreisträger für Ökonomie, benannt wurde) zur Verteilung von Gutschriften unter den Spielern in einem Spiel mit ungleichen Beiträgen zum Ergebnis.

Auf hoher Ebene betrachtet die Attributionsberechnung der Konversionsgewichtung für jeden Touchpoint jeden Marketing-Touchpoint innerhalb eines Lookback-Fensters als eine Koalition von Akteuren, auf die ein Überschuss gleichmäßig verteilt werden muss. Die Überschusshöhe jeder Koalition wird nach dem Überschuss bestimmt, der zuvor von jeder Unterkoalition (oder zuvor teilnehmenden Dimensionselementen) rekursiv erzeugt wurde. Weitere Einzelheiten finden Sie in den Originalarbeiten von John Harsanyi und Lloyd Shapley:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!IMPORTANT]
>
>Das Ergebnis der algorithmischen Attribution unterscheidet sich nur dann von anderen Modellen, wenn innerhalb des angegebenen Lookback-Fensters mehrere Touchpoints vorhanden sind. Konversionen mit einem einzigen Touchpoint erhalten eine Gewichtung von 100 % unabhängig vom Attributionsmodell.
