---
title: (B2B) Hinzufügen von Daten der Kontoebene als Lookup-Datensatz
description: Erfahren Sie, wie Sie in Customer Journey Analytics kontobasierte Daten als Lookup-Datensatz hinzufügen.
translation-type: tm+mt
source-git-commit: de5717d42fbe29554351a789cce594ac9ad47ee1
workflow-type: tm+mt
source-wordcount: '939'
ht-degree: 89%

---


# (B2B) Hinzufügen von Daten der Kontoebene als Lookup-Datensatz

Dieser Anwendungsfall für den B2B-Bereich zeigt auf, wie Sie festlegen, dass für Ihre Analysen nicht Daten der Personenebene verwendet werden, sondern solche der Kontoebene. Analysen auf Kontoebene liefern Aufschluss über folgende Fragen:

* Welcher Unternehmensname ist diesem Konto zugehörig?
* Wie viele Mitarbeiter sind diesem Konto/diesem Unternehmen zugeordnet?
* Welche Rollen sind in diesem Konto vertreten?
* Wie schneidet dieses Konto in Bezug auf die Leistung einer bestimmten Marketing-Kampagne im Vergleich zu einem anderen Konto ab?
* Weisen bestimmte Rollen (z. B. IT-Experten) im einen Konto ein von einem anderen Konto abweichendes Verhalten auf?

Aufschluss darüber erhalten Sie, indem Sie Informationen der Kontoebene als [Lookup](/help/getting-started/cja-glossary.md)-Datensatz (ähnlich der Klassifizierungen im klassischen Adobe Analytics) einspielen.

Erstellen Sie zunächst in Adobe Experience Platform ein Lookup-Schema und dann durch Aufnahme CSV-basierter Kontodaten einen Datensatz vom Typ „Lookup-Tabelle“. Im nächsten Schritt erstellen Sie eine CJA-Verbindung, die verschiedene Datensätze kombiniert, darunter auch den von Ihnen erstellen Lookup-Datensatz. Jetzt erstellen Sie noch eine Datenansicht. Damit können Sie alle diese Daten dann in Workspace nutzen.

>[!NOTE]
>
>Lookup-Tabellen können eine Größe von bis zu 1 GB erreichen.

## 1. Erstellen eines Lookup-Schemas (Experience Platform)

Durch die Erstellung eines eigenen Schemas für die [Lookup](/help/getting-started/cja-glossary.md)-Tabelle stellen Sie sicher, dass der verwendete Datensatz in CJA korrekt eingerichtet ist (d. h. den Typ „Datensatz“ aufweist). Als Best Practice empfiehlt sich die [Erstellung einer benutzerdefinierten Schemaklasse](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) mit dem Namen „Lookup“, die keinerlei Elemente enthält. Diese kann dann für alle Lookup-Tabellen wiederverwendet werden.

![](assets/create-new-class.png)

## 2. Erstellen eines Lookup-Datensatzes (Experience Platform)

Nachdem dem Erstellen des Schemas müssen Sie daraus in Experience Platform einen Lookup-Datensatz erstellen. Dieser Lookup-Datensatz enthält Marketing-Informationen auf Kontoebene wie etwa den Unternehmensnamen, die Gesamtzahl der Mitarbeiter, den Namen der Domain, die Branche, in der das Unternehmen tätig ist, den Jahresumsatz, ob es sich um aktuelle Kunden von Experience Platform handelt oder nicht, in welcher Phase des Verkaufszyklus sie sich befinden, welches Team in diesem Konto CJA nutzt usw.

>[!IMPORTANT]
>
>CJA unterstützt keine Ganzzahlen in Lookup-Datensätzen. Wenn Sie die ganzzahligen Felder in Ihrem XDM-Schema für Ihren Nachschlagedataset hinzufügen, können Sie diese Ganzzahlen nicht als Metriken oder berechnete Metriken verwenden. Wenn beispielsweise AnnualRevenue oder totalEmployees als Ganzzahlen definiert sind, wird in CJA als &quot;0&quot;in Berichte angezeigt. Wenn Sie sie jedoch als Zeichenfolgen zuweisen, können Sie sie als Nachschlageinformationen verwenden.

So werden beispielsweise &quot;yearRevenue&quot;oder &quot;totalEmployees&quot;im folgenden Beispiel als Integer definiert, was der Grund ist, dass &quot;0&quot;in CJA angezeigt wird.

1. Rufen Sie in Adobe Experience Platform **[!UICONTROL Daten-Management > Datensätze]** auf.
1. Klicken Sie auf **[!UICONTROL + Datensatz erstellen]**.
1. Klicken Sie auf **[!UICONTROL Datensatz aus Schema erstellen]**.
1. Wählen Sie die von Ihnen erstellte Lookup-Schemaklasse aus.
1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Geben Sie einen Namen für den Datensatz (in unserem Beispiel „B2B Info“) sowie eine Beschreibung ein.
1. Klicken Sie auf **[!UICONTROL Fertig stellen]**.

