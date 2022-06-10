---
title: Überblick über Customer Journey Analytics
description: Erfahren Sie, wie Sie mit Customer Journey Analytics Analysis Workspace mit Daten aus Experience Platform verwenden können.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 17030d5ac3b488a6c628e6de7aab8b710e5c175a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Überblick über Customer Journey Analytics

Customer Journey Analytics ist eine Analytics-Funktion, mit der Sie die Funktionen von Analysis Workspace mit Daten von Adobe Experience Platform nutzen können. Sie kann die Daten mehrerer Jahre aufschlüsseln, filtern, abfragen und visualisieren und wird mit der Fähigkeit von Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Mithilfe des **Erlebnis-Datenmodells (XDM)** können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und untersucht werden können. Mit dem **Experience-Abfragedienst** können Sie SQL-kompatible Tools und Frameworks verwenden, um alle Ihre Daten abzufragen und zu bearbeiten.

Die allgemeine Architektur von Customer Journey Analytics wird hier gezeigt:

![Architektur](assets/cja-architecture.png)

Im Folgenden finden Sie eine Videoübersicht zu Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## Vergleich von CJA mit traditionellem Adobe Analytics

Customer Journey Analytics ergänzt den Umfang von Adobe Analytics durch benutzerfreundliche kanalübergreifende Funktionen. Außerdem werden die Einschränkungen in früheren Versionen von Adobe Analytics aufgehoben. Einige wichtige Verbesserungen sind:

* **Unbegrenzte Variablen und Ereignisse**: Die Konzepte von eVars, Props und Ereignissen existieren nicht mehr. Die Daten werden in erster Linie in Dimensionen und Metriken betrachtet. Datensätze können eine unbegrenzte Anzahl an eindeutigen Dimensionen und Metriken aufweisen.
* **Unbegrenzte Anzahl eindeutiger Werte**: Bei Adobe Experience Platform ist die Anzahl eindeutiger Werte nicht beschränkt.
* **Historische Daten ändern**: Mit Adobe Experience Platform können Daten entfernt oder korrigiert werden.
* **Report Suite-übergreifende Daten**: Vorhandene Implementierungen aus mehreren Datensätzen können in Platform kombiniert werden.

Die erste Version von Customer Journey Analytics enthält viele der in Analysis Workspace enthaltenen Funktionen. Eine vollständige Liste finden Sie unter [Customer Journey Analytics-Funktionen](cja-aa.md).

## Vergleich von CJA mit Geräteübergreifenden Analysen

[Geräteübergreifende Analysen](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) lassen sich mit dem [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=de) integrieren und verwenden entweder das Kooperationsdiagramm oder das private Diagramm, um zu ermitteln, wie digitale Geräte Personen zugeordnet werden. Sie sind für Adobe Analytics Ultimate-Kunden verfügbar.

CJA lässt sich dagegen mit Adobe Experience Platform-Datensätzen integrieren und ermöglicht die kanalübergreifende Analyse in Analysis Workspace. Obwohl CJA noch nicht in die Kooperations- oder privaten Identitätsdiagramme integriert ist, können Sie „Ihre eigene ID mitbringen“, um Datensätze zusammenzuführen. Diese Datensätze können abgesehen von digitalen Daten auch sowohl Online- als auch Offline-Touchpoints enthalten. Die Voraussetzungen für CJA werden nachfolgend ausführlicher behandelt.

## Wichtige Anwendungsfälle

Customer Journey Analytics unterstützt folgende Anwendungsfälle:

* **Kunden im Journey-Kontext anzeigen**: Sie können Daten sequenziell über mehrere Kanal hinweg anzeigen und analysieren. Daten aus Ihrem Callcenter, aus PoS-Systemen und aus Online-Eigenschaften können zu einer Berichterstellungsansicht zusammengefasst werden.
* **Einblicke für jedermann zugänglich machen**: Geben Sie allen Benutzern Datenzugriff, sodass mehr Benutzer datengestützte Geschäftsentscheidungen treffen können. Jeder in der Organisation, der für einen Aspekt des Kundenerlebnisses verantwortlich ist, kann auf der Grundlage vollständigerer Daten schneller echte Entscheidungen treffen.
* **Möglichkeiten der Datenwissenschaft für Ihre Analysten nutzen**: Mit Customer Journey Analytics können normale Menschen mithilfe der Datenwissenschaft tiefe Einblicke und Analysen gewinnen.
* **Visualisieren und Interagieren mit Ihren Datensätzen mithilfe von Ad-hoc-Berichten**: Workspace kann jeden Datensatz aus Adobe Experience Platform verwenden, der einigen Grundregeln entspricht.
* **Nicht-Webdaten anzeigen**: Arbeitsbereich ist nicht mehr auf eine starre Definition eines „Treffers“ oder „Ereignisses“ beschränkt. Benutzerdefinierte Schemata ermöglichen die vollständige Kontrolle über Daten und Definitionen.
* **Mehr Kontrolle über die Datenmanipulationen**: Ändern Sie hochgeladene Daten, erstellen Sie neue Datensätze und importieren Sie sie in Arbeitsbereich. Adobe Experience Platform bietet Tools zum Abfragen, Extrahieren, Transformieren und Laden über den Experience Cloud-Abfragedienst.

## Voraussetzungen

Bevor Sie Customer Journey Analytics verwenden können, müssen die folgenden Voraussetzungen erfüllt sein:

* Ihr Unternehmen hat einen aktiven Vertrag mit Adobe Analytics für Select, Prime oder Ultimate mit dem Add-on Customer Journey Analytics. Wenn Sie sich nicht sicher sind, welche Art von Vertrag Sie haben oder ob Sie über das Add-on CJA verfügen, wenden Sie sich an den Account Manager Ihres Unternehmens.
* Ihr Unternehmen wurde für Adobe Experience Platform bereitgestellt.

