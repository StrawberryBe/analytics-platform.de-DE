---
title: (B2B) Hinzufügen Daten auf Kontoebene als Abfragedatensatz
description: Erfahren Sie, wie Sie CJA kontobasierte Daten als Nachschlagedataset hinzufügen
translation-type: tm+mt
source-git-commit: 721915ffdc9f196a13a360fb5ac145f750788bcf
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 1%

---


# (B2B) Hinzufügen Daten auf Kontoebene als Abfragedatensatz

Dieser B2B-Anwendungsfall zeigt Ihnen, wie Sie Ihre Daten für die Analyse auf Kontoebene und nicht auf Personenebene angeben können. Die Analyse auf Kontoebene kann Fragen wie

* Welcher Firmen-Name ist mit diesem Konto verknüpft?
* Wie viele Mitarbeiter sind mit diesem Konto/dieser Firma verbunden?
* Welche Rollen sind in diesem Konto vertreten?
* Wie verhält sich dieses Konto im Vergleich zu einem anderen Konto in Bezug auf eine bestimmte Marketing-Kampagne insgesamt?
* Verhalten sich bestimmte Rollen (z. B. IT-Manager) bei einem Konto anders als bei einem anderen Konto dieselbe Rolle?

Dies erreichen Sie, indem Sie die Informationen auf Kontoebene als [lookup](/help/getting-started/cja-glossary.md) Datensatz (ähnlich wie Klassifizierungen im traditionellen Adobe Analytics).

Zuerst erstellen Sie in Adobe Experience Platform ein Lookup-Schema und dann einen Lookup-Tabellendatensatz, indem Sie CSV-basierte Kontodaten eingeben. Anschließend erstellen Sie eine Verbindungs-CJA, die verschiedene Datensätze kombiniert, einschließlich des von Ihnen erstellten Lookups. Anschließend erstellen Sie eine Datenansicht und können schließlich alle Daten in Workspace nutzen.

>[!NOTE]
>
>Suchtabellen können bis zu 1 GB groß sein.

## 1. Schema für Suche erstellen (Experience Platform)

Erstellen Sie Ihr eigenes Schema für die [lookup](/help/getting-started/cja-glossary.md) table ensures that the dataset used will be available in CJA with the correct setup (record type). Bewährte Verfahren: [Erstellen einer benutzerdefinierten Schema-Klasse](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) &quot;Suche&quot;, leer von jedem Element, das für alle Suchtabellen wiederverwendet werden kann.

![](assets/create-new-class.png)

## 2. Suchdatensatz erstellen (Experience Platform)

Nachdem das Schema erstellt wurde, müssen Sie einen Nachschlagedatensatz aus diesem Schema in Experience Platform erstellen. Dieser Nachschlagedatensatz enthält Marketinginformationen auf Kontoebene, z. B.: Name der Firma, Gesamtanzahl der Mitarbeiter, Domänenname, Branchenzugehörigkeit, Jahresumsatz, ob es sich um aktuelle Kunden der Experience Platform handelt oder nicht, in welcher Verkaufsstufe sie sich befinden, welches Kontoteam CJA verwendet usw.

1. In Adobe Experience Platform gehen Sie zu **[!UICONTROL Data Management > Datensätze]**.
1. Klicken **[!UICONTROL + Datensatz erstellen]**.
1. Klicken **[!UICONTROL Datensatz aus Schema erstellen]**.
1. Wählen Sie die von Ihnen erstellte Lookup-Schema-Klasse aus.
1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Benennen Sie den Datensatz (in unserem Beispiel B2B-Info) und geben Sie eine Beschreibung ein.
1. Klicken Sie auf **[!UICONTROL Fertigstellen]**.


## 3. Datasets in einer Verbindung kombinieren (Customer Journey Analytics)

In diesem Beispiel kombinieren wir 3 Datensätze zu einer CJA-Verbindung:

| Datensatzname | Beschreibung | AEP-Schema-Klasse | Datensatzdetails |
|---|---|---|---|
| B2B-Impression | Enthält Clickstream- und Ereignis-Daten auf Kontoebene. Es enthält beispielsweise die E-Mail-ID und die entsprechende Konto-ID sowie den Marketingnamen für die Ausführung von Marketinganzeigen. Er enthält auch die Impressionen für diese Anzeigen pro Benutzer. | Basierend auf der XDM ExperienceEvent-Schema-Klasse | Die `emailID` wird als primäre Identität verwendet und einer `Customer ID` namensraum. Daher wird es als Standard angezeigt **[!UICONTROL Person-ID]** in Customer Journey Analytics. ![Impressionen](assets/impressions-mixins.png) |
| B2B-Profil | Dieser Profil-Datensatz informiert Sie über die Benutzer in einem Konto, wie z.B. ihre Berufsbezeichnung, ihr Konto, ihr LinkedIn-Profil usw. | Basierend auf der XDM Individuelle Profil Schema-Klasse | Keine Auswahl erforderlich `emailID` als primäre ID in diesem Schema. Stellen Sie sicher, dass **[!UICONTROL Profil]**; if you don&#39;t, CJA will not be able to connect the `emailID` in B2B Profile with the `emailID` in B2B-Impressionsdaten. (Diese Funktion wird als &quot;Feldbasierte Suche&quot;bezeichnet.) ![Profil](assets/profile-mixins.png) |
| B2B-Info | Siehe &quot;Erstellen des Suchtabfragedatensatzes&quot;weiter oben. | B2BAccount (benutzerdefinierte Lookup-Schema-Klasse) | Die Beziehung zwischen `accountID` und der B2B-Impressions-Datensatz wurde automatisch erstellt, indem der B2B-Info-Datensatz mit dem B2B-Impressionsdataset in CJA verbunden wurde, wie in den folgenden Schritten beschrieben. ![Suche](assets/lookup-mixins.png) |

So kombinieren Sie die Datensätze:

1. Wählen Sie in Customer Journey Analytics die Option **[!UICONTROL Verbindungen]** angezeigt.
1. Wählen Sie die Datensätze aus (in unserem Beispiel die drei oben genannten), die Sie kombinieren möchten.
1. (Nicht sicher, wo der Schritt hingehört...) Wählen Sie für den B2B-Info-Datensatz die Option `accountID` -Schlüssel, der in Ihrer Suchtabelle verwendet wird. Then select its matching key (corresponding dimension), also `accountID` in Ihrem Ereignis-Datensatz.
1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Name and describe the connection and configure it according to [diese Anweisungen](/help/connections/create-connection.md).
1. Klicken Sie auf **[!UICONTROL Speichern]**.

Jetzt werden die Daten erfasst. Je nach Größe der Suchtabelle dauert es etwa 2 bis 4 Stunden, bis die Daten eingebettet und die Suche eingerichtet ist.

## Eine Datenansicht aus dieser Verbindung erstellen

Befolgen Sie die Anweisungen [Erstellen von Datenansichten](/help/data-views/create-dataview.md).

* hinzufügen alle Komponenten (Dimensionen und Metriken), die Sie aus den Datensätzen benötigen.

## Analysieren der Daten in Workspace

Sie können jetzt Workspace-Projekte basierend auf den Daten aus allen 3 Datensätzen erstellen.

Sie können beispielsweise Antworten auf die Antworten finden, die in der Einführung gestellt werden:

* Unterteilen Sie die emailID nach accountID, um herauszufinden, zu welcher Firma eine E-Mail-ID gehört.
* Wie viele Mitarbeiter sind einer bestimmten Konto-ID zugeordnet?
* Zu welcher Branche gehört eine Konto-ID?

![](assets/project-lookup.png)
