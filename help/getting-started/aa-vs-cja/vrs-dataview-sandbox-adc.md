---
title: Virtual Report Suites, Datenansichten, AEP-Sandboxes und der Analytics Source Connector
description: Erfahren Sie mehr über virtuelle Reporting-Umgebungen und Sandbox-Umgebungen.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
source-git-commit: 6603aed778980c37d69843f11f3ee64e64cd13b5
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 8%

---

# Virtual Report Suites, Datenansichten, AEP-Sandboxes und der Analytics Source Connector

Adobe bietet eine Vielzahl von Möglichkeiten zum Erstellen virtueller Reporting-Umgebungen und Sandbox-Umgebungen. Es ist nützlich, die Ähnlichkeiten und Unterschiede zwischen den folgenden Funktionen zu verstehen und zu verstehen, wie diese Funktionen mit dem [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de):

* Virtual Report Suites von Adobe Analytics
* CJA-Datenansichten
* AEP-Sandboxes

## Adobe Analytics Virtual Report Suites (VRS)

Weitere Informationen finden Sie unter: [Virtual Report Suites - Übersicht](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=de).

Eine Virtual Report Suite:

* Kann auf Adobe Analytics-Segmenten basieren.
* Können auf historische und neue Daten auf zerstörungsfreie Weise angewendet werden.
* Ermöglicht die Erstellung einer oder mehrerer virtueller Ansichten über eine Adobe Analytics Report Suite zur Verwendung durch verschiedene Geschäftsteams.
* Kann verwendet werden, um den Zugriff auf verschiedene Arten von Daten für verschiedene Benutzer in Adobe Analytics zu steuern und diese zu kuratieren.
* Bietet optional [Berichtszeitverarbeitung](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) Funktionen für Adobe Analytics. In diesem Fall kann eine VRS verwendet werden, um eine benutzerdefinierte Definition für &quot;Besuch&quot;zu erstellen.
* wird zur Berichtslaufzeit angewendet, ähnlich wie bei der Segmentauswertung. Dies ist _after_ die Daten in Adobe Analytics erfasst und gespeichert wurden.
* Ist erforderlich für [Geräteübergreifende Analyse](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) in Adobe Analytics.
* Hat dieselbe Anzahl von Variablen für die Verwendung als Standard-Analytics Report Suite (250 eVars, 250 Props, 1000 Ereignisse) zur Verfügung, obwohl die VRS-Kuratierung die Benutzerexponierung begrenzen kann.
* Unterstützt benutzerdefinierte Kalenderoptionen.

Eine Virtual Report Suite ist nicht:

* Ein Mittel zur Kombination von Report Suites.
* Verfügbar in der Adobe Analytics-Data Warehouse.
* Verfügbar als Quelle für Datenflüsse in AEP über den Analytics Source Connector. Nur vollständige (nicht virtuelle) Report Suites sind für die Verwendung mit dem Analytics Source Connector verfügbar.


## CJA-Datenansichten

Weitere Informationen finden Sie unter: [Datenansichten - Übersicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de).

Datenansicht:

* Kann auf CJA-Filtern basieren.
* Können auf historische und neue Daten auf zerstörungsfreie Weise angewendet werden.
* Ermöglicht die Erstellung einer oder mehrerer virtueller Ansichten über eine CJA-Verbindung, die von verschiedenen Geschäftsteams verwendet werden können.
* Kann verwendet werden, um den Zugriff auf verschiedene Arten von Daten für verschiedene Benutzer in CJA zu steuern und diese zu kuratieren.
* Bietet leistungsstarke, zerstörungsfreie Optionen zum Transformieren und Verbessern von Daten, die über eine CJA-Verbindung in CJA eingehen.
* basiert auf den Berichtszeitverarbeitungsfunktionen von CJA.
* Ermöglicht Benutzern das Erstellen einer benutzerdefinierten Definition für &quot;Sitzung&quot;.
* wird zur Berichtslaufzeit angewendet, ähnlich wie bei einer Filterauswertung. Dies ist _after_ der Quell-Connector (Adobe Analytics oder andere) Daten in einen Datensatz im AEP-Data Lake geschrieben hat und _after_ die Daten wurden über eine CJA-Verbindung in CJA erfasst.
* Ermöglicht eine unbegrenzte Anzahl von Variablen, obwohl die Kuratierung einschränken kann, welche Variablen Benutzern angezeigt werden
* Ermöglicht die benutzerdefinierte Benennung von Ereignis-, Sitzungs- und Personen-Containern.
* Unterstützt benutzerdefinierte Kalenderoptionen.

Eine Datenansicht ist nicht:

* Stellen Sie direkt eine Möglichkeit bereit, Report Suites oder andere Datensätze zu kombinieren. Stattdessen werden Datensätze mit in einer CJA-Verbindung kombiniert. Die kombinierten Daten aus der CJA-Verbindung stehen in allen Datenansichten zur Verfügung, die auf dieser Verbindung basieren.

## AEP-Sandboxes

Weitere Informationen finden Sie unter: [Sandbox-Übersicht](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=de).

Eine AEP-Sandbox:

* Bietet eine Möglichkeit, eine einzelne AEP-Instanz in separate virtuelle Umgebungen (Entwicklung, Test, Staging, Produktion usw.) zu unterteilen. Unterstützung bei der Entwicklung und Weiterentwicklung von Programmen für digitale Erlebnisse.
* Kann als Container betrachtet werden, der alle Daten und Anwendungen für eine bestimmte Umgebung enthält.

Eine AEP-Sandbox:

* Stellen Sie ähnliche Funktionen wie Virtual Report Suites, CJA-Verbindungen oder Datenansichten bereit.
* Report Suites selbst können mit oder ohne andere Datensätze kombiniert werden. Die Datensätze innerhalb einer Sandbox können jedoch innerhalb einer CJA-Verbindung kombiniert werden.

Beachten Sie, dass:

* Daten aus verschiedenen Sandboxes können nicht in CJA kombiniert werden.
* Der Analytics Source Connector sendet Report Suite-Daten _in_ eine bestimmte Sandbox. Jede Report Suite kann als Quelle für eine Sandbox konfiguriert werden. Siehe [Analytics Source Connector-Dokumentation](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) für weitere Details.
