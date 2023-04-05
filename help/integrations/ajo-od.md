---
title: Integrieren der Adobe Journey Optimizer-Entscheidungsverwaltung mit Customer Journey Analytics (CJA)
description: Einbinden von durch die Entscheidungsverwaltung von Adobe Journey Optimizer generierten Daten und Analysieren mit Analysis Workspace in Customer Journey Analytics.
source-git-commit: f9ee0db464c49339bc36b144e18ef4aea4f4f033
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 19%

---

# Integrieren der Entscheidungsverwaltung in Customer Journey Analytics


Adobe Journey Optimizer [Entscheidungsverwaltung](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=en) erleichtert die Personalisierung mit einer zentralen Bibliothek von Marketing-Angeboten und einer Entscheidungs-Engine, die Regeln und Begrenzungen auf von Adobe Experience Platform erstellte umfangreiche Echtzeitprofile anwendet, damit Sie Ihren Kunden zum richtigen Zeitpunkt das richtige Angebot unterbreiten können.

Die Entscheidungsverwaltung ist Teil von und in Adobe Journey Optimizer (AJO) integriert. Es kann auch unabhängig von Journey und Kampagnen verwendet werden, die in AJO definiert sind, und zwar mithilfe seines umfangreichen [API](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/api-reference/getting-started.html?lang=en) unterstützen.

Sie können von der Entscheidungsverwaltung generierte Daten importieren, um eine erweiterte Analyse in Customer Journey Analytics (CJA) durchzuführen, indem Sie die folgenden Schritte ausführen:

## Senden von Daten aus der Entscheidungsverwaltung an Adobe Experience Platform

Adobe Experience Platform dient als zentrale Datenquelle und Verknüpfung zwischen Entscheidungsverwaltung und Customer Journey Analytics. Daten aus der Entscheidungsverwaltung werden in der Experience Platform erfasst **automatisch** oder als Teil von **explizit gesendete Erlebnisereignisse** (z. B. Impressionen oder Klicks). Siehe [Erste Schritte mit der Datenerfassung](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/collect-event-data/data-collection.html?lang=en) für weitere Details.

## Verbindung herstellen

Sobald sich die Entscheidungsverwaltungsdaten in Adobe Experience Platform befinden, können Sie eine [Verbindung](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de) basierend auf Ihren Entscheidungsmanagement-Datensätzen. Alternativ können Sie einer vorhandenen Verbindung Entscheidungsverwaltungsdatensätze hinzufügen.

Wählen Sie die folgenden Datensätze aus und konfigurieren Sie sie:

| Datensatz | Typ des Datensatzes | Verbindungseinstellungen | Beschreibung |
| --- | --- | --- | --- |
| ODE DecisonEvents - _Sandbox_ Entscheidungsfindung | Ereignis-   | Personen-ID: `IdentityMap` | Enthält automatisch generierte Daten für Entscheidungsereignisse in der Entscheidungsverwaltung. _Sandbox_ bezieht sich auf den spezifischen Sandbox-Namen. |
| Datensatz mit AJO-Nachrichten-Feedback-Ereignissen | Ereignis-   | Personen-ID: `IdentityMap` | Enthält Ereignisse zum Nachrichtenversand. |
| AJO-E-Mail-Tracking-Erlebnisdatensatz | Ereignis-   | Personen-ID: `IdentityMap` | Enthält E-Mail-Tracking-Ereignisse. |
| AJO Push Tracking Experience Event Datensatz | Ereignis-   | Personen-ID: `IdentityMap` | Enthält Push-Tracking-Ereignisse. |
| AJO-Entitätsdatensatz | Suche | Schlüssel: `_id`<br>Übereinstimmungsschlüssel: `_experience.decisioning.propositions.`<br>`scopeDetails.correlationID` | Enthält Classifications, die Journey- und Campaign-Metadaten mit allen AJO-Ereignisdaten verknüpfen. |

{style="table-layout:auto"}

## Datenansicht erstellen

Nachdem eine Verbindung erstellt wurde, können Sie eine oder mehrere [Datenansichten](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=de) , um die in CJA verfügbaren gewünschten Dimensionen und Metriken zu konfigurieren.

>[!NOTE]
>
>Die Datenabweichungen zwischen AJO und CJA betragen in der Regel weniger als 1-2 %. Größere Abweichungen sind bei Daten möglich, die innerhalb der letzten zwei Stunden erfasst wurden. Verwenden Sie Datumsbereiche, die den heutigen Tag ausschließen, um Abweichungen aufgrund der Verarbeitungszeit zu vermeiden.

