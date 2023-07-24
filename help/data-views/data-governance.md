---
title: Beschriftungen und Richtlinien
description: Erfahren Sie, wie sich in Adobe Experience Platform definierte Datenbezeichnungen und Richtlinien auf Datenansichten und Berichte in Customer Journey Analytics auswirken.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
source-git-commit: d14db99f6cf597c4b62cdb148853b0f11503eaa1
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 58%

---

# Beschriftungen und Richtlinien

Wenn Sie einen Datensatz in Experience Platform erstellen, können Sie [Datennutzungsbezeichnungen](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=de) für einige oder alle Elemente im Datensatz erstellen. Sie können diese Beschriftungen und Richtlinien in Customer Journey Analytics anzeigen.

Die folgenden Beschriftungen sind für den Customer Journey Analytics von besonderem Interesse:

* Die `C8` Bezeichnung – **[!UICONTROL Keine Messung]**. Diese Bezeichnung bedeutet, dass Daten nicht für Analysen auf den Websites oder Apps Ihres Unternehmens verwendet werden können.

* Die `C12` Bezeichnung – **[!UICONTROL Kein allgemeiner Datenexport]**. Auf diese Weise gekennzeichnete Schemafelder können nicht aus dem Customer Journey Analytics exportiert oder heruntergeladen werden (über Berichte, Export, API usw.)

>[!NOTE]
>
>Datennutzungsbezeichnungen werden nicht automatisch in zugeordnete Datensätze übertragen. Sie können jedoch manuell hinzugefügt werden.

Die Beschriftung an sich bedeutet nicht, dass diese Datennutzungsbezeichnungen erzwungen werden. Dafür werden Richtlinien verwendet. Sie erstellen Ihre Richtlinien mithilfe der Variablen [Experience Platform-Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=de) oder über die [Policy Service-API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=de) in der Experience Platform.

In Customer Journey Analytics werden zwei von der Adobe definierte Richtlinien angezeigt, die sich auf die Berichterstellung und Download-/Freigabe auswirken:

* **[!UICONTROL Analytics erzwingen]**-Richtlinie
* **[!UICONTROL Download erzwingen]**-Richtlinie

## Anzeigen von Datenbeschriftungen in Customer Journey Analytics-Datenansichten

Datenbeschriftungen, die in Experience Platform erstellt wurden, werden an drei Stellen in der Benutzeroberfläche der Datenansichten angezeigt:

| Standort | Beschreibung |
| --- | --- |
| Informationsschaltfläche in einem Schemafeld | Durch Klicken auf diese Schaltfläche wird angegeben, welche [!UICONTROL Datennutzungsbezeichnungen] derzeit auf ein Feld angewendet werden:<p>![](assets/data-label-left.png) |
| Rechte Leiste unter [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) | Alle [!UICONTROL Datennutzungsbezeichnungen] sind hier aufgeführt:<p>![](assets/data-label-right.png) |
| Hinzufügen von Datenbeschriftungen als Spalte | Sie können [!UICONTROL Datennutzungsbezeichnungen] als Spalte zu den [!UICONTROL Enthaltene Komponenten] Spalten in Datenansichten hinzufügen. Klicken Sie einfach auf das Symbol für die Spaltenauswahl und wählen Sie **[!UICONTROL Datennutzungsbezeichnungen]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtern nach Data Governance-Beschriftungen in Datenansichten

Klicken Sie im Datenansichtseditor auf die [!UICONTROL filter] Symbol im linken Pfad und Filtern Sie die Datenansichtskomponenten nach **[!UICONTROL Data Governance]** und Art der **[!UICONTROL Titel]**:

![](assets/filter-labels.png)

Klicken **[!UICONTROL Anwenden]**, um zu sehen, an welche Komponenten Beschriftungen angehängt sind.

## Filtern nach Data Governance-Richtlinien in Datenansichten

Sie können überprüfen, ob eine Richtlinie aktiviert ist, die die Verwendung bestimmter Datenansichtselemente des Customer Journey Analytics für Analysen oder Exporte blockiert.

Klicken Sie erneut auf die [!UICONTROL filter] Symbol in der linken Leiste und unter **[!UICONTROL Data Governance]** klicken **[!UICONTROL Richtlinien]**:

![](assets/filter-policies.png)

Klicken Sie auf **[!UICONTROL Anwenden]**, um zu sehen, welche Richtlinien aktiviert sind.

## Wie sich aktivierte Richtlinien auf Datenansichten auswirken

Wenn die Richtlinien **[!UICONTROL Analytics erzwingen]** oder **[!UICONTROL Download erzwingen]** aktiviert sind, können die Schemakomponenten, denen bestimmte Datenbeschriftungen (wie C8 oder C12) zugeordnet sind, nicht zu Datenansichten hinzugefügt werden.

Diese Komponenten sind in der linken Liste [!UICONTROL Schemafelder]-Liste ausgegraut:

![](assets/component-greyed.png)

Sie können auch keine Datensicht speichern, die gesperrte Felder enthält.

>[!MORELIKETHIS]
>[Herunterladen sensibler Daten](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[Was sind eingeschränkte Beschriftungen in Report Builder?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=de)


