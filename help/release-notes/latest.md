---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: a6ce6409eb7a4d853d5390cd62f4a9506ee6282a
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 39%

---

# Aktuelle Customer Journey Analytics-Versionshinweise (CJA) (Januar 2023)

**Letzte Aktualisierung**: 23. Januar 2023

Versionen von Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Wichtige Funktionen und Updates

| Funktion | Beschreibung | [Start des Rollouts](/help/release-notes/releases.md) | [Allgemeine Verfügbarkeit](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Aktualisierung auf CJA-Zielgruppen** | Nachdem Sie eine Audience erstellt haben, [Adobe erstellt ein Experience Platformen-Streaming-Segment für jede neue CJA-Zielgruppe](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#after-audience-created). | Nicht angegeben | 23. Januar 2023 |
| **Ordner in Workspace** | Mit Ordnern können Sie Ihre Projekte organisieren und kategorisieren, um den Abruf und den Zugriff zu verbessern. Darüber hinaus wird eine freigegebene **[!UICONTROL Firma]** -Ordner ermöglicht es Administratoren, mühelos Inhalte zu erstellen und für alle Workspace-Benutzer freizugeben. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.html?lang=de) | Nicht angegeben | 11. Januar 2023 |
| **Standard-Landingpage** | Die [neue Landingpage](/help/getting-started/landing.md) die Anfang 2022 eingeführt wurde, wird zum Standarderlebnis für alle Benutzer auf **11. Januar 2023**. Die veraltete Landingpage wird nicht mehr unterstützt und alle müssen das neue Erlebnis verwenden. | Nicht angegeben | 11. Januar 2023 |
| **Seite &quot;Projektmanager&quot;veraltet** | Mit der Veröffentlichung der neuen Landingpage wird die **[!UICONTROL Projektmanager]** gemäß **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Komponenten]**. Die neue Landingpage verfügt über alle Funktionen der alten Seite &quot;Projektmanager&quot;und mehr. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#deprecate-pm-page) | Nicht angegeben | 11. Januar 2023 |
| **Arbeitsmappen in Report Builder planen** | In Customer Journey Analytics können Sie Zeitpläne erstellen, um Arbeitsmappen in regelmäßigen Abständen zu senden. Jetzt können Empfänger regelmäßig die neuesten Aktualisierungen Ihrer Arbeitsmappen erhalten. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/schedule-reportbuilder.html) | Nicht angegeben | 11. Januar 2023 |
| **Automatisches Speichern neuer Projekte** | Analysis Workspace speichert jetzt automatisch neu erstellte Projekte. Wenn Sie aus irgendeinem Grund unerwartet den Zugriff auf ein neu erstelltes Projekt verlieren, bevor Sie es manuell speichern, ist jetzt eine Wiederherstellungsversion Ihres Projekts verfügbar. Zuvor wurden Projekte erst automatisch gespeichert, nachdem sie zuvor manuell gespeichert wurden. [Weitere Informationen](/help/analysis-workspace/build-workspace-project/save-projects.md) | Nicht angegeben | 11. Januar 2023 |
| **Erweiterte Benutzereinstellungen** | Sie können jetzt zusätzliche Voreinstellungen auf Benutzerebene konfigurieren (in [!UICONTROL Komponenten] > [!UICONTROL Voreinstellungen]). Wenn Sie die Benutzereinstellungen festlegen, erstreckt sich Ihre Auswahl über Ihre Projekte, Tabellen und Visualisierungen. Die Seite Voreinstellungen enthält jetzt die folgenden neuen Registerkarten, von denen jede viele neue Konfigurationsoptionen enthält:<ul><li>Freiformtabelle</li><li>Visualisierungen >/li></ul>  Darüber hinaus sind jetzt weitere Voreinstellungen auf der **[!UICONTROL Allgemein]** und **[!UICONTROL Projekt]** Registerkarten.<p>Zuvor waren viele dieser Voreinstellungen nur für einzelne Projekte, Tabellen und Visualisierungen konfigurierbar. [Weitere Informationen](/help/analysis-workspace/user-preferences.md) | Nicht angegeben | 11. Januar 2023 |

{style=&quot;table-layout:auto&quot;}

## Fehlerbehebungen

AN-287349; AN-301684; AN-305491; AN-305769; AN-307912

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| **Verbessertes IP-Geolokalisierungs-Mapping** | 29. September 2022 | Der Anbieter von IP-Suchen für Adobe, Digital Element, aktualisiert auf einen neuen verbesserten Datensatz (NetAcuity Pulse) für die Geolokalisierung von IPs. Adobe Analytics hat die Annahme dieses neuen Datensatzes auf **11. Januar 2023**. Die neue Datenbank wird genauer sein als frühere Versionen. Einige Geolokalisierungen von IPs werden sich ändern/verbessern, wenn die neue Datenbank übernommen wird.<p> CJA-Daten, die über den [!UICONTROL Analytics Source Connector] bereitgestellt werden, nutzen ebenfalls automatisch die neuen Mappings. |

{style=&quot;table-layout:auto&quot;}


## Verwandte Ressourcen

* [Frühere Versionshinweise von CJA für 2022](/help/release-notes/2022.md)

* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)

* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)

* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)

* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
