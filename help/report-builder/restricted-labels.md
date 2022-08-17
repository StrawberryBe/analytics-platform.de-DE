---
title: Einschränkungen bei Beschriftungen in Report Builder
description: Beschreibt eingeschränkte Beschriftungen in Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 2%

---

# Eingeschränkte Beschriftungen in Report Builder

Im Allgemeinen werden Data Governance-bezogene Einstellungen in Customer Journey Analytics von Adobe Experience Platform übernommen. Die Integration zwischen CJA und Adobe Experience Platform Data Governance ermöglicht die Kennzeichnung sensibler CJA-Daten und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbezeichnungen und Richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im Arbeitsablauf für CJA-Datenansichten angezeigt werden. Diese Beschriftungen stoppen oder warnen Benutzer, die Metriken und/oder Dimensionen aus sensiblen Feldern erstellen. Informationen zu Datensätzen finden Sie unter [Datensätze - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=de)

Darüber hinaus werden beim Exportieren von Daten aus Customer Journey Analytics (über Reporting, Export, API usw.) Warnhinweise oder Beschriftungen hinzugefügt, die Benutzer darauf hinweisen, dass ein Bericht sensible Informationen enthält, die auf bestimmte Weise behandelt werden müssen.

Durch diese Integration können Sie die Compliance einfacher verwalten. Data Stewards in Ihrem Unternehmen können Richtlinien festlegen, um die Nutzung zu beschränken. Daher können Ihre CJA-Benutzer Daten in dem Bewusstsein, dass sie den von Data Stewards definierten Richtlinien entsprechen, sicherer verwenden.

Weitere Informationen finden Sie unter [Customer Journey Analytics und Data Governance](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)

## Anzeigen eingeschränkter Daten in Report Builder

In Customer Journey Analytics werden zwei von Adoben definierte Richtlinien angezeigt, die sich auf das Reporting, Herunterladen und Freigeben auswirken:

* Analytics-Richtlinie durchsetzen
* Download-Richtlinie durchsetzen

Komponenten, die von diesen Richtlinien betroffen sind, sind grau ausgeblendet. Wenn Sie den Mauszeiger über eine Komponente bewegen, auf die eine Richtlinie angewendet wurde, wird ein Hinweis angezeigt, der Folgendes angibt: **Auf dieses Feld wurden Richtlinien angewendet, die die Verwendung dieser Daten untersagen.** Weitere Informationen finden Sie unter [Beschriftungen und Richtlinien](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html).

![](assets/rb-restricted-label.png)

## Berichte mit eingeschränkten Daten aktualisieren

Wenn ein Report Builder einen Bericht mit Datenelementen erstellt hat, die später eingeschränkt sind, wird bei der Aktualisierung des Berichts eine Fehlermeldung angezeigt.

![](assets/error-restricted-data.png)
