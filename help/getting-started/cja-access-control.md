---
title: CJA-Zugriffssteuerung
description: Erfahren Sie, wie Sie die Zugriffskontrolle in CJA implementieren können.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: 04957adebd848739b8b3609eb35366d8296ee752
workflow-type: tm+mt
source-wordcount: '945'
ht-degree: 29%

---

# CJA-Zugriffssteuerung

Customer Journey Analytics (CJA) wird durch drei Zugriffsebenen oder drei Rollen gesteuert: Produktadministrator, Produktprofil-Administrator und Anwenderzugriff. In diesem Thema werden diese Rollen ausführlicher erläutert.

Darüber hinaus werden detailliertere Möglichkeiten zur Beschränkung des Zugriffs beschrieben, z. B. die Kuratierung von Workspace und die Zeilenebene sowie die Zugriffskontrolle auf Wertebene.

## Produktadministrator-Rolle

Produktadministratoren sind berechtigt, alle in Customer Journey Analytics erforderlichen Aufgaben auszuführen. Sie müssen als Produktadministrator zum **Customer Journey Analytics-Produktprofil** im [Admin Console](https://adminconsole.adobe.com/enterprise/) under [!UICONTROL Customer Journey Analytics] > [!UICONTROL Administratoren] tab > [!UICONTROL Admin hinzufügen]. Produktadmins erhalten die folgenden Berechtigungen:

* Erstellen/Aktualisieren/Löschen von Verbindungen oder Datenansichten
* Aktualisieren/Löschen von Projekten, Filtern, berechneten Metriken, Zielgruppen, Anmerkungen oder Filtern, die von anderen Benutzern erstellt wurden
* Freigeben von Workspace-Projekten für alle Benutzenden

Wenn Sie in Customer Journey Analytics Produktadministrator werden, reicht es nicht aus, eine [connection](/help/connections/overview.md). Um eine Verbindung zu einem Experience Platform-Datensatz herzustellen, benötigen Sie auch Experience Platform-Berechtigungen. Insbesondere müssen Sie Teil eines **Experience Platform-Produktprofils** ein, das Ihnen die folgenden Berechtigungen gewährt:

* Datenmodellierung: Schemas anzeigen, Schemas verwalten
* Daten-Management: Datensätze anzeigen, Datensätze verwalten
* Datenaufnahme: Quellen verwalten
* Anzeigen von Identity-Namespaces

Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Zugriffssteuerung in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=de).

## Produktprofil-Administratorrolle

Ein Produktprofil ist ein Satz von Berechtigungen. Produktprofiladministratoren können

* Erstellen und verwalten Sie einzelne Produktprofile, z. B. das Hinzufügen neuer Benutzer oder das Verwalten von Benutzergruppen und den zugehörigen Produktprofilen.

* Bearbeiten Sie in CJA Datenansichten, die Teil eines von ihnen verwalteten Produktprofils sind. Sie können keine neuen Datenansichten erstellen.

## Zugriff auf Anwenderebene

Benutzer in Customer Journey Analytics können keine Datenansichten oder -verbindungen erstellen, bearbeiten oder anzeigen. Anwender können in Admin Console Filter, Projekte, Zielgruppen und berechnete Metriken mit speziellen Berechtigungen erstellen.

## Workspace-Projektkuratierung

Eine weitere Zugriffskontrollebene kann auf der Workspace-Berichtsebene verwendet werden. Sie können den Zugriff auf bestimmte Komponenten für bestimmte Benutzer einschränken. Weitere Informationen dazu, wie Sie Komponenten (Dimensionen, Metriken, Segmente, Datumsbereiche) auf Workspace-Projektebene einschränken und wie die Kuratierung mit Datenansichten verknüpft ist, finden Sie unter [Kuratieren von Projekten](/help/analysis-workspace/curate-share/curate.md).

## Gewähren von Zugriff auf einzelne Metriken oder Dimensionen

Sie können für einzelne Metriken oder Dimensionen in Customer Journey Analytics nicht wie im herkömmlichen Adobe Analytics Berechtigungen gewähren oder verweigern. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) und können sich daher in CJA ändern. Wenn Sie sie ändern, wird auch die Berichterstellung rückwirkend geändert.

## Anwendungsbeispiele

Im Folgenden finden Sie einige Anwendungsfälle, die veranschaulichen, wie die Zugriffskontrolle in Echtzeit-Szenarien verwendet werden kann.

### Zugriff auf Drittanbieter

Ein Drittanbieter, mit dem Ihr Unternehmen zusammenarbeitet, hat einen Teamleiter, der als Produktprofil-Administrator festgelegt werden kann. Dieser Administrator kann diesem Produktprofil dann Benutzer seines Teams hinzufügen. Dieser Administrator kann Zugriff auf bestimmte Datenansichten gewähren und diesem Produktprofil weitere Benutzer hinzufügen. Sie können auch die Datenansichten ändern, über die sie verfügen, um sie an die Anforderungen ihres Teams anzupassen.

