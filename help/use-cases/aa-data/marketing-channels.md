---
title: Verwenden von Marketing-Kanal-Dimensionen in Adobe Experience Platform
description: Verwenden Sie Analytics Source Connector, um Verarbeitungsregeln für den Marketing-Kanal in Adobe Experience Platform zu importieren.
exl-id: d1739b7d-3410-4c61-bb08-03dd4161c529
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: af9113f3afced902b385747bceaa9e51b72d83e6
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 98%

---

# Verwenden von Marketing-Kanal-Dimensionen in Adobe Experience Platform

Wenn Ihr Unternehmen [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) verwendet, um Report Suite-Daten in Customer Journey Analytics zu importieren, können Sie in Customer Journey Analytics eine Verbindung konfigurieren, um Berichte über die Dimensionen des Marketing-Kanals zu erstellen.

## Voraussetzungen

* Report Suite-Daten müssen bereits mit [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de) in Adobe Experience Platform importiert worden sein. Andere Datenquellen werden nicht unterstützt, da Marketing-Kanäle auf Verarbeitungsregeln in einer Analytics Report Suite angewiesen sind.
* Verarbeitungsregeln für den Marketing-Kanal müssen bereits eingerichtet sein. Siehe [Verarbeitungsregeln für Marketing-Kanäle](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-rules.html?lang=en) im Handbuch zu Analytics-Komponenten.

## Marketing-Kanal: Schema-Elemente

Nachdem Sie Analytics Source Connector für eine gewünschte Report Suite eingerichtet haben, wird ein XDM-Schema für Sie erstellt. Dieses Schema enthält alle Analytics-Dimensionen und -Metriken als Rohdaten. Diese Rohdaten enthalten keine Attribution oder Persistenz. Stattdessen durchläuft jedes Ereignis die Verarbeitungsregeln des Marketing-Kanals und zeichnet die erste Regel auf, die es erfüllt. Beim Erstellen einer Datenansicht in Customer Journey Analytics legen Sie Attribution und Persistenz fest.

1. [Erstellen Sie eine Verbindung](/help/connections/create-connection.md), die einen Datensatz enthält, der auf Analytics Source Connector basiert.
2. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) mit folgenden Dimensionen:
   * **`channel.typeAtSource`**: entspricht der [Marketing-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=de)-Dimension.
   * **`channel._id`**: entspricht dem [Marketing-Kanal-Detail](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-detail.html?lang=de).
3. Weisen Sie jeder Dimension das gewünschte Attributionsmodell und die gewünschte Persistenz zu. Wenn Sie sowohl die First Touch- als auch die Last Touch-Dimension verwenden möchten, ziehen Sie jede Marketing-Kanal-Dimension mehrmals in den Komponentenbereich. Weisen Sie jeder Dimension das gewünschte Attributionsmodell und die gewünschte Persistenz zu. Adobe empfiehlt außerdem, jeder Dimension einen Anzeigenamen zu geben, um die Verwendung in Arbeitsbereich zu vereinfachen.
4. Erstellen Sie die Datenansicht.

Die Dimensionen Ihres Marketing-Kanals stehen jetzt in Analysis Workspace zur Verfügung.

>[!NOTE]
>
> Analytics Source Connector erfordert, dass sowohl `channel.typeAtSource` (Marketing-Kanal) als auch `channel._id` (Details zum Marketing-Kanal) ausgefüllt werden, sonst wird keiner der Werte in das XDM ExperienceEvent übertragen. Wenn die Details zum Marketing-Kanal in der Quell-Report Suite leer sind, führt dies zu einer leeren `channel._id` und Analytics Source Connector wird auch `channel.typeAtSource` leer lassen. Dies kann zu Berichtsunterschieden zwischen Adobe Analytics und Customer Journey Analytics führen.

## Unterschiede in der Verarbeitung und der Architektur

>[!IMPORTANT]
>
>Es gibt mehrere grundlegende Datenunterschiede zwischen Report Suite-Daten und Platform-Daten. Adobe empfiehlt dringend, die Verarbeitungsregeln für den Marketing-Kanal Ihrer Report Suite anzupassen, um eine korrekte Datenerfassung in Platform zu erleichtern.

>[!NOTE]
>
>Um die Effektivität von Marketing-Kanälen für Attribution IQ und Customer Journey Analytics zu maximieren, haben wir einige [überarbeitete Best Practices](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/mchannel-best-practices.html?lang=de) veröffentlicht.

Die Marketing-Kanal-Einstellungen funktionieren bei Platform-Daten und Report Suite-Daten unterschiedlich. Beachten Sie beim Einrichten von Marketing-Kanälen für Customer Journey Analytics die folgenden Unterschiede:

