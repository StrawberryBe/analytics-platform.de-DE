---
title: Verbindung erstellen
description: Beschreibt, wie eine Verbindung zu einem Plattform-Datensatz in Customer Journey Analytics hergestellt wird.
translation-type: tm+mt
source-git-commit: 674835d9c8b79850051729c875bc67f0e4052a66
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 4%

---


# Verbindung erstellen

Mithilfe einer Verbindung können Sie Datensätze aus [!DNL Adobe Experience Platform] in [!UICONTROL Workspace]integrieren. Für die Berichterstellung zu [!DNL Experience Platform] Datensätzen müssen Sie zunächst eine Verbindung zwischen Datensätzen in [!DNL Experience Platform] und [!UICONTROL Workspace]herstellen.

Klicken Sie [hier](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/connecting-customer-journey-analytics-to-data-sources-in-platform.html) , um eine Videoübersicht zu erhalten.

>[!IMPORTANT] Sie können mehrere [!DNL Experience Platform] Datensätze zu einer einzigen Verbindung kombinieren.

1. Go to [https://analytics.adobe.com](https://analytics.adobe.com).

1. Click the **[!UICONTROL Connections]** tab.

1. Klicken Sie oben rechts auf Neue Verbindung **** erstellen.

   ![Verbindung herstellen](assets/create-connection.png)

1. Wählen Sie zunächst eine Sandbox in Experience Platform aus, die die Datensätze enthält, zu denen Sie eine Verbindung herstellen möchten. Adobe Experience Platform provides [sandboxes](https://docs.adobe.com/content/help/en/experience-platform/sandbox/home.html) which partition a single Platform instance into separate virtual environments to help develop and evolve digital experience applications. Sandboxes können als &quot;Datensilos&quot;mit Datensätzen betrachtet werden. Sandboxen dienen zur Steuerung des Zugriffs auf Datensätze. Sie können nicht über Sandboxen auf Daten zugreifen.

1. Nachdem Sie die Sandbox ausgewählt haben, zeigt die linke Leiste alle Datensätze in der Sandbox an, aus denen Sie ziehen können. Wählen Sie einen oder mehrere Datensätze aus, die Sie in [!UICONTROL Customer Journey Analytics] ziehen möchten, und klicken Sie auf **[!UICONTROL Hinzufügen]**. (Wenn Sie viele Datensätze auswählen können, können Sie über die Suchleiste oberhalb der Liste der Datensätze nach den richtigen Datensätzen suchen.)

1. Als Nächstes legt [!UICONTROL Customer Journey Analytics] für jeden Datensatz, den Sie zu dieser Verbindung hinzugefügt haben, automatisch den Datasettyp anhand der Daten fest, die eingehen. Es gibt 3 verschiedene Datensatztypen: [!UICONTROL Ereignis] -, [!UICONTROL Profil] - und [!UICONTROL Suchdaten] .

   | Typ des Datensatzes | Beschreibung | Zeitstempel | Schema | Personen-ID |
   |---|---|---|---|---|
   | [!UICONTROL Ereignis] | Daten, die zeitliche Ereignis darstellen (z. B. Webbesuche, Interaktionen, Transaktionen, POS-Daten, Daten zur Umfrage, Daten zu Anzeigenimpressionen usw.). Dies können beispielsweise typische Clickstream-Daten mit einer Kunden-ID oder einer Cookie-ID und einem Zeitstempel sein. Bei Ereignis-Daten haben Sie die Flexibilität, welche ID als Personen-ID verwendet wird. | Wird automatisch auf das Standardzeitstempelfeld von Ereignis-basierten Schemas in der [UICONTROL Experience Platform]eingestellt. | Jedes integrierte oder benutzerdefinierte Schema, das auf einer XDM-Klasse mit dem Verhalten &quot;Zeitreihen&quot;basiert. Beispiele sind &quot;XDM Experience Ereignis&quot;oder &quot;XDM Decision Ereignis&quot;. | Sie können auswählen, welche Person-ID Sie einbeziehen möchten. Jedes in der Erlebnisplattform definierte DataSet-Schema kann einen eigenen Satz einer oder mehrerer Identitäten definieren und mit einem Identitäts-Namensraum verknüpft sein. Jede dieser Optionen kann als Personen-ID verwendet werden. Beispiele sind Cookie-ID, zugewiesene ID, Benutzer-ID, Rückverfolgungscode usw. |
   | [!UICONTROL Suche] | Entspricht einer Classifications-Datei. Diese Daten werden zum Nachschlagen von Werten oder Schlüsseln in Ihren Ereignis- oder Profil-Daten verwendet. Sie können beispielsweise Suchdaten hochladen, die numerische IDs in Ihren Ereignis-Daten Produktnamen zuordnen. | nicht angegeben | Jedes integrierte oder benutzerdefinierte Schema, das auf einer XDM-Klasse mit dem Verhalten &quot;Record&quot;basiert, mit Ausnahme der Klasse &quot;XDM Individuelles Profil&quot;. | nicht angegeben |
   | [!UICONTROL Profil] | Analog zu [!UICONTROL Kundenattributen] - für nicht ändernde und nicht zeitliche Attribute. Daten, die auf Ihre Besucher, Benutzer oder Kunden in den [!UICONTROL Ereignis] -Daten angewendet werden. Sie können beispielsweise CRM-Daten zu Ihren Kunden hochladen. | nicht angegeben | Jedes integrierte oder benutzerdefinierte Schema, das auf der Klasse &quot;XDM Individuelles Profil&quot;basiert. | Sie können auswählen, welche Person-ID Sie einbeziehen möchten. Jeder Datensatz, der in der definiert ist, [!DNL Experience Platform] verfügt über einen eigenen Satz von einer oder mehreren Personen-IDs, wie z. B. Cookie-ID, Stitched ID, Benutzer-ID, Rückverfolgungscode usw.<br>![Person](assets/person-id.png)**IDNote **: Wenn Sie eine Verbindung erstellen, die Datensätze mit unterschiedlichen IDs enthält, wird dies vom Berichte übernommen. Um Datasets wirklich zusammenzuführen, müssen Sie dieselbe Person-ID verwenden. |

1. Durch Klicken auf **[!UICONTROL Weiter]** gelangen Sie zum Dialogfeld Verbindung [!UICONTROL erstellen] .

   ![Verbindung herstellen](assets/create-connection2.png)

1. Legen Sie im Dialogfeld Verbindung [!UICONTROL erstellen] die folgenden Einstellungen fest:

   | Feld | Beschreibung |
   |---|---|
   | [!UICONTROL Namensverbindung] | Geben Sie der Verbindung einen beschreibenden Namen. Die Verbindung kann nicht ohne Namen gespeichert werden. |
   | [!UICONTROL Beschreibung] | Hinzufügen detailliertere Informationen, um diese Verbindung von anderen zu unterscheiden. |
   | [!UICONTROL Datensätze] | Die in dieser Verbindung enthaltenen Datensätze. |
   | [!UICONTROL Importieren Sie alle neuen Datensätze in dieser Verbindung automatisch, beginnend heute.] | Wählen Sie diese Option, wenn Sie eine fortlaufende Verbindung herstellen möchten, damit neue Datenstapel, die den Datensätzen in dieser Verbindung hinzugefügt werden, automatisch in [!UICONTROL Workspace]fließen. |
   | [!UICONTROL Alle vorhandenen Daten importieren] | Wenn Sie diese Option auswählen und die Verbindung speichern, werden alle vorhandenen (historischen) Daten aus [!DNL Experience Platform] allen Datensätzen, die in dieser Verbindung vorhanden sind, importiert. Künftig werden auch alle vorhandenen historischen Daten für neue Datensätze, die zu dieser gespeicherten Verbindung hinzugefügt werden, automatisch importiert. <br>**Beachten Sie, dass diese Einstellung nach dem Speichern dieser Verbindung nicht mehr geändert werden kann.** |

   **Bedenken Sie Folgendes:**

   * Wenn die kumulative Größe der historischen Daten für alle Datensätze in der Verbindung 1,5 Milliarden Zeilen überschreitet, zeigt eine Fehlermeldung an, dass Sie diese Menge an historischen Daten nicht importieren können. Wenn Sie jedoch einen Datensatz mit 1 Milliarde Zeilen historischer Daten hinzufügen und diese Daten importieren würden, und eine Woche später einen weiteren Datensatz derselben Größe hinzufügen und seine historischen Daten importieren würden, würde dies funktionieren.
   * Neue Daten, die einem Datensatz in der Verbindung hinzugefügt werden, werden priorisiert, sodass diese Daten die niedrigste Latenz aufweisen.
   * Sämtliche Aufstockungsdaten (historische Daten) werden langsamer importiert.

1. Klicken Sie auf **[!UICONTROL Speichern]**.

Der nächste Schritt im Workflow besteht darin, eine Ansicht [zu](/help/data-views/create-dataview.md)erstellen.
