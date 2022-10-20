---
title: Auditprotokolle
description: Erfahren Sie, wie Sie CJA-Auditprotokolle anzeigen und verwalten.
source-git-commit: a866dec61df93bf730529a2d7513b4d76bab6694
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Auditprotokolle

>[!NOTE]
>
>Diese Funktion wird derzeit [eingeschränkt getestet](/help/release-notes/releases.md).

Um die Transparenz und Sichtbarkeit der im System durchgeführten Aktivitäten zu erhöhen, können Sie mit Customer Journey Analytics (CJA) die Benutzeraktivität für verschiedene Dienste und Funktionen in Form von &quot;Auditprotokollen&quot;überprüfen. Diese Protokolle bilden ein Audit-Protokoll, das Ihnen bei der Fehlerbehebung helfen und Ihrem Unternehmen helfen kann, die Richtlinien der Unternehmensdatenverwaltung und die gesetzlichen Anforderungen wie den Health Insurance Portability and Accounability Act (HIPAA) effektiv zu erfüllen.

In einem Prüfprotokoll wird **who** ausgeführt **what** Aktion und **when**. Jede in einem Protokoll aufgezeichnete Aktion enthält Metadaten, die den Aktionstyp, das Datum und die Uhrzeit, die E-Mail-ID des Benutzers, der die Aktion ausgeführt hat, und zusätzliche Attribute für den Aktionstyp angeben.

In diesem Thema werden Auditprotokolle in CJA behandelt, einschließlich der Anzeige und Verwaltung dieser Protokolle in der Benutzeroberfläche.

## Zugriff auf Prüfprotokolle

Wenn die Funktion für Ihr Unternehmen aktiviert ist, werden bei auftretenden Aktivitäten automatisch Prüfprotokolle erfasst. Sie müssen die Datenerfassung in Auditprotokollen nicht manuell aktivieren.

Um Prüfprotokolle anzeigen und exportieren zu können, muss Ihnen die **[!UICONTROL Zugriff auf Prüfprotokolle]** Zugriffssteuerungsberechtigungen in der Adobe Console. Informationen zum Verwalten individueller Berechtigungen für CJA-Funktionen finden Sie im Abschnitt [Zugriffssteuerungsdokumentation](/help/getting-started/cja-access-control.md).

## Audit-Protokolle in der Benutzeroberfläche anzeigen

Navigieren Sie in CJA zu **[!UICONTROL Instrumente]** > **[!UICONTROL Auditprotokolle]**.

Das Auditprotokoll für heute und gestern wird standardmäßig angezeigt.

![Auditprotokoll](assets/audit_ui.png)

Sie können auswählen, welche Spalten sichtbar sind, indem Sie oben rechts in die Spaltenauswahl wechseln.

## Anzeigen von Informationen zu einzelnen Protokolleinträgen

Doppelklicken Sie auf die Schaltfläche Info (i) neben einer Beschreibung.

![Auditprotokoll](assets/info-button-audit.png)

Die folgenden Elemente werden angezeigt:

| Element | Beschreibung |
| --- | --- |
| Aktionsname | Im Folgenden finden Sie eine Liste möglicher Aktionen: <ul><li>API_Request</li><li>Genehmigen</li><li>Erstellung</li><li>Vorlage  </li><li>Exportieren</li><li>Login_failed</li><li>Login_success</li><li>Abmelden</li><li>org_change</li><li>Aktualisieren</li><li>Freigeben</li><li>Übertragen</li><li>Nicht genehmigen</li><li>Freigabe aufheben</li></ul> |
| Beschreibung | Eine Zusammenfassung der Aktion, des Komponententyps (mit ID) und anderer Werte. |
| Benutzername | Der Benutzer, der die Aktion durchführt. |
| Typ der Komponente | Mögliche Komponententypen sind: <ul><li>Anmerkung</li><li>Zielgruppe</li><li>Berechnete Metrik</li><li>Verbindung</li><li>Data_Group</li><li>data_view</li><li>Feature_Access</li><li>Filter</li><li>IMS_Org</li><li>Mobil</li><li>Projekt </li><li>Bericht</li><li>Scheduled_Project</li><li>Benutzer</li><li>User_Group</li></ul> |
| Kennung der IMS-Organisation | Eine eindeutige ID, die Ihrer Instanz bei der ersten Anmeldung bei Adobe Experience Cloud zugewiesen wird. Sie sollte im folgenden Format vorliegen: xxx@AdobeOrg |
| Benutzer-ID | Eine eindeutige ID, die den Benutzer angibt, der diese Aktion ausgeführt hat. |
| Erstellt am | Zeitpunkt, zu dem diese Maßnahme ergriffen wurde. |
| E-Mail | Die E-Mail des Benutzers, der die Aktion ausführt. |
| Komponenten-ID | Eine eindeutige ID, die die Komponente identifiziert, für die gehandelt wird. |
| ID-Protokoll | Eine eindeutige ID, die diesen Protokolleintrag identifiziert. |
| Benutzertyp | Mögliche Typen sind: IMS, OKTA |

