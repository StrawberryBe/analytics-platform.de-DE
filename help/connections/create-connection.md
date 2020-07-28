---
title: Verbindung herstellen
description: Beschreibt, wie eine Verbindung zu einem Platform-Datensatz in Customer Journey Analytics hergestellt wird.
translation-type: tm+mt
source-git-commit: 756c6e7c187b76636cf96d18c949908a97db51ed
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 38%

---


# Verbindung herstellen

A connection lets you integrate datasets from [!DNL Adobe Experience Platform] into [!UICONTROL Workspace]. In order to report on [!DNL Experience Platform] datasets, you first have to establish a connection between datasets in [!DNL Experience Platform] and [!UICONTROL Workspace].

Eine Videoübersicht finden Sie [hier](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html).

>[!IMPORTANT]
>
>Sie können mehrere [!DNL Experience Platform]-Datensätze zu einer Verbindung zusammenfassen.

1. Gehen Sie zu [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Klicken Sie oben rechts auf Neue Verbindung **** erstellen.

   ![Verbindung herstellen](assets/create-connection0.png)

1. Wählen Sie eine Sandbox in der Experience Platform aus, die die Datensätze enthält, zu denen Sie eine Verbindung herstellen möchten.

   Adobe Experience Platform provides [sandboxes](https://docs.adobe.com/content/help/de-DE/experience-platform/sandbox/home.html) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. Sandboxes können als &quot;Datensilos&quot;mit Datensätzen betrachtet werden. Sandboxen dienen zur Steuerung des Zugriffs auf Datensätze. Sie können nicht über Sandboxen auf Daten zugreifen. Nachdem Sie die Sandbox ausgewählt haben, zeigt die linke Leiste alle Datensätze in der Sandbox an, aus denen Sie ziehen können.

1. Select one or more dataset(s) you want to pull into [!UICONTROL Customer Journey Analytics] and click **[!UICONTROL Add]**.

   (If you have a lot of datasets to choose from, you can search for the right one(s) using the **[!UICONTROL Search datasets]** search bar above the list of datasets.)

## Datensatz konfigurieren

Auf der rechten Seite können Sie jetzt den hinzugefügten Datensatz konfigurieren.

![Datensatz konfigurieren](assets/create-connection.png)

1. **[!UICONTROL Datensatztyp]**: Für jeden Datensatz, den Sie dieser Verbindung hinzugefügt haben, legt [!UICONTROL Customer Journey Analytics] den Datensatztyp automatisch anhand der Daten fest, die eingehen.

   There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

   | Typ des Datensatzes | Beschreibung | Zeitstempel | Schema | Personen-ID |
   |---|---|---|---|---|
   | [!UICONTROL Ereignis-] | Daten, die zeitliche Ereignis darstellen (z. B. Webbesuche, Interaktionen, Transaktionen, POS-Daten, Umfragedaten, Ad-Impression-Daten usw.). Dies können beispielsweise typische Klickdaten mit einer Kunden-ID oder einer Cookie-ID und einem Zeitstempel sein. Bei Ereignisdaten können Sie entscheiden, welche ID als Personen-ID verwendet wird. | Wird automatisch auf das standardmäßige Zeitstempelfeld von ereignisbasierten Schemata in [UICONTROL Experience Platform] gesetzt. | Jedes integrierte oder benutzerdefinierte Schema, das auf einer XDM-Klasse mit dem Verhalten „Zeitreihen“ basiert. Beispiele sind „XDM-Erlebnisereignis“ oder „XDM-Entscheidungsereignis“. | Sie können auswählen, welche Personen-ID Sie einbeziehen möchten. Für jedes in Experience Platform definierte Datensatzschema kann ein eigener Satz von einer oder mehreren Identitäten definiert und mit einem Identitäts-Namespace verknüpft werden. Jede dieser Optionen kann als Personen-ID verwendet werden. Beispiele sind Cookie-ID, zugeordnete ID, Benutzer-ID, Trackingcode usw. |
   | [!UICONTROL Suche] | Entspricht einer Classifications-Datei. Diese Daten werden verwendet, um nach Werten oder Schlüsseln in Ihren Ereignis- oder Profildaten zu suchen. Beispielsweise können Sie Suchdaten hochladen, die numerische IDs in Ihren Ereignisdaten Produktnamen zuordnen. | nicht angegeben | Jedes integrierte oder benutzerdefinierte Schema, das auf einer XDM-Klasse mit dem Verhalten „Eintrag“ basiert, mit Ausnahme der Klasse „XDM-Individuelles Profil“. | nicht angegeben |
   | [!UICONTROL Profil] | Analogous to [!UICONTROL Customer Attributes] - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. Sie können beispielsweise CRM-Daten zu Ihren Kunden hochladen. | nicht angegeben | Jedes integrierte oder benutzerdefinierte Schema, das auf der Klasse „XDM-Individuelles Profil“ basiert. | Sie können auswählen, welche Personen-ID Sie einbeziehen möchten. Für jeden in [!DNL Experience Platform] definierten Datensatz ist ein eigener Satz von einer oder mehreren definierten Personen-IDs definiert, z. B. Cookie-ID, zugeordnete ID, Benutzer-ID, Trackingcode usw.<br>![Personen-ID](assets/person-id.png)**Hinweis:** Wenn Sie eine Verbindung erstellen, die Datensätze mit unterschiedlichen IDs enthält, wird dies in der Berichterstellung berücksichtigt. Um Datensätze zusammenzuführen, müssen Sie dieselbe Personen-ID verwenden. |

1. **[!UICONTROL Datenbestand-ID]**: Diese ID wird automatisch generiert.

1. **[!UICONTROL Zeitstempel]**: Inhalt hier hinzufügen

1. **[!UICONTROL Schema]**: Dies ist das [Schema](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/schema/composition.html) , auf dem der Datensatz in Adobe Experience Platform erstellt wurde.

1. **[!UICONTROL Person-ID]**: Wählen Sie eine Personen-ID aus der Dropdown-Liste der verfügbaren Identitäten. Diese Identitäten wurden im DataSet-Schema in der Experience Platform definiert. Weitere Informationen zur Verwendung von Identity Map als Personen-ID finden Sie unten.

   >[!IMPORTANT]
   >
   >Wenn keine Personen-IDs zur Auswahl stehen, bedeutet das, dass eine oder mehrere Personen-IDs im Schema nicht definiert wurden. Ansicht [dieses Videos](https://youtu.be/G_ttmGl_LRU) zum Definieren einer Identität in der Experience Platform.

1. Klicken Sie auf **[!UICONTROL Weiter]** , um das Dialogfeld Verbindung [!UICONTROL aktivieren] aufzurufen.

### Identitätskarte als Personen-ID verwenden

Customer Journey Analytics unterstützt jetzt die Möglichkeit, die Identitätskarte für seine Person-ID zu verwenden. Identity Map ist eine Map-Datenstruktur, die es jemandem ermöglicht, Schlüssel -> Wert Paare hochzuladen. Bei den Namensräumen handelt es sich um Identitätsschlüssel und bei dem Wert um eine Struktur, die den Identitätswert enthält. Die Identitätszuordnung existiert auf jeder hochgeladenen Zeile/jedem hochgeladenen Ereignis und wird für jede Zeile entsprechend gefüllt.

Die Identitätszuordnung ist für alle Datensätze verfügbar, die ein Schema verwenden, das auf der XDM- [Klasse](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/home.html) von ExperienceEvent basiert. Wenn Sie einen solchen Datensatz für eine CJA-Verbindung auswählen, können Sie entweder ein Feld als primäre ID oder die Identitätszuordnung auswählen:

![](assets/idmap1.png)

Wenn Sie &quot;Identitätskarte&quot;auswählen, erhalten Sie zwei zusätzliche Konfigurationsoptionen:

| Option | Beschreibung |
|---|---|
| [!UICONTROL Primären ID-Namespace verwenden] | Dadurch wird CJA angewiesen, die Identität in der Identitätszuordnung, die mit dem Attribut &quot;primary=true&quot;gekennzeichnet ist, pro Zeile zu suchen und diese als Personen-ID für diese Zeile zu verwenden. Dies bedeutet, dass dies der Hauptschlüssel ist, der in der Experience Platform für die Partitionierung verwendet wird. Es ist außerdem der beste Kandidat für die Verwendung als CJA-Besucher-ID (je nachdem, wie der Datensatz in einer CJA-Verbindung konfiguriert ist). |
| [!UICONTROL Namespace] | (Diese Option ist nur verfügbar, wenn Sie den Namensraum für die Primär-ID nicht verwenden.) Identity namespaces are a component of [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html) that serve as indicators of the context to which an identity relates. Wenn Sie einen Namensraum angeben, sucht CJA in der Identitätszuordnung jeder Zeile nach diesem Namensraum-Schlüssel und verwendet die Identität unter diesem Namensraum als Personen-ID für diese Zeile. Beachten Sie, dass, da CJA nicht alle Zeilen vollständig scannen kann, um festzustellen, welche Namensraum tatsächlich vorhanden sind, alle möglichen Namensraum in der Dropdown-Liste aufgeführt werden. Sie müssen wissen, welche Namensraum in den Daten angegeben werden. kann nicht automatisch erkannt werden. |

### Edge-Fälle von Identitätszuordnungen

Die folgende Tabelle zeigt die beiden Konfigurationsoptionen, wenn Edge-Fälle vorhanden sind und wie sie behandelt werden:

| Option | In der Identitätszuordnung sind keine IDs vorhanden | Keine IDs werden als primär markiert | Mehrere IDs werden als primär markiert | Eine einzelne ID wird als primär markiert | Ungültiger Namensraum mit einer als primär markierten ID |
|---|---|---|---|---|---|
| **&quot;Primär ID-Namensraum verwenden&quot;markiert** | Die Zeile wird von CJA abgelegt. | Die Zeile wird von CJA abgelegt, da keine primäre ID angegeben wurde. | Alle als primär markierten IDs werden unter allen Namensräumen in eine Liste extrahiert. Sie werden dann alphabetisch sortiert; Bei dieser neuen Sortierung wird der erste Namensraum mit der ersten ID als Personen-ID verwendet. | Die als primär markierte einzelne ID wird als Person-ID verwendet. | Obwohl der Namensraum ungültig sein kann (nicht in AEP vorhanden), verwendet CJA die primäre ID unter diesem Namensraum als Personen-ID. |
| **Spezifischer Identitätszuordnungs-Namensraum ausgewählt** | Die Zeile wird von CJA abgelegt. | Alle IDs unter dem ausgewählten Namensraum werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. | Alle IDs unter dem ausgewählten Namensraum werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. | Alle IDs unter dem ausgewählten Namensraum werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. | Alle IDs unter dem ausgewählten Namensraum werden in eine Liste extrahiert und die erste wird als Personen-ID verwendet. (Bei der Erstellung der Verbindung kann nur ein gültiger Namensraum ausgewählt werden. Daher ist es nicht möglich, einen ungültigen Namensraum/eine ungültige ID als Personen-ID zu verwenden.) |

## Verbindung aktivieren

![Verbindung aktivieren](assets/create-connection2.png)

1. Um eine Verbindung zu aktivieren, definieren Sie die folgenden Einstellungen:

   | Option | Beschreibung |
   |---|---|
   | [!UICONTROL Verbindung benennen] | Geben Sie der Verbindung einen beschreibenden Namen. Die Verbindung kann nicht ohne Namen gespeichert werden. |
   | [!UICONTROL Beschreibung] | Fügen Sie weitere Details hinzu, um diese Verbindung von anderen zu unterscheiden. |
   | [!UICONTROL Datensätze] | Die in dieser Verbindung enthaltenen Datensätze. |
   | [!UICONTROL Importieren Sie alle neuen Datensätze in dieser Verbindung automatisch, beginnend heute.] | Select this option if you want to establish an ongoing connection, so that any new data batches that get added to the datasets in this connection automatically flow into [!UICONTROL Workspace]. |
   | [!UICONTROL Alle vorhandenen Daten importieren] | Wenn Sie diese Option auswählen und die Verbindung speichern, werden alle vorhandenen (historischen) Daten von [!DNL Experience Platform] für alle Datensätze importiert, die sich in dieser Verbindung befinden. In Zukunft werden für alle neuen Datensätze, die dieser gespeicherten Verbindung hinzugefügt werden, auch alle vorhandenen historischen Daten automatisch importiert. <br>**Beachten Sie, dass diese Einstellung nach dem Speichern dieser Verbindung nicht mehr geändert werden kann.** |

   **Bedenken Sie Folgendes:**

   * Wenn die kumulative Größe der historischen Daten für alle Datensätze in der Verbindung 1,5 Milliarden Zeilen überschreitet, wird eine Fehlermeldung angezeigt, dass Sie diese Menge an historischen Daten nicht importieren können. Wenn Sie jedoch einen Datensatz mit 1 Milliarde Zeilen historischer Daten hinzufügen und diese Daten importieren würden, und eine Woche später einen weiteren Datensatz derselben Größe hinzufügen und seine historischen Daten importieren würden, würde dies funktionieren.
   * Neue Daten, die einem Datensatz in der Verbindung hinzugefügt werden, werden priorisiert, sodass diese Daten die geringste Latenz aufweisen.
   * Alle (historischen) Aufstockungsdaten werden langsamer importiert.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Der nächste Schritt im Workflow ist das [Erstellen einer Datenansicht](/help/data-views/create-dataview.md).
