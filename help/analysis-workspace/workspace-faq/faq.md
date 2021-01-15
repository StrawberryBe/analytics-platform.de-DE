---
description: Häufig gestellte Fragen zum Arbeitsbereich und Tipps zur Fehlerbehebung.
title: Häufig gestellte Fragen
translation-type: tm+mt
source-git-commit: d14817f28e757e94435c3b1059765fabe7cec54b
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 84%

---


# Häufig gestellte Fragen

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Weitere Informationen ...](/help/getting-started/cja-aa.md)

| Frage | Antwort |
|--- |--- |
| **Was sind die Voraussetzungen für die Verwendung von Analysis Workspace?** | Für die Verwendung von Analysis Workspace ist eine Implementierung des funktionierenden Customer Journey Analytics erforderlich. Vergewissern Sie sich, dass Ihr Unternehmen Daten an das Adobe Experience Platform sendet, bevor Sie das Tool verwenden. |
| **Welche Administrations- und Zugriffsanforderungen gibt es für Analysis Workspace?** | Siehe [Administrationsanforderungen](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **Wirkt sich die Verwendung von Analysis Workspace auf die Datenerfassung aus?** | Da Analysis Workspace ein Berichtswerkzeug ist, hat dies keine Auswirkungen auf die Datenerfassung. Komponenten wahllos in ein Projekt zu ziehen, um zu sehen, was funktioniert, hat keine weiteren Folgen. Ziehen Sie verschiedene Kombinationen von Dimensionen und Metriken in Ihr Workspace-Projekt, um zu sehen, welche Möglichkeiten Sie haben. Wenn Sie versehentlich eine ungültige Komponente in Ihr Workspace-Projekt ziehen oder einen Schritt zurückgehen möchten, drücken Sie Strg+Z (Windows) oder Befehl+Z (Mac), um die letzte durchgeführte Aktion rückgängig zu machen. Sie können auch mit einem leeren Arbeitsbereich beginnen, indem Sie im Menü oben links auf *[!UICONTROL Projekt] > [!UICONTROL Neu]* klicken. |
| **Wie implementiere ich Analysis Workspace?** | Es ist keine spezielle Implementierung erforderlich. Analysis Workspace steht allen Firmen Customer Journey Analytics zur Verfügung. Es gelten jedoch Standardberechtigungen für Inhalte (wie z. B. Projektkomponenten) sowie für das Kuratieren und Freigeben von Projekten. Weitere Informationen finden Sie unter [Administrations- und Zugriffsanforderungen](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **Wie kann ich die Leistung von Analysis Workspace optimieren?** | Siehe [Leistungsoptimierung](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Fehlerbehebung

**Wenn ich eine Metrik ziehe, wird die Meldung „Ungültige Daten“ angezeigt.**

„Ungültige Daten“ bedeuten, dass Adobe keine Daten mit der Kombination von Dimensionen und Metriken zurückgeben kann, die im Bericht verwendet werden. Beispielsweise können zwei Metriken, die übereinander gestapelt sind, nicht als Daten zurückgegeben werden, da es nicht möglich ist, zwei Metriken in dieser Weise anzuzeigen. Platzieren Sie die Metriken stattdessen nebeneinander.

**Wenn ich eine Metrik ziehe, sehe ich keine tatsächlichen Daten - nur Nullen.**

Wenn Sie einen Workspace-Bericht erfolgreich erstellt haben, aber keine Daten vorhanden sind, können Sie einige Punkte prüfen:

* Überprüfen Sie die Report Suite und stellen Sie sicher, dass sie mit Daten gefüllt ist.
* Wenn Sie ein Segment in Ihrem Bericht angewendet haben, stimmen die Segmentkriterien möglicherweise nicht mit den Daten überein. Versuchen Sie, das Segment zu entfernen oder die Segmentdefinition anzupassen.
* Überprüfen Sie den Datumsbereich oben rechts und stellen Sie sicher, dass er auf einen erwarteten Wert eingestellt ist.
* Navigieren Sie zu Ihrer Website und überprüfen Sie mit dem [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=de-DE), ob Daten erfasst werden.