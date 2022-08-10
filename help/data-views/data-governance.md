---
title: Beschriftungen und Richtlinien
description: Erfahren Sie, wie sich in AEP definierte Datenbezeichnungen und Richtlinien auf Datenansichten und Berichte in CJA auswirken.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: a28247e861e2f8853a6e2d2b81e7f6ed221caec0
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 2%

---

# Beschriftungen und Richtlinien

>[!NOTE]
>
>Diese Funktion wird derzeit [eingeschränkt getestet](/help/release-notes/releases.md).

Wenn Sie einen Datensatz in Experience Platform erstellen, können Sie [Datennutzungsbezeichnungen](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) für einige oder alle Elemente im Datensatz. Bisher wurden diese Beschriftungen nicht in CJA verfügbar gemacht. Mit dieser Version können Sie diese Beschriftungen in CJA anzeigen. Für CJA sind die folgenden Beschriftungen von besonderem Interesse:

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
| Hinzufügen von Datenbeschriftungen als Spalte | Sie können [!UICONTROL Datenbeschriftungen] als Spalte zum [!UICONTROL Enthaltene Komponenten] Spalten in Datenansichten. Klicken Sie einfach auf das Symbol für die Spaltenauswahl und wählen Sie **[!UICONTROL Datennutzungsbezeichnungen]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## Filtern nach Data Governance-Beschriftungen in Datenansichten

Klicken Sie im Datenansichtseditor auf das Filtersymbol im linken Bereich und filtern Sie die Datenansichtskomponenten nach den Data Governance-Beschriftungen:

![](assets/filter-labels.png)

Klicken **[!UICONTROL Anwenden]** , um zu sehen, an welche Komponenten Beschriftungen angehängt sind.

## Filtern nach Data Governance-Richtlinien in Datenansichten

Sie können überprüfen, ob eine Richtlinie aktiviert ist, die die Verwendung bestimmter CJA-Datenansichtselemente für Analyse- oder Exportzwecke blockiert.

Klicken Sie erneut auf das Filtersymbol in der linken Leiste und unter Data Governance auf Richtlinien:

![](assets/filter-policies.png)

Klicken **[!UICONTROL Anwenden]** , um zu sehen, welche Richtlinien aktiviert sind.

## Die [!UICONTROL Analytics erzwingen] Richtlinien wirken sich auf Workspace-Projekte aus

Wenn diese Richtlinie aktiviert ist, können die Schemafelder, denen bestimmte Datenbezeichnungen (z. B. C8) zugeordnet sind, nicht für Analysezwecke in CJA Workspace verwendet werden.

Für die Berichterstellung bedeutet dies, dass

* Sie können diese Felder nicht zu Datenansichten hinzufügen. Sie sind in der linken Leiste ausgegraut. [!UICONTROL Schemafelder] Liste.
* Eine Datenansicht mit gesperrten Feldern kann nicht gespeichert werden.

Wenn Sie versuchen, Workspace-Analysen für Datenansichten durchzuführen, die für Analysen verbotene Elemente enthalten, erhalten Sie einen ähnlichen Hinweis:

![](assets/policy-enforce.png)

Bei einzelnen Komponenten ähnelt die Nachricht Folgendem:

![](assets/policy-enforce2.png)

## Die [!UICONTROL Download durchsetzen] Richtlinien wirken sich auf Workspace-Projekte aus

Wenn diese Richtlinie aktiviert ist, werden die sensiblen Felder durch Exporte oder Downloads (z. B. E-Mail-Versand oder Freigabe-PDFs) von Workspace-Projekten gehasht. Sie können diese Felder weiterhin in Workspace analysieren. Wenn Sie jedoch versuchen, ein Projekt per E-Mail zu versenden oder auf andere Weise freizugeben, werden die blockierten Felder in der PDF-Datei als Hash-Elemente angezeigt.

Fügen Sie hier einen Screenshot hinzu.

## Anzeigen von Bezeichnungen in Report Builder

Siehe _diesem Abschnitt_ für weitere Informationen. (Link zum Dokument von Christine)
