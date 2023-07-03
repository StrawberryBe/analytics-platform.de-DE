---
title: Stitching-Übersicht
description: Übersicht über das Stitching.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '1220'
ht-degree: 32%

---

# Stitching-Übersicht

Die Identitätszuordnung (oder einfach das Stitching) ist eine leistungsstarke Funktion, die die Eignung eines Ereignis-Datensatzes für die kanalübergreifende Analyse erhöht. Die kanalübergreifende Analyse ist ein Hauptanwendungsfall, den Customer Journey Analytics handhaben kann. So können Sie Berichte basierend auf einer gemeinsamen Kennung (Personen-ID) nahtlos kombinieren und für mehrere Datensätze aus verschiedenen Kanälen ausführen.

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Attribution geräte- und kanalübergreifend übernommen. Beispiel: Ein Benutzer besucht Ihre Site zum ersten Mal über eine Werbeanzeige auf seinem Desktop. Dieser Benutzer stößt bei seiner Bestellung auf ein Problem und ruft dann Ihren Kundendienst an, um das Problem zu beheben. Mit der kanalübergreifenden Analyse können Sie Callcenter-Ereignisse der Anzeige zuordnen, auf die sie ursprünglich geklickt haben.

Leider sind nicht alle ereignisbasierten Datensätze, die Teil Ihrer Verbindung in Customer Journey Analytics sind, ausreichend mit Daten gefüllt, um diese Attribution standardmäßig zu unterstützen. Insbesondere verfügen Web- oder mobile-basierte Erlebnisdatensätze häufig nicht über tatsächliche Personen-ID-Informationen für alle Ereignisse.

Die Zuordnung ermöglicht die Neuzuordnung von Identitäten in den Zeilen eines Datensatzes, um sicherzustellen, dass die gewünschte Personen-ID (zugeordnete ID) für jedes Ereignis verfügbar ist. Beim Zuordnen werden Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen untersucht, um eine zugeordnete ID zu generieren. Die Zuordnung ermöglicht die Auflösung verschiedener Datensätze zu einer einzelnen zugeordneten ID für die Analyse auf Personenebene und nicht auf Geräte- oder Cookie-Ebene.

Sie profitieren von einer kanalübergreifenden Analyse, wenn Sie einen oder mehrere Ihrer zugeordneten Datensätze mit anderen Datensätzen, z. B. Callcenter-Daten, kombinieren, um Ihre Customer Journey Analytics-Verbindung zu definieren. Dabei wird davon ausgegangen, dass diese anderen Datensätze bereits in jeder Zeile eine Personen-ID enthalten, die der zugeordneten ID ähnelt.


## Voraussetzungen 

>[!IMPORTANT]
>
>Wenn nicht alle Voraussetzungen erfüllt sind, kann die Durchführung einer kanalübergreifenden Analyse fehlschlagen.

Stellen Sie vor der Verwendung von Stitching sicher, dass Ihr Unternehmen wie folgt vorbereitet ist:

