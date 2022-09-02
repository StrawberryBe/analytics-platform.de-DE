---
title: Was sind eingeschränkte Beschriftungen in Report Builder
description: Beschreibt eingeschränkte Beschriftungen in Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: ht
source-wordcount: '311'
ht-degree: 100%

---

# Eingeschränkte Beschriftungen in Report Builder

Im Allgemeinen werden alle Einstellungen in Bezug auf die Data Governance in Customer Journey Analytics von Adobe Experience Platform übernommen. Die Integration zwischen CJA und Adobe Experience Platform Data Governance ermöglicht die Kennzeichnung sensibler CJA-Daten und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbeschriftungen und -richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im CJA-Datenansichts-Workflow angezeigt werden. Diese Beschriftungen stoppen oder warnen Benutzer, die Metriken und/oder Dimensionen aus sensiblen Feldern erstellen. Weiterführende Informationen über Datensätze finden Sie in der [Datensatzübersicht](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=de)

Darüber hinaus werden beim Exportieren von Daten aus Customer Journey Analytics (über Reporting, Export, API usw.) Warnhinweise oder Beschriftungen hinzugefügt, die Benutzer darauf hinweisen, dass ein Bericht sensible Informationen enthält, die auf bestimmte Weise behandelt werden müssen.

Durch diese Integration können Sie die Compliance einfacher verwalten. Datenverantwortliche in Ihrem Unternehmen können Richtlinien festlegen, um die Nutzung zu beschränken. Dadurch können Ihre CJA-Benutzer die Daten sicherer nutzen, da sie wissen, dass sie mit den von den Datenverwaltern festgelegten Richtlinien übereinstimmen.

Weitere Informationen finden Sie unter [Customer Journey Analytics und Data Governance](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=de)

## Anzeigen eingeschränkter Daten in Report Builder

In CJA werden zwei von Adobe definierte Richtlinien angezeigt, die sich auf das Reporting und die Freigabe auswirken:

* Analytics erzwingen-Richtlinie
* Download erzwingen-Richtlinie

Komponenten, die von diesen Richtlinien betroffen sind, sind grau ausgeblendet. Wenn Sie den Mauszeiger über eine Komponente bewegen, auf die eine Richtlinie angewendet wurde, wird ein Hinweis angezeigt, der Folgendes angibt: **Auf dieses Feld wurden Richtlinien angewendet, die die Verwendung dieser Daten untersagen.** Weitere Informationen finden Sie unter [Beschriftungen und Richtlinien](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=de).

![](assets/rb-restricted-label.png)

## Aktualisieren von Berichten mit eingeschränkten Daten

Wenn ein Anwender einen Report Builder-Bericht mit Datenelementen erstellt hat, die später eingeschränkt werden, wird bei der Aktualisierung des Berichts eine Fehlermeldung angezeigt.

![](assets/error-restricted-data.png)
