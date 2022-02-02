---
description: Durch Kuratierung können Sie die Komponenten einschränken, bevor Sie ein Projekt freigeben.
keywords: Analysis Workspace-Kuratierung
title: Kuratieren von Projekten
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 45%

---

# Kuratieren von Projekten

Durch Kuratierung können Sie die Komponenten (Dimensionen, Metriken, Filter, Datumsbereiche) vor der Freigabe eines Projekts einschränken. Wenn ein Empfänger das Projekt öffnet, wird ihm eine begrenzte Anzahl von Komponenten angezeigt, die Sie für ihn kuratiert haben. Die Kuratierung ist ein optionaler, aber empfehlenswerter Schritt, bevor Sie ein Projekt freigeben.

>[!NOTE]
> Produktprofile bestimmen als Hauptmechanismen, welche Komponenten ein Anwender sehen kann. Sie werden über die [Adobe Experience Cloud-Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=de). Kuratierung ist ein Sekundärfilter.

## Anwenden der Projektkuratierung

1. Klicken Sie auf **[!UICONTROL Freigeben]** > **[!UICONTROL Projektdaten kuratieren]**.
Die im Projekt verwendeten Komponenten werden automatisch hinzugefügt.
1. (Optional) Um weitere Komponenten hinzuzufügen, ziehen Sie die freizugebenden Komponenten aus der linken Leiste in das Feld [!UICONTROL Komponenten kuratieren].
1. Klicken Sie auf **[!UICONTROL Fertig]**.

Eine Kuratierung kann auch über das Menü [!UICONTROL Freigeben] angewendet werden, indem Sie auf **[!UICONTROL Kuratieren und freigeben]** klicken. Diese Option kuratiert das Projekt automatisch auf die im Projekt verwendeten Komponenten. Sie können weitere Komponenten hinzufügen, wie oben beschrieben.

![](assets/curation-field.png)

## Ansicht des kuratierten Projekts

Wenn ein Empfänger ein kuratiertes Projekt öffnet, wird ihm nur der ausgewählte Satz der von Ihnen definierten Komponenten angezeigt:

![](assets/curate-project.png)

## Entfernen der Projektkuratierung

So entfernen Sie die Projektkuratierung und stellen Sie den vollständigen Satz der Komponenten in der linken Leiste wieder her:

1. Klicken Sie auf **[!UICONTROL Freigeben]** > **[!UICONTROL Projektdaten kuratieren]**.
1. Klicken Sie auf **[!UICONTROL Kuratierung entfernen]**.
1. Klicken Sie auf **[!UICONTROL Fertig]**.

## Optionen zur Komponentenkuratierung

In einem kuratierten Projekt erhält der Empfänger die Möglichkeit, **[!UICONTROL Alle anzeigen]** Komponenten in der linken Leiste. [!UICONTROL Alle anzeigen] zeigt verschiedene Komponentensätze an, je nach:

* Berechtigungsebene des Benutzers (Administrator oder Nicht-Administrator)
* Projektrolle (Inhaber/Bearbeiter oder nicht)
* Art der angewendeten Kuratierung (auf Projektebene)

| Kurationstyp | Admin kann | Projekteigentümer ohne Administratorrechte (oder Bearbeitungsrolle) können | Duplizierte Rollen ohne Administratorrechte können |
| --- | --- | --- | --- |
| **Komponenten in einer Datenansicht &quot;ausgeblendet&quot;** | Alle für die Berichterstellung verfügbaren Datenansichtskomponenten (ausgeblendete Komponenten erfordern das Klicken auf &quot;Alle anzeigen&quot;) | Nicht für Berichte verfügbar | Nicht für Berichte verfügbar |
| **Komponenten, die zur Datenansicht hinzugefügt oder daraus entfernt wurden** | Nur Komponenten, die zur Datenansicht hinzugefügt wurden (ausgeblendet oder nicht ausgeblendet). Administratoren können keine Berichte zu Feldern oder Komponenten erstellen, die nicht in der Datenansicht definiert sind. | Nur Komponenten, die zur Datenansicht hinzugefügt wurden, oder Komponenten, die dem Benutzer gehören oder für ihn freigegeben wurden. Ausgeblendete Komponenten sind nicht verfügbar (wie VRS-Kuratierung). | Nur Komponenten, die zum DV hinzugefügt wurden, sind nicht ausgeblendet und wurden in die Projektkuratierung aufgenommen. |
| **Kuratierte Komponenten in einem Projekt** | Alle für die Berichterstellung verfügbaren Datenansichtskomponenten (ausgeblendete Komponenten erfordern das Klicken auf &quot;Alle anzeigen&quot;) | Alle nicht ausgeblendeten Datenansichtskomponenten (erfordert das Klicken auf &quot;Alle anzeigen&quot;) | Nur kuratierte Komponenten sowie alle Komponenten, die dem Benutzer gehören oder für ihn freigegeben wurden |
| **Kuratiertes Projekt mit einer Datenansicht mit ausgeblendeten Komponenten** | Alle für die Berichterstellung verfügbaren Datenkomponenten (ausgeblendete und nicht kuratierte Komponenten erfordern das Klicken auf &quot;Alle anzeigen&quot;) | Alle nicht kuratierten Projektkomponenten, alle nicht ausgeblendeten Datenansichtskomponenten und alle Komponenten, die dem Benutzer gehören oder für ihn freigegeben wurden | Nur kuratierte Komponenten sowie alle Komponenten, die dem Benutzer gehören oder für ihn freigegeben wurden |
