---
title: CJA-Zugriffssteuerung
description: Informationen über die Implementierung der Zugriffskontrolle in CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: ee3196b78e1cf613446840e8cde1fac565d0f2b7
workflow-type: ht
source-wordcount: '936'
ht-degree: 100%

---

# CJA-Zugriffssteuerung

Customer Journey Analytics (CJA) wird durch drei Zugriffsebenen oder drei Rollen gesteuert: Produktadministrator, Produktprofil-Administrator und Anwenderzugriff. In diesem Thema werden diese Rollen ausführlicher erläutert.

Darüber hinaus werden granulare Möglichkeiten zur Einschränkung des Zugriffs behandelt, beispielsweise die Workspace-Kuratierung und die Zugriffskontrolle auf Zeilen- und Werteebene.

## Produktadministrator-Rolle

Produktadministratoren sind berechtigt, alle in Customer Journey Analytics erforderlichen Aufgaben auszuführen. Sie müssen dem **Customer Journey Analytics-Produktprofil** in der [Admin Console](https://adminconsole.adobe.com/enterprise/) unter [!UICONTROL Customer Journey Analytics] > Registerkarte [!UICONTROL Admins] > [!UICONTROL Admin hinzufügen] als Produkt-Admin hinzugefügt werden. Produktadmins erhalten die folgenden Berechtigungen:

* Erstellen/Aktualisieren/Löschen von Verbindungen oder Datenansichten
* Aktualisieren/Löschen von Projekten, Filtern, Berechnungsmetriken, Zielgruppen, Kommentaren oder von anderen Benutzenden erstellten Filtern
* Freigeben von Workspace-Projekten für alle Benutzenden

Ein Produkt-Admin in Customer Journey Analytics zu werden, reicht allein nicht aus, um eine [Verbindung](/help/connections/overview.md) zu erstellen, zu aktualisieren oder zu löschen. Um eine Verbindung zu einem Experience Platform-Datensatz herzustellen, benötigen Sie auch Experience Platform-Berechtigungen. Insbesondere müssen Sie Teil eines **Experience Platform-Produktprofils** ein, das Ihnen die folgenden Berechtigungen gewährt:

* Datenmodellierung: Schemas anzeigen, Schemas verwalten
* Daten-Management: Datensätze anzeigen, Datensätze verwalten
* Datenaufnahme: Quellen verwalten
* Anzeigen von Identity-Namespaces

Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Zugriffssteuerung in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=de).

## Produktprofil-Administratorrolle

Ein Produktprofil ist ein Satz von Berechtigungen. Produktprofil-Admins können Folgendes:

* Individuelle Produktprofile erstellen und verwalten, beispielsweise neue Benutzende hinzufügen oder Benutzergruppen und ihre zugehörigen Produktprofile verwalten.

* Datenansichten in CJA bearbeiten, die Teil eines durch sie verwalteten Produktprofils sind. Sie können keine neuen Datenansichten erstellen.

## Zugriff auf Benutzerebene

Benutzende in Customer Journey Analytics können keine Datenansichten oder Verbindungen erstellen, bearbeiten oder anzeigen. Anwender können in Admin Console Filter, Projekte, Zielgruppen und berechnete Metriken mit speziellen Berechtigungen erstellen.

## Workspace-Projektkuratierung

Eine weitere Ebene der Zugriffskontrolle kann auf der Workspace-Berichtsebene verwendet werden. Der Zugriff auf bestimmte Komponenten kann für bestimmte Benutzende eingeschränkt werden. Weitere Informationen dazu, wie Sie Komponenten (Dimensionen, Metriken, Segmente, Datumsbereiche) auf Workspace-Projektebene einschränken und wie die Kuratierung mit Datenansichten verknüpft ist, finden Sie unter [Kuratieren von Projekten](/help/analysis-workspace/curate-share/curate.md).

## Gewähren von Zugriff auf einzelne Metriken oder Dimensionen

Sie können für einzelne Metriken oder Dimensionen in Customer Journey Analytics nicht wie im herkömmlichen Adobe Analytics Berechtigungen gewähren oder verweigern. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) geändert werden und unterliegen somit einer Änderung in CJA. Wenn sie geändert werden, ändert sich auch die Berichterstellung rückwirkend.

## Anwendungsbeispiele

Hier sind einige Anwendungsfälle, die zeigen, wie die Zugriffskontrolle in realen Szenarien eingesetzt werden kann.

### Zugriff durch Dritte

Ein Drittanbieter, mit dem Ihr Unternehmen zusammenarbeitet, hat einen Teamleiter, der als Produktprofil-Admin festgelegt werden kann. Dieser Admin kann diesem Produktprofil dann Benutzende seines Teams hinzufügen. Dieser Admin kann Zugriff auf bestimmte Datenansichten gewähren und andere Benutzende zu diesem Produktprofil hinzufügen. Außerdem können sie die Datenansichten, über die sie die Kontrolle haben, an die Anforderungen ihrer Teams anpassen.

