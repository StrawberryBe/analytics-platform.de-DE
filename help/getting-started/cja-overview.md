---
title: Überblick über Customer Journey Analytics
description: Einführung in Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 7afdf490d0a63b1286a1a646a487ee96d4b6ed8f

---


# Überblick über Customer Journey Analytics

Customer Journey Analytics ist eine Analytics-Funktion, mit der Sie die Leistungsfähigkeit von Analysis Workspace mit Daten aus Adobe Experience Platform nutzen können. Es kann Daten im Wert von Jahren aufschlüsseln, filtern, abfragen und visualisieren und wird mit der Fähigkeit der Plattform kombiniert, alle möglichen Datenschemata und -typen zu speichern. Mithilfe des **Erlebnis-Datenmodells (XDM)** können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und erforscht werden können. **Mit Experience Query Services** können Sie SQL-kompatible Werkzeuge und Frameworks verwenden, um alle Daten abzufragen und zu bearbeiten.

## Vergleichen von CJA mit dem Analysis Workspace

Customer Journey Analytics erweitert den Umfang von Analytics, indem es benutzerfreundliche kanalübergreifende Funktionen anbietet und Einschränkungen in früheren Versionen von Adobe Analytics beseitigt. Einige wichtige Verbesserungen sind:

* **Unbegrenzte Variablen und Ereignisse**: Die Konzepte von eVars, Props und Ereignissen existieren nicht mehr. Die Daten konzentrieren sich in erster Linie auf Dimensionen und Metriken. Datensätze können eine unbegrenzte Anzahl an eindeutigen Dimensionen und Metriken aufweisen.
* **Unbegrenzte Uniques**: Adobe Experience Platform ist nicht auf eindeutige Einschränkungen beschränkt, wie z. B. die eindeutigen 500-k-Werte in herkömmlichen Report Suites.
* **Verlaufsdaten**&#x200B;ändern: Mit Adobe Experience Platform können Daten entfernt oder korrigiert werden.
* **Report Suite-übergreifende Daten**: Vorhandene Implementierungen aus mehreren Datensätzen können in Plattform kombiniert werden.

Die erste Version von Customer Journey Analytics umfasst viele der Funktionen, die im Analysis Workspace enthalten sind. Eine vollständige Liste finden Sie unter Unterstützung für [Customer Journey Analytics-Funktionen](cja-aa.md).

### Aktualisierungen der Terminologie

Mehrere Funktionen von CJA wurden in Übereinstimmung mit Branchenstandards umbenannt. Zu den aktualisierten Namen gehören:

* Segmente werden jetzt als &quot;Filter&quot;bezeichnet
* Virtual Report Suites werden jetzt als &quot;Ansichten&quot;bezeichnet
* Klassifizierungen werden jetzt als &quot;Suchdatasets&quot;bezeichnet
* Kundenattribute werden jetzt als &quot;Profildatasets&quot;bezeichnet
* Trefferbehälter werden jetzt als &quot;Ereignisbehälter&quot;bezeichnet
* Besuchsbehälter werden jetzt als &quot;Sitzungsbehälter&quot;bezeichnet
* Besucherbehälter werden jetzt als &quot;Personen&quot;-Container bezeichnet

## Wichtigste Verwendungsfälle

Customer Journey Analytics ermöglicht Ihnen Folgendes:

* **Betrachten Sie den Kunden in einem Reisekontext**: Sie können Daten sequenziell über mehrere Kanäle anzeigen und analysieren. Daten aus Call Center, POS-Systemen und Online-Eigenschaften können in einer einzigen Berichtsansicht kombiniert werden.
* **Machen Sie allen** Einblicke zugänglich: Demokratisieren Sie den Datenzugriff und lassen Sie mehr Menschen Geschäftsentscheidungen mit datengestützten Erkenntnissen treffen. Jeder Mitarbeiter des Unternehmens, der für alle Aspekte der Kundenerfahrung verantwortlich ist, kann anhand vollständigerer Daten schneller echte Entscheidungen treffen.
* **Nutzen Sie die Kraft der Datenwissenschaft für Ihre Analysten**: Mit Customer Journey Analytics können normale Menschen mithilfe von Datenwissenschaften tiefe Einblicke und Analysen gewinnen.
* **Visualisieren und interagieren Sie mit Ihren Datensets mithilfe von Ad-hoc-Berichten**: Workspace kann jeden Datensatz aus Adobe Experience Platform verwenden, der einigen grundlegenden Regeln entspricht.
* **Nicht-Web-Daten** anzeigen: Workspace ist nicht mehr auf eine starre Definition eines Treffers oder Ereignisses beschränkt. Benutzerdefinierte Schemata ermöglichen die vollständige Kontrolle über Daten und Definitionen.
* **Verbessern Sie die Kontrolle über Ihre Datenbearbeitung**: Ändern Sie die hochgeladenen Daten, erstellen Sie neue Datensätze und importieren Sie sie in Workspace. Adobe Experience Platform bietet Werkzeuge zum Abfragen, Extrahieren, Transformieren und Laden über den Experience Cloud-Abfragedienst.

