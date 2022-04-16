---
title: Aktuelle Versionshinweise zu Customer Journey Analytics anzeigen
description: Neueste CJA-Versionshinweise
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 56f62d8af96e64a6867e38a9701219bcefc62a6a
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 15%

---

# Aktuelle Versionshinweise zu Customer Journey Analytics (CJA) (April 2022)

>[!NOTE]
>
>Diese Seite enthält Informationen zur Vorabversion, die geändert werden können.

**Letzte Aktualisierung**: 13. April 2022

## Wichtigste Funktionen

| Funktion | Beschreibung | [Zieldatum](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- |
| Dimension-Unterzeichenfolgen | Bietet mehrere Methoden zum Extrahieren des gewünschten Teils einer Zeichenfolge zur Verwendung als Dimensionselemente. Mit dieser Funktion können Sie eine Zeichenfolgendimension auch als Array behandeln, wenn die Zeichenfolge durch Trennzeichen getrennte Werte enthält. [Weitere Informationen](../data-views/component-settings/substring.md) | 20. April 2022 |
| Datenvorbereitung für Analytics Source Connector | Die [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) ist jetzt in die [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) Funktionen von Adobe Experience Platform. Kunden von Adobe Real-time Customer Data Platform (RTCDP), CJA und Adobe Journey Optimizer (AJO) können jetzt die Analytics-Feldergruppe um zusätzliche Feldergruppen erweitern. Sie können außerdem 100+ Data Prep-Operatoren nutzen, um die Analytics-Daten während der Aufnahme in Adobe Experience Platform (AEP) anzureichern. RTCDP-Kunden können jetzt mehrere Data Prep-fähige Report Suites für Profile aktivieren.<p>CJA-Kunden, die mehrere Report Suites über Analytics Source Connector erfassen, können jetzt Spaltenunterschiede zwischen Report Suites aufheben. Wenn beispielsweise &quot;Suchbegriff&quot;in `eVar1` in einer Report Suite und in `eVar2` in einer anderen Report Suite können Sie mithilfe der Datenvorbereitung die Analytics-Feldergruppe um eine neue Spalte erweitern, in der die Werte aus den beiden eVars zusammengeführt werden. | 25. April 2022 |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analytics – Aktualisierungen der Dokumentation](/help/release-notes/doc-changes.md)
