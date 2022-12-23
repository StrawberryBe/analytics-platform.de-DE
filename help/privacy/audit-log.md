---
title: Auditprotokolle
description: Erfahren Sie, wie Sie CJA-Auditprotokolle anzeigen und verwalten können.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
source-git-commit: bb6e4dcc1c917fcfb565430232e3c5562f63fd1a
workflow-type: ht
source-wordcount: '849'
ht-degree: 100%

---

# Auditprotokolle

Um die Transparenz und Sichtbarkeit der im System durchgeführten Aktivitäten zu erhöhen, ermöglicht Ihnen Customer Journey Analytics (CJA), die Benutzeraktivität für verschiedene Services und Funktionen mithilfe von Auditprotokollen zu erfassen. Diese Protokolle bilden einen Prüfpfad, der Ihnen bei der Fehlerbehebung helfen kann und Ihrem Unternehmen ermöglicht, betriebliche Datenverwaltungsrichtlinien und gesetzliche Anforderungen wie den Health Insurance Portability and Accountability Act (HIPAA) einzuhalten.

In einem Auditprotokoll wird festgehalten, **wer** **welche** Aktion **wann** ausgeführt hat. Jede in einem Protokoll aufgezeichnete Aktion enthält Metadaten, die den Aktionstyp, das Datum und die Uhrzeit, die E-Mail-ID des/der Benutzenden, der/die die Aktion ausgeführt hat, und zusätzliche Attribute des Aktionstyps angeben.

In diesem Artikel werden Auditprotokolle in CJA behandelt, einschließlich der Frage, wie sie in der Benutzeroberfläche angezeigt und verwaltet werden können.

## Zugriff auf Auditprotokolle

Wenn diese Funktion für Ihr Unternehmen aktiviert ist, werden bei Aktivitäten automatisch Auditprotokolle aufgezeichnet. Sie müssen die Datenerfassung in Auditprotokollen nicht manuell aktivieren.

Um Auditprotokolle anzeigen und exportieren zu können, benötigen Sie in der Adobe-Konsole die Zugriffsberechtigung **[!UICONTROL Zugriff auf Auditprotokolle]**. Informationen zum Verwalten individueller Berechtigungen für CJA-Funktionen finden Sie in der [Dokumentation zur Zugriffssteuerung](/help/getting-started/cja-access-control.md).

## Administratorprotokoll in der Benutzeroberfläche anzeigen

Navigieren Sie in CJA zu **[!UICONTROL Tools]** > **[!UICONTROL Auditprotokolle]**.

Das Auditprotokoll für den heutigen und gestrigen Tag wird standardmäßig angezeigt.

![Auditprotokoll](assets/audit_ui.png)

Sie können auswählen, welche Spalten sichtbar sein sollen, indem Sie oben rechts zur Spaltenauswahl wechseln.

## Anzeigen von Informationen zu einzelnen Protokolleinträgen

Doppelklicken Sie auf die Info-Schaltfläche (i) neben einer Beschreibung.

![Auditprotokoll](assets/info-button-audit.png)

Die folgenden Informationen werden angezeigt:

| Element | Beschreibung |
| --- | --- |
| Aktionsname | Dies ist die Liste möglicher Aktionen: <ul><li>API_Request</li><li>Genehmigen</li><li>Erstellen</li><li>Bearbeiten</li><li>Exportieren</li><li>Login_failed</li><li>Login_success</li><li>Abmelden</li><li>Org_change</li><li>Aktualisieren</li><li>Freigeben</li><li>Übertragen</li><li>Genehmigung aufheben</li><li>Freigabe aufheben</li></ul> |
| Beschreibung | Eine Zusammenfassung der Aktion, des Komponententyps (mit ID) und anderer Werte. |
| Benutzername | Der Benutzer, der die Aktion durchführt. |
| Typ der Komponente | Mögliche Komponententypen sind: <ul><li>Anmerkung</li><li>Zielgruppe</li><li>Berechnete Metrik</li><li>Verbindung</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>Filter</li><li>IMS_Org</li><li>Mobile</li><li>Projekt</li><li>Bericht</li><li>Scheduled_Project</li><li>Benutzer</li><li>User_Group</li></ul> |
| Kennung der IMS-Organisation | Eine eindeutige ID, die Ihrer Instanz bei der ersten Anmeldung bei Adobe Experience Cloud zugewiesen wird. Sie sollte im folgenden Format vorliegen: xxx@AdobeOrg |
| Benutzer-ID | Eine eindeutige ID, die den/die Benutzende repräsentiert, der/die diese Aktion ausgeführt hat. |
| Erstellt am | Zeitpunkt, zu dem diese Aktion durchgeführt wurde. |
| E-Mail | Die E-Mail des/der Benutzenden, der/die die Aktion durchgeführt hat. |
| Komponenten-ID | Eine eindeutige ID, die die Komponente identifiziert, für die eine Aktion durchgeführt wird. |
| Protokoll-ID | Eine eindeutige ID für diesen Protokolleintrag. |
| Benutzertyp | Mögliche Typen sind: IMS, OKTA |

