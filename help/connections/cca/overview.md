---
title: Überblick über Cross-Channel Analytics
description: Schlüssel für Besucher-IDs aus mehreren Datensätzen zum Zuordnen von Besuchern erneut verwenden.
exl-id: 69763313-de27-4487-8e32-8277f1f693d8
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: fff0ffb3a513c3fc514d6769f8c3bc70fa75459e
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 93%

---

# Überblick über Cross-Channel Analytics

**Journey IQ: Cross-Channel Analytics** ist eine Funktion, mit der Sie die Personen-ID eines Datensatzes neu eingeben können. Dies ermöglicht eine nahtlose Kombination mehrerer Datensätze. Die kanalübergreifende Analyse untersucht Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen, um eine zugeordnete ID zu generieren. Mithilfe Cross-Channel Analytics können Sie Fragen beantworten wie beispielsweise:

* Wie viele Personen beginnen ihr Erlebnis auf einem Kanal und beenden es auf einem anderen?
* Wie viele Menschen interagieren mit meiner Marke? Wie viele und welche Gerätetypen verwenden sie? Wie überschneiden sich diese?
* Wie oft beginnen Personen mit einer Aufgabe auf einem Mobilgerät und wechseln dann zu einem Desktop-PC, um die Aufgabe abzuschließen? Führen Kampagnen-Clickthroughs auf einem Gerät zur Konversion auf einem anderen Gerät?
* Wie ändern sich meine Daten zur Wirksamkeit einer Kampagne, wenn ich geräteübergreifende Journeys berücksichtige? Wie ändert sich meine Trichteranalyse?
* Welche sind die häufigsten Pfade, die Benutzer beim Wechsel von einem Gerät zum anderen verwenden? Wo steigen sie aus? Wo schließen sie ihre Aktion erfolgreich ab?
* Wie unterscheidet sich das Verhalten von Benutzern mit mehreren Geräten von Benutzern mit nur einem Gerät?

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Attribution geräte- und kanalübergreifend übernommen. Beispiel: Ein Benutzer besucht Ihre Site zum ersten Mal über eine Werbeanzeige auf seinem Desktop. Dieser Benutzer stößt bei seiner Bestellung auf ein Problem und ruft dann Ihren Kundendienst an, um das Problem zu beheben. Mit Cross-Channel Analytics können Sie Callcenter-Ereignisse der Anzeige zuordnen, auf die ursprünglich geklickt wurde.

## Voraussetzungen

>[!IMPORTANT]
>
>Werden nicht alle Voraussetzungen erfüllt, kann beim Kombinieren von Datensätzen unter Umständen keine Verbindung für die kanalübergreifende Analyse hergestellt werden oder die Ergebnisse fallen mangelhaft aus.

Bevor Sie Cross-Channel Analytics verwenden, sollten Sie sicherstellen, dass Ihr Unternehmen folgende Voraussetzungen erfüllt:

* Ein Datensatz in Adobe Experience Platform muss über zwei Spalten verfügen, mit denen Besucher identifiziert werden können:
   * Eine **beständige ID**, eine Kennung, die in jeder Zeile vorhanden ist. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics AppMeasurement-Bibliothek generiert wurde.
   * Eine **vorübergehende ID**, eine Kennung, die nur in einigen Zeilen vorhanden ist. Beispiel: ein/e gehashte/r Benutzername oder E-Mail-Adresse, wenn sich ein Besucher authentifiziert. Sie können praktisch jede beliebige Kennung verwenden, sofern sie mindestens einmal für dasselbe Ereignis als beständige ID vorkommt.
* Ein anderer Datensatz, beispielsweise Callcenter-Daten, der in jeder Zeile eine vorübergehende ID enthält. Diese Personen-ID muss ähnlich wie die vorübergehende ID in dem anderen Datensatz formatiert sein.
* Mit dieser Funktion können Sie Datensätze zuordnen und somit beispielsweise authentifizierte und nicht authentifizierte Benutzerdaten zusammenführen. Vergewissern Sie sich vor dem Zusammenführen von Datensätzen, dass Sie die geltenden Gesetze und Vorschriften einhalten, wie etwa das Einholen der erforderlichen Berechtigungen der Endanwender.

## Einschränkungen

>[!IMPORTANT]
>
>Jede Änderung am globalen Ereignis-Datensatzschema muss auch im neuen zugewiesenen Datensatzschema angewendet werden. Andernfalls wird der zugeordnete Datensatz beschädigt.
>
>Wenn Sie den Quelldatensatz entfernen, wird der zugeordnete Datensatz nicht weiter verarbeitet und vom System entfernt.

Cross-Channel Analytics ist eine innovative und zuverlässige Funktion, deren Verwendung jedoch gewissen Einschränkungen unterliegt.