* Importieren Sie die gewünschten Daten in Adobe Experience Platform:

   * Informationen zu Adobe Analytics-Daten finden Sie unter [Verwenden von Adobe Analytics Report Suite-Daten in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * Informationen zu anderen Datentypen finden Sie unter [Erstellen eines Schemas](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) und [Aufnehmen von Daten](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=de) in der Adobe Experience Platform-Dokumentation.

* Der Datensatz in Adobe Experience Platform, auf den Sie die Zuordnung anwenden möchten, muss über zwei Spalten verfügen, die die Identifizierung von Besuchern erleichtern:

   * Eine **beständige ID**, eine Kennung, die in jeder Zeile vorhanden ist. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics-AppMeasurement-Bibliothek generiert wurde, oder eine ECID, die vom Adobe Experience Cloud Identity-Dienst generiert wurde.
   * Eine **vorübergehende ID**, eine Kennung, die nur in einigen Zeilen vorhanden ist. Beispiel: ein/e gehashte/r Benutzername oder E-Mail-Adresse, wenn sich ein Besucher authentifiziert. Sie können praktisch jede beliebige Kennung verwenden, sofern diese mindestens einmal für dasselbe Ereignis wie eine bestimmte beständige ID vorhanden ist.

* Die Zuordnung umfasst das Zusammenführen authentifizierter und nicht authentifizierter Benutzerdaten. Stellen Sie vor dem Zusammenführen von Datensätzen sicher, dass Sie die geltenden Gesetze und Vorschriften einhalten, einschließlich der Erlangung der erforderlichen Endbenutzerberechtigungen.


## Stitching verwenden

Sobald Ihr Unternehmen alle Voraussetzungen erfüllt und die [Einschränkungen](#limitations)können Sie die folgenden Schritte ausführen, um mit der Verwendung von &quot;Stitching&quot;in Customer Journey Analytics zu beginnen:

### Support anfordern

1. Wenden Sie sich mit den folgenden Informationen an den Adobe-Support:

   * Eine Anfrage zum Aktivieren der Zuordnung.
   * Die Datensatz-ID für den Datensatz, den Sie neu zuweisen möchten.
   * Der Spaltenname der beständigen ID für den gewünschten Datensatz (Kennung, die in jeder Zeile erscheint).
   * Der Spaltenname der vorübergehenden ID für den gewünschten Datensatz (die Verbindung der Personenkennung zwischen Datensätzen).
   * Ihre Voreinstellung für die Häufigkeit der [Wiederholungen](explained.md) und die Lookback-Länge. Zu den verfügbaren Optionen gehören eine Wiederholung pro Woche mit einem 7-tägigen Lookback-Fenster oder eine tägliche Wiederholung mit einem 1-tägigen Lookback-Fenster.
   * Sandbox-Name.


2. Der Adobe-Kundensupport arbeitet mit Adobe Engineering zusammen, um das Stitching nach Erhalt Ihrer Anfrage zu aktivieren. Nach der Aktivierung wird in Adobe Experience Platform ein neu verschlüsselter Datensatz angezeigt, der eine neue Spalte für die Personen-ID enthält. Der Adobe-Support stellt die neue Datensatz-ID und den Namen der Personen-ID-Spalte bereit.

3. Bei der erstmaligen Aktivierung stellt Adobe eine Aufstockung der zusammengefügten Daten bereit, die bis zum Beginn des Vormonats zurückreicht (bis zu 60 Tage). Um diese Aufstockung durchzuführen, muss die vorübergehende ID in den nicht zugewiesenen Daten bis zu diesem Zeitpunkt vorhanden sein.

4. [Verbindung erstellen](/help/connections/create-connection.md) in Customer Journey Analytics mit dem neu erstellten Datensatz und allen anderen Datensätzen, die Sie einbeziehen möchten. Wählen Sie für jeden Datensatz die korrekte Personen-ID.

5. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) auf Grundlage der Verbindung.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Sobald die Datenansicht eingerichtet ist, erfolgt die kanalübergreifende Analyse in Customer Journey Analytics genau wie jede andere Analyse in Customer Journey Analytics, bis auf die Tatsache, dass die Daten jetzt kanalübergreifend und geräteübergreifend verwendet werden.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


## Einschränkungen

>[!IMPORTANT]
>
>Wenden Sie alle Änderungen, die Sie an dem Schema des globalen Ereignis-Datensatzes vornehmen, auch auf das neue zugeordnete Datensatzschema an, da es andernfalls den zugewiesenen Datensatz beschädigt.
>
>Wenn Sie den Quelldatensatz entfernen, wird der zugeordnete Datensatz nicht weiter verarbeitet und vom System entfernt.

Das Stitching ist eine innovative und zuverlässige Funktion, die jedoch Einschränkungen hinsichtlich der Verwendung aufweist.

* Die aktuellen Funktionen zur Neuzuweisung sind auf einen Schritt beschränkt (beständige ID auf vorübergehende ID). Eine mehrstufige Neuzuweisung wird nicht unterstützt, beispielsweise beständige ID zu vorübergehender ID und dann zu einer weiteren vorübergehenden ID.
* Es werden nur Ereignis-Datensätze unterstützt. Andere Datensätze, wie beispielsweise Lookup-Datensätze, werden nicht unterstützt.
* Benutzerdefinierte ID-Maps, die in Ihrem Unternehmen verwendet werden, werden nicht unterstützt.
* Beim Stitching wird das für das Stitching verwendete Feld in keiner Weise umgewandelt. Beim Zuordnen wird der Wert im angegebenen Feld verwendet, da er im nicht zugeordneten Datensatz im Data Lake vorhanden ist. Beim Zuordnen wird zwischen Groß- und Kleinschreibung unterschieden. Wenn beispielsweise manchmal das Wort &quot;Bob&quot;im Feld erscheint und manchmal das Wort &quot;BOB&quot;erscheint, werden diese IDs als zwei separate Personen behandelt.
* Beim Stitching wird zwischen Groß- und Kleinschreibung unterschieden. Für Datensätze, die über den Analytics Source Connector generiert werden, empfiehlt Adobe die Überprüfung aller VISTA-Regeln oder Verarbeitungsregeln, die für das vorübergehende ID-Feld gelten. Diese Überprüfung stellt sicher, dass keine dieser Regeln neue Formen derselben ID einführt. So sollten Sie beispielsweise sicherstellen, dass keine VISTA- oder Verarbeitungsregeln dafür sorgen, dass im Feld für die vorübergehende ID nur für einen Teil der Ereignisse Kleinschreibung verwendet wird.
* Beim Stitching werden keine Felder kombiniert oder verkettet.
* Das Feld für die vorübergehende ID sollte einen einzelnen ID-Typ enthalten ( IDs aus einem einzelnen Namespace). Das Feld für die vorübergehende ID sollte beispielsweise keine Kombination aus Anmelde-IDs und E-Mail-IDs enthalten.
* Wenn mehrere Ereignisse mit demselben Zeitstempel für dieselbe beständige ID auftreten, aber unterschiedliche Werte im Feld der vorübergehenden ID vorhanden sind, wird bei der Zuordnung die ID basierend auf der alphabetischen Reihenfolge ausgewählt. Wenn also eine beständige ID A zwei Ereignisse mit demselben Zeitstempel aufweist und eines der Ereignisse &quot;Bob&quot;und das andere &quot;Ann&quot;angibt, wählt &quot;Zuordnen&quot;Ann.
* Wenn ein Gerät von mehreren Personen gemeinsam genutzt wird und die Gesamtzahl der Übergänge zwischen Benutzern 50.000 überschreitet, stoppt der Customer Journey Analytics die Zuordnung von Daten für dieses Gerät.

Verwechseln Sie nicht das Stitching mit:

* Die Zusammenführung von zwei oder mehr Datensätzen. Die Zuordnung gilt nur für einen Datensatz. Die Zusammenführung von Datensätzen erfolgt durch Einrichten einer Customer Journey Analytics-Verbindung und Auswählen derselben Personen-ID für die ausgewählten Datensätze in der Verbindung.

* Der Join von zwei Datensätzen. In Customer Journey Analytics wird häufig ein Join für Suchen oder Klassifizierungen in Analysis Workspace verwendet. Obwohl das Stitching die Join-Funktion verwendet, umfasst der Prozess selbst viel mehr als nur Joins.

