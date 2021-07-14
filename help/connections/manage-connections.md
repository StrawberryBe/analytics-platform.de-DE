---
title: Verbindungen verwalten
description: Beschreibt, wie Verbindungen zu Experience Platform-Datensätzen in Customer Journey Analytics (CJA) verwaltet werden.
mini-toc-levels: 3
source-git-commit: ec76734f270666d13db28fd60ffdf62c04e378bf
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 8%

---

# Verbindungen verwalten

Sobald Admin-Benutzer [eine oder mehrere Verbindungen](/help/connections/create-connection.md) erstellt haben, können sie diese im Manager [!UICONTROL Verbindungen] verwalten. Das neueste Update der Verbindungserfahrung bietet zwei wichtige Funktionen auf der Seite Verbindungsdetails , die weiter unten auf dieser Seite beschrieben werden:

* Damit können Sie den Status **der Datensätze Ihrer Verbindung und des Aufnahmevorgangs** überprüfen. Mit dieser Statusprüfung erfahren Sie, wann Ihre Daten verfügbar sind, damit Sie zu Analysis Workspace gehen und mit der Analyse beginnen können.

* Damit können Sie **alle Datendiskrepanzen** aufgrund einer Fehlkonfiguration identifizieren. Vermissen Sie Zeilen? Wenn ja, welche Zeilen fehlen und warum? Haben Sie Verbindungen falsch konfiguriert und fehlende Daten in CJA verursacht?

>[!NOTE]
> Diese Funktion ist ab dem 19. August 2021 allgemein verfügbar.

## Connections Manager {#connections-manager}

Mit dem Connections Manager können Sie:

* Zeigen Sie alle Verbindungen auf einen Blick an, einschließlich des Eigentümers, der Sandbox und des Zeitpunkts ihrer Erstellung und Änderung.
* Alle Datensätze in einer Verbindung anzeigen.
* Überprüfen Sie den Status einer Verbindung.
* eine Verbindung löschen.
* eine Verbindung umbenennen.
* eine Datenschicht aus einer Verbindung erstellen.

![Verbindungen verwalten](assets/conn-manager.png)

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Name] | Der Anzeigename der Verbindung. Wenn Sie auf den Hyperlink-Namen klicken, gelangen Sie zur Seite Verbindungsdetails , die unten beschrieben wird. |
| Verbindungsinformationen | Klicken Sie auf das Informationssymbol neben dem Verbindungsnamen, um die folgenden Informationen anzuzeigen:![Verbindungsinformationen anzeigen](assets/conn-info.png) |
| Verbindung bearbeiten | Klicken Sie auf die Auslassungszeichen (..) neben dem Verbindungsnamen und dann auf [!UICONTROL Bearbeiten].![Verbindung bearbeiten ](assets/conn-edit-delete.png) Weitere Informationen finden Sie unten unter &quot;Verbindung bearbeiten&quot;. |
| eine Verbindung löschen | Klicken Sie auf die Auslassungszeichen (..) neben dem Verbindungsnamen und dann auf [!UICONTROL Löschen]. Weitere Informationen finden Sie unter der Überschrift &quot;Verbindungen löschen&quot;. |
| Datenansicht erstellen | Klicken Sie auf die Auslassungszeichen (..) neben dem Verbindungsnamen und dann auf [!UICONTROL Datenansicht erstellen]. Diese Aktion erstellt eine neue Datenansicht, die auf dieser Verbindung basiert. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Datensätze] | Die Datensätze, die Teil der Verbindung sind. Sie können auf den Hyperlink klicken, um alle Datensätze in der Verbindung anzuzeigen. Wenn Sie auf einen Datensatz klicken, wird dieser Datensatz in Adobe Experience Platform in einer neuen Registerkarte geöffnet. |
| [!UICONTROL Sandbox] | Die [Adobe Experience Platform-Sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en), aus der diese Verbindung ihre Datensätze zeichnet. Diese Sandbox wurde beim ersten Erstellen der Verbindung ausgewählt. Sie kann nicht geändert werden. |
| [!UICONTROL Inhaber] | Die Person, die die Verbindung hergestellt hat. |
| [!UICONTROL Importieren von Datensätzen] | Hiermit können Sie das so genannte &quot;Daten-Streaming&quot;aktivieren oder deaktivieren. |
| [!UICONTROL Erstellt am] | Das Datum, an dem die Verbindung zum ersten Mal erstellt wurde. |
| [!UICONTROL Zuletzt geändert] | Das Datum, an dem die Verbindung zuletzt aktualisiert wurde. |

### Verbindungen löschen {#connections-delete}

Nur Administratoren haben die Berechtigung, eine Verbindung zu löschen. Diese Aktion wird nicht für Administratoren angezeigt.

1. Klicken Sie auf die Auslassungspunkte (...) neben dem Verbindungsnamen.
1. Klicken Sie auf [!UICONTROL Löschen].

Wenn Sie eine Verbindung in [!UICONTROL Customer Journey Analytics] löschen, wird eine Fehlermeldung angezeigt, dass:

