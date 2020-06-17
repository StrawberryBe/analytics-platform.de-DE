---
description: Häufig gestellte Fragen zu Workspace
title: Häufig gestellte Fragen und Fehlerbehebung in Workspace
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 56%

---


# Häufig gestellte Fragen

>[!NOTE] Sie sehen sich die Dokumentation zum Analysis Workspace in Customer Journey Analytics an. Das Funktionssatz unterscheidet sich geringfügig von dem [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Mehr Infos...](/help/getting-started/cja-aa.md)

| Frage | Antwort |
|--- |--- |
| Was sind die Voraussetzungen für die Verwendung von Analysis Workspace? | Die Verwendung von Analysis Workspace erfordert eine Implementierung des funktionierenden Customer Journey Analytics. Vergewissern Sie sich, dass Ihr Unternehmen Daten an die Adobe Experience Platform sendet, bevor Sie das Tool verwenden. |
| Welche Administrations- und Zugriffsanforderungen gibt es für Analysis Workspace? | Siehe [Administrationsanforderungen](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Wirkt sich die Verwendung von Analysis Workspace auf die Datenerfassung aus? | Da Analysis Workspace ein Berichtswerkzeug ist, hat dies keine Auswirkungen auf die Datenerfassung. Komponenten wahllos in ein Projekt zu ziehen, um zu sehen, was funktioniert, hat keine weiteren Folgen. Ziehen Sie verschiedene Kombinationen von Dimensionen und Metriken in Ihr Workspace-Projekt, um zu sehen, welche Möglichkeiten Sie haben. Wenn Sie versehentlich eine ungültige Komponente in Ihr Workspace-Projekt ziehen oder einen Schritt zurückgehen möchten, drücken Sie Strg+Z (Windows) oder Befehl+Z (Mac), um die letzte durchgeführte Aktion rückgängig zu machen. Sie können auch mit einem leeren Arbeitsbereich beginnen, indem Sie im Menü oben links auf *[!UICONTROL Projekt] > [!UICONTROL Neu]* klicken. |
| Wie wird der Analysis Workspace implementiert? | Es ist keine spezielle Implementierung erforderlich. Analysis Workspace steht allen Firmen Customer Journey Analytics zur Verfügung. Es gelten jedoch Standardberechtigungen für Inhalte (wie z. B. Projektkomponenten) sowie für das Kuratieren und Freigeben von Projekten. Weitere Informationen finden Sie unter [Administrations- und Zugriffsanforderungen](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| Wie kann ich die Leistung von Analysis Workspace optimieren? | Siehe [Leistungsoptimierung](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |

## Fehlerbehebung

**Wenn ich eine Metrik ziehe, wird die Meldung „Ungültige Daten“ angezeigt.**

„Ungültige Daten“ bedeuten, dass Adobe keine Daten mit der Kombination von Dimensionen und Metriken zurückgeben kann, die im Bericht verwendet werden. Beispielsweise können zwei Metriken, die übereinander gestapelt sind, nicht als Daten zurückgegeben werden, da es nicht möglich ist, zwei Metriken in dieser Weise anzuzeigen. Platzieren Sie die Metriken stattdessen nebeneinander.

**Wenn ich eine Metrik ziehe, sehe ich keine tatsächlichen Daten - nur Nullen.**

Wenn Sie erfolgreich einen Arbeitsbereichbericht erstellt haben, aber keine Daten vorhanden sind, können Sie Folgendes überprüfen:

* Dublette überprüft die Report Suite und stellt sicher, dass sie mit Daten gefüllt ist.
* Wenn Sie ein Segment in Ihrem Bericht angewendet haben, stimmen die Segmentkriterien möglicherweise nicht mit den Daten überein. Versuchen Sie, das Segment zu entfernen oder die Segmentdefinition anzupassen.
* Überprüfen Sie den Datumsbereich in der oberen rechten Ecke und stellen Sie sicher, dass er auf einen erwarteten Wert eingestellt ist.
* Navigate to your website and use the [Debugger](https://docs.adobe.com/content/help/de-DE/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.