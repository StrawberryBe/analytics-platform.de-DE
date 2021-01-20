---
title: Überblick über Kanal-Analytics
description: Schlüssel für Besucher-IDs aus mehreren Datensätzen zum Zusammenfügen von Besuchern erneut verwenden.
translation-type: tm+mt
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 19%

---


# Überblick über Kanal-Analytics

**Journey IQ: Die benutzerübergreifende** Analyse ist eine Funktion, mit der Sie die Personen-ID eines Datasets neu eingeben können. Dies ermöglicht eine nahtlose Kombination mehrerer Datensätze. CCA untersucht Benutzerdaten aus authentifizierten und nicht authentifizierten Sitzungen, um eine zugewiesene ID zu generieren. Mithilfe von Cross-Kanal Analytics können Sie Fragen wie die folgenden beantworten:

* Wie viele Menschen beginnen ihre Erfahrung in einem Kanal und dann in einem anderen?
* Wie viele Menschen interagieren mit meiner Marke? Wie viele und welche Gerätetypen verwenden sie? Wie überschneiden sich diese?
* Wie oft beginnen Personen mit einer Aufgabe auf einem Mobilgerät und wechseln dann zu einem Desktop-PC, um die Aufgabe abzuschließen? Führen Kampagnen-Clickthroughs auf einem Gerät zur Konversion auf einem anderen Gerät?
* Wie ändern sich meine Daten zur Wirksamkeit einer Kampagne, wenn ich geräteübergreifende Journeys berücksichtige? Wie ändert sich meine Trichteranalyse?
* Welche sind die häufigsten Pfade, die Benutzer beim Wechsel von einem Gerät zum anderen verwenden? Wo steigen sie aus? Wo schließen sie ihre Aktion erfolgreich ab?
* Wie unterscheidet sich das Verhalten von Benutzern mit mehreren Geräten von Benutzern mit nur einem Gerät?

Wenn Sie Datensätze mit ähnlichen Personen-IDs kombinieren, wird die Zuordnung geräteübergreifend und über Kanal hinweg übernommen. Beispiel: Ein Benutzer besucht Ihre Site zum ersten Mal über eine Werbeanzeige auf seinem Desktop. Dieser Benutzer stößt bei seiner Bestellung auf ein Problem und ruft dann das Kundendienstteam an, um es zu beheben. Mit Cross-Kanal Analytics können Sie Call-Center-Ereignis der Anzeige zuordnen, auf die sie ursprünglich geklickt haben.

## Voraussetzungen

>[!IMPORTANT]
>
>Wird nicht alle Voraussetzungen erfüllt, kann es beim Kombinieren von Datensätzen zu einer CCA-Verbindung oder zu schlechten Ergebnissen kommen.

Bevor Sie Analytics für verschiedene Kanal verwenden, sollten Sie sicherstellen, dass Ihr Unternehmen mit Folgendem vorbereitet ist:

* Ein Datensatz in Adobe Experience Platform muss aus zwei Spalten bestehen, mit denen Besucher identifiziert werden können:
   * Eine **beständige ID**, eine Kennung, die in jeder Zeile vorhanden ist. Beispielsweise eine Besucher-ID, die von einer Adobe Analytics AppMeasurement Library generiert wurde.
   * Eine **transiente ID**, eine ID, die nur auf einigen Zeilen vorhanden ist. Beispiel: Ein Hash-Benutzername oder eine E-Mail-Adresse, sobald sich ein Besucher authentifiziert. Sie können praktisch jeden Bezeichner verwenden, den Sie möchten, sofern er mindestens einmal auf demselben Ereignis wie eine angegebene beständige ID vorhanden ist.
* Ein anderer Datensatz, z. B. Call-Center-Daten, der in jeder Zeile eine transiente ID enthält. Diese Personen-ID muss ähnlich wie die transiente ID im anderen Datensatz formatiert sein.
* Mit dieser Funktion können Sie Datasets zusammenführen, die authentifizierte und nicht authentifizierte Benutzerdaten zusammenführen können. Vergewissern Sie sich vor dem Zusammenführen von Datensätzen, dass Sie die geltenden Gesetze und Vorschriften einhalten, einschließlich der erforderlichen Endbenutzerberechtigungen.

## Einschränkungen

Cross-Kanal Analytics ist eine bahnbrechende und robuste Funktion, deren Verwendung jedoch eingeschränkt werden kann.

* Die aktuellen Rekeying-Funktionen sind auf einen Schritt beschränkt (beständige ID auf transiente ID). Mehrstufige Neuzuordnung (z. B. beständige ID zu einer transienten ID und dann zu einer anderen transienten ID) wird nicht unterstützt.
* Nur Ereignis-Datensätze werden unterstützt. Andere Datensätze, wie z. B. Nachschlagedatasets, werden nicht unterstützt.
* Benutzerdefinierte ID-Maps, die in Ihrem Unternehmen verwendet werden, werden nicht unterstützt.
* Das Adobe-Co-op-Diagramm und das Private-Diagramm werden nicht unterstützt.

## Kanal-übergreifende Analyse aktivieren

Sobald Ihr Unternehmen alle Voraussetzungen erfüllt und die Einschränkungen versteht, können Sie die folgenden Schritte ausführen, um mit dem Unternehmen in CJA Beginn zu erzielen.

1. Importieren Sie die gewünschten Daten nach Adobe Experience Platform. Siehe [Erstellen eines Schemas](https://docs.adobe.com/content/help/de-DE/experience-platform/xdm/tutorials/create-schema-ui.html) und [Daten](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.html) in der Adobe Experience Platform-Dokumentation.
1. Wenden Sie sich an Ihren Adobe-Kundenbetreuer, der Folgendes enthält:
   * Eine Anforderung zum Aktivieren von Kanal-übergreifender Analytics
   * Die DataSet-ID für den Datensatz, den Sie neu starten möchten
   * Der Spaltenname der beständigen ID für den gewünschten Datensatz (Bezeichner, der in jeder Zeile angezeigt wird)
   * Der Spaltenname der transienten ID für den gewünschten Datensatz (der Link zur Kennung der Person zwischen Datensätzen)
   * Ihre Voreinstellung für [Wiederholung](replay.md) Häufigkeit und Lookback-Länge. Zu den Optionen gehören eine Wiederholung einmal pro Woche mit einem 7-tägigen Lookback-Fenster oder eine Wiederholung jeden Tag mit einem 1-tägigen Lookback-Fenster.
1. Der Adobe Account Manager aktiviert Cross-Kanal Analytics, wenn Sie Ihre Anforderung erhalten. Nach der Aktivierung wird in Adobe Experience Platform ein neuer Datensatz mit einer neuen Person-ID angezeigt. Ihr Adobe-Kundenbetreuer kann die neue Dataset-ID und den Spaltennamen der Person-ID angeben.
1. [Erstellen Sie eine ](../create-connection.md) Verbindung in CJA mit dem neu erstellten Datensatz und allen anderen Datensätzen, die Sie einbeziehen möchten. Wählen Sie die richtige Personen-ID für jeden Datensatz.
1. [Erstellen Sie eine ](/help/data-views/create-dataview.md) Datenansicht basierend auf der Verbindung.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

Sobald die Ansicht eingerichtet ist, erfolgt die Analyse in CJA genau wie bei jeder anderen Analyse in CJA, bis auf die Tatsache, dass die Daten über mehrere Kanal und Geräte hinweg verarbeitet werden.