* Datenansichten, die auf der gelöschten Verbindung erstellt wurden, funktionieren nicht mehr.
* Ebenso funktionieren alle Workspace-Projekte nicht mehr, die von den Datenansichten der gelöschten Verbindung abhängig sind.

[Erfahren Sie ](/help/getting-started/cja-deletion.md) mehr über die Auswirkungen von Löschungen.

### Suchen nach einer Verbindung oder einem Datensatz

Sie können über die Suchleiste oben unter dem Titel [!UICONTROL Verbindungen] nach Verbindungen suchen.

### Verbindungen sortieren

Sie können Verbindungen sortieren, indem Sie auf jede Spaltenüberschrift klicken und nach oben oder unten sortieren.

## Seite &quot;Verbindungsdetails&quot; {#connection-detail}

Auf der neuen Seite Verbindungsdetails erhalten Sie einen sehr detaillierten Überblick über den Status einer Verbindung.

Damit können Sie:

* Überprüfen Sie den Status der Datensätze Ihrer Verbindung und des Aufnahmevorgangs.
* Ermitteln Sie Konfigurationsprobleme, die zu übersprungenen oder gelöschten Datensätzen führen.
* Ermitteln Sie, wann die Daten für Berichte verfügbar sind.

Im Folgenden werden Widgets und Einstellungen erläutert:

![Verbindungsdetails anzeigen](assets/conn-details.png)