### Filtern von Auditprotokollen

Wählen Sie das Trichtersymbol (![Filter](assets/filter-icon.png)), um eine Liste von Filterfeldern anzuzeigen, mit denen die Ergebnisse eingegrenzt werden können. Unabhängig von den ausgewählten Filtern werden nur die letzten 1.000 Datensätze angezeigt.

![Filter](assets/filters.png)

Die Benutzeroberfläche verfügt für Protokolle über folgende Filter:

| Filter | Beschreibung |
| --- | --- |
| [!UICONTROL Datumsbereich] | Sie können nach einem Datumsbereich filtern, indem Sie ein Datum auswählen. Sie können einen Datumsbereich auswählen, indem Sie den Cursor über mehrere Daten ziehen. Standardmäßig sind das heutige und das gestrige Datum ausgewählt. |
| [!UICONTROL Aktion] | Sie können nach einer oder mehreren der folgenden Aktionen filtern: <ul><li>API_Request</li><li>Genehmigen</li><li>Erstellen</li><li>Bearbeiten</li><li>Exportieren</li><li>Login_failed</li><li>Login_success</li><li>Abmelden</li><li>Org_change</li><li>Aktualisieren</li><li>Freigeben</li><li>Übertragen</li><li>Genehmigung aufheben</li><li>Freigabe aufheben</li></ul> |
| [!UICONTROL Benutzer-ID] | Filtern nach der Benutzer-ID eines/einer bestimmten Benutzenden. Die Benutzer-ID finden Sie, indem Sie auf die Info-Schaltfläche (i) neben einem Benutzernamen klicken. |
| [!UICONTROL E-Mail] | Filtern nach der E-Mail-Adresse eines/einer bestimmten Benutzenden. Die E-Mail-Adresse finden Sie, indem Sie auf die Info-Schaltfläche (i) neben einem Benutzernamen klicken. |
| [!UICONTROL Komponenten-ID] | Filtern nach einer bestimmten Komponenten-ID. Die Komponenten-ID finden Sie, indem Sie auf die Info-Schaltfläche (i) für die gewünschte Komponente klicken. |
| [!UICONTROL Typ der Komponente] | Filtern nach einem oder mehreren Komponententypen: <ul><li>Anmerkung</li><li>Zielgruppe</li><li>Berechnete Metrik</li><li>Verbindung</li><li>Data_Group</li><li>Data_View</li><li>Feature_Access</li><li>Filter</li><li>IMS_Org</li><li>Mobile</li><li>Projekt</li><li>Bericht</li><li>Scheduled_Project</li><li>Benutzer</li><li>User_Group</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Von Auditprotokollen erfasste Ereignistypen

In der folgenden Tabelle ist aufgeführt, welche Aktionen für welche Komponenten durch Auditprotokolle aufgezeichnet werden:

| Typ der Komponente | Aktionen |
| --- | --- |
| [!UICONTROL Anmerkung] | <ul><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Zielgruppe] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li><li>Exportieren</li><li>Aktualisieren</li></ul> |
| [!UICONTROL Berechnete Metrik] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Verbindung] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Datenansicht] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Datumsbereich] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Filter] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL IMS-Organisation] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Projekt ] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Bericht] | <ul><li>API_Request</li></ul> |
| [!UICONTROL Geplantes Projekt] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Benutzer] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |
| [!UICONTROL Benutzergruppe] | <ul><li>API_Request</li><li>Erstellen</li><li>Löschen</li><li>Bearbeiten</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Herunterladen von Auditprotokollen

Sie können Auditprotokolle im CSV- oder JSON-Format herunterladen. Alle angewendeten Filter oder ausgewählten Spalten werden in den heruntergeladenen Dateien übernommen.

1. Klicken Sie in der rechten oberen Ecke des Bildschirms auf **[!UICONTROL Herunterladen]**.
1. Geben Sie das Format an.
1. Klicken Sie erneut auf **[!UICONTROL Herunterladen]**.

## Verwalten von Auditprotokollen in der API

Alle Aktionen, die Sie in der Benutzeroberfläche ausführen können, können auch über API-Aufrufe ausgeführt werden. Weitere Informationen finden Sie in der [CJA-API-Dokumentation](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs).