### Dimensionen konfigurieren

Sie können die folgenden Dimensionen in einer Datenansicht erstellen, um eine ungefähre Parität mit ähnlichen Dimensionen in der Entscheidungsverwaltung zu erreichen. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichts-Manager für Details zu den Anpassungsoptionen für Dimensionen.

| Dimension | Schemaelement | Einstellungen der Komponente |
| --- | --- | --- |
| Aktivitätsname | `_experience.decisioning.`<br/>`propositionDetails.activity.name` | Komponententyp: Dimension |
| Container-ID | `_experience.decisioning.containerID` | Komponententyp: Dimension |
| Korrelationskennung | `_experience.decisioning.`<br/>`propositions.scopeDetails.correlationID` | Komponententyp: Dimension |
| Name der Entscheidungsoption | `_experience.decisioning.`<br/>`propositionDetails.selections.name` | Komponententyp: Dimension |
| Optionsname für Fallback-Entscheidung | `_experience.decisioning.`<br/>`propositionDetails.fallback.name` | Komponententyp: Dimension |
| Name der Platzierung | `_experience.decisioning.`<br/>`propositionDetails.placement.name` | Komponententyp: Dimension |

{style="table-layout:auto"}


### Metriken konfigurieren

Sie können die folgenden Metriken in einer Datenansicht erstellen, um eine ungefähre Parität mit ähnlichen Metriken in der Entscheidungsverwaltung zu erreichen. Siehe [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) im Datenansichts-Manager für weitere Informationen zu den Anpassungsoptionen von Metriken.

| Metrik | Beschreibung | Schemaelement | Einstellungen der Komponente |
| --- | --- | --- | --- |
| Ereignistyp (umbenennen, um auf ein bestimmtes Ereignis zu verweisen, z. B. `Feedback` für `message.feedback`) [1] | Betrag eines bestimmten Ereignistyps | `eventType` | Komponententyp: Metrik<br/>**[!UICONTROL Einschlusswerte festlegen ]**: on<br/>**[!UICONTROL Übereinstimmung]**: [!UICONTROL Wenn alle Kriterien erfüllt sind]<br/>**[!UICONTROL Kriterien ]**:**[!UICONTROL  Gleich ]**`message.feedback` |
| Entscheidungsoptionen-Bewertung | Berechneter Wert für eine Entscheidungsoption im Kontext eines einzelnen Umfangs. | `_experience.decisioning.`<br/>`propositionDetails.selections.score` | Komponententyp: Metrik |
| Bewertung der Fallback-Entscheidungsoptionen | Berechneter Wert für eine Fallback-Entscheidungsoption im Kontext eines einzelnen Umfangs. | `_experience.decisioning.`<br/>`propositionDetails.fallback.score` | Komponententyp: Metrik |
| Angebote verwerfen | Die Anzahl der Angebote, die ohne andere direkte Interaktion verworfen oder abgelehnt wurden. | `_experience.decisioning.`<br/>`propositionEventType.display` | Komponententyp: Metrik |
| Angebotsanzeige | Die Anzahl der dem Profil angezeigten Angebote. | `_experience.decisioning.`<br/>`propositionEventType.display` | Komponententyp: Metrik |
| Angebote Interact | Die Anzahl der dem Profil angezeigten Angebote. | `_experience.decisioning.`<br/>`propositionEventType.interact` | Komponententyp: Metrik |
| Angebotsversand | Die Anzahl der an das Profil gesendeten Angebote. | `_experience.decisioning.`<br/>`propositionEventType.send` | Komponententyp: Metrik |
| Trigger von Angeboten | Die Anzahl der vom Client-SDK ausgewählten Angebote. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Komponententyp: Metrik |
| Abmeldung von Angeboten | Die Anzahl der Angebote, die nach Profil angefordert wurden, wird in Zukunft nicht angezeigt. | `_experience.decisioning.`<br/>`propositionEventType.trigger` | Komponententyp: Metrik |

{style="table-layout:auto"}
[1] Sie können für die verschiedenen verfügbaren Ereignistypen mehrere Metriken definieren. Siehe [Komponenteneinstellungen für Ausschlusswerte einschließen](/help/data-views/component-settings/include-exclude-values.md) für weitere Informationen.
