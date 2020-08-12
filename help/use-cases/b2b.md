---
title: (B2B) Hinzufügen Daten auf Kontoebene als Abfragedatensatz
description: Erfahren Sie, wie Sie CJA kontobasierte Daten als Nachschlagedataset hinzufügen
translation-type: tm+mt
source-git-commit: e3d4a672c33b8c536246836a062d544e3d5b8a01
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 2%

---


# (B2B) Hinzufügen Daten auf Kontoebene als Abfragedatensatz

Dieser B2B-Anwendungsfall zeigt Ihnen, wie Sie Ihre Daten für die Analyse auf Kontoebene und nicht auf Personenebene angeben können. Die Analyse auf Kontoebene kann Fragen wie

* Welcher Firmen-Name ist mit diesem Konto verknüpft?
* Wie viele Mitarbeiter sind mit diesem Konto/dieser Firma verbunden?
* Welche Rollen sind in diesem Konto vertreten?
* Wie verhält sich dieses Konto im Vergleich zu einem anderen Konto in Bezug auf eine bestimmte Marketing-Kampagne insgesamt?
* Verhalten sich bestimmte Rollen (z. B. IT-Manager) bei einem Konto anders als bei einem anderen Konto dieselbe Rolle?

You accomplish all this by bringing in the account-level information as a [lookup](/help/getting-started/cja-glossary.md) Datensatz (ähnlich wie Klassifizierungen im traditionellen Adobe Analytics).

Zuerst erstellen Sie in Adobe Experience Platform ein Lookup-Schema und dann einen Lookup-Tabellendatensatz, indem Sie CSV-basierte Kontodaten eingeben. Anschließend erstellen Sie eine Verbindungs-CJA, die verschiedene Datensätze kombiniert, einschließlich des von Ihnen erstellten Lookups. Anschließend erstellen Sie eine Datenansicht und können schließlich alle Daten in Workspace nutzen.

>[!NOTE]
>
>Suchtabellen können bis zu 1 GB groß sein.

## 1. Schema für Suche erstellen (Experience Platform)

Creating your own schema for the [lookup](/help/getting-started/cja-glossary.md) stellt sicher, dass der verwendete Datensatz in CJA mit dem richtigen Setup (Datensatztyp) verfügbar ist. Best practice is to [Erstellen einer benutzerdefinierten Schema-Klasse](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) &quot;Suche&quot;, leer von jedem Element, das für alle Suchtabellen wiederverwendet werden kann.

![](assets/create-new-class.png)

## 2. Suchdatensatz erstellen (Experience Platform)

Nachdem das Schema erstellt wurde, müssen Sie einen Nachschlagedatensatz aus diesem Schema in Experience Platform erstellen. Dieser Nachschlagedatensatz enthält Marketinginformationen auf Kontoebene, z. B.: Name der Firma, Gesamtanzahl der Mitarbeiter, Domänenname, Branchenzugehörigkeit, Jahresumsatz, ob es sich um aktuelle Kunden der Experience Platform handelt oder nicht, in welcher Verkaufsstufe sie sich befinden, welches Kontoteam CJA verwendet usw.

1. In Adobe Experience Platform gehen Sie zu **[!UICONTROL Data Management > Datasets]**.
1. Click **[!UICONTROL + Datensatz erstellen]**.
1. Klicken **[!UICONTROL Create dataset from schema]**.
1. Wählen Sie die von Ihnen erstellte Lookup-Schema-Klasse aus.
1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Benennen Sie den Datensatz (in unserem Beispiel B2B-Info) und geben Sie eine Beschreibung ein.
1. Klicken Sie auf **[!UICONTROL Fertigstellen]**.

## 3. Ingest data into Experience Platform

