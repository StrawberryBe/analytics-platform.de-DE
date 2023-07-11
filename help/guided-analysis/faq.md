---
title: Häufig gestellte Fragen zur geführten Analyse
description: Häufig gestellte Fragen zur geführten Analyse.
exl-id: 32bfce23-a59c-45cb-b1cd-82f048fb13d2
feature: Guided Analysis
source-git-commit: d5208a28c9efd6c31ecbfc6ff6b4e44a52f396e8
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 2%

---

# Häufig gestellte Fragen zur geführten Analyse

{{release-limited-testing}}

Häufig gestellte Fragen zur geführten Analyse.

+++**Ist die geführte Analyse für alle verfügbar?**

Nein; Geführte Analyse ist ein kostenpflichtiges Add-on für Customer Journey Analytics. Wenden Sie sich an Ihr Adobe Account Team, wenn Sie mit der Verwendung dieses Add-ons beginnen möchten.

+++

+++**Welche Implementierungsänderungen sind erforderlich, um die geführte Analyse zu verwenden?**

Wenn Sie Analysis Workspace bereits in Customer Journey Analytics verwenden, sind keine zusätzlichen Implementierungsänderungen erforderlich. Geführte Analysen verwenden dieselben Datenansichten und Verbindungen wie Analysis Workspace. Der Prozess zum Einbinden und Verwenden eines beliebigen Projekttyps ist für alle Customer Journey Analytics identisch, einschließlich der geführten Analyse.

+++

+++**Wie stehen Begriffe innerhalb und außerhalb der geführten Analyse zueinander in Beziehung?**

Geführte Analyse verwendet Begriffe, die in der Produktanalysebranche häufiger verwendet werden. Sie können diese Tabelle referenzieren, wenn Sie zwischen der geführten Analyse und Analysis Workspace wechseln.

| Geführter Analysebegriff | Analysis Workspace-Begriff |
| --- | --- |
| Ereignis-   | Metrik |
| Eigenschaft | Dimension |
| Wert | Dimensionselement |
| Segment | Filter |

{style="table-layout:auto"}

+++

+++**Was sind einige Unterschiede in der Vorgehensweise bei Berichten mit Analysis Workspace und Guided Analysis?**

Während die Analyse mit Analysis Workspace und Guided die gleichen zugrunde liegenden Daten verwendet, unterscheidet sich die Art und Weise, wie jedes Tool diese Daten abfragt.

**Analysis Workspace ist ein dimensionszentriertes Erlebnis.** Tabellen bestehen normalerweise aus Dimensionselementzeilen, während Spalten normalerweise Metriken sind. Sie können Filter auf anwenden, um die gewünschten Daten abzurufen.

![Workspace-Struktur](assets/workspace-structure.png)

**Geführte Analyse ist ein ereigniszentriertes Erlebnis.** Visualisierungen konzentrieren sich auf Ereignisse und ergänzen diese Daten mit Dimensionen und Filtern.

![Geführte Analysestruktur](assets/guided-analysis-structure.png)

Betrachten Sie das folgende Beispiel, in dem Sie sich auf Daten rund um die Startseite Ihrer Website konzentrieren. Teams stellen ähnliche Fragen, aber der Analysenansatz kann unterschiedlich sein.

* Ein typischer, dimensionszentrierter Analysis Workspace-Ansatz wäre: &quot;Wie viele Seitenansichten hat die Homepage erhalten?&quot;

  ![Dimension zentriert](assets/dimension-centered.png)

* Ein typischer, ereigniszentrierter Ansatz der geführten Analyse wäre: &quot;Wie viele Benutzer haben die Homepage angesehen?&quot;

  ![Ereignis zentriert](assets/event-centered.png)

Diese Anweisungen veranschaulichen zwei verschiedene Methoden, um je nach Ereignisverwaltungsstrategie denselben Bericht zu erreichen.

+++
