---
description: Verwalten des Cloud-Exportspeicherorts, an den Customer Journey Analytics-Daten gesendet werden können
keywords: Analysis Workspace
title: Verwalten von Cloud-Exportspeicherorten und -konten
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 3d4017ba36ac4b0c9ccb10a3e3127c6ea386fb1e
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 6%

---

# Verwalten von Cloud-Exportspeicherorten und -konten

Sie können Cloud-Exportspeicherorte anzeigen, bearbeiten und löschen.

Informationen zum Erstellen eines neuen Standorts finden Sie unter [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

## Filtern und Suchen von Standorten

Um benötigte Informationen zu finden, können Sie entweder die Liste der Standorte filtern oder nach einem Ort suchen.

### Filtern der Ortsliste

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standorte**] Registerkarte.

1. Wählen Sie die **Filter** Symbol.

   <!-- add screenshot -->

   Sie können nach folgenden Kriterien filtern:

   | Filter | Beschreibung |
   |---------|----------|
   | [!UICONTROL **Standorttyp**]<!--should this be changed to Account type?--> | Der Kontotyp, mit dem der Ort verknüpft ist. Die folgenden Kontotypen können verfügbar sein: <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Snowflake**]</li></ul> |
   | [!UICONTROL **Konto**] | Der Name des Kontos, mit dem der Standort verknüpft ist. |
   | [!UICONTROL **Erstellt von**] | Die E-Mail-Adresse des Benutzers, der den Standort erstellt hat. |

   {style="table-layout:auto"}

### Suchen nach Orten

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standorte**] Registerkarte.

1. Geben Sie auf der Registerkarte &quot;Suchen&quot;alle Informationen ein, die mit dem gesuchten Ort verknüpft sind. Sie können in einer beliebigen Spalte der Tabelle nach Daten suchen.

## Bearbeitungsorte

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standorte**] und wählen Sie dann den Ort aus, den Sie bearbeiten möchten.

   <!-- add screenshot? -->

1. Wählen Sie [!UICONTROL **Bearbeiten**] aus.

1. Nehmen Sie die gewünschten Änderungen vor und wählen Sie dann [!UICONTROL **Speichern**].

## Speicherorte löschen

Wenn Sie einen Speicherort löschen, werden auch alle Exporte gelöscht, die diesen Speicherort verwenden.

Prüfen Sie vor dem Löschen eines Standorts zunächst, ob dieser für beliebige Exporte verwendet wird. Aktivieren Sie dazu das Informationssymbol neben dem Ortsnamen.

![verbundene Exporte](assets/location-connected-exports.png)

So löschen Sie einen Speicherort:

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standorte**] und wählen Sie einen oder mehrere Speicherorte aus, die Sie löschen möchten.

   <!-- add screenshot? -->

1. Auswählen [!UICONTROL **Löschen**], wählen Sie [!UICONTROL **Löschen**] erneut im Bestätigungsdialogfeld angezeigt.

## Konten bearbeiten

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standortkonten**] Registerkarte.

   ![Kontoseite](assets/account-page.png)

1. Auswählen [!UICONTROL **Details anzeigen**] auf dem Konto, das Sie bearbeiten möchten.

1. Nehmen Sie die gewünschten Änderungen vor und wählen Sie dann [!UICONTROL **Speichern**].

## Löschen von Konten

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Standortkonten**] Registerkarte.

   ![Kontoseite](assets/account-page.png)

1. Wählen Sie das 3-Punkt-Symbol für das Konto aus, das Sie bearbeiten möchten, und wählen Sie dann [!UICONTROL **Konto löschen**].

1. Auswählen [!UICONTROL **Löschen**] erneut im Bestätigungsdialogfeld angezeigt.
