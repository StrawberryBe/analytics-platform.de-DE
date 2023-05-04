---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7737a285c701946dcf92c2610c1918022e05de36
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (CJA) (April 2023)

**Letzte Aktualisierung**: 12. April 2023

Versionen von Customer Journey Analytics basieren auf einem [Modell der kontinuierlichen Bereitstellung](releases.md), das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht. Dementsprechend werden diese Versionshinweise mehrmals im Monat aktualisiert. Bitte überprüfen Sie sie regelmäßig.

## Wichtige Funktionen und Updates

| Funktion | Beschreibung | [Start des Rollouts](/help/release-notes/releases.md) | [Allgemeine Verfügbarkeit](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Zeilen-/Spaltenfilter für Analytics Source Connector-Streaming** | Der Analytics-Source-Connector in Adobe Experience Platform ermöglicht jetzt das Filtern von Analytics-Daten, mit denen Profile in [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) gefüllt werden. Die Filterung auf Zeilenebene hilft, die Anzahl der mit Profilen verknüpften Ereignisse zu reduzieren. Die Filterung auf Spaltenebene hilft, die Vielfalt der Ereignisse selbst zu reduzieren, und ermöglicht es Ihnen so, die Nutzung von Profilberechtigungen zu optimieren. Diese Filterung gilt nur für Daten, die an das Echtzeit-Kundenprofil und an [Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=de) gesendet werden. **Die Filterung wirkt sich nicht auf die Daten aus, die zur Verwendung in Anwendungen wie Customer Journey Analytics an Data Lake gesendet werden**. [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de#filtering-for-profile) | Nicht angegeben | 29. März 2023 |
| **Datenwörterbuch in Analysis Workspace** | Das Datenwörterbuch hilft Benutzenden und Admins, die Komponenten (Dimensionen, Metriken) in ihrer CJA-Umgebung zu verfolgen, zu verwalten und besser zu verstehen. [Weitere Informationen](/help/components/data-dictionary/data-dictionary-overview.md) | 8. März 2023 | 29. März 2023 |
| **Link-Freigabe für Projekte (keine Anmeldung erforderlich)** | <p>Sie können jetzt schreibgeschützte Links zu Analysis Workspace-Projekten für Personen freigeben, die keinen Zugriff auf Adobe Analytics haben. Dazu gehört die Freigabe für Personen außerhalb Ihres Unternehmens oder für Mitarbeiter innerhalb Ihres Unternehmens, die nicht für Customer Journey Analytics bereitgestellt werden. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link)</p> <p>Diese Funktion ist standardmäßig aktiviert und kann vom Systemadministrator deaktiviert werden. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#company-preferences)</p> | 3. Mai 2023 | Juni 2023 |
| **Adobe Product Analytics - Nur privater Beta-Zugriff** | Am 21. März 2023 kündigte Adobe die Adobe Product Analytics an, eine neue Methode zur Interaktion mit kanalübergreifenden Daten und Einblicken in Customer Journey Analytics. Diese neuen Funktionen ermöglichen es Produktteams, Daten und Einblicke in ihr Produkterlebnis mithilfe geführter Analyse-Workflows &#x200B; selbst bereitzustellen. Teams können:<ul><li>Verstehen Sie Muster der Benutzerinteraktion im Zeitverlauf &#x200B;</li><li>Analysieren des Wachstums der &#x200B;</li><li>Identifizieren Sie Reibungspunkte in einer Sequenz von Schritten&#x200B;</li><li>Auswirkungen der Versionen von Funktionen messen&#x200B;</li><li>Entdecken Sie aussagekräftige Segmente, um während des gesamten Lebenszyklus des Journey mit dem Produkt zu interagieren und zu pflegen &#x200B;</li><li>Öffnen Sie in Analysis Workspace für eine tiefere Analyse und Zusammenarbeit mit Analysten und vieles mehr! &#x200B;</li></ul>Wenn Sie CJA-Kunde sind und an der privaten Beta-Phase teilnehmen möchten, wenden Sie sich an Ihr Adobe Account Team. [Weitere Informationen](https://business.adobe.com/products/product-analytics/adobe-product-analytics.html) | Nicht angegeben | 17. Juli 2023 |

{style="table-layout:auto"}

## Fehlerbehebungen in Customer Journey Analytics

AN-313118; AN-313390; AN-314135; AN-316381; AN-316811

## Wichtige Hinweise für CJA-Admins

| Hinweis | Hinweis hinzugefügt oder aktualisiert | Beschreibung |
| --- | --- | --- |
| Nicht angegeben | nicht angegeben | Nicht angegeben |

{style="table-layout:auto"}

## Verwandte Ressourcen

* [Frühere Versionshinweise von CJA für 2023](/help/release-notes/2023.md)
* [Versionshinweise zu Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=de)
* [Versionshinweise zu Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=de)
* [Versionshinweise zu Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=de)
* [Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