### Zugriffskontrolle auf Zeilenebene

Angenommen, die Benutzenden sollen nur auf die Daten eines bestimmten Tages zugreifen können. So könnte der Zugriff auf diese speziellen Zeilen beschränkt werden:

1. Erstellen Sie in CJA einen Filter, bei dem **[!UICONTROL Tag]** dem Datum entspricht, an dem die Daten zugänglich sein sollen.
1. Fügen Sie in [!UICONTROL Datenansichten] > [!UICONTROL Einstellungen] den Filter zu der Datenansicht hinzu.
1. Wenn Sie nun die Datenansicht speichern, wird der Filter automatisch auf den Datensatz angewendet. Alle Zeilen, die nicht der Filterdefinition entsprechen, werden jetzt automatisch aus der bearbeiteten Datenansicht ausgeschlossen.
1. Erstellen Sie ein neues Produktprofil in der Admin Console, fügen Sie Benutzende hinzu und beschränken Sie deren Zugriff auf diese Datenansicht.

### Zugriffskontrolle auf Wertebene

Benutzende, die Zugriff auf eine Datenansicht haben, können nur mit den Metriken und Dimensionen arbeiten, die vom Admin in diese Datenansicht aufgenommen worden sind. Admins können die [Funktion zum Ein- oder Ausschließen](/help/data-views/component-settings/include-exclude-values.md) in Datenansichten verwenden, um beispielsweise bestimmte Dimensionswerte aus einer Datenansicht auszuschließen.

Hier ist ein Beispiel aus dem Gesundheitswesen: Angenommen, in einer Datenansicht wird eine Metrik mit der Bezeichnung „Hypertonie“ aus einem Datensatz erstellt, der diese Daten enthält. Die Tatsache, dass es sich um eine Metrik handelt, ermöglicht es, den aggregierten Wert dieser Metrik zu sehen, aber nicht die einzelnen Patientinnen und Patienten, die unter diese Metrik fallen.

## CJA-Berechtigungen in Admin Console

Die Registerkarte **[!UICONTROL Berechtigungen]** ist Teil jedes Produktprofils in [Admin Console](https://adminconsole.adobe.com/enterprise/). Benutzende können zu bestimmten Produktprofilen hinzugefügt werden. Anschließend werden Rechte für bestimmte Datenansichten zugewiesen und festgelegt, welche Berechtigungen die Benutzenden in einem Produktprofil haben. Dies sind die CJA-spezifischen Berechtigungen:

![Admin Console-Berechtigungen](assets/permissions.png)

| Berechtigung | Definition |
| --- | --- |
| **[!UICONTROL Datenansichten]** | Wenn **[!UICONTROL Auto-Include]** auf **[!UICONTROL Ein]** umgeschaltet wird, können Benutzende, die Teil dieses Produktprofils sind, alle vorhandenen und neu erstellten Datenansichten anzeigen. Wenn diese Einstellung auf **[!UICONTROL Aus]** gesetzt ist, können bestimmte Datenansichten ausgewählt werden, auf die Benutzende Zugriff haben. |
| **[!UICONTROL Reporting-Tools]**: |  |
| **[!UICONTROL Zugriff auf Auditprotokolle]** | Diese Berechtigung erzwingt die Berechtigungsprüfung für die [API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) und die die bevorstehende Benutzeroberfläche für Auditprotokolle. |
| **[!UICONTROL Verwaltung der Reporting-Nutzung]** | Ermöglicht Benutzenden das Anzeigen und Löschen aller in ihrem Unternehmen laufenden Berichte. (Die Funktionalität zur Berichtsnutzung ist noch nicht veröffentlicht.) |
| **[!UICONTROL Anzeige der Reporting-Nutzung]** | Ermöglicht Benutzenden die Anzeige aller gleichzeitigen Berichtsanfragen. (Die Funktionalität zur Berichtsnutzung ist noch nicht veröffentlicht.) |
| **[!UICONTROL Erstellung berechneter Metriken]** | Ermöglicht Benutzenden die Erstellung von [berechneten Metriken](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filter-Erstellung]** | Ermöglicht Benutzenden die Erstellung von [Filtern](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs-Zugriff]** | Ermöglicht Benutzenden den Zugriff auf die Registerkarte [Labs](/help/labs/labs.md) in CJA. |
| **[!UICONTROL Anmerkungserstellung]** | Ermöglicht Benutzenden das Erstellen von [Anmerkungen](/help/components/annotations/overview.md). |
| **[!UICONTROL Zielgruppenerstellung]** | Ermöglicht Benutzenden das Erstellen von [Zielgruppen](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Zielgruppenansicht]** | Ermöglicht Benutzenden die Ansicht von [Zielgruppen](/help/components/audiences/audiences-overview.md). |

{style=&quot;table-layout:auto&quot;}