| Widget/Einstellung | Beschreibung |
| --- | --- |
| Datensatz-Auswahl | Ermöglicht die Auswahl eines oder aller Datensätze in der Verbindung. Datensätze können nicht mehrmals ausgewählt werden. Die Standardeinstellung ist [!UICONTROL Alle Datensätze]. |
| Kalender/Datumsbereiche | Der Datumsbereich gibt an, wann Sie der Verbindung Daten hinzugefügt haben. Alle Standardkalendervorgaben sind enthalten. Sie können den Datumsbereich anpassen, es werden jedoch keine benutzerdefinierten Datumsbereiche in der Dropdown-Liste angezeigt. |
| [!UICONTROL Verfügbares ] Widget aufzeichnen | Stellt die Gesamtzahl der für die Berichterstellung verfügbaren Zeilen dar, **für die gesamte Verbindung**. Diese Anzahl ist unabhängig von Kalendereinstellungen. Es ändert sich, wenn Sie einen Datensatz aus der Datensatz-Auswahl auswählen oder indem Sie einen Datensatz in der Tabelle auswählen. ( Beachten Sie, dass es eine Latenz von 1-2 Stunden gibt, damit die Daten nach dem Hinzufügen in Berichten angezeigt werden.) |
|  Metriken-Widget | Fasst die hinzugefügten/übersprungenen/gelöschten Datensätze sowie die Anzahl der hinzugefügten Batches, **für den ausgewählten Datensatz und den ausgewählten Datumsbereich** zusammen. |
| [!UICONTROL Records ] addedwidget | Gibt an, wie viele Zeilen im ausgewählten Zeitraum hinzugefügt wurden, **für den ausgewählten Datensatz und Datumsbereich**. Alle zehn Minuten aktualisiert. |
| [!UICONTROL Datensatz-] skippedwidget | Gibt an, wie viele Zeilen im ausgewählten Zeitraum übersprungen wurden, **für den ausgewählten Datensatz und Datumsbereich**. Gründe für das Überspringen von Datensätzen sind: Fehlende Zeitstempel, fehlende Personen-ID usw. Alle zehn Minuten aktualisiert. |
| [!UICONTROL Datensätze löschen ] Widget | Gibt an, wie viele Zeilen im ausgewählten Zeitraum gelöscht wurden, **für den ausgewählten Datensatz und Datumsbereich**. Jemand könnte beispielsweise einen Datensatz in Experience Platform gelöscht haben. Alle zehn Minuten aktualisiert. |
| Datensatzsuchfeld | Sie können nach Datensatznamen oder [!UICONTROL Datensatz-ID] suchen. |
| [!UICONTROL Datensätze] | Zeigt die Datensätze an, die Teil der Verbindung sind. Sie können auf den Hyperlink klicken, um alle Datensätze in der Verbindung anzuzeigen. |
| [!UICONTROL Datensatz-ID] | Diese ID wird automatisch von Adobe Experience Platform generiert. |
| [!UICONTROL Batches] | Gibt an, wie viele Daten-Batches zu diesem Datensatz hinzugefügt wurden. |
| [!UICONTROL Zuletzt hinzugefügt] | Zeigt den Zeitstempel für den zuletzt zu diesem Datensatz hinzugefügten Batch an. |
| [!UICONTROL Typ des Datensatzes] | Der Datensatztyp für diesen Datensatz kann [!UICONTROL Ereignis], [!UICONTROL Suche] oder [!UICONTROL Profil] sein. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| Schema | Das Adobe Experience Platform-Schema, auf dem die Datensätze in dieser Verbindung basieren. |
| **Rechtsleiste auf Verbindungsebene** |  |
| [!UICONTROL Aktualisieren] | Aktualisieren Sie die Verbindung, damit kürzlich hinzugefügte Datensätze angezeigt werden. |
| [!UICONTROL Löschen] | Löschen Sie diese Verbindung. |
| [!UICONTROL Datenansicht erstellen] | Erstellen Sie eine neue Datenansicht, die auf dieser Verbindung basiert. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL Name der Verbindung] | Zeigt den Anzeigenamen der Verbindung an. |
| [!UICONTROL Verbindungsbeschreibung] | Zeigt eine detailliertere Beschreibung an, die den Zweck dieser Verbindung idealerweise beschreibt. |
| [!UICONTROL Personen-ID] | Zeigt eine Identität an, die im Datensatzschema in der Experience Platform definiert wurde. Dies ist die [!UICONTROL Personen-ID], die Sie bei der Erstellung der Verbindung ausgewählt haben. Wenn Sie eine Verbindung erstellen, die Datensätze mit unterschiedlichen IDs enthält, spiegelt die Berichterstellung dies wider. Um Datensätze wirklich zusammenzuführen, müssen Sie dieselbe [!UICONTROL Personen-ID] verwenden. |
| [!UICONTROL Sandbox] | Die [Adobe Experience Platform-Sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en), aus der diese Verbindung ihre Datensätze zieht. Diese Sandbox wurde beim ersten Erstellen der Verbindung ausgewählt. Sie kann nicht geändert werden. |
| [!UICONTROL Verbindungs-ID] | Diese ID wird in Adobe Experience Platform vom System generiert. |
| [!UICONTROL Kennung der IMS-Organisation] | Die [Organisations-ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en), die mit Ihrem bereitgestellten Experience Cloud-Unternehmen verknüpft ist. Zuvor als &quot;Login Company&quot; bezeichnet. |
| [!UICONTROL Datenaufrufe, die Verbindungen verwenden] | Listet alle Datenansichten auf, die diese Verbindung verwenden. |
| [!UICONTROL Neue Daten importieren] | Gibt an, ob den historischen Daten (Aufstockung) neue Datenstapel hinzugefügt werden sollen oder nicht. |
| **Rechtsleiste auf Datensatzebene** |  |
| [!UICONTROL Beschreibung des Datensatzes] | Beschreibt die Parameter der einzelnen Datensätze in dieser Verbindung. |
| [!UICONTROL Verfügbare Datensätze] | Stellt die Gesamtzahl der Zeilen dar, die für diesen Datensatz in dem im Kalender ausgewählten Zeitraum aufgenommen wurden. Es gibt keine Latenz dafür, wie die Daten nach dem Hinzufügen in Berichten angezeigt werden. (Die Ausnahme ist, dass beim Erstellen einer brandneuen Verbindung [Latenz](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#3.-getting-data-in-customer-Journey-analytics) vorhanden ist. |
| [!UICONTROL Hinzugefügte Datensätze] | Wie viele Zeilen wurden im ausgewählten Zeitraum hinzugefügt? |
| [!UICONTROL Übersprungene Datensätze] | Wie viele Zeilen während der Aufnahme im ausgewählten Zeitraum übersprungen wurden. |
| [!UICONTROL Fehler bei ausgelassenen Datensätzen] | Der Grund, warum Datensätze übersprungen wurden, wird hier angegeben. Dazu können fehlende Zeitstempel, fehlende Personen-ID usw. gehören. |
| [!UICONTROL Aufgenommene Batches] | Wie viele Daten-Batches wurden diesem Datensatz hinzugefügt. |
| [!UICONTROL Zuletzt hinzugefügt] | Der Zeitpunkt, zu dem der letzte Batch hinzugefügt wurde. |
| [!UICONTROL Typ des Datensatzes] | Entweder [!UICONTROL Ereignis], [!UICONTROL Suche] oder [!UICONTROL Profil]. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| [!UICONTROL Schema] | Das Adobe Experience Platform-Schema, auf dem dieser Datensatz basiert. |
| [!UICONTROL Datensatz-ID] | Diese ID wird in Adobe Experience Platform vom System generiert. |
| [!UICONTROL Aufstockungsdaten] | Aufstockungsdaten (historische Daten) werden in drei Status verfolgt: [!UICONTROL In Warteschlange], [!UICONTROL Gestartet] (mit angegebenem Fortschrittsprozentsatz) und [!UICONTROL Abgeschlossen]. |

### Verbindung bearbeiten

Ermöglicht es Administratoren, die Verbindung zu bearbeiten. Wählen Sie eine Verbindung aus und klicken Sie dann auf [!UICONTROL Verbindung bearbeiten], um zu diesem Dialogfeld zu gelangen. Hier können Sie Folgendes tun:

* Import neuer Daten starten und beenden. Dieser Prozess wurde früher als &quot;Daten-Streaming&quot;bezeichnet.
* eine Verbindung umbenennen.
