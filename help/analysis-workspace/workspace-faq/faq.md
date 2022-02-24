---
description: Häufig gestellte Fragen zu Workspace und Tipps zur Fehlerbehebung.
title: Häufig gestellte Fragen
feature: FAQ
exl-id: d7233b26-9887-4b71-ad46-3c6ffe27d904
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '412'
ht-degree: 100%

---

# Häufig gestellte Fragen

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=de). [Weitere Informationen...](/help/getting-started/cja-aa.md)

| Frage | Antwort |
|--- |--- |
| **Was sind die Voraussetzungen für die Verwendung von Analysis Workspace?** | Für die Verwendung von Analysis Workspace ist eine funktionierende Implementierung von Customer Journey Analytics erforderlich. Vergewissern Sie sich, dass Ihre Organisation Daten an Adobe Experience Platform sendet, bevor Sie das Tool verwenden. |
| **Welche Administrations- und Zugriffsanforderungen gibt es für Analysis Workspace?** | Siehe [Administrationsanforderungen](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **Wirkt sich die Verwendung von Analysis Workspace auf die Datenerfassung aus?** | Da Analysis Workspace ein Berichtswerkzeug ist, hat dies keine Auswirkungen auf die Datenerfassung. Komponenten wahllos in ein Projekt zu ziehen, um zu sehen, was funktioniert, hat keine weiteren Folgen. Ziehen Sie verschiedene Kombinationen von Dimensionen und Metriken in Ihr Workspace-Projekt, um zu sehen, welche Möglichkeiten Sie haben. Wenn Sie versehentlich eine ungültige Komponente in Ihr Workspace-Projekt ziehen oder einen Schritt zurückgehen möchten, drücken Sie Strg + Z (Windows) oder Befehl + Z (Mac), um die letzte durchgeführte Aktion rückgängig zu machen. Sie können auch mit einem leeren Arbeitsbereich beginnen, indem Sie im Menü oben links auf *[!UICONTROL Projekt] > [!UICONTROL Neu]* klicken. |
| **Wie wird Analysis Workspace implementiert?** | Es ist keine spezielle Implementierung erforderlich. Analysis Workspace steht allen Unternehmen mit Customer Journey Analytics zur Verfügung. Es gelten jedoch die Standardberechtigungen für Inhalte (z. B. Projektkomponenten) und für die Kuratierung und Freigabe von Projekten. Weitere Informationen finden Sie unter [Administrations- und Zugriffsanforderungen](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **Wie kann ich die Leistung von Analysis Workspace optimieren?** | Siehe [Leistungsoptimierung](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Fehlerbehebung

**Wenn ich eine Metrik ziehe, wird die Meldung „Ungültige Daten“ angezeigt.**

„Ungültige Daten“ bedeuten, dass Adobe keine Daten mit der Kombination von Dimensionen und Metriken zurückgeben kann, die im Bericht verwendet werden. Beispielsweise können zwei Metriken, die übereinander gestapelt sind, nicht als Daten zurückgegeben werden, da es nicht möglich ist, zwei Metriken in dieser Weise anzuzeigen. Platzieren Sie die Metriken stattdessen nebeneinander.

**Wenn ich eine Metrik ziehe, sehe ich keine tatsächlichen Daten - nur Nullen.**

Wenn Sie einen Workspace-Bericht erfolgreich erstellt haben, aber keine Daten vorhanden sind, können Sie einige Punkte prüfen:

* Wenn Sie einen Filter in Ihrem Bericht angewendet haben, stimmen die Filterkriterien möglicherweise nicht mit den Daten überein. Versuchen Sie, den Filter zu entfernen oder die Filterdefinition anzupassen.
* Überprüfen Sie den Datumsbereich oben rechts und stellen Sie sicher, dass er auf einen erwarteten Wert eingestellt ist.
* Navigieren Sie zu Ihrer Website und überprüfen Sie mit dem [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=de), ob Daten erfasst werden.