Anweisungen zum [Zuordnen einer CSV-Datei zu einem XDM-Schema](https://docs.adobe.com/content/help/en/experience-platform/ingestion/tutorials/map-a-csv-file.html) sollte Ihnen helfen, wenn Sie eine CSV-Datei verwenden.

[Andere Methoden](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) sind auch verfügbar.

Je nach Größe der Suchtabelle dauert es etwa 2 bis 4 Stunden, bis die Daten eingebettet und die Suche eingerichtet ist.

## 4. Datasets in einer Verbindung kombinieren (Customer Journey Analytics)

In diesem Beispiel kombinieren wir 3 Datensätze zu einer CJA-Verbindung:

| Datensatzname | Beschreibung | AEP-Schema-Klasse | Datensatzdetails |
|---|---|---|---|
| B2B-Impression | Enthält Clickstream- und Ereignis-Daten auf Kontoebene. Es enthält beispielsweise die E-Mail-ID und die entsprechende Konto-ID sowie den Marketingnamen für die Ausführung von Marketinganzeigen. Er enthält auch die Impressionen für diese Anzeigen pro Benutzer. | Basierend auf der XDM ExperienceEvent-Schema-Klasse | Die `emailID` wird als primäre Identität verwendet und einer `Customer ID` namensraum. Daher wird es als Standard angezeigt **[!UICONTROL Person-ID]** in Customer Journey Analytics. ![Impressionen](assets/impressions-mixins.png) |
| B2B-Profil | Dieser Profil-Datensatz informiert Sie über die Benutzer in einem Konto, wie z.B. ihre Berufsbezeichnung, ihr Konto, ihr LinkedIn-Profil usw. | Basierend auf der XDM Individuelle Profil Schema-Klasse | No need to select `emailID` als primäre ID in diesem Schema. Stellen Sie sicher, dass **[!UICONTROL Profil]**; if you don&#39;t, CJA will not be able to connect the `emailID` im B2B-Profil mit dem `emailID` in B2B-Impressionsdaten. (Diese Funktion wird als &quot;Feldbasierte Suche&quot;bezeichnet.) ![Profil](assets/profile-mixins.png) |
| B2B-Info | See &quot;Create lookup data set&quot; above. | B2BAccount (benutzerdefinierte Lookup-Schema-Klasse) | The relationship between `accountID` und der B2B-Impressions-Datensatz wurde automatisch erstellt, indem der B2B-Info-Datensatz mit dem B2B-Impressionsdataset in CJA verbunden wurde, wie in den folgenden Schritten beschrieben. ![Suche](assets/lookup-mixins.png) |

So kombinieren Sie die Datensätze:

1. In Customer Journey Analytics, select the **[!UICONTROL Verbindungen]** angezeigt.
1. Wählen Sie die Datensätze aus (in unserem Beispiel die drei oben genannten), die Sie kombinieren möchten.
1. Wählen Sie für den B2B-Info-Datensatz die Variable `accountID` key that will be used in your lookup table. Wählen Sie dann den zugehörigen Schlüssel (entsprechende Dimension), auch `accountID` in Ihrem Ereignis-Datensatz.
1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Name and describe the connection and configure it according to [diese Anweisungen](/help/connections/create-connection.md).
1. Klicken Sie auf **[!UICONTROL Speichern]**.

## 5. Eine Datenansicht aus dieser Verbindung erstellen

Follow instructions on [Erstellen von Datenansichten](/help/data-views/create-dataview.md).

* hinzufügen alle Komponenten (Dimensionen und Metriken), die Sie aus den Datensätzen benötigen.

## 6. Analysieren der Daten in Workspace

Sie können jetzt Workspace-Projekte basierend auf den Daten aus allen 3 Datensätzen erstellen.

Sie können beispielsweise Antworten auf die Antworten finden, die in der Einführung gestellt werden:

* Unterteilen Sie die emailID nach accountID, um herauszufinden, zu welcher Firma eine E-Mail-ID gehört.
* Wie viele Mitarbeiter sind einer bestimmten Konto-ID zugeordnet?
* Zu welcher Branche gehört eine Konto-ID?

![](assets/project-lookup.png)
