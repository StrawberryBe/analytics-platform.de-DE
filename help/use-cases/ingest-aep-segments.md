---
title: Aufnehmen von AEP-Zielgruppen in Customer Journey Analytics
description: Erläutert, wie AEP-Zielgruppen für weitere Analysen in Customer Journey Analytics aufgenommen werden.
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: ed01fd0899cac21fff156e0c31dc2b52ff7c8cca
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 2%

---


# Aufnehmen von AEP-Zielgruppen in Customer Journey Analytics (CJA)

>[!NOTE]
>
>Dieses Thema befindet sich im Aufbau.

(Brandon, fyi, &quot;Unified Profile&quot;ist ein veralteter Begriff für &quot;Echtzeit-Kundenprofil&quot;- laut AEP-Dokumentmanager. Im AEP-Dokumentensatz finden Sie keine Dokumente zu &quot;UP&quot;.)

In diesem Anwendungsbeispiel wird eine vorläufige, manuelle Methode zur Einbindung von Adobe Experience Platform-Zielgruppen (AEP) in CJA untersucht. Diese Zielgruppen wurden möglicherweise im Segmentaufbau von AEP, Adobe Audience Manager oder anderen Tools erstellt und sind im Echtzeit-Kundenprofil (RTCP) gespeichert. Die Zielgruppen bestehen aus Listen mit Personen-IDs, Profil-IDs usw. und wir möchten sie zur Analyse in CJA Workspace importieren.

## Voraussetzungen

* Zugriff auf Adobe Experience Platform (AEP), insbesondere Echtzeit-Kundenprofil.
* Zugang zum Customer Journey Analytics
* Möglichkeit, benutzerdefinierten Code zu schreiben?
* Was sonst noch.

## Schritt 1: Zielgruppe(n) im Echtzeit-Kundenprofil auswählen {#audience}

Adobe Experience Platform [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) (RTCP) bietet Ihnen die Möglichkeit, eine ganzheitliche Sicht auf jeden einzelnen Kunden zu erhalten, indem Sie Daten aus verschiedenen Kanälen, einschließlich Online-, Offline-, CRM- und Drittanbieter-Kanälen, kombinieren. Wahrscheinlich haben Sie bereits Audiences in RTCP, die aus verschiedenen Quellen stammen könnten. Wählen Sie eine oder mehrere Zielgruppen aus.

## Schritt 2: Erstellen eines Profilunionsdatensatzes für den Export

Um die Zielgruppe in einen Datensatz zu exportieren, der dann eine Verbindung mit CJA herstellen kann, müssen Sie einen Datensatz erstellen, dessen Schema ein Profil ist [Vereinigungsschema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
Vereinigungsschemas bestehen aus mehreren Schemas, die dieselbe Klasse teilen und für Profile aktiviert wurden. Mit dem Vereinigungsschema können Sie eine Zusammenführung aller Felder sehen, die in Schemas enthalten sind, die dieselbe Klasse teilen. Das Echtzeit-Kundenprofil verwendet das Vereinigungsschema, um eine ganzheitliche Ansicht jedes einzelnen Kunden zu erstellen.

## Schritt 3: Zielgruppe über einen API-Aufruf in einen Datensatz exportieren {#export}

Bevor Sie eine Zielgruppe in Customer Journey Analytics importieren können, müssen Sie sie in einen Datensatz in AEP exportieren. Dies kann nur mit der Segmentierungs-API und insbesondere mit dem [Export Job API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). Sie können einen Exportauftrag erstellen und die Ergebnisse in den AEP-Datensatz der Profilunion einfügen, den Sie in Schritt 2 erstellt haben.

## Schritt 4: Exportausgabe bearbeiten

Beim Erstellen des Exportauftrags für eine Zielgruppe benötigen wir nur die Personen-ID und die Zielgruppen-ID für die Berichterstellung in CJA. Der standardmäßige Exportauftrag enthält jedoch mehr Daten. Daher müssen wir diese Ausgabe bearbeiten, um irrelevante Daten zu entfernen.

Im Folgenden finden Sie ein Beispiel für die Exportausgabe im Datensatz Profilunion . **before** beliebige Bearbeitung:

![Nicht bearbeitete Ausgabe](assets/export-unedited.png)

Beachten Sie Folgendes:

* Die Zielgruppen-ID ist unter `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Der Status muss &quot;realisiert&quot;oder &quot;eingegeben&quot;, aber nicht &quot;beendet&quot;sein. Ersetzen Sie &quot;Exited&quot;durch &quot;blank&quot;.

Dies ist das Format des Profildatensatzes, den Sie an CJA senden können.

![Bearbeitete Ausgabe](assets/export-edited.png)

Folgende Datenelemente müssen vorhanden sein:

* `_aresprodvalidation`: Bezieht sich auf Ihre Organisations-ID. Deins wird anders sein.
* `personID`: In diesem Fall wird ein benutzerfreundlicher Name
* `audienceMembershipIdList` Zeichenfolgenfeld: Die Zielgruppen-ID
* Fügen Sie einen Anzeigenamen für die Zielgruppe hinzu (`audienceMembershipIdName`), z. B.

   ![Anzeigename der Zielgruppe](assets/audience-name.png)

## Schritt 5: Erstellen einer Verbindung in CJA mit diesem Profildatensatz

[Verbindung herstellen](/help/connections/create-connection.md)

## Schritt 6: Erstellen einer Datenansicht

Hinzufügen `audienceMembershipIdName` und `personID` in die Datenansicht.

## Schritt 7: Bericht in Workspace

Sie können jetzt Berichte erstellen zu `audienceMembershipIdName` und `personID` in Workspace.
Screenshot wäre großartig.

Gehen Sie folgendermaßen vor:

schreiben Sie mehr Schritte für , wenn Sie es mit Personen zu tun haben, die mehreren Zielgruppen angehören.




