---
title: Überblick über die kanalübergreifende Analyse
description: Schlüssel für Besucher-IDs aus mehreren Datensätzen zum Zuordnen von Besuchern erneut verwenden.
translation-type: tm+mt
source-git-commit: cc78a3941a4179be0dbf46055fea60df8e7e8b97
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 84%

---


# Überblick über die kanalübergreifende Analyse

**Journey IQ: Die kanalübergreifende Analyse** ist eine Funktion, mit der Sie die Personen-ID eines Datensatzes neu eingeben können. Dies ermöglicht eine nahtlose Kombination mehrerer Datensätze. Die kanalübergreifende Analyse untersucht Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen, um eine zugeordnete ID zu generieren. Mithilfe der kanalübergreifenden Analyse können Sie Fragen beantworten wie beispielsweise:

* Wie viele Personen beginnen ihr Erlebnis auf einem Kanal und beenden es auf einem anderen?
* Wie viele Menschen interagieren mit meiner Marke? Wie viele und welche Gerätetypen verwenden sie? Wie überschneiden sich diese?
* Wie oft beginnen Personen mit einer Aufgabe auf einem Mobilgerät und wechseln dann zu einem Desktop-PC, um die Aufgabe abzuschließen? Führen Kampagnen-Clickthroughs auf einem Gerät zur Konversion auf einem anderen Gerät?
* Wie ändern sich meine Daten zur Wirksamkeit einer Kampagne, wenn ich geräteübergreifende Journeys berücksichtige? Wie ändert sich meine Trichteranalyse?
* Welche sind die häufigsten Pfade, die Benutzer beim Wechsel von einem Gerät zum anderen verwenden? Wo steigen sie aus? Wo schließen sie ihre Aktion erfolgreich ab?
* Wie unterscheidet sich das Verhalten von Benutzern mit mehreren Geräten von Benutzern mit nur einem Gerät?

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Attribution geräte- und kanalübergreifend übernommen. Beispiel: Ein Benutzer besucht Ihre Site zum ersten Mal über eine Werbeanzeige auf seinem Desktop. Dieser Benutzer stößt bei seiner Bestellung auf ein Problem und ruft dann Ihren Kundendienst an, um das Problem zu beheben. Mit der kanalübergreifenden Analyse können Sie Callcenter-Ereignisse der Anzeige zuordnen, auf die ursprünglich geklickt wurde.

## Voraussetzungen

>[!IMPORTANT]
>
>Werden nicht alle Voraussetzungen erfüllt, kann beim Kombinieren von Datensätzen unter Umständen keine Verbindung für die kanalübergreifende Analyse hergestellt werden oder die Ergebnisse fallen mangelhaft aus.

Bevor Sie die kanalübergreifende Analyse verwenden, sollten Sie sicherstellen, dass Ihr Unternehmen folgende Voraussetzungen erfüllt:

* Ein Datensatz in Adobe Experience Platform muss über zwei Spalten verfügen, mit denen Besucher identifiziert werden können:
   * Eine **beständige ID**, eine Kennung, die in jeder Zeile vorhanden ist. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics AppMeasurement-Bibliothek generiert wurde.
   * Eine **vorübergehende ID**, eine Kennung, die nur in einigen Zeilen vorhanden ist. Beispiel: ein/e gehashte/r Benutzername oder E-Mail-Adresse, wenn sich ein Besucher authentifiziert. Sie können praktisch jede beliebige Kennung verwenden, sofern sie mindestens einmal für dasselbe Ereignis als beständige ID vorkommt.
* Ein anderer Datensatz, beispielsweise Callcenter-Daten, der in jeder Zeile eine vorübergehende ID enthält. Diese Personen-ID muss ähnlich wie die vorübergehende ID in dem anderen Datensatz formatiert sein.
* Mit dieser Funktion können Sie Datensätze zuordnen und somit beispielsweise authentifizierte und nicht authentifizierte Benutzerdaten zusammenführen. Vergewissern Sie sich vor dem Zusammenführen von Datensätzen, dass Sie die geltenden Gesetze und Vorschriften einhalten, wie etwa das Einholen der erforderlichen Berechtigungen der Endanwender.

## Einschränkungen