* Die aktuellen Funktionen zur Neuzuweisung sind auf einen Schritt beschränkt (beständige ID auf vorübergehende ID). Eine mehrstufige Neuzuweisung wird nicht unterstützt, beispielsweise beständige ID zu vorübergehender ID und dann zu einer weiteren vorübergehenden ID.
* Es werden nur Ereignis-Datensätze unterstützt. Andere Datensätze, wie beispielsweise Lookup-Datensätze, werden nicht unterstützt.
* Benutzerdefinierte ID-Maps, die in Ihrem Unternehmen verwendet werden, werden nicht unterstützt.
* Das geräteübergreifende private Diagramm wird nicht unterstützt.
* Cross-Channel Analytics transformiert nicht das zum Verbinden verwendete Feld. Die feldbasierte Zuordnung verwendet den Wert im angegebenen Feld so, wie er im nicht zugewiesenen Datensatz innerhalb des Datensees vorhanden ist. Bei der Zuordnung wird zwischen Groß- und Kleinschreibung unterschieden. Wenn beispielsweise das Wort „Bob“ im Feld erscheint und manchmal das Wort „BOB“ angezeigt wird, werden diese als zwei separate Personen behandelt.
* Bei der feldbasierten Zuordnung wird zwischen Groß- und Kleinschreibung unterschieden. Bei Analytics-Datensätzen, die über den Analytics Source Connector generiert werden, empfiehlt Adobe, alle VISTA-Regeln oder Verarbeitungsregeln zu überprüfen, die für das vorübergehende ID-Feld gelten, um sicherzustellen, dass keine dieser Regeln neue Formen derselben ID einführt. So sollten Sie beispielsweise sicherstellen, dass keine VISTA- oder Verarbeitungsregeln dafür sorgen, dass im Feld für die vorübergehende ID nur für einen Teil der Ereignisse Kleinschreibung verwendet wird.
* Bei der feldbasierten Suche werden Felder nicht kombiniert oder verknüpft.
* Das Feld für die vorübergehende ID sollte nur einen ID-Typ enthalten (also IDs aus einem einzigen Namespace). Das Feld für die vorübergehende ID sollte beispielsweise keine Kombination aus Anmelde-IDs und E-Mail-IDs enthalten.
* Wenn mehrere Ereignis mit demselben Zeitstempel für dieselbe permanente ID auftreten, jedoch unterschiedliche Werte im Feld für die vorübergehende ID vorliegen, wird die feldbasierte Zuordnung auf Grundlage der alphabetischen Reihenfolge gewählt. Wenn also eine permanente ID A zwei Ereignisse mit demselben Zeitstempel hat und eines der Ereignis „Bob“ und das andere „Ann“ angibt, wählt die feldbasierte Zuordnung „Ann“.
* In Cross-Channel Analytics werden alle beständigen ID-Werte für einen Zeitraum von 1 Jahr verfolgt (TTL = 1 Jahr). Wenn ein Gerät länger als ein Jahr keine Aktivität aufweist und danach erneut Aktivität verzeichnet, werden die neuen Ereignisse mit einer anonymen Person verknüpft, bis der Benutzer wieder identifiziert wird (z. B. über eine erneute Anmeldung).
* Wenn ein Gerät von mehreren Personen gemeinsam genutzt wird und die Gesamtzahl der Transitionen aller Benutzer 50.000 überschreitet, stoppt die kanalübergreifende Analyse die Zuordnung von Daten für dieses Gerät.


## Aktivieren von Cross-Channel Analytics

Sobald Ihre Organisation alle Anforderungen erfüllt und die Einschränkungen überblickt, können Sie die folgenden Schritte ausführen, um mit der Verwendung in Customer Journey Analytics zu beginnen.

1. Importieren Sie die gewünschten Daten in Adobe Experience Platform. Siehe unter [Ein Schema erstellen](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=de) und [Daten aufnehmen](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=de) in der Adobe Experience Platform-Dokumentation.
1. Wenden Sie sich mit den folgenden Informationen an den Adobe-Support:
   * Eine Anfrage zur Aktivierung von Cross-Channel Analytics
   * Die Datensatz-ID für den Datensatz, den Sie neu zuweisen möchten
   * Der Spaltenname der beständigen ID für den gewünschten Datensatz (Kennung, die in jeder Zeile erscheint)
   * Der Spaltenname der vorübergehenden ID für den gewünschten Datensatz (die Verbindung der Personenkennung zwischen Datensätzen)
   * Ihre Voreinstellung für die Häufigkeit der [Wiederholungen](replay.md) und die Lookback-Länge. Zu den verfügbaren Optionen gehören eine Wiederholung pro Woche mit einem 7-tägigen Lookback-Fenster oder eine tägliche Wiederholung mit einem 1-tägigen Lookback-Fenster.
   * Sandbox-Name.
1. Wenn Sie eine Anfrage bezüglich Cross-Channel Analytics an den Adobe-Support stellen, wird diese Funktion in Zusammenarbeit mit dem Engineering-Team von Adobe aktiviert. Nach der Aktivierung wird in Adobe Experience Platform ein neu verschlüsselter Datensatz angezeigt, der eine neue Spalte für die Personen-ID enthält. Der Adobe-Support stellt die neue Datensatz-ID und den Namen der Personen-ID-Spalte bereit.
1. Bei der erstmaligen Verwendung stellt Adobe eine Aufstockung der zugeordneten Daten bereit, die bis zum Beginn des Vormonats zurückreicht (bis zu 60 Tage). Um diese Aufstockung durchführen zu können, muss die vorübergehende ID in den nicht zugewiesenen Daten aus dem so weit zurückreichenden Zeitfenster vorhanden sein.
1. [Erstellen Sie eine Verbindung](../create-connection.md) in CJA mit dem neu erstellten Datensatz und beliebigen weiteren Datensätzen, die Sie einbeziehen möchten. Wählen Sie für jeden Datensatz die korrekte Personen-ID.
1. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) auf Grundlage der Verbindung.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Sobald die Datenansicht eingerichtet ist, erfolgt die Analyse in Customer Journey Analytics genau wie bei jeder anderen Customer Journey Analytics-Analyse, bis auf die Tatsache, dass die Daten nun kanal- und geräteübergreifend verarbeitet werden.