### Auditprotokolle filtern

Wählen Sie das Trichtersymbol (![filter](assets/filter-icon.png)), um eine Liste von Filtersteuerelementen anzuzeigen, die die Eingrenzung der Ergebnisse unterstützen. Es werden nur die letzten 1.000 Datensätze angezeigt, unabhängig von den ausgewählten Filtern.

![Filter](assets/filters.png)

Die folgenden Filter sind für Prüfereignisse in der Benutzeroberfläche verfügbar:

| Filter | Beschreibung |
| --- | --- |
| [!UICONTROL Datumsbereich] | Filtern Sie nach einem anderen Datumsbereich, indem Sie ein anderes Datum auswählen oder einen Datumsbereich auswählen, indem Sie den Cursor über mehrere Daten ziehen. Standardmäßig sind das heutige und das gestrige Datum ausgewählt. |
| [!UICONTROL Aktion] | Filtern Sie nach einer oder mehreren der folgenden Aktionen: <ul><li>API_Request</li><li>Genehmigen</li><li>Erstellung</li><li>Vorlage  </li><li>Exportieren</li><li>Login_failed</li><li>Login_success</li><li>Abmelden</li><li>org_change</li><li>Aktualisieren</li><li>Freigeben</li><li>Übertragen</li><li>Nicht genehmigen</li><li>Freigabe aufheben</li></ul> |
| [!UICONTROL Benutzer-ID] | Filtern nach einem bestimmten Benutzer nach seiner Benutzer-ID. Sie können die Benutzer-ID ermitteln, indem Sie auf die Schaltfläche info (i) neben einem Benutzernamen klicken. |
| [!UICONTROL E-Mail] | Filtern nach der E-Mail-Adresse eines bestimmten Benutzers. Sie können die E-Mail über die Info-Schaltfläche (i) neben einem Benutzernamen finden. |
| [!UICONTROL Komponenten-ID] | Filtern nach einer bestimmten Komponenten-ID. Sie können die Benutzer-ID ermitteln, indem Sie die Schaltfläche info (i) für eine gewünschte Komponente auswählen. |
| [!UICONTROL Typ der Komponente] | Filtern nach einem oder mehreren Komponententypen: <ul><li>Anmerkung</li><li>Zielgruppe</li><li>Berechnete Metrik</li><li>Verbindung</li><li>Data_Group</li><li>data_view</li><li>Feature_Access</li><li>Filter</li><li>IMS_Org</li><li>Mobil</li><li>Projekt </li><li>Bericht</li><li>Scheduled_Project</li><li>Benutzer</li><li>User_Group</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Von Audit-Protokollen erfasste Ereignistypen

In der folgenden Tabelle wird beschrieben, welche Aktionen bei welchen Komponententypen von Prüfprotokollen aufgezeichnet werden:

| Typ der Komponente | Aktionen |
| --- | --- |
| [!UICONTROL Anmerkung] | <ul><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |
| [!UICONTROL Zielgruppe] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li><li>Exportieren</li><li>Aktualisieren</li></ul> |
| [!UICONTROL Berechnete Metrik] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |
| [!UICONTROL Verbindung] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |
| [!UICONTROL Datenansicht] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |
| [!UICONTROL Datumsbereich] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |
| [!UICONTROL Filter] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |
| [!UICONTROL IMS-Organisation] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |
| [!UICONTROL Projekt ] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |
| [!UICONTROL Bericht] | <ul><li>API_Request</li></ul> |
| [!UICONTROL Geplantes Projekt] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |
| [!UICONTROL Benutzer] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |
| [!UICONTROL Benutzergruppe] | <ul><li>API_Request</li><li>Erstellung</li><li>Löschen</li><li>Vorlage  </li></ul> |

{style=&quot;table-layout:auto&quot;}

## Audit-Protokolle herunterladen

Sie können Auditprotokolle im CSV- oder JSON-Format herunterladen. Alle angewendeten Filter oder ausgewählten Spalten werden in den heruntergeladenen Dateien übernommen.

1. Klicken **[!UICONTROL Download]** oben rechts auf dem Bildschirm.
1. Geben Sie das Format an.
1. Klicken **[!UICONTROL Download]** erneut.

## Verwalten von Auditprotokollen in der API

Alle Aktionen, die Sie in der Benutzeroberfläche ausführen können, können auch über API-Aufrufe ausgeführt werden. Siehe [CJA-API-Referenzdokument](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) für weitere Informationen.