---
title: Überblick über Customer Journey Analytics
description: Einführung in Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 336adb3762258cc657ffa5c74a50d28e6f63c7db

---


# Überblick über Customer Journey Analytics

Customer Journey Analytics ist eine Analytics-Funktion, mit der Sie die Leistungsfähigkeit von Analyse Workspace mit Daten von Adobe Experience Platform nutzen können. Es kann Daten im Wert von Jahren aufschlüsseln, filtern, Abfragen vornehmen und visualisieren und wird mit der Fähigkeit der Plattform kombiniert, alle möglichen Schema und Typen von Daten zu speichern. Mithilfe des **Erlebnis-Datenmodells (XDM)** können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und erforscht werden können. **Mit Experience Abfrage Services** können Sie SQL-kompatible Tools und Frameworks zur Abfrage und Manipulation aller Daten verwenden.

## Vergleich von CJA mit herkömmlichen Adobe Analytics

Customer Journey Analytics erweitert den Umfang von Analytics, indem es benutzerfreundliche Funktionen für Kanal bietet und Einschränkungen in früheren Versionen von Adobe Analytics beseitigt. Einige wichtige Verbesserungen sind:

* **Unbegrenzte Variablen und Ereignis**: Die Konzepte von eVars, Props und Ereignissen existieren nicht mehr. Die Daten konzentrieren sich in erster Linie auf Dimensionen und Metriken. Datensätze können eine unbegrenzte Anzahl an eindeutigen Dimensionen und Metriken aufweisen.
* **Unbegrenzte eindeutige Werte**: Adobe Experience Platform ist nicht auf eindeutige Einschränkungen beschränkt, wie z. B. die eindeutigen 500-k-Werte in herkömmlichen Report Suites.
* **Verlaufsdaten**&#x200B;ändern: Mit Adobe Experience Platform können Daten entfernt oder korrigiert werden.
* **Report Suite-übergreifende Daten**: Vorhandene Implementierungen aus mehreren Datensätzen können in Plattform kombiniert werden.

Die erste Version von Customer Journey Analytics umfasst viele der Funktionen von Analyse Workspace. Eine vollständige Liste finden Sie unter Unterstützung [der](cja-aa.md)Customer Journey Analytics-Funktionen.

## Vergleichen von CJA mit geräteübergreifenden Analysen

[Geräteübergreifende Analysen](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) können mit dem Identitätsdienst für Adobe Experience Platform integriert werden. Dabei wird entweder das Co-op-Diagramm oder das private Diagramm verwendet, um zu ermitteln, wie digitale Geräte Personen zugeordnet werden. Es ist für Adobe Analytics Ultimate-Kunden verfügbar.

CJA ist mit Adobe Experience Platform-Datensätzen integriert und ermöglicht die Analyse über mehrere Kanal in Analyse Workspace. Obwohl CJA noch nicht in die Co-op- oder Private-Identity-Diagramme integriert ist, können Sie &quot;Ihre eigene ID&quot;zusammenführen, um Datasets zusammenzuführen. Diese Datensätze können über digitale Daten hinausgehen und sowohl Online- als auch Offline-Touchpoints einschließen. Die CJA-Voraussetzungen werden nachfolgend ausführlicher behandelt.

## Wichtigste Verwendungsfälle

Customer Journey Analytics ermöglicht Ihnen Folgendes:

* **Betrachten Sie den Kunden in einem Reisekontext**: Sie können Daten sequenziell über mehrere Kanal hinweg Ansicht und analysieren. Daten aus Call Center, POS-Systemen und Online-Eigenschaften können in einer einzigen Berichte-Ansicht zusammengefasst werden.
* **Machen Sie allen** Einblicke zugänglich: Demokratisieren Sie den Datenzugriff und lassen Sie mehr Menschen Geschäftsentscheidungen mit datengestützten Erkenntnissen treffen. Jeder Mitarbeiter des Unternehmens, der für alle Aspekte der Kundenerfahrung verantwortlich ist, kann anhand vollständigerer Daten schneller echte Entscheidungen treffen.
* **Nutzen Sie die Kraft der Datenwissenschaft für Ihre Analysten**: Customer Journey Analytics ermöglicht es normalen Menschen, mithilfe von Datenwissenschaften tiefe Einblicke und Analyse zu gewinnen.
* **Visualisieren und interagieren Sie mit Ihren Datensets mithilfe von Ad-hoc-Berichten**: Workspace kann jeden Datensatz aus Adobe Experience Platform verwenden, der einigen grundlegenden Regeln entspricht.
* **Nicht-Webdaten** der Ansicht: Workspace ist nicht mehr auf eine starre Definition von &quot;Treffer&quot;oder &quot;Ereignis&quot;beschränkt. Benutzerdefinierte Schema ermöglichen die vollständige Kontrolle über Daten und Definitionen.
* **Verbessern Sie die Kontrolle über Ihre Datenbearbeitung**: Ändern Sie die hochgeladenen Daten, erstellen Sie neue Datensätze und importieren Sie sie in Workspace. Adobe Experience Platform bietet Werkzeuge zum Abfragen, Extrahieren, Transformieren und Laden über den Experience Cloud Abfrage Service.

