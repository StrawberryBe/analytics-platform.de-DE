---
title: Fehlende Berechtigungen
description: Erfahren Sie, wie Sie Probleme beheben können, die durch fehlende Berechtigungen verursacht werden.
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
feature: Troubleshooting
source-git-commit: 1905e37b76843a7622af4e874a2d74aceff55384
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 4%

---


# Fehlende Berechtigungen

Customer Journey Analytics funktioniert nicht ordnungsgemäß, wenn bestimmte Adobe Experience Platform-Berechtigungen nicht vorhanden sind.

Beispiel: nach der Erstellung eines [Verbindung](../connections/overview.md) und [Datenansicht](../data-views/data-views.md)kann die folgende Fehlermeldung in der [Komponenten](/help/data-views/create-dataview.md#components) Abschnitt:


>[!BEGINSHADEBOX]

*[!UICONTROL Etwas ist schiefgelaufen und wir konnten keine Schemafelder laden. Bitte versuchen Sie es erneut.]*

>[!ENDSHADEBOX]


Um diesen Fehler zu beheben, müssen Sie über System- oder Produktadministratorberechtigungen für ein Unternehmen verfügen, das über ein Experience Platform-Produkt verfügt. Siehe [Zugriffskontrolle - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=en#platform-permissions) für weitere Informationen.

1. Navigieren Sie zur Benutzeroberfläche von Adobe Experience Platform.

1. Auswählen **[!UICONTROL Berechtigungen]** über die linke Leiste.

1. Auswählen **[!UICONTROL Rollen]**.

1. Navigieren Sie zur entsprechenden Rolle.

1. Auswählen ![Bearbeiten](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL Bearbeiten]** , um die Rolle zu bearbeiten.

1. Sichern **[!UICONTROL Richtlinien zur Datennutzung verwalten]** und **[!UICONTROL Datennutzungsrichtlinien anzeigen]** werden der **[!UICONTROL Data Governance]** Container.

1. Auswählen **[!UICONTROL Speichern]** , um die Änderungen zu speichern.


