---
title: Virtual Report Suites, Datenansichten, AEP-Sandboxes und der Analytics-Quell-Connector
description: Erfahren Sie mehr über virtuelle Reporting-Umgebungen und Sandbox-Umgebungen.
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
source-git-commit: 6603aed778980c37d69843f11f3ee64e64cd13b5
workflow-type: ht
source-wordcount: '720'
ht-degree: 100%

---

# Virtual Report Suites, Datenansichten, AEP-Sandboxes und der Analytics-Quell-Connector

Adobe bietet eine Vielzahl von Möglichkeiten zum Erstellen virtueller Reporting-Umgebungen und Sandbox-Umgebungen. Es ist nützlich, die Ähnlichkeiten und Unterschiede zwischen den folgenden Funktionen und deren Beziehung zum [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) zu verstehen:

* Virtual Report Suites in Adobe Analytics
* CJA-Datenansichten
* AEP-Sandboxes

## Virtual Report Suites (VRS) in Adobe Analytics

Weitere Informationen finden Sie unter [Virtual Report Suites – Übersicht](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=de).

Eine Virtual Report Suite:

* Kann auf Adobe Analytics-Segmenten basieren.
* Kann auf zerstörungsfreie Weise auf historische und neue Daten angewendet werden.
* Ermöglicht die Erstellung einer oder mehrerer virtueller Ansichten auf Basis einer Adobe Analytics-Report Suite zur Verwendung durch verschiedene Unternehmens-Teams.
* Kann verwendet werden, um den Zugriff auf verschiedene Arten von Daten für verschiedene Benutzer in Adobe Analytics zu steuern und diese Daten zu kuratieren.
* Bietet optional Funktionen für die [Berichtszeitverarbeitung](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=de) für Adobe Analytics. In diesem Fall kann eine VRS verwendet werden, um eine benutzerdefinierte Definition für „Besuch“ zu erstellen.
* Wird zur Berichtslaufzeit angewendet, ähnlich wie die Segmentauswertung. Dies geschieht, _nachdem_ die Daten in Adobe Analytics erfasst und gespeichert wurden.
* Ist für [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) in Adobe Analytics erforderlich.
* Weist dieselbe Anzahl von Variablen für die Verwendung auf wie eine standardmäßige Analytics-Report Suite (250 eVars, 250 Eigenschaften, 1.000 Ereignisse), allerdings kann die VRS-Kuratierung begrenzen, welche Variablen für Benutzende verfügbar sind.
* Unterstützt benutzerdefinierte Kalenderoptionen.

Einschränkungen einer Virtual Report Suite:

* Sie ist kein Mittel zur Kombination von Report Suites.
* Sie ist nicht in Adobe Analytics Data Warehouse verfügbar.
* Sie ist nicht als Quelle für Datenflüsse in AEP über den Analytics-Quell-Connector verfügbar. Nur vollständige (nicht virtuelle) Report Suites sind für die Verwendung mit dem Analytics-Quell-Connector verfügbar.


## CJA-Datenansichten

Weitere Informationen finden Sie unter [Datenansichten – Übersicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de).

Eine Datenansicht:

* Kann auf CJA-Filtern basieren.
* Kann auf zerstörungsfreie Weise auf historische und neue Daten angewendet werden.
* Ermöglicht die Erstellung einer oder mehrerer virtueller Ansichten auf Basis einer CJA-Verbindung, die von verschiedenen Unternehmens-Teams verwendet werden können.
* Kann verwendet werden, um den Zugriff auf verschiedene Arten von Daten für verschiedene Benutzer in CJA zu steuern und diese Daten zu kuratieren.
* Bietet leistungsstarke, zerstörungsfreie Optionen zum Transformieren und Verbessern von Daten, die über eine CJA-Verbindung in CJA eingehen.
* Basiert auf den Funktionen für die Berichtszeitverarbeitung von CJA.
* Ermöglicht Benutzern das Erstellen einer benutzerdefinierten Definition für „Sitzung“.
* Wird zur Berichtslaufzeit angewendet, ähnlich wie eine Filterauswertung. Dies geschieht, _nachdem_ der Quell-Connector (Adobe Analytics oder ein anderer) Daten in einen Datensatz im AEP-Data Lake geschrieben hat und _nachdem_ die Daten über eine CJA-Verbindung in CJA erfasst wurden.
* Ermöglicht eine unbegrenzte Anzahl von Variablen, allerdings kann die Kuratierung einschränken, welche Variablen für Benutzer verfügbar sind.
* Ermöglicht die benutzerdefinierte Benennung von Containern für Ereignisse, Sitzungen und Personen.
* Unterstützt benutzerdefinierte Kalenderoptionen.

Einschränkungen einer Datenansicht:

* Sie stellt direkt keine Möglichkeit bereit, Report Suites oder andere Datensätze zu kombinieren. Stattdessen werden Datensätze in einer CJA-Verbindung kombiniert. Die kombinierten Daten aus der CJA-Verbindung können in allen Datenansichten verwendet werden, die auf dieser Verbindung basieren.

## AEP-Sandboxes

Weitere Informationen finden Sie unter [Sandboxes – Übersicht](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=de).

Eine AEP-Sandbox:

* Bietet eine Möglichkeit, eine einzelne AEP-Instanz in getrennte virtuelle Umgebungen (Entwicklung, Test, Staging, Produktion usw.) zu unterteilen, um die Entwicklung und Weiterentwicklung von Programmen für digitale Erlebnisse zu unterstützen.
* Kann als Container betrachtet werden, der alle Daten und Programme für eine bestimmte Umgebung enthält.

Einschränkungen einer AEP-Sandbox:

* Bietet keine vergleichbaren Funktionen wie Virtual Report Suites, CJA-Verbindungen oder Datenansichten.
* Report Suites können damit nicht mit oder ohne andere Datensätze kombiniert werden. Die Datensätze innerhalb einer Sandbox können jedoch innerhalb einer CJA-Verbindung kombiniert werden.

Beachten Sie Folgendes:

* Daten aus verschiedenen Sandboxes können nicht in CJA kombiniert werden.
* Der Analytics-Quell-Connector sendet Report Suite-Daten _in_ eine bestimmte Sandbox. Jede Report Suite kann als Quelle für eine einzelne Sandbox konfiguriert werden. Weitere Details finden Sie in der [Dokumentation zum Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de).
