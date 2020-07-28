---
title: Verbindung herstellen
description: Beschreibt, wie eine Verbindung zu einem Platform-Datensatz in Customer Journey Analytics hergestellt wird.
translation-type: tm+mt
source-git-commit: 220f164ae128c47aa89b319829336a5fc1b3d8c4
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 65%

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

   ![Verbindung herstellen](assets/create-connection.png)

1. Wählen Sie eine Sandbox in der Experience Platform aus, die die Datensätze enthält, zu denen Sie eine Verbindung herstellen möchten.

   Adobe Experience Platform provides [sandboxes](https://docs.adobe.com/content/help/de-DE/experience-platform/sandbox/home.html) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. Sandboxes können als &quot;Datensilos&quot;mit Datensätzen betrachtet werden. Sandboxen dienen zur Steuerung des Zugriffs auf Datensätze. Sie können nicht über Sandboxen auf Daten zugreifen. Nachdem Sie die Sandbox ausgewählt haben, zeigt die linke Leiste alle Datensätze in der Sandbox an, aus denen Sie ziehen können.

1. Select one or more dataset(s) you want to pull into [!UICONTROL Customer Journey Analytics] and click **[!UICONTROL Add]**.

   (If you have a lot of datasets to choose from, you can search for the right one(s) using the **[!UICONTROL Search datasets]** search bar above the list of datasets.)

## Datensatz konfigurieren

Auf der rechten Seite können Sie jetzt den hinzugefügten Datensatz konfigurieren.

1. **[!UICONTROL Datensatztyp]**: Für jeden Datensatz, den Sie dieser Verbindung hinzugefügt haben, legt [!UICONTROL Customer Journey Analytics] den Datensatztyp automatisch anhand der Daten fest, die eingehen.

   There are 3 different dataset types: [!UICONTROL Event] data, [!UICONTROL Profile] data, and [!UICONTROL Lookup] data.

   | Typ des Datensatzes | Beschreibung | Zeitstempel | Schema | Personen-ID |
   |---|---|---|---|---|
   | [!UICONTROL Ereignis-] | Daten, die zeitliche Ereignis darstellen (z. B. Webbesuche, Interaktionen, Transaktionen, POS-Daten, Umfragedaten, Ad-Impression-Daten usw.). Dies können beispielsweise typische Klickdaten mit einer Kunden-ID oder einer Cookie-ID und einem Zeitstempel sein. Bei Ereignisdaten können Sie entscheiden, welche ID als Personen-ID verwendet wird. | Wird automatisch auf das standardmäßige Zeitstempelfeld von ereignisbasierten Schemata in [UICONTROL Experience Platform] gesetzt. | Jedes integrierte oder benutzerdefinierte Schema, das auf einer XDM-Klasse mit dem Verhalten „Zeitreihen“ basiert. Beispiele sind „XDM-Erlebnisereignis“ oder „XDM-Entscheidungsereignis“. | Sie können auswählen, welche Personen-ID Sie einbeziehen möchten. Für jedes in Experience Platform definierte Datensatzschema kann ein eigener Satz von einer oder mehreren Identitäten definiert und mit einem Identitäts-Namespace verknüpft werden. Jede dieser Optionen kann als Personen-ID verwendet werden. Beispiele sind Cookie-ID, zugeordnete ID, Benutzer-ID, Trackingcode usw. |
   | [!UICONTROL Suche] | Entspricht einer Classifications-Datei. Diese Daten werden verwendet, um nach Werten oder Schlüsseln in Ihren Ereignis- oder Profildaten zu suchen. Beispielsweise können Sie Suchdaten hochladen, die numerische IDs in Ihren Ereignisdaten Produktnamen zuordnen. | nicht angegeben | Jedes integrierte oder benutzerdefinierte Schema, das auf einer XDM-Klasse mit dem Verhalten „Eintrag“ basiert, mit Ausnahme der Klasse „XDM-Individuelles Profil“. | nicht angegeben |
   | [!UICONTROL Profil] | Analogous to [!UICONTROL Customer Attributes] - for non-changing and non-temporal attributes. Data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. Sie können beispielsweise CRM-Daten zu Ihren Kunden hochladen. | nicht angegeben | Jedes integrierte oder benutzerdefinierte Schema, das auf der Klasse „XDM-Individuelles Profil“ basiert. | Sie können auswählen, welche Personen-ID Sie einbeziehen möchten. Für jeden in [!DNL Experience Platform] definierten Datensatz ist ein eigener Satz von einer oder mehreren definierten Personen-IDs definiert, z. B. Cookie-ID, zugeordnete ID, Benutzer-ID, Trackingcode usw.<br>![Personen-ID](assets/person-id.png)**Hinweis:** Wenn Sie eine Verbindung erstellen, die Datensätze mit unterschiedlichen IDs enthält, wird dies in der Berichterstellung berücksichtigt. Um Datensätze zusammenzuführen, müssen Sie dieselbe Personen-ID verwenden. |

1. **[!UICONTROL Datenbestand-ID]**: Diese ID wird automatisch generiert.

1. **[!UICONTROL Zeitstempel]**: Inhalt hier hinzufügen

1. **[!UICONTROL Schema]**:

1. **[!UICONTROL Personen-ID]**:

1. Klicken Sie auf **[!UICONTROL Weiter]** , um das Dialogfeld Verbindung [!UICONTROL aktivieren] aufzurufen.

   ![Verbindung aktivieren](assets/create-connection2.png)

## Verbindung aktivieren

1. In the [!UICONTROL Create Connection] dialog, define these settings:

   | Feld | Beschreibung |
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
