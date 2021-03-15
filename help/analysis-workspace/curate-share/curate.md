---
description: Durch Kuratierung können Sie die Komponenten einschränken, bevor Sie ein Projekt freigeben.
keywords: Analysis Workspace-Kuratierung
title: Kuratieren von Projekten
translation-type: tm+mt
source-git-commit: 1fd11bf0f34b9e4698285e5d29fd57fbab5238be
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 50%

---


# Kuratieren von Projekten

Mit der Kuratierung können Sie die Komponenten (Dimensionen, Metriken, Segmente, Datumsbereiche) vor der Freigabe eines Projekts einschränken. Wenn ein Empfänger das Projekt öffnet, wird ihm eine begrenzte Anzahl von Komponenten angezeigt, die Sie für ihn kuratiert haben. Die Kuratierung ist ein optionaler, aber empfehlenswerter Schritt, bevor Sie ein Projekt freigeben.

>[!NOTE]
> Produktprofile bestimmen als Hauptmechanismen, welche Komponenten ein Anwender sehen kann. Sie werden über die [Adobe Experience Cloud-Admin Console](https://docs.adobe.com/content/help/de-DE/core-services/interface/manage-users-and-products/admin-getting-started.html) verwaltet. Kuratierung ist ein Sekundärfilter.

## Anwenden der Projektkuratierung

1. Klicken Sie auf **[!UICONTROL Freigeben]** > **[!UICONTROL Projektdaten kuratieren]**.
Die im Projekt verwendeten Komponenten werden automatisch hinzugefügt.
   **Hinweis**: Wenn ein Projekt mehrere Report Suites hat, wird für jede Report Suite im Projekt ein Feld zum Kuratieren angezeigt.
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

In einem kuratierten Projekt wird dem Empfänger die Option **[!UICONTROL Alle]**-Komponenten in der linken Leiste anzeigen angezeigt. [!UICONTROL Alle anzeigen] zeigt verschiedene Komponentensätze an, je nach:

* Berechtigungsebene des Benutzers (Administrator oder Nicht-Administrator)
* Projektrolle (Inhaber/Bearbeiter oder nicht)
* Art der beantragten Kuration (auf Projektebene)

| Kurationstyp | Admin kann | Der Eigentümer des Nicht-Admin-Projekts (oder die Bearbeitungsrolle) kann | Rolle &quot;Nicht-Admin-Duplikat&quot;kann |
| --- | --- | --- | --- |
| **Komponenten &quot;ausgeblendet&quot;aus einer Ansicht** | Alle für Berichte verfügbaren Komponenten zur Ansicht von Daten (ausgeblendete Komponenten erfordern Klicken auf &quot;Alle anzeigen&quot;) | Nicht verfügbar für Berichte | Nicht verfügbar für Berichte |
| **Komponenten, die zu einer Ansicht hinzugefügt oder daraus entfernt wurden** | Nur Komponenten, die der Ansicht hinzugefügt wurden (ausgeblendet oder nicht ausgeblendet). Administratoren können keine Berichte zu Feldern oder Komponenten erstellen, die nicht von der Ansicht definiert sind. | Nur Komponenten, die der Datenkomponente hinzugefügt wurden, oder Komponenten, die dem Ansicht gehören oder für ihn freigegeben wurden. Ausgeblendete Komponenten sind nicht verfügbar (wie VRS-Kuration). | Nur Komponenten, die dem DV hinzugefügt wurden, werden nicht ausgeblendet und wurden in die Projektkuration aufgenommen. |
| **Kuratierte Komponenten in einem Projekt** | Alle für Berichte verfügbaren Komponenten zur Ansicht von Daten (ausgeblendete Komponenten erfordern Klicken auf &quot;Alle anzeigen&quot;) | Alle nicht ausgeblendeten Datenkomponenten (Ansicht durch Klicken auf &quot;Alle anzeigen&quot;) | Nur kuratierte Komponenten sowie alle Komponenten, die dem Benutzer gehören oder für ihn freigegeben wurden |
| **Kuratiertes Projekt mithilfe einer Ansicht mit verborgenen Komponenten** | Alle für den Berichte verfügbaren Datenkomponenten (ausgeblendete und nicht kuratierte Komponenten müssen auf &quot;Alle anzeigen&quot;klicken) | Alle nicht kuratierten Projektkomponenten, alle nicht verborgenen Komponenten der Ansicht von Daten sowie alle Komponenten, die dem Benutzer gehören oder für ihn freigegeben wurden | Nur kuratierte Komponenten sowie alle Komponenten, die dem Benutzer gehören oder für ihn freigegeben wurden |