### Zugriffskontrolle auf Zeilenebene

Angenommen, Sie möchten Benutzern nur von einem Tag aus Zugriff auf Daten gewähren. So beschränken Sie den Zugriff auf diese bestimmten Zeilen:

1. Erstellen Sie einen Filter in CJA, wobei **[!UICONTROL Tag]** entspricht dem Datum, auf das Sie Datenzugriff haben möchten.
1. In [!UICONTROL Datenansichten] > [!UICONTROL Einstellungen], fügen Sie diesen Filter zur Datenansicht hinzu.
1. Speichern Sie die Datenansicht und wenden Sie den Filter automatisch auf den Datensatz an. Alle Zeilen, die nicht zur Filterdefinition passen, werden jetzt automatisch aus der bearbeiteten Datenansicht ausgeschlossen.
1. Erstellen Sie ein neues Produktprofil in Admin Console, fügen Sie Benutzer hinzu und beschränken Sie den Zugriff auf diese Datenansicht.

### Zugriffskontrolle auf Wertebene

Benutzer, die Zugriff auf eine Datenansicht haben, können nur mit den Metriken und Dimensionen arbeiten, die der Administrator in dieser Datenansicht angegeben hat. Administratoren können die [Ein-/Ausschlussfunktion](/help/data-views/component-settings/include-exclude-values.md) in Datenansichten, um beispielsweise bestimmte Dimensionswerte aus einer Datenansicht auszuschließen.

Im Folgenden finden Sie ein Beispiel für die Gesundheitsversorgung: Angenommen, Sie erstellen in einer Datenansicht eine Metrik namens &quot;Hypertonie&quot;aus einem Datensatz, der diese Daten enthält. Die Tatsache, dass es sich um eine Metrik handelt, würde es Ihnen ermöglichen, den aggregierten Wert dieser Metrik zu sehen, aber nicht die einzelnen Patienten, die darunter fallen.

## CJA-Berechtigungen in Admin Console

Die **[!UICONTROL Berechtigungen]** -Registerkarte ist Teil jedes Produktprofils in [Admin Console](https://adminconsole.adobe.com/enterprise/). Sie können Benutzer zu bestimmten Produktprofilen hinzufügen. Anschließend weisen Sie bestimmten Datenansichten Berechtigungen zu und geben an, welche Berechtigungen die Benutzer in einem Produktprofil haben. Im Folgenden finden Sie die CJA-spezifischen Berechtigungen:

![Admin Console-Berechtigungen](assets/permissions.png)

| Berechtigung | Definition |
| --- | --- |
| **[!UICONTROL Datenansichten]** | Wenn Sie **[!UICONTROL Automatisch einschließen]** nach **[!UICONTROL on]**, können Benutzer, die Teil dieses Produktprofils sind, alle vorhandenen und neu erstellten Datenansichten anzeigen. Wenn diese Einstellung auf **[!UICONTROL Aus]** können Sie bestimmte Datenansichten auswählen, auf die Benutzer Zugriff haben. |
| **[!UICONTROL Reporting-Tools]**: |  |
| **[!UICONTROL Zugriff auf Auditprotokolle]** | Zurzeit [Auditprotokolle](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) sind nur über die API verfügbar. Diese Berechtigung erzwingt die Berechtigungsprüfung für die API und eine bevorstehende Benutzeroberfläche für Prüfprotokolle. |
| **[!UICONTROL Verwaltung der Reporting-Nutzung]** | Ermöglicht Benutzern das Anzeigen und Löschen von Berichten, die in ihrem Unternehmen ausgeführt werden. (Die Berichtsverwendungsfunktion wurde noch nicht veröffentlicht.) |
| **[!UICONTROL Anzeige der Reporting-Nutzung]** | Damit können Benutzer alle gleichzeitigen Berichtsanforderungen sehen. (Die Berichtsverwendungsfunktion wurde noch nicht veröffentlicht.) |
| **[!UICONTROL Erstellung berechneter Metriken]** | Benutzer können [berechnete Metriken](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Filtererstellung]** | Benutzer können [Filter](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Lab-Zugriff]** | Benutzer können auf die [Labs](/help/labs/labs.md) in CJA. |
| **[!UICONTROL Anmerkungserstellung]** | Benutzer können [Anmerkungen](/help/components/annotations/overview.md). |
| **[!UICONTROL Zielgruppenerstellung]** | Benutzer können [Zielgruppen](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Zielgruppenansicht]** | Benutzeransicht [Zielgruppen](/help/components/audiences/audiences-overview.md). |

{style=&quot;table-layout:auto&quot;}
