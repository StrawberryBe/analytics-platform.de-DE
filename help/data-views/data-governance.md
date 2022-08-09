---
title: CJA-Unterstützung für Adobe Experience Platform Data Governance
description: null
source-git-commit: 40b87cd748717124a355b030b17b1e3b6f94a99e
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 0%

---


# CJA-Unterstützung für Adobe Experience Platform Data Governance

Die Integration zwischen CJA und [Adobe Experience Platform Data Governance](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) ermöglicht die Kennzeichnung sensibler CJA-Daten und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbezeichnungen und Richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im Arbeitsablauf für CJA-Datenansichten angezeigt werden. Diese Beschriftungen stoppen oder warnen Benutzer, die Metriken und/oder Dimensionen aus sensiblen Feldern erstellen.

Darüber hinaus werden beim Exportieren von Daten aus Customer Journey Analytics (über Reporting, Export, API usw.) Warnhinweise oder Beschriftungen hinzugefügt, die Benutzer darauf hinweisen, dass ein Bericht sensible Informationen enthält, die auf bestimmte Weise behandelt werden müssen.

Durch diese Integration können Sie die Compliance einfacher verwalten. Data Stewards in Ihrem Unternehmen können Richtlinien festlegen, um die Nutzung zu beschränken. Daher können Ihre CJA-Benutzer Daten in dem Bewusstsein, dass sie den von Data Stewards definierten Richtlinien entsprechen, sicherer verwenden.

## Beschriftung und Richtlinien in Adobe Experience Platform

Wenn Sie einen Datensatz in Experience Platform erstellen, können Sie [Datennutzungsbezeichnungen](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) für einige oder alle Elemente im Datensatz. Bisher wurden diese Beschriftungen nicht in CJA verfügbar gemacht. Mit dieser Version können Sie diese Beschriftungen in CJA anzeigen. Von besonderem Interesse für CJA ist das C8-Etikett, in dem steht: &quot;Daten können nicht zur Messung der Websites oder Apps Ihres Unternehmens verwendet werden&quot;.

Die Beschriftung an sich bedeutet nicht, dass diese Datennutzungsbezeichnungen erzwungen werden. Dafür werden Richtlinien verwendet. Sie können Ihre Richtlinien mithilfe der Variablen [Policy Service-API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) in der Experience Platform.

Richtlinien haben zwei Komponenten: die Datenbeschriftung und eine Marketing-Aktion, die Verbraucher im Zusammenhang mit eingeschränkten Datennutzungsrichtlinien ausführen können. Im Kontext von CJA werden zwei Adoben definiert [Marketing-Aktionen](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) sind wichtig:

* Analytics: Verwendung von Daten zu Analysezwecken, z. B. zur Messung, Analyse und Berichterstellung zur Nutzung der Sites oder Apps Ihres Unternehmens durch die Verbraucher.

* Exportieren dieser Daten aus der Adobe-Umgebung, z. B. zum Exportieren von Daten an einen Drittanbieter.

Sie verknüpfen Beschriftungen und Marketing-Aktionen mit einer Richtlinie und aktivieren dann die Richtlinie. Die Richtlinie verwendet den Titel und die Marketing-Aktion und sagt: diese Einschränkung durchsetzen. In CJA werden zwei von Adoben definierte Richtlinien angezeigt:

* Analytics-Richtlinie
* Download-Richtlinie

## Anzeigen von Datenbeschriftungen in CJA-Datenansichten

Datenbeschriftungen, die in Experience Platform erstellt wurden, werden an drei Stellen in der Benutzeroberfläche &quot;Datenansichten&quot;angezeigt:

| Standort | Beschreibung |
| --- | --- |
| Info-Schaltfläche in einem Schemafeld | Wenn Sie auf diese Schaltfläche klicken, wird angezeigt, welche Datennutzungsbezeichnungen derzeit für ein Feld gelten:<p>![](assets/data-label-left.png) |
| Rechte Leiste unter [Komponenteneinstellungen](/help/data-views/component-settings/overview.md) | Sämtliche Datennutzungsbezeichnungen sind hier aufgeführt:<p>![](assets/data-label-right.png) |
| Hinzufügen von Datenbeschriftungen als Spalte | Sie können Datenbezeichnungen als Spalte zu den Spalten Einbezogene Komponenten in Datenansichten hinzufügen. Klicken Sie einfach auf das Spaltenauswahlsymbol und wählen Sie Datennutzungsbezeichnungen aus:<p>![](assets/data-label-column.png) |

### Filtern nach Data Governance-Beschriftungen in CJA

Klicken Sie im Datenansichtseditor auf das Filtersymbol im linken Bereich und filtern Sie die Datenansichtskomponenten nach Data Governance-Beschriftungen:

![](assets/filter-labels.png)

### Filtern nach Data Governance-Richtlinien in CJA

Sie können überprüfen, ob eine Richtlinie aktiviert ist, die die Verwendung bestimmter CJA-Datenansichtselemente für Analyse- oder Exportzwecke blockiert.

Klicken Sie erneut auf das Filtersymbol in der linken Leiste und unter Data Governance auf Richtlinien:

![](assets/filter-policies.png)

Wenn die Richtlinie aktiviert ist, können die Schemafelder, denen bestimmte Datenbezeichnungen (z. B. C8) zugeordnet sind, nicht für Analyse- oder Download-Zwecke (z. B. zum Senden von E-Mails oder Freigeben von PDF-Dateien) in CJA Workspace verwendet werden.

Beachten Sie Folgendes

* Sie dürfen sie nicht zu Datenansichten hinzufügen. Diese Felder werden in der Liste der Schemafelder in der linken Leiste grau dargestellt.
* Eine Datenansicht mit gesperrten Feldern kann nicht gespeichert werden.