## Administratorzugriffsberechtigungen

Zum Erstellen von Verbindungen, Hinzufügen von Datensätzen usw. benötigen Sie die folgenden Berechtigungen in der [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Um auf Customer Journey Analytics zugreifen oder eine Verbindung herstellen zu können, müssen Sie als Administrator dem **Customer Journey Analytics-Produkt** in [Admin Console](https://adminconsole.adobe.com/enterprise/) hinzugefügt werden. Produktadministratoren erhalten die folgenden Berechtigungen:
   * Erstellen/Aktualisieren/Löschen von Verbindungen oder Ansichten
   * Aktualisieren/Löschen von Projekten, Filtern, Berechnungsmetriken oder von durch andere Benutzer erstellten Filtern
   * Freigeben eines Workspace-Projekts für alle Benutzer
* Wenn Sie in Customer Journey Analytics Produktadministrator werden, reicht dies nicht aus, um eine Verbindung zu erstellen, zu aktualisieren oder zu löschen. Um eine Verbindung zu einem Experience Platform-Datensatz herzustellen, benötigen Sie auch Experience Platform-Berechtigungen. Insbesondere müssen Sie Teil eines **Experience Platform-Produktprofils** ein, das Ihnen die folgenden Berechtigungen gewährt:
   * Anzeigen von Schemata
   * Verwalten von Schemata
   * Anzeigen von Identitäts-Namespaces
   * Anzeigen von Datensätzen

Weitere Informationen zu Berechtigungen für Experience Platform finden Sie unter [Zugriffssteuerung in Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=de).

>[!NOTE]
>
>Einzelne Metriken oder Dimensionen in Customer Journey Analytics können nicht wie im herkömmlichen Adobe Analytics genehmigt werden. Metriken und Dimensionen können in [Datenansichten](/help/data-views/data-views.md) geändert werden. Dadurch können sich diese Werte auch in CJA ändern, was sich rückwirkend auch auf das Reporting auswirken kann.

### Benutzerzugriff

Nicht-Produkt-Administratoren (Benutzer) in Customer Journey Analytics können keine Datenansichten oder Verbindungen anzeigen, sie können aber Filter, Projekte und berechnete Metriken erstellen.

## Aktualisierungen der Terminologie

Verschiedene Funktionen von CJA wurden gegenüber dem herkömmlichen Adobe Analytics umbenannt, um sie an Branchenstandards anzupassen. Zur aktualisierten Terminologie gehören:

* Segmente werden jetzt als Filter bezeichnet.
* Virtuelle Report Suites werden jetzt als „Datenansichten“ bezeichnet.
* Klassifizierungen werden jetzt als Suchdatensätze bezeichnet.
* Kundenattribute werden jetzt als Profildatensätze bezeichnet.
* Treffer-Container werden jetzt als Ereignis-Container bezeichnet.
* Besuchs-Container werden jetzt als Sitzungs-Container bezeichnet.
* Besucher-Container werden jetzt als Personen-Container bezeichnet.

## Weitere auf Adobe Experience Platform basierende Funktionen

Customer Journey Analytics ist eine von vielen Funktionen, die auf Adobe Experience Platform basieren. Mehrere andere Funktionen, die ebenfalls auf Experience Platform basieren, ermöglichen die optimale Datennutzung.

Mit Adobe Experience Platform können Sie Kundendaten und Inhalte aus beliebigen Systemen zentral zusammenführen und standardisieren sowie mithilfe von Datenwissenschaft und maschinellem Lernen die Gestaltung und Bereitstellung personalisierter Erlebnisse verbessern. Kundendaten in Platform werden als Datensätze gespeichert, die aus einem Schema und Datenstapeln bestehen. Weitere Informationen zu Platform finden Sie unter [Übersicht über die Adobe Experience Platform-Architektur](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=de).

Von der Datenerfassung bis zum direkten SQL-Zugriff sind mehrere Komponenten von Experience Platform für Customer Journey Analytics von zentraler Bedeutung und agieren in Verbindung damit:

* [Abfragedienst](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de): Verwenden Sie Standard-SQL, um Daten von Adobe Experience Platform abzurufen, z. B. Adobe-Lösungsdaten, Erstanbieter-Kundendaten oder andere Platform-Daten. Es handelt sich dabei um ein Server-loses Tool, mit dem Sie beliebige Datensätze zusammenführen und die Abfrageergebnisse als neuen Datensatz erfassen können. Dieser kann in Berichten, Data Science Workspace oder zur Aufnahme in den Profil-Service verwendet werden. Mit dem Abfragedienst können Sie Ökosysteme für die Datenanalyse erstellen und sich ein Bild über die Verbraucher über ihre verschiedenen Interaktionskanäle hinweg machen. Zu diesen Kanälen umfassen beispielsweise POS-Systeme, Web-, mobile und CRM-Systeme usw.
* [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de):
* [Identity-Dienst](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html):
* [Data Science Workspace](https://experienceleague.adobe.com/docs/experience-platform/data-science-workspace/home.html?lang=de) in Entwicklermodus: Sie können vorgefertigte Modelle für künstliche Intelligenz (KI) und maschinelles Lernen in Adobe Experience Platform verwenden, um verschiedene Aspekte der Customer Journey zu beeinflussen. Durch das Aufspüren verborgener Erkenntnisse können Sie bessere Vorhersagen für die gesamte Customer Journey treffen, Empfehlungen für die besten nächsten Schritte geben oder umständliche Prozesse automatisieren.

## Videos

* Arbeiten mit Daten in Customer Journey Analytics:

   >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Architektur und Integrationen von Customer Journey Analytics:

   >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

