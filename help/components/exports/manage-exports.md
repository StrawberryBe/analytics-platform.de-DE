---
description: Vorhandene Exporte verwalten
keywords: Analysis Workspace
title: Verwalten von Exporten
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
source-git-commit: 34588ccd39d7464387197a0b4bfd6a9e416bd9c0
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 6%

---

# Verwalten von Exporten

{{release-limited-testing}}

Nachdem Sie eine vollständige Tabelle wie unter [Customer Journey Analytics-Berichte in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md), sind die Exporte im Abschnitt [!UICONTROL Exporte] auf der Registerkarte [!UICONTROL Exporte] Seite.

Es werden nur die von Ihnen erstellten Exporte angezeigt.

## Filtern und Suchen nach Exporten

Um die benötigten Informationen zu finden, können Sie entweder die Liste der Exporte filtern oder nach einem Export suchen.

### Filtern der Exportliste

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Exporte**] Registerkarte.

1. Wählen Sie die **Filter** Symbol.

   <!--add screenshot -->

   Sie können nach folgenden Kriterien filtern:

   | Filter | Beschreibung |
   |---------|----------|
   | [!UICONTROL **Kontotyp**] | Der Kontotyp, mit dem der Export verknüpft ist. Die folgenden Kontotypen sind verfügbar: <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Status**] | Der Status des Exports. Die folgenden Status sind verfügbar: <ul><li>[!UICONTROL **Aktiv**]: Gibt an, dass ein geplanter Export noch nicht abgelaufen ist. </li><li>[!UICONTROL **Abgeschlossen**]: Gibt an, dass ein Export erfolgreich exportiert wurde. Bei geplanten Exporten bedeutet dies, dass der Zeitplan abgelaufen ist.</li><li>[!UICONTROL **Fehlgeschlagen**]<p>Die folgenden Situationen können zu einem fehlgeschlagenen Export führen. Bewegen Sie den Mauszeiger über den Status Fehlgeschlagen , um Details zum Fehler anzuzeigen. <ul><li>Geplanter Exportablauf</li><li>Zeilenlimit für geplanten Export erreicht </li></ul> </p></li></ul> |
   | [!UICONTROL **Häufigkeit**] | Wie oft der Export erfolgt. Die folgenden Häufigkeiten sind verfügbar: <ul><li>[!UICONTROL **Einmalig**]</li><li>[!UICONTROL **Täglich**]</li><li>[!UICONTROL **Wöchentlich**]</li><li>[!UICONTROL **Monatlich**]</li><li>[!UICONTROL **Jährlich**]</li></ul> |

   {style="table-layout:auto"}

### Nach Exporten suchen

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Wählen Sie die [!UICONTROL **Exporte**] Registerkarte.

1. Geben Sie im Suchfeld alle Informationen ein, die mit dem gesuchten Export verbunden sind. Sie können in einer beliebigen Spalte der Tabelle nach Daten suchen.

## Export bearbeiten

Sie können die Eigenschaften, das Format, die Planung und die Standortinformationen eines Exports bearbeiten.

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Im [!UICONTROL **Exporte**] den zu bearbeitenden Export auswählen.

   Diese Option ist nicht verfügbar, wenn mehrere Exporte ausgewählt werden.

1. Wählen Sie [!UICONTROL **Bearbeiten**] aus.

## Export duplizieren

Sie können einen vorhandenen Export duplizieren.

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Im [!UICONTROL **Exporte**] den zu duplizierenden Export auswählen.

   Diese Option ist nicht verfügbar, wenn mehrere Exporte ausgewählt werden.

1. Wählen Sie [!UICONTROL **Duplizieren**] aus.

   Ein Duplikat des Exports wird erstellt. Der Name des neuen Exports entspricht dem Namen des ursprünglichen Exports mit _[!UICONTROL - Kopie]_ an den Dateinamen angehängt.

