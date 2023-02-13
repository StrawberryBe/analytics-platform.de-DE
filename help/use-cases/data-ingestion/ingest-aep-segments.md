---
title: Aufnehmen von AEP-Zielgruppen in Customer Journey Analytics
description: Hier wird erläutert, wie AEP-Zielgruppen in Customer Journey Analytics aufgenommen werden, um danach Analysen durchzuführen.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: af9113f3afced902b385747bceaa9e51b72d83e6
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 99%

---

# Aufnehmen von AEP-Zielgruppen in Customer Journey Analytics (CJA)

In diesem Anwendungsbeispiel wird eine manuelle Methode zur Aufnahme von Adobe Experience Platform-Zielgruppen (AEP) in CJA erklärt. Diese Zielgruppen wurden möglicherweise in AEP Segment Builder, Adobe Audience Manager oder anderen Tools erstellt und sind im Echtzeit-Kundenprofil (RTCP) gespeichert. Die Zielgruppen bestehen aus einer Reihe von Profil-IDs und den entsprechenden Attributen/Ereignissen/etc. Wir möchten sie zur Analyse in CJA Workspace importieren.

## Voraussetzungen

* Zugriff auf Adobe Experience Platform (AEP), insbesondere auf das Echtzeit-Kundenprofil.
* Zugriff auf die Funktionen zum Erstellen/Verwalten von AEP-Schemas und -Datensätzen.
* Zugriff auf AEP Query Service (und die Möglichkeit, SQL zu schreiben) oder ein anderes Tool, um einige simple Umwandlungen durchzuführen.
* Zugriff auf Customer Journey Analytics. Sie müssen ein CJA-Produktadministrator sein, um CJA-Verbindungen und -Datenansichten erstellen/ändern zu können.
* Möglichkeit zur Verwendung der Adobe-APIs (Segmentierung, optional andere)

## Schritt 1: Wählen Sie Zielgruppen im Echtzeit-Kundenprofil aus {#audience}

[Das Echtzeit-Kundenprofil von Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) bietet eine ganzheitliche Sicht auf jeden einzelnen Kunden, indem es Daten aus verschiedenen Kanälen, einschließlich Online-, Offline-, CRM- und Drittanbieterdaten, kombiniert.

Wahrscheinlich haben Sie bereits Zielgruppen im Echtzeit-Kundenprofil, die aus verschiedenen Quellen stammen. Wählen Sie eine oder mehrere Zielgruppen für die Aufnahme in Customer Journey Analytics aus.

## Schritt 2: Erstellen Sie einen Profilvereinigungsdatensatz für den Export

Um die Zielgruppe in einen Datensatz zu exportieren, der schließlich zu einer Verbindung in CJA hinzugefügt werden kann, müssen Sie einen Datensatz erstellen, dessen Schema ein [Profilvereinigungsschema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=de#understanding-union-schemas) ist.

Vereinigungsschemas bestehen aus mehreren Schemas, die dieselbe Klasse haben und für ein Profil aktiviert wurden. Im Vereinigungsschema können Sie eine Zusammenführung aller Felder sehen, die in Schemas enthalten sind, die dieselbe Klasse haben. Das Echtzeit-Kundenprofil verwendet das Vereinigungsschema, um eine ganzheitliche Ansicht jedes einzelnen Kunden zu erstellen.

## Schritt 3: Exportieren Sie eine Zielgruppe über einen API-Aufruf in den Profilvereinigungsdatensatz  {#export}

Bevor Sie eine Zielgruppe in Customer Journey Analytics importieren können, müssen Sie sie in einen AEP-Datensatz exportieren. Dies kann nur mit der Segmentierungs-API und insbesondere mit dem [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=de) geschehen.

Sie können einen Exportvorgang mit der Zielgruppen-ID Ihrer Wahl erstellen und die Ergebnisse in den Profilvereinigungsdatensatz von AEP einfügen, den Sie in Schritt 2 erstellt haben. Obwohl Sie verschiedene Attribute/Ereignisse für die Zielgruppe exportieren können, müssen Sie nur das spezifische Profilkennungsfeld exportieren, das dem Personen-ID-Feld entspricht, das in der von Ihnen verwendeten CJA-Verbindung vorhanden ist (siehe Schritt 5 unten).

## Schritt 4: Bearbeiten Sie die Exportausgabe

Die Ergebnisse des Exportvorgangs müssen in einen separaten Profildatensatz umgewandelt werden, damit sie in CJA aufgenommen werden können. Diese Umwandlung kann mit [AEP Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de) oder einem anderen Transformations-Tool Ihrer Wahl durchgeführt werden. Für die Berichterstellung in CJA benötigen wir nur die Profilkennung (die der Personen-ID in CJA entspricht) und eine oder mehrere Zielgruppen-ID(s).

Der standardmäßige Exportvorgang enthält jedoch zusätzliche Daten. Daher müssen Sie diese Ausgabe bearbeiten, um irrelevante Daten zu entfernen und einige Dinge umzustellen.  Außerdem müssen Sie zuerst ein Schema/einen Datensatz erstellen, bevor Sie die umgewandelten Daten hinzufügen.

Im Folgenden finden Sie ein Beispiel für die Exportausgabe im Profilvereinigungsdatensatz **vor** der Bearbeitung:

![Nicht bearbeitete Ausgabe](../assets/export-unedited.png)

Beachten Sie Folgendes:

* Die Zielgruppen-ID ist unter `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status` vorhanden.
* Der Status muss „realized“ oder „entered“, darf aber nicht „exited“ sein.

Dies ist das Format des Profildatensatzes, den Sie an CJA senden können.

![Bearbeitete Ausgabe](../assets/export-edited.png)

Folgende Datenelemente müssen vorhanden sein:

* Zeichenfolgenfeld `_aresprodvalidation`: Bezieht sich auf Ihre Organisations-ID. Ihre wird anders lauten.
* Zeichenfolgenfeld `personID`: Dies ist das standardmäßige XDM-Schemafeld in Profildatensätzen, das die Person identifiziert. Verwenden Sie die Profil-ID vom Export.
* Zeichenfolgenfeld `audienceMembershipId`: Die Zielgruppen-ID vom Export. HINWEIS: Dieses Feld kann beliebig benannt werden (in Ihrem eigenen Schema).
* Fügen Sie einen Anzeigenamen für die Zielgruppe hinzu (`audienceMembershipIdName`), z. B.

   ![Anzeigename der Zielgruppe](../assets/audience-name.png)

* Fügen Sie bei Bedarf weitere Zielgruppen-Metadaten hinzu.

## Schritt 5: Fügen Sie diesen Profildatensatz zu einer vorhandenen Verbindung in CJA hinzu

Sie könnten [eine neue Verbindung erstellen](/help/connections/create-connection.md), aber die meisten Kunden möchten den Profildatensatz zu einer vorhandenen Verbindung hinzufügen. Die Zielgruppen-IDs ergänzen die vorhandenen Daten in CJA.

## Schritt 6: Ändern Sie die vorhandene CJA-Datenansicht (oder erstellen Sie eine neue)

Fügen Sie `audienceMembershipId`, `audienceMembershipIdName` und `personID` zur Datenansicht hinzu.

## Schritt 7: Erstellen Sie einen Bericht in Workspace

Sie können jetzt Berichte zu `audienceMembershipId`, `audienceMembershipIdName` und `personID` in Workspace erstellen.

## Weitere Hinweise

* Sie sollten diesen Prozess regelmäßig durchführen, damit die Zielgruppendaten in Customer Journey Analytics laufend aktualisiert werden.
* Sie können mehrere Zielgruppen in eine einzige CJA-Verbindung importieren. Dies erhöht zwar die Komplexität des Prozesses, es ist jedoch möglich. Damit dies funktioniert, müssen Sie einige Änderungen am obigen Prozess vornehmen:
   1. Führen Sie diesen Prozess für jede gewünschte Zielgruppe in Ihrer Zielgruppensammlung innerhalb des Echtzeit-Kundenprofis aus.
   1. CJA unterstützt Arrays/Objekt-Arrays in Profildatensätzen. Es wird empfohlen, für audienceMembershipId oder audienceMembershipIdName ein [Array von Objekten](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html) zu verwenden.
   1. Erstellen Sie in Ihrer Datenansicht eine neue Dimension mithilfe der Teilzeichenfolgenumwandlung des `audienceMembershipId`-Felds, um die Zeichenfolge mit kommagetrennten Werten in ein Array zu konvertieren. HINWEIS: Derzeit besteht für das Array eine Beschränkung von 10 Werten.
   1. Jetzt können Sie in CJA Workspace Berichte zur neuen Dimension `audienceMembershipIds` erstellen.