## Voraussetzungen

Bevor Sie Customer Journey Analytics verwenden können, müssen die folgenden Schritte ausgeführt werden:

* Ihr Unternehmen hat einen aktiven Vertrag mit Adobe Analytics für Select, Prime oder Ultimate mit dem Customer Journey Analytics-Add-on. Wenden Sie sich an den Kundenbetreuer Ihres Unternehmens, wenn Sie sich nicht sicher sind, welche Art von Vertrag Sie haben oder ob Sie das CJA-Add-on installiert haben.
* Ihr Unternehmen wurde für Adobe Experience Platform bereitgestellt.

## Benutzerzugriffsberechtigungen

Zum Erstellen von Verbindungen, zum Hinzufügen von Datensätzen usw. benötigen Sie die folgenden Berechtigungen in der [Admin-Konsole](https://adminconsole.adobe.com/enterprise/):

* Zur Verwaltung von Datensätzen in der Experience Platform müssen Sie Teil eines Plattform-Produktprofils sein, das Ihnen die Berechtigung zum Verwalten von Datensätzen erteilt. Weitere Informationen finden Sie unter [Zugriffssteuerung in der Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Um eine Verbindung zu einem Plattform-Dataset herzustellen, müssen Sie Teil eines Plattform-Produktprofils sein, das Ihnen die folgenden Berechtigungen erteilt:
   * Schemas anzeigen
   * Datenblätter anzeigen
   * Identitätsnamensräume verwalten
   * Sandboxen anzeigen
* Um auf Customer Journey Analytics zugreifen oder eine Verbindung herstellen zu können, müssen Sie auch einem Customer Journey Analytics-Produktprofil in der [Admin-Konsole](https://adminconsole.adobe.com/enterprise/)hinzugefügt werden.

## Weitere Funktionen, die auf Adobe Experience Platform basieren

Customer Journey Analytics ist eine Funktion unter vielen, die auf der Adobe Experience Platform basieren. Einige andere Funktionen, die auch auf der Plattform basieren, ermöglichen es Ihnen, Ihre Daten optimal zu nutzen.

Mit der Adobe Experience Platform können Sie Kundendaten und -inhalte aus jedem System zentralisieren und standardisieren und mithilfe von Datenwissenschaften und maschinellem Lernen die Gestaltung und Bereitstellung personalisierter Erlebnisse verbessern. Kundendaten in der Plattform werden als Datensätze gespeichert, die aus einem Schema und Datenstapeln bestehen. Weitere Informationen zur Plattform finden Sie unter Übersicht über die [Adobe Experience Platform Architecture](https://www.adobe.io/apis/experienceplatform/home/overview.html).

Von der Dateningestion bis hin zum direkten SQL-Zugriff sind mehrere Komponenten der Experience Platform von zentraler Bedeutung für Customer Journey Analytics und stehen in Verbindung damit:

* [Abfragedienst](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html): Verwenden Sie Standard-SQL, um Daten von Adobe Experience Platform abzurufen, z. B. Adobe-Lösungsdaten, Daten von Kunden-Erstanbietern oder andere Plattformdaten. Es ist ein serverloses Tool, mit dem Sie beliebige Datensätze zusammenführen und die Abfrageergebnisse als neuer Datensatz zur Verwendung in Berichten, Data Science Workspace oder zur Erfassung in den Profildienst erfassen können. Mit dem Query Service können Sie Datenanalyseökosysteme erstellen, um ein Bild der Verbraucher über ihre verschiedenen Interaktionskanäle hinweg zu erstellen. Zu diesen Kanälen gehören u. a. Point-of-Sale-Systeme, Web-, Mobile-, CRM-Systeme usw.
* [Echtzeit-Kundenprofil](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Identitätsdienst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) in der Option &quot;Entwickler&quot;: Sie können vorgefertigte Modelle für künstliche Intelligenz (AI) und maschinelles Lernen in Adobe Experience Platform verwenden, um verschiedene Punkte der Customer Journey zu beeinflussen. Indem Sie verborgene Einblicke entdecken, können Sie während der gesamten Customer Journey bessere Vorhersagen treffen, empfohlene Best-Next-Schritte empfehlen oder schwerfällige Prozesse automatisieren.
