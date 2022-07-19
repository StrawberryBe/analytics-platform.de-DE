---
title: Überblick über Customer Journey Analytics
description: Erfahren Sie, wie Sie mit Customer Journey Analytics Analysis Workspace mit Daten aus Experience Platform verwenden können.
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: f7b4dcb893586e71302cc6a20ebe931743ea8924
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 86%

---

# Überblick über Customer Journey Analytics

Customer Journey Analytics ist eine Analytics-Funktion, mit der Sie die Funktionen von Analysis Workspace mit Daten von Adobe Experience Platform nutzen können. Sie kann die Daten mehrerer Jahre aufschlüsseln, filtern, abfragen und visualisieren und wird mit der Fähigkeit von Platform kombiniert, alle Arten von Datenschemata und -typen zu speichern. Mithilfe des **Erlebnis-Datenmodells (XDM)** können Daten einheitlich dargestellt und organisiert werden, sodass sie kombiniert und untersucht werden können. Mit dem **Experience-Abfragedienst** können Sie SQL-kompatible Tools und Frameworks verwenden, um alle Ihre Daten abzufragen und zu bearbeiten.

Die allgemeine Architektur von Customer Journey Analytics wird hier gezeigt:

![Architektur](assets/cja-architecture.png)

Im Folgenden finden Sie eine Videoübersicht zu Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30090/?quality=12)

## Vergleich von CJA mit traditionellem Adobe Analytics

Customer Journey Analytics erweitert den Umfang von Adobe Analytics, indem es einfache, kanalübergreifende Funktionen anbietet und Einschränkungen in früheren Versionen von Adobe Analytics beseitigt. Einige wichtige Verbesserungen sind:

* **Unbegrenzte Variablen und Ereignisse**: Die Konzepte von eVars, Props und Ereignissen existieren nicht mehr. Die Daten werden in erster Linie in Dimensionen und Metriken betrachtet. Datensätze können eine unbegrenzte Anzahl eindeutiger Dimensionen und Metriken aufweisen.
* **Unbegrenzte Anzahl eindeutiger Werte**: Bei Adobe Experience Platform ist die Anzahl eindeutiger Werte nicht beschränkt.
* **Historische Daten ändern**: Mit Adobe Experience Platform können Daten entfernt oder korrigiert werden.
* **Report Suite-übergreifende Daten**: Vorhandene Implementierungen aus mehreren Datensätzen können in Platform kombiniert werden.

Die erste Version von Customer Journey Analytics enthält viele der in Analysis Workspace enthaltenen Funktionen. Eine vollständige Liste finden Sie unter [Customer Journey Analytics-Funktionen](/help/getting-started/aa-vs-cja/cja-aa.md).

## Wichtige Anwendungsfälle

Customer Journey Analytics unterstützt folgende Anwendungsfälle:

* **Kunden im Journey-Kontext anzeigen**: Sie können Daten sequenziell über mehrere Kanal hinweg anzeigen und analysieren. Daten aus Ihrem Callcenter, aus PoS-Systemen und aus Online-Eigenschaften können zu einer Berichterstellungsansicht zusammengefasst werden.
* **Einblicke für jedermann zugänglich machen**: Geben Sie allen Benutzern Datenzugriff, sodass mehr Benutzer datengestützte Geschäftsentscheidungen treffen können. Jeder in der Organisation, der für einen Aspekt des Kundenerlebnisses verantwortlich ist, kann auf der Grundlage vollständigerer Daten schneller echte Entscheidungen treffen.
* **Möglichkeiten der Datenwissenschaft für Ihre Analysten nutzen**: Mit Customer Journey Analytics können normale Menschen mithilfe der Datenwissenschaft tiefe Einblicke und Analysen gewinnen.
* **Visualisieren und Interagieren mit Ihren Datensätzen mithilfe von On-Demand-Berichten**: Workspace kann jeden Datensatz aus Adobe Experience Platform verwenden, der einigen Grundregeln entspricht.
* **Nicht-Webdaten anzeigen**: Arbeitsbereich ist nicht mehr auf eine starre Definition eines „Treffers“ oder „Ereignisses“ beschränkt. Benutzerdefinierte Schemata ermöglichen die vollständige Kontrolle über Daten und Definitionen.
* **Mehr Kontrolle über Ihre Datenmanipulationen**: Ändern Sie die hochgeladenen Daten, erstellen Sie Datensätze und importieren Sie sie in Workspace. Adobe Experience Platform bietet Tools zum Abfragen, Extrahieren, Transformieren und Laden über den Experience Cloud-Abfragedienst.

## Voraussetzungen

Bevor Sie Customer Journey Analytics verwenden können, müssen die folgenden Voraussetzungen erfüllt sein:

* Ihr Unternehmen hat einen aktiven Vertrag mit Adobe Analytics für Select, Prime oder Ultimate mit dem Add-on Customer Journey Analytics. Wenn Sie sich nicht sicher sind, welche Art von Vertrag Sie haben oder ob Sie über das Add-on CJA verfügen, wenden Sie sich an den Account Manager Ihres Unternehmens.
* Ihr Unternehmen wurde für Adobe Experience Platform bereitgestellt.

## Zugangssteuerung

Siehe Abschnitt [Zugriffssteuerung](/help/getting-started/cja-access-control.md) Thema.

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

Von der Datenerfassung bis zum direkten SQL-Zugriff sind mehrere Komponenten der Experience Platform von zentraler Bedeutung für den Customer Journey Analytics und ergänzen sie:

* [Abfragedienst](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de): Verwenden Sie Standard-SQL, um Daten von Adobe Experience Platform abzurufen, z. B. Adobe-Lösungsdaten, Erstanbieter-Kundendaten oder andere Platform-Daten. Es handelt sich dabei um ein Server-loses Tool, mit dem Sie beliebige Datensätze zusammenführen und die Abfrageergebnisse als neuen Datensatz erfassen können. Dieser kann in Berichten, Data Science Workspace oder zur Aufnahme in den Profil-Service verwendet werden. Mit dem Abfragedienst können Sie Ökosysteme für die Datenanalyse erstellen und sich ein Bild über die Verbraucher über ihre verschiedenen Interaktionskanäle hinweg machen. Diese Kanäle können Point-of-Sale-Systeme, Web-, Mobile-, CRM-Systeme usw. umfassen.
* [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de):
* [Identity-Dienst](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=de):
* [Data Science Workspace](https://experienceleague.adobe.com/docs/experience-platform/data-science-workspace/home.html?lang=de) in Entwicklermodus: Sie können vorgefertigte Modelle für künstliche Intelligenz (KI) und maschinelles Lernen in Adobe Experience Platform verwenden, um verschiedene Aspekte der Customer Journey zu beeinflussen. Durch das Aufspüren verborgener Erkenntnisse können Sie bessere Vorhersagen für die gesamte Customer Journey treffen, Empfehlungen für die besten nächsten Schritte geben oder umständliche Prozesse automatisieren.

## Videos

* Arbeiten mit Daten in Customer Journey Analytics:

   >[!VIDEO](https://video.tv.adobe.com/v/32112/?quality=12)

* Architektur und Integrationen von Customer Journey Analytics:

   >[!VIDEO](https://video.tv.adobe.com/v/32483/?quality=12)