Die kanalübergreifende Analyse ist eine innovative und zuverlässige Funktion, deren Verwendung jedoch gewissen Einschränkungen unterliegt.

* Die aktuellen Funktionen zur Neuzuweisung sind auf einen Schritt beschränkt (beständige ID auf vorübergehende ID). Eine mehrstufige Neuzuweisung wird nicht unterstützt, beispielsweise beständige ID zu vorübergehender ID und dann zu einer weiteren vorübergehenden ID.
* Es werden nur Ereignis-Datensätze unterstützt. Andere Datensätze, wie beispielsweise Lookup-Datensätze, werden nicht unterstützt.
* Benutzerdefinierte ID-Maps, die in Ihrem Unternehmen verwendet werden, werden nicht unterstützt.
* Das Adobe Co-op-Diagramm und das Private-Diagramm werden nicht unterstützt.
* Das zum Verbinden verwendete Kanal wird in Analytics nicht transformiert. Die feldbasierte Suche verwendet den Wert im angegebenen Feld, wie er im nicht zugewiesenen Datensatz innerhalb des Datensees vorhanden ist. Wenn beispielsweise das Wort &quot;Bob&quot;im Feld erscheint und manchmal das Wort &quot;BOB&quot;angezeigt wird, werden diese als zwei separate Personen behandelt.


## Aktivieren der kanalübergreifenden Analyse

Sobald Ihre Organisation alle Anforderungen erfüllt und die Einschränkungen überblickt, können Sie die folgenden Schritte ausführen, um mit der Verwendung in Customer Journey Analytics zu beginnen.

1. Importieren Sie die gewünschten Daten in Adobe Experience Platform. Siehe unter [Ein Schema erstellen](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/tutorials/create-schema-ui.html) und [Daten aufnehmen](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.html) in der Adobe Experience Platform-Dokumentation.
1. Wenden Sie sich an Ihren Adobe Account Manager, was Folgendes umfassen kann:
   * Eine Anfrage zum Aktivieren der kanalübergreifenden Analyse
   * Die Datensatz-ID für den Datensatz, den Sie neu zuweisen möchten
   * Der Spaltenname der beständigen ID für den gewünschten Datensatz (Kennung, die in jeder Zeile erscheint)
   * Der Spaltenname der vorübergehenden ID für den gewünschten Datensatz (die Verbindung der Personenkennung zwischen Datensätzen)
   * Ihre Voreinstellung für die Häufigkeit der [Wiederholungen](replay.md) und die Lookback-Länge. Zu den verfügbaren Optionen gehören eine Wiederholung pro Woche mit einem 7-tägigen Lookback-Fenster oder eine tägliche Wiederholung mit einem 1-tägigen Lookback-Fenster.
1. Der Kundenbetreuer der Adobe arbeitet mit der Adobe-Engineering zusammen, um bei Eingang Ihrer Anfrage Cross-Kanal Analytics zu aktivieren. Nach der Aktivierung wird in Adobe Experience Platform ein neuer Datensatz mit einer neuen Spalte mit der ID der Person angezeigt. Ihr Adobe Account Manager kann die neue Datensatz-ID und den Namen der Person-ID-Spalte bereitstellen.
1. Wenn die Adobe zum ersten Mal aktiviert ist, wird eine Aufstockung der gehefteten Daten bereitgestellt, die bis zum Beginn des Vormonats (bis zu 60 Tage) zurückreicht. Um diese Aufstockung durchführen zu können, muss die transiente ID bis zu diesem Zeitpunkt in den nicht zugewiesenen Daten vorhanden sein.
1. [Erstellen Sie eine Verbindung](../create-connection.md) in CJA mit dem neu erstellten Datensatz und beliebigen weiteren Datensätzen, die Sie einbeziehen möchten. Wählen Sie für jeden Datensatz die korrekte Personen-ID.
1. [Erstellen Sie eine Datenansicht](/help/data-views/create-dataview.md) auf Grundlage der Verbindung.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Sobald die Datenansicht eingerichtet ist, erfolgt die Analyse in Customer Journey Analytics genau wie bei jeder anderen Customer Journey Analytics-Analyse, bis auf die Tatsache, dass die Daten nun kanal- und geräteübergreifend verarbeitet werden.