1. (Optional) [Neuen Export bearbeiten](#edit-an-export), einschließlich des Dateinamens und anderer Eigenschaften, die Sie ändern möchten.

## Manuelles Initiieren eines Exports

Sie können einen Export für einen geplanten Export oder einen einmaligen Export, der zuvor abgeschlossen wurde, manuell starten.

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Im [!UICONTROL **Exporte**] wählen Sie den Export aus, den Sie ausführen möchten.

   Diese Option ist nicht verfügbar, wenn mehrere Exporte ausgewählt werden.

1. Auswählen [!UICONTROL **Export jetzt**].

## Export taggen

Wenn Sie Tags auf einen Export anwenden, können Sie diese Tags im [!UICONTROL Tags] in der Spalte [!UICONTROL Exporte] Seite. Siehe [Spalten konfigurieren](#configure-columns) für weitere Informationen.

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Im [!UICONTROL **Exporte**] einen oder mehrere Exporte auswählen, die Sie taggen möchten.

1. Auswählen [!UICONTROL **Tag**].

1. Geben Sie im Dialogfeld Tag-Export den Namen eines Tags ein, um ein neues Tag zu erstellen, oder wählen Sie ein vorhandenes Tag aus dem Dropdownmenü aus.

   Alle gemeinsamen Tags zwischen den ausgewählten Exporten werden im Tag-Dialogfeld angezeigt. <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. Auswählen [!UICONTROL **Tags anwenden**].

## Export löschen

Sie können Exporte über die Seite Exporte löschen. Geplante, gelöschte Exporte werden nicht mehr gesendet.

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].

1. Im [!UICONTROL **Exporte**] einen oder mehrere Exporte auswählen, die Sie löschen möchten.

1. Auswählen [!UICONTROL **Löschen**], wählen Sie [!UICONTROL **Löschen**] wenn die Bestätigungsmeldung angezeigt wird.

## Konfigurieren Sie die Spalten in der [!UICONTROL Exporte] page

Sie können Spalten zum [!UICONTROL Exporte] um zu konfigurieren, welche Informationen angezeigt werden.

Wählen Sie eine Spaltenüberschrift aus, um die Exporte nach dieser Spalte zu sortieren. Standardmäßig werden Exporte nach Datum und Uhrzeit der letzten Änderung des Exports sortiert.

1. Wählen Sie die **Tabelle anpassen** icon ![Anpassbare Tabelle](assets/customize-table-icon.png) oben rechts im [!UICONTROL Exporte] Seite.

   Die folgenden Spalten sind verfügbar:

   | Spalte verfügbar | Beschreibung |
   |---------|----------|
   | Name | Der Name des Exports. Benutzer geben Exporten einen Namen, wenn sie sie erstellen, wie in [Customer Journey Analytics-Berichte in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md). |
   | ID | Die beim Erstellen automatisch dem Export zugewiesene Kennung. <!-- True? --> |
   | Status | Der Status des Exports. Verfügbare Status sind [!UICONTROL Aktiv], [!UICONTROL Angehalten], [!UICONTROL Abgeschlossen], und [!UICONTROL Fehlgeschlagen].<p> **Hinweis:** Informationen zur Fehlerbehebung bei fehlgeschlagenen Exporten finden Sie unter [Fehlerbehebung bei fehlgeschlagenen Exporten](/help/components/exports/troubleshoot-exports.md).</p> |
   | Name der Datenansicht | Der Name der mit dem Export verknüpften Datenansicht. Benutzer können die Datenansicht beim Erstellen des Exports auswählen, wie unter [Customer Journey Analytics-Berichte in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md). |
   | Status | Der Status des Exports. Verfügbare Status sind [!UICONTROL Ausstehend], [!UICONTROL Zugestellt], und [!UICONTROL Fehlgeschlagen]. |
   | Tabellengröße (zuletzt gesendet) | Die Größe des Exports beim letzten Versand. |
   | Erstellt von | Der Benutzer, der den Export erstellt hat. |
   | Erstellt | Datum und Uhrzeit der Erstellung des Exports. <!-- true? --> |
   | Standort | Der Speicherort auf dem Konto, auf dem die Daten exportiert wurden. |
   | Konto | Das Konto, in das die Daten exportiert wurden. |
   | Häufigkeit | Die Häufigkeit, mit der der Export durchgeführt wird. Verfügbare Optionen sind [!UICONTROL Einmalig], [!UICONTROL Täglich], [!UICONTROL Wöchentlich], [!UICONTROL Monatlich nach Wochentag], [!UICONTROL Monatlich nach Tag des Monats], [!UICONTROL Jährlich nach Tag des Monats], und [!UICONTROL Jährlich nach spezifischem Datum]. |
   | Gesendet um | Der Zeitpunkt, zu dem der Export gesendet wurde. |
   | Zuletzt gesendet | Das letzte Mal, dass der Export gesendet wurde. |
   | Zuletzt geändert | Das letzte Mal, dass der Export geändert wurde. Die Elemente auf der Seite Exporte sind standardmäßig nach dieser Spalte sortiert. |
   | Kontotyp | Der Typ des Cloud-Kontos, in das die Daten exportiert wurden. Verfügbare Kontotypen sind [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake], und [!UICONTROL Adobe Experience Platform]. |
   | Tags | Zeigt alle Tags an, die auf den Export angewendet werden. Informationen zum Anwenden von Tags auf einen Export finden Sie unter [Export taggen](#tag-an-export). |

   {style="table-layout:auto"}

1. Stellen Sie sicher, dass alle Spalten ausgewählt sind, die angezeigt werden sollen. Die ausgewählten Spalten werden auf der Seite Exporte angezeigt und zeigen die relevanten Informationen an.
