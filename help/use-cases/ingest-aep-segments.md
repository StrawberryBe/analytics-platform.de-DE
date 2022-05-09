---
title: Aufnehmen von AEP-Zielgruppen in Customer Journey Analytics
description: Erläutert, wie AEP-Zielgruppen für weitere Analysen in Customer Journey Analytics aufgenommen werden.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 9c4869bb632f3d69d8704009744246b975cb5c4a
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 2%

---

# Aufnehmen von AEP-Zielgruppen in Customer Journey Analytics (CJA)

In diesem Anwendungsbeispiel wird eine vorläufige, manuelle Methode zur Einbindung von Adobe Experience Platform-Zielgruppen (AEP) in CJA untersucht. Diese Zielgruppen wurden möglicherweise im Segmentaufbau von AEP, Adobe Audience Manager oder anderen Tools erstellt und sind im Echtzeit-Kundenprofil (RTCP) gespeichert. Die Zielgruppen bestehen aus einer Reihe von Profil-IDs zusammen mit den entsprechenden Attributen/Ereignissen/etc. und wir möchten sie zur Analyse in CJA Workspace importieren.

## Voraussetzungen

* Zugriff auf Adobe Experience Platform (AEP), insbesondere Echtzeit-Kundenprofil.
* Zugriff zum Erstellen/Verwalten von AEP-Schemas und -Datensätzen.
* Zugriff auf AEP Query Service (und die Möglichkeit, SQL zu schreiben) oder ein anderes Tool, um einige leichte Umwandlungen durchzuführen.
* Zugriff auf Customer Journey Analytics. Sie müssen ein CJA-Produktadministrator sein, um CJA-Verbindungen und Datenansichten erstellen/ändern zu können.
* Möglichkeit zur Verwendung der Adobe-APIs (Segmentierung, optional andere)

## Schritt 1: Zielgruppe(n) im Echtzeit-Kundenprofil auswählen {#audience}

Adobe Experience Platform [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) (RTCP) bietet Ihnen die Möglichkeit, eine ganzheitliche Sicht auf jeden einzelnen Kunden zu erhalten, indem Sie Daten aus verschiedenen Kanälen, einschließlich Online-, Offline-, CRM- und Drittanbieter-Kanälen, kombinieren.

Wahrscheinlich haben Sie bereits Audiences in RTCP, die aus verschiedenen Quellen stammen könnten. Wählen Sie eine oder mehrere Zielgruppen für die Aufnahme in Customer Journey Analytics aus.

## Schritt 2: Erstellen eines Profilunionsdatensatzes für den Export

Um die Zielgruppe in einen Datensatz zu exportieren, der schließlich zu einer Verbindung in CJA hinzugefügt werden kann, müssen Sie einen Datensatz erstellen, dessen Schema ein Profil ist [Vereinigungsschema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).

Vereinigungsschemas bestehen aus mehreren Schemas, die dieselbe Klasse teilen und für Profile aktiviert wurden. Mit dem Vereinigungsschema können Sie eine Zusammenführung aller Felder sehen, die in Schemas enthalten sind, die dieselbe Klasse teilen. Das Echtzeit-Kundenprofil verwendet das Vereinigungsschema, um eine ganzheitliche Ansicht jedes einzelnen Kunden zu erstellen.

## Schritt 3: Exportieren einer Zielgruppe in den Datensatz der Profilunion über einen API-Aufruf {#export}

Bevor Sie eine Zielgruppe in Customer Journey Analytics importieren können, müssen Sie sie in einen AEP-Datensatz exportieren. Dies kann nur mit der Segmentierungs-API und insbesondere mit dem [Export Job API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en).

Sie können einen Exportauftrag mit der Zielgruppen-ID Ihrer Wahl erstellen und die Ergebnisse in den Datensatz mit dem Profil-Vereinigungs-AEP einfügen, den Sie in Schritt 2 erstellt haben. Obwohl Sie verschiedene Attribute/Ereignisse für die Zielgruppe exportieren können, müssen Sie nur das spezifische Feld für die Profil-ID exportieren, das mit dem Feld für die Personen-ID übereinstimmt, das in der von Ihnen verwendeten CJA-Verbindung verwendet wird (siehe unten in Schritt 5).

## Schritt 4: Exportausgabe bearbeiten

Die Ergebnisse des Exportauftrags müssen in einen separaten Profildatensatz umgewandelt werden, damit sie in CJA aufgenommen werden können.  Diese Umwandlung kann mit [AEP Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de)oder ein anderes Transformationstool Ihrer Wahl. Für die Berichterstellung in CJA benötigen wir nur die Profil-ID (die mit der Personen-ID in CJA übereinstimmt) und eine oder mehrere Zielgruppen-ID(s).

