---
title: Beschriftungen und Richtlinien
description: Erfahren Sie, wie sich in AEP definierte Datenbezeichnungen und Richtlinien auf Datenansichten und Berichte in CJA auswirken.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: b135175e0276ab26514d1c785793feb817c09898
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 2%

---

# Beschriftungen und Richtlinien

>[!NOTE]
>
>Diese Funktion wird derzeit [eingeschränkt getestet](/help/release-notes/releases.md).

Wenn Sie einen Datensatz in Experience Platform erstellen, können Sie [Datennutzungsbezeichnungen](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) für einige oder alle Elemente im Datensatz. Bisher wurden diese Beschriftungen nicht in CJA verfügbar gemacht. Mit dieser Version können Sie diese Beschriftungen und Richtlinien in CJA anzeigen.

Für CJA sind die folgenden Beschriftungen von besonderem Interesse:

* Die `C8` label - **[!UICONTROL Keine Messung]**. Diese Bezeichnung bedeutet, dass Daten nicht für Analysen auf den Websites oder Apps Ihres Unternehmens verwendet werden können.

* Die `C12` label - **[!UICONTROL Kein allgemeiner Datenexport]**. Auf diese Weise gekennzeichnete Schemafelder können nicht aus CJA exportiert oder heruntergeladen werden (über Reporting, Export, API usw.)

Die Beschriftung an sich bedeutet nicht, dass diese Datennutzungsbezeichnungen erzwungen werden. Dafür werden Richtlinien verwendet. Sie können Ihre Richtlinien mithilfe der Variablen [Policy Service-API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) in der Experience Platform.

In CJA werden zwei von Adoben definierte Richtlinien angezeigt, die sich auf die Berichterstellung und Download/Freigabe auswirken:

* **[!UICONTROL Analytics erzwingen]** policy
* **[!UICONTROL Download durchsetzen]** policy

## Anzeigen von Datenbeschriftungen in CJA-Datenansichten

Datenbeschriftungen, die in Experience Platform erstellt wurden, werden an drei Stellen in der Benutzeroberfläche &quot;Datenansichten&quot;angezeigt:

| Standort | Beschreibung |
| --- | --- |
| Info-Schaltfläche in einem Schemafeld | Durch Klicken auf diese Schaltfläche wird angegeben, [!UICONTROL Datennutzungsbezeichnungen] wird derzeit auf ein Feld angewendet:<p>![](assets/data-label-left.png) |
| Rechte Leiste unter [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) | Alle [!UICONTROL Datennutzungsbezeichnungen] sind hier aufgeführt:<p>![](assets/data-label-right.png) |
| Hinzufügen von Datenbeschriftungen als Spalte | Sie können [!UICONTROL Datennutzungsbezeichnungen] als Spalte zum [!UICONTROL Enthaltene Komponenten] Spalten in Datenansichten. Klicken Sie einfach auf das Symbol für die Spaltenauswahl und wählen Sie **[!UICONTROL Datennutzungsbezeichnungen]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## Filtern nach Data Governance-Beschriftungen in Datenansichten

Klicken Sie im Datenansichtseditor auf das Filtersymbol im linken Bereich und filtern Sie die Datenansichtskomponenten nach **[!UICONTROL Data Governance]** und Art der **[!UICONTROL Titel]**:

![](assets/filter-labels.png)

Klicken **[!UICONTROL Anwenden]** , um zu sehen, an welche Komponenten Beschriftungen angehängt sind.

## Filtern nach Data Governance-Richtlinien in Datenansichten

Sie können überprüfen, ob eine Richtlinie aktiviert ist, die die Verwendung bestimmter CJA-Datenansichtselemente für Analyse- oder Exportzwecke blockiert.

Klicken Sie erneut auf das Symbol Filter in der linken Leiste und unter **[!UICONTROL Data Governance]** klicken **[!UICONTROL Richtlinien]**:

![](assets/filter-policies.png)

Klicken **[!UICONTROL Anwenden]** , um zu sehen, welche Richtlinien aktiviert sind.

## Auswirkungen von aktivierten Richtlinien auf Datenansichten

Wenn die Variable **[!UICONTROL Analytics erzwingen]** oder **[!UICONTROL Download durchsetzen]** Richtlinien aktiviert sind, können Schemakomponenten, denen bestimmte Datenbezeichnungen (wie C8 oder C12) zugeordnet sind, nicht zu Datenansichten hinzugefügt werden.

Diese Komponenten sind in der linken Leiste grau dargestellt [!UICONTROL Schemafelder] list:

![](assets/component-greyed.png)

Sie können auch keine Datenansicht speichern, in der Felder blockiert sind.

>[!MORELIKETHIS]
>[Herunterladen sensibler Daten](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[Was sind eingeschränkte Beschriftungen in Report Builder?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=en)