* **Ist erste Seite des Besuchs**: Dieses Regelkriterium ist in verschiedenen Standarddefinitionen des Marketing-Kanals üblich. Jede Verarbeitungsregel, die dieses Kriterium enthält, wird in Platform ignoriert (andere Kriterien in derselben Regel sind weiterhin gültig). Sitzungen werden zum Zeitpunkt der Datenabfrage und nicht zum Zeitpunkt der Datenerfassung festgelegt. Dadurch wird verhindert, dass Platform dieses spezifische Regelkriterium verwendet. Adobe empfiehlt, alle Marketing-Kanal-Verarbeitungsregeln, die die Kriterien „Ist erste Seite des Besuchs“ enthalten, neu zu bewerten und alternative Ansätze zu wählen, die die gewünschten Ergebnisse liefern.

   ![Erste Seite des Besuchs](../assets/first-page-of-visit.png)

* **Last Touch-Kanal überschreiben**: Diese Einstellung im Marketing-Kanal-Manager verhindert normalerweise, dass bestimmte Kanäle eine Last Touch-Kanal-Gutschrift erhalten. Platform ignoriert diese Einstellung, sodass breite Kanäle wie „Direkt“ oder „Intern“ Metriken möglicherweise auf unerwünschte Art zuordnen können. Adobe empfiehlt, Kanäle zu entfernen, bei denen „Last Touch-Kanal überschreiben“ deaktiviert ist.
   * Sie können den Marketing-Kanal „Direkt“ im Marketing-Kanal-Manager löschen und sich dann auf das Dimensionselement „Kein Wert“ von Customer Journey Analytics für diesen Kanal verlassen. Sie können dieses Dimensionselement auch in „Direkt“ umbenennen oder das Dimensionselement beim Konfigurieren einer Datenansicht vollständig ausschließen.
   * Alternativ können Sie eine Marketing-Kanal-Klassifizierung erstellen und jeden Wert für sich selbst klassifizieren, mit Ausnahme der Kanäle, die Sie in Customer Journey Analytics ausschließen möchten. Sie können diese Klassifizierungsdimension dann beim Erstellen einer Datenansicht anstelle von `channel.typeAtSource` verwenden.

   ![Last Touch-Kanal überschreiben](../assets/override-last-touch-channel.png)

* **Ablauf des Marketing-Kanals**: Mit dieser Einstellung für den Interaktionszeitraum wird der Zeitraum der Inaktivität festgelegt, bevor ein Besucher einen neuen First Touch-Kanal in den Report Suite-Daten abrufen kann. Platform verwendet eigene Attributionseinstellungen, sodass diese Einstellung in Customer Journey Analytics vollständig ignoriert wird.

   ![Marketing-Kanalablauf](../assets/marketing-channel-expiration.png)

## Vergleiche von Daten aus Customer Journey Analytics und herkömmlichem Analytics

Da sich die Architektur von Adobe Experience Platform von einer herkömmlichen Analytics Report Suite unterscheidet, wird eine Übereinstimmung der Ergebnisse nicht garantiert. Sie können jedoch die folgenden Tipps nutzen, um diesen Vergleich zu erleichtern:

* Vergewissern Sie sich, dass die oben aufgeführten Unterschiede in der Architektur Ihren Vergleich nicht beeinträchtigen. Dazu gehört das Entfernen von Kanälen, die den Last Touch-Kanal nicht überschreiben, und das Entfernen von Regelkriterien, die dem ersten Treffer eines Besuchs (Sitzung) entsprechen.
* Überprüfen Sie, ob für Ihre Verbindung dieselbe Report Suite wie für herkömmliches Analytics verwendet wird. Wenn Ihre Customer Journey Analytics-Verbindung mehrere Report Suites mit eigenen Verarbeitungsregeln für Marketing-Kanäle enthält, ist es nicht einfach, diese mit herkömmlichem Analytics zu vergleichen. Sie müssten dann für jede Report Suite eine separate Verbindung für den Datenvergleich erstellen.
* Vergewissern Sie sich, dass Sie die gleichen Datumsbereiche vergleichen und dass die Zeitzoneneinstellung in Ihrer Datenansicht mit der Zeitzone der Report Suite übereinstimmt.
* Verwenden Sie beim Anzeigen von Report Suite-Daten ein benutzerspezifisches Attributionsmodell. Verwenden Sie beispielsweise die Dimension [Marketing-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html?lang=de) für Metriken mit nicht standardmäßigem Attributionsmodell. Adobe rät davon ab, die Standarddimensionen [First Touch-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html?lang=de) oder [Last Touch-Kanal](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html?lang=de) zu vergleichen, da sie auf Attributionen beruhen, die in der Report Suite erfasst wurden. Customer Journey Analytics stützt sich nicht auf die Attributionsdaten einer Report Suite. Stattdessen werden diese berechnet, wenn ein Customer Journey Analytics-Bericht ausgeführt wird.
* Einige Metriken bieten aufgrund von Architektur-Unterschieden zwischen Report Suite-Daten und Platform-Daten keinen angemessenen Vergleich. Dies könnte beispielsweise Besuche/Sitzungen, Besucher/Personen und Instanzen/Ereignisse betreffen.
