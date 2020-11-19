---
title: Marketing Kanal-Dimensionen in Adobe Experience Platform verwenden
description: Verwenden Sie den Analytics Data Connector, um Verarbeitungsregeln für Marketing Kanal in Adobe Experience Platform zu importieren.
translation-type: tm+mt
source-git-commit: b5ed4c65877fa8e2de83810a3c4bd1a4048f5b31
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 3%

---


# Marketing Kanal-Dimensionen in Adobe Experience Platform verwenden

Wenn Ihr Unternehmen den [Analytics Data Connector](https://docs.adobe.com/content/help/de-DE/experience-platform/sources/connectors/adobe-applications/analytics.html) verwendet, um Report Suite-Daten in CJA zu importieren, können Sie eine Verbindung in CJA konfigurieren, um Berichte über die Dimensionen des Marketing-Kanals zu erstellen.

## Voraussetzungen

* Report Suite-Daten müssen bereits mit dem [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) in Adobe Experience Platform importiert werden. Andere Datenquellen werden nicht unterstützt, da Marketing-Kanal auf Verarbeitungsregeln in einer Analytics-Report Suite angewiesen sind.
* Verarbeitungsregeln für Marketing Kanal müssen bereits eingerichtet sein. Siehe [Verarbeitungsregeln für Marketing-Kanal](https://docs.adobe.com/content/help/de-DE/analytics/components/marketing-channels/c-rules.html) im Handbuch zu Analytics-Komponenten.

## Marketing Kanal Schema-Elemente

Nachdem Sie Analytics Data Connector für eine gewünschte Report Suite eingerichtet haben, wird ein XDM-Schema für Sie erstellt. Dieses Schema enthält alle Analytics-Dimensionen und -Metriken als Rohdaten. Diese Rohdaten enthalten keine Zuordnung oder Persistenz. Stattdessen durchläuft jedes Ereignis die Verarbeitungsregeln von Marketing Kanal und zeichnet die erste Regel auf, die es erfüllt. Beim Erstellen einer Ansicht in CJA geben Sie Zuordnung und Persistenz an.

1. [Erstellen Sie eine ](/help/connections/create-connection.md) Verbindung, die einen Datensatz enthält, der auf dem Analytics Data Connector basiert.
2. [Erstellen Sie eine ](/help/data-views/create-dataview.md) Datenansicht mit den folgenden Dimensionen:
   * **`channel.typeAtSource`**: Entspricht der  [Marketingkanal-](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) Dimension.
   * **`channel._id`**: Entspricht den Details zum  [Marketing-Kanal](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. Weisen Sie jeder Dimension das gewünschte Zuordnungsmodell und die gewünschte Persistenz zu. Wenn Sie sowohl die First Touch- als auch die Last Touch-Dimension verwenden möchten, ziehen Sie jede Marketing Kanal-Dimension mehrmals in den Komponentenbereich. Weisen Sie jeder Dimension das gewünschte Zuordnungsmodell und die gewünschte Persistenz zu. Adobe empfiehlt außerdem, jeder Dimension einen Anzeigenamen zuzuweisen, um die Verwendung in Workspace zu vereinfachen.
4. Erstellen Sie die Daten-Ansicht.

Die Dimensionen Ihrer Marketing-Kanal stehen jetzt in Analysis Workspace zur Verfügung.

## Unterschiede in der Verarbeitung und Architektur

>[!IMPORTANT]
>
>Es gibt mehrere grundlegende Datenunterschiede zwischen Report Suite-Daten und Plattformdaten. Adobe empfiehlt dringend, die Verarbeitungsregeln für Marketing Kanal Ihrer Report Suite anzupassen, um eine ordnungsgemäße Datenerfassung in der Plattform zu erleichtern.

Die Marketing Kanal-Einstellungen funktionieren unterschiedlich zwischen Plattformdaten und Report Suite-Daten. Beachten Sie beim Einrichten von Marketing-Kanälen für CJA die folgenden Unterschiede:

* **Ist erste Seite des Besuchs**: Diese Regelkriterien sind in verschiedenen Standarddefinitionen des Marketing-Kanals üblich. Jede Verarbeitungsregel, die diese Kriterien enthält, wird in der Plattform ignoriert (andere Kriterien in derselben Regel gelten weiterhin). Sitzungen werden zur Abfrage der Daten und nicht zum Zeitpunkt der Datenerfassung festgelegt, wodurch verhindert wird, dass Plattform diese spezifischen Regelkriterien verwendet. Adobe empfiehlt, die Kriterien &quot;Ist erste Seite des Besuchs&quot;aus jeder Verarbeitungsregel für Marketing-Kanal zu entfernen.

   ![Erste Seite des Besuchs](assets/first-page-of-visit.png)

* **Last Touch-Kanal** überschreiben: Diese Einstellung im Marketing Kanal Manager verhindert normalerweise, dass bestimmte Kanal eine Last Touch-Kanal-Gutschrift erhalten. Die Plattform ignoriert diese Einstellung, sodass breite Kanal wie &quot;Direkt&quot;oder &quot;Intern&quot;Metriken potenziell unerwünscht zuordnen können. Adobe empfiehlt, Kanal zu entfernen, bei denen &quot;Last Touch-Kanal überschreiben&quot;deaktiviert ist.
   * Sie können den &quot;Direct&quot;-Marketing-Kanal im Marketing Kanal-Manager löschen und sich dann auf das Dimensionselement &quot;Kein Wert&quot;von CJA für diesen Kanal verlassen. Sie können dieses Dimensionselement auch in &quot;Direkt&quot;umbenennen oder das Dimensionselement beim Konfigurieren einer Ansicht vollständig ausschließen.
   * Alternativ können Sie eine Marketing-Kanal-Classification erstellen und jeden Wert für sich selbst klassifizieren, mit Ausnahme der Kanal, die Sie in CJA ausschließen möchten. Sie können diese Classification-Dimension dann beim Erstellen einer Data Ansicht anstelle von `channel.typeAtSource` verwenden.

   ![Last Touch-Kanal überschreiben](assets/override-last-touch-channel.png)

* **Ablauf** des Marketing-Kanals: Diese Einstellung für den Interaktionszeitraum bestimmt den Inaktivitätszeitraum, bevor ein Besucher einen neuen First Touch-Kanal in den Report Suite-Daten abrufen kann. Die Plattform verwendet ihre eigenen Zuordnungseinstellungen, sodass diese Einstellung in CJA vollständig ignoriert wird.

   ![Marketing-Kanalablauf](assets/marketing-channel-expiration.png)

## Vergleichen von Daten zwischen CJA und herkömmlicher Analytics

Da sich die Architektur von Adobe Experience Platform von der klassischen Analytics-Report Suite unterscheidet, wird eine Übereinstimmung der Ergebnisse nicht garantiert. Sie können jedoch die folgenden Tipps verwenden, um diesen Vergleich zu erleichtern:

* Vergewissern Sie sich, dass die oben aufgeführten Unterschiede in der Architektur Ihren Vergleich nicht beeinträchtigen. Dazu gehören das Entfernen von Kanälen, die Last Touch-Kanal nicht überschreiben, und das Entfernen von Regelkriterien, die der erste Treffer eines Besuchs (Sitzung) sind.
* Überprüfen Sie anhand der Dublette, ob für Ihre Verbindung dieselbe Report Suite wie für herkömmliche Analytics verwendet wird. Wenn Ihre CJA-Verbindung mehrere Report Suites mit eigenen Verarbeitungsregeln für Marketing Kanal enthält, ist es nicht einfach, diese mit herkömmlichen Analytics zu vergleichen. Sie möchten für jede Report Suite eine separate Verbindung zum Datenvergleich erstellen.
* Vergewissern Sie sich, dass Sie dieselben Datumsbereiche vergleichen und dass die Zeitzoneneinstellung in Ihrer Ansicht mit der Zeitzone der Report Suite übereinstimmt.
* Verwenden Sie beim Anzeigen von Report Suite-Daten ein benutzerdefiniertes Zuordnungsmodell. Verwenden Sie beispielsweise die Dimension [Marketing-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html) mit Metriken, die ein nicht standardmäßiges Zuordnungsmodell verwenden. Adobe rät davon ab, die Standarddimensionen [First Touch-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html) oder [Last Touch-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html) zu vergleichen, da sie auf der Zuordnung beruhen, die in der Report Suite erfasst wurde. CJA stützt sich nicht auf die Zuordnungsdaten einer Report Suite; stattdessen wird er berechnet, wenn ein CJA-Bericht ausgeführt wird.
* Einige Metriken weisen aufgrund architektonischer Unterschiede zwischen Report Suite-Daten und Plattformdaten keinen angemessenen Vergleich auf. Beispiele sind Besuche/Sitzungen, Besucher/Personen und Instanzen/Ereignis.