## Voraussetzungen

Bevor Sie Beginn mit Customer Journey Analytics ausführen können, müssen die folgenden Voraussetzungen erfüllt sein:

* Ihr Unternehmen hat einen aktiven Vertrag mit Adobe Analytics für Select, Prime oder Ultimate mit dem Customer Journey Analytics-Add-on. Wenden Sie sich an den Kundenbetreuer Ihres Unternehmens, wenn Sie sich nicht sicher sind, welche Art von Vertrag Sie haben oder ob Sie das CJA-Add-on installiert haben.
* Ihr Unternehmen wurde für Adobe Experience Platform bereitgestellt.

## Benutzerzugriffsberechtigungen

Zum Erstellen von Verbindungen, zum Hinzufügen von Datensätzen usw. benötigen Sie die folgenden Berechtigungen in der [Admin-Konsole](https://adminconsole.adobe.com/enterprise/):

* Zur Verwaltung von Datensätzen in der Experience Platform müssen Sie Teil eines Platform Product-Profils sein, das Ihnen die Berechtigung &quot;Datasets verwalten&quot;erteilt. Weitere Informationen finden Sie unter [Zugriffskontrolle in der Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md).
* Um eine Verbindung zu einem Platform DataSet herzustellen, müssen Sie Teil eines Platform Product Profils sein, das Ihnen die folgenden Berechtigungen erteilt:
   * Ansicht Schema
   * Ansichten-Datensätze
   * Identitäts-Namensraum verwalten
   * Ansicht-Sandboxen
* Um auf Customer Journey Analytics zugreifen oder eine Verbindung herstellen zu können, müssen Sie auch einem Customer Journey Analytics-Produktprogramm in der [Admin-Konsole](https://adminconsole.adobe.com/enterprise/)hinzugefügt werden.

### Aktualisierungen der Terminologie

Mehrere Funktionen von CJA wurden in Übereinstimmung mit Branchenstandards umbenannt. Zu den aktualisierten Namen gehören:

* Segmente werden jetzt als &quot;Filter&quot;bezeichnet.
* Virtual Report Suites werden jetzt als &quot;Ansichten&quot;bezeichnet.
* Klassifizierungen werden jetzt als &quot;Suchdatasets&quot;bezeichnet.
* Kundenattribute werden jetzt als &quot;Profil-Datensätze&quot;bezeichnet.
* Treffer-Container werden jetzt als &quot;Ereignis&quot;-Container bezeichnet.
* Besuchsbesuche Container werden jetzt als &quot;Sitzungs&quot;-Container bezeichnet.
* Besucher-Container werden jetzt als &quot;Person&quot;-Container bezeichnet.

## Weitere Funktionen, die auf Adobe Experience Platform basieren

Customer Journey Analytics ist eine Funktion unter vielen, die auf der Adobe Experience Platform basieren. Einige andere Funktionen, die auch auf der Plattform basieren, ermöglichen es Ihnen, Ihre Daten optimal zu nutzen.

Mit der Adobe Experience Platform können Sie Kundendaten und -inhalte aus allen Systemen zentralisieren und standardisieren sowie Daten- und maschinelles Lernen anwenden, um die Gestaltung und den Versand personalisierter Erlebnisse zu verbessern. Kundendaten auf der Plattform werden als Datensätze gespeichert, die aus einem Schema und Datenstapeln bestehen. Weitere Informationen zur Plattform finden Sie unter Übersicht über die [Adobe Experience Platform Architecture](https://www.adobe.io/apis/experienceplatform/home/overview.html).

Von der Dateningestion bis hin zum direkten SQL-Zugriff sind mehrere Komponenten der Experience Platform von zentraler Bedeutung für Customer Journey Analytics und stehen in Verbindung damit:

* [Abfrage-Dienst](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html): Verwenden Sie Standard-SQL, um Daten von Adobe Experience Platform abzurufen, z. B. Adobe-Lösungsdaten, Daten von Kunden-Erstanbietern oder andere Plattformdaten. Es ist ein serverloses Tool, mit dem Sie beliebige Datensätze zusammenführen und die Abfragen als neuer Datensatz erfassen können, der in Berichte, Data Science Workspace oder zur Erfassung in Profil Service verwendet werden kann. Sie können Abfrage Service verwenden, um Ökosysteme für die Analyse von Daten zu erstellen und so ein Bild von den Verbrauchern über ihre verschiedenen Interaktions-Kanal hinweg zu erstellen. Zu diesen Kanälen zählen u. a. Point-of-Sale-Systeme, Web-, Mobile-, CRM-Systeme usw.
* [Echtzeit-Kundenprofil](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [Identitätsdienst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) in der Option &quot;Entwickler&quot;: Sie können vorgefertigte Modelle für künstliche Intelligenz (AI) und maschinelles Lernen in Adobe Experience Platform verwenden, um verschiedene Punkte der Customer Journey zu beeinflussen. Indem Sie verborgene Einblicke entdecken, können Sie während der gesamten Customer Journey bessere Vorhersagen treffen, empfohlene Best-Next-Schritte empfehlen oder schwerfällige Prozesse automatisieren.