## 3. Erfassen von Daten in Experience Platform

Anweisungen zum [Zuordnen einer CSV-Datei zu einem XDM-Schema](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/tutorials/map-a-csv-file.html) können Ihnen helfen, wenn Sie eine CSV-Datei verwenden.

[Andere Methoden](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.html) sind auch verfügbar.

Je nach Größe der Lookup-Tabelle dauert die Aufnahme der Daten und die Erstellung der Lookup-Verbindung zwischen 2 und 4 Stunden.

## 4. Kombinieren der Datensätze in einer Verbindung (Customer Journey Analytics)

In diesem Beispiel kombinieren wir drei Datensätze zu einer CJA-Verbindung:

| Datensatzname | Beschreibung | AEP-Schemaklasse | Datensatzdetails |
|---|---|---|---|
| B2B Impressions | Umfasst Clickstream-Ereignisdaten auf Kontoebene. Beispiele für den Inhalt sind die E-Mail-ID einschließlich zugehöriger Konto-ID sowie der Marketing-Name für die Ausführung von Marketing-Anzeigen enthalten. Ebenfalls darin enthalten sind die pro Benutzer ermittelten Impressions für diese Anzeigen. | Basierend auf Schemaklasse „XDM ExperienceEvent“ | Verwenden Sie `emailID` als primäre Identität und weisen Sie als Namespace `Customer ID` zu. Dadurch wird sie in Customer Journey Analytics als die standardmäßige **[!UICONTROL Personen-ID]** angezeigt. ![Impressionen](assets/impressions-mixins.png) |
| B2B Profile | Dieser Profildatensatz liefert nähere Informationen über die in einem Konto enthaltenen Benutzer, z. B. deren Position im Unternehmen, welchem Konto sie zugeordnet sind, ihr LinkedIn-Profil usw. | Basierend auf Schemaklasse „XDM Individual Profile“ | Die Auswahl von `emailID` als primäre ID ist bei diesem Schema nicht erforderlich. Stellen Sie jedoch sicher, dass Sie **[!UICONTROL Profil]** aktivieren. Dies ist erforderlich, damit CJA die `emailID` aus „B2B Profil“ mit der `emailID` aus „B2B Impressions“ verbinden kann. (Diese Funktion wird als „feldbasiertes Zusammenfügen“ bezeichnet.) ![Profil](assets/profile-mixins.png) |
| B2B Info | Siehe „Erstellen eines Lookup-Datensatzes“ weiter oben. | B2BAccount (benutzerdefinierte Schemaklasse) | Die Beziehung zwischen `accountID` und dem Datensatz „B2B Impressions“ wurde automatisch erstellt, indem der Datensatz „B2B Info“ in CJA mit dem Datensatz „B2B Impressions“ verbunden wird, wie in den folgenden Schritten beschrieben. ![Suche](assets/lookup-mixins.png) |

Gehen Sie wie folgt vor, um die Datensätze zu kombinieren:

1. Rufen Sie in Customer Journey Analytics die Registerkarte **[!UICONTROL Verbindungen]** auf.
1. Wählen Sie die Datensätze aus, die Sie kombinieren möchten (in unserem Beispiel die drei in den Schritten oben erstellten).
1. Wählen Sie für den B2B-Info-Datensatz den Schlüssel `accountID`, der in Ihrer Suchtabelle verwendet wird. Wählen Sie dann den dazu passenden Schlüssel (der zugehörigen Dimension), also ebenfalls `accountID` aus Ihrem Ereignisdatensatz aus.
1. Klicken Sie auf **[!UICONTROL Weiter]**.
1. Geben Sie einen Namen und eine Beschreibung für die Verbindung ein und konfigurieren Sie sie entsprechend [dieser Anweisungen](/help/connections/create-connection.md).
1. Klicken Sie auf **[!UICONTROL Speichern]**.

## 5. Eine Ansicht mit Daten aus dieser Verbindung erstellen

Befolgen Sie die Anweisungen [Erstellen von Ansichten](/help/data-views/create-dataview.md).

* Fügen Sie alle Komponenten (d. h. Dimensionen und Metriken), hinzu, die sie aus den Datensätzen benötigen.

## 6. Analysieren der Daten in Workspace

Sie können jetzt Workspace-Projekte auf Basis der Daten aus allen drei Datensätzen erstellen.

Diese können Ihnen beispielsweise Aufschluss über die Fragen aus der Einführung erhalten.

* Wenn Sie die emailID nach accountID aufschlüsseln, können Sie etwa feststellen, welchem Unternehmen eine E-Mail-ID zugehörig ist.
* Welche Mitarbeiter einer bestimmten Konto-ID zugeordnet sind, können Sie ebenfalls herausfinden.
* Oder auch, welcher Branche eine Konto-ID zugehörig ist?

![](assets/project-lookup.png)