Der standardmäßige Exportauftrag enthält jedoch mehr Daten. Daher müssen wir diese Ausgabe bearbeiten, um irrelevante Daten zu entfernen und einige Dinge zu verschieben.  Außerdem müssen Sie zuerst ein Schema/einen Datensatz erstellen, bevor Sie die umgewandelten Daten hinzufügen.

Im Folgenden finden Sie ein Beispiel für die Exportausgabe im Datensatz Profilunion . **before** beliebige Bearbeitung:

![Nicht bearbeitete Ausgabe](assets/export-unedited.png)

Beachten Sie Folgendes:

* Die Zielgruppen-ID ist unter `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Der Status muss &quot;realisiert&quot;oder &quot;eingegeben&quot;, aber nicht &quot;beendet&quot;sein.

Dies ist das Format des Profildatensatzes, den Sie an CJA senden können.

![Bearbeitete Ausgabe](assets/export-edited.png)

Folgende Datenelemente müssen vorhanden sein:

* `_aresprodvalidation` Zeichenfolgenfeld: Bezieht sich auf Ihre Organisations-ID. Deins wird anders sein.
* `personID` Zeichenfolgenfeld: Dies ist das standardmäßige XDM-Schemafeld in Profildatensätzen, das die Person identifiziert. Verwenden Sie die Profil-ID aus dem Export.
* `audienceMembershipId` Zeichenfolgenfeld: Die Zielgruppen-ID aus dem Export.  HINWEIS: Dieses Feld kann beliebig benannt werden (aus Ihrem eigenen Schema).
* Fügen Sie einen Anzeigenamen für die Zielgruppe hinzu (`audienceMembershipIdName`), z. B.

   ![Anzeigename der Zielgruppe](assets/audience-name.png)

* Fügen Sie bei Bedarf weitere Zielgruppen-Metadaten hinzu.

## Schritt 5: Fügen Sie diesen Profildatensatz zu einer vorhandenen Verbindung in CJA hinzu.

Du könntest [eine neue Verbindung erstellen](/help/connections/create-connection.md), aber die meisten Kunden möchten den Profildatensatz zu einer vorhandenen Verbindung hinzufügen. Die Zielgruppen-IDs ergänzen die vorhandenen Daten in CJA.

## Schritt 6: Vorhandene (oder neue) CJA-Datenansicht ändern

Hinzufügen `audienceMembershipId`, `audienceMembershipIdName` und `personID` in die Datenansicht.

## Schritt 7: Bericht in Workspace

Sie können jetzt Berichte erstellen zu `audienceMembershipId`, `audienceMembershipIdName` und `personID` in Workspace.

## Weitere Hinweise

* Sie sollten diesen Prozess regelmäßig durchführen, damit die Zielgruppendaten in Customer Journey Analytics ständig aktualisiert werden.
* Sie können mehrere Zielgruppen in eine einzige CJA-Verbindung importieren. Dies erhöht die Komplexität des Prozesses, ist jedoch möglich. Damit dies funktioniert, müssen Sie einige Änderungen am obigen Prozess vornehmen:
   1. Führen Sie diesen Prozess für jede gewünschte Zielgruppe in Ihrer Zielgruppensammlung innerhalb von RTCP durch.
   1. Bei der Durchführung der Umwandlungen der Exportauftragsausgabe müssen Sie eine Liste von `audienceMembershipId(s)`, da eine einzelne CJA-Personen-ID mehreren Zielgruppen angehören kann. Zu einem späteren Zeitpunkt unterstützt CJA Arrays/Objekt-Arrays in Profildatensätzen. Sobald diese unterstützt werden, verwenden Sie ein Array von Objekten für die `audienceMembershipId` oder `audienceMembershipIdName` wird die beste Option sein. Extrahieren Sie in der Zwischenzeit alle aktuellen Zielgruppen-IDs für jede Profil-ID in der Ausgabe des Exportauftrags (mit dem Status &quot;realisiert&quot;oder &quot;eingegeben&quot;) und fügen Sie sie in eine durch Kommata getrennte Wertzeichenfolge ein (d. h. `<id1>,<id2>,...`).  Wenn es eine Zielgruppen-ID mit dem Status &quot;Beendet&quot;gibt, stellen Sie sicher, dass diese NICHT in der Liste enthalten ist.  Wenn Sie die Zuordnung des Anzeigenamens zur ID beibehalten möchten, können Sie sie am Ende jeder ID in der Liste (zusammen mit allen anderen Metadaten) anhängen.
   1. Erstellen Sie in Ihrer Datenansicht eine neue Dimension mithilfe der Subzeichenfolgenumwandlung auf der `audienceMembershipId` -Feld, um die Zeichenfolge mit kommagetrennten Werten in ein Array zu konvertieren. HINWEIS: Es gibt derzeit eine Beschränkung von 10 Werten im Array.
   1. Sie können jetzt Berichte zu dieser neuen Dimension erstellen `audienceMembershipIds` in CJA Workspace.
