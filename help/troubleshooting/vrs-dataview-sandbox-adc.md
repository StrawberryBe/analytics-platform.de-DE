---
source-git-commit: f2f85db4b670f1c4b1f6bc0954a5549c793edf5a
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 87%

---
# Virtual Report Suites, Datenansichten, Adobe Experience Platform-Sandboxes und der Analytics-Quell-Connector

Adobe bietet eine Vielzahl von Möglichkeiten zum Erstellen virtueller Reporting-Umgebungen und Sandbox-Umgebungen. Es ist nützlich, die Ähnlichkeiten und Unterschiede zwischen den folgenden Funktionen und ihren Beziehungen zum [Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) zu überblicken:

* Virtual Report Suites in Adobe Analytics
* Customer Journey Analytics-Datenansichten
* Adobe Experience Platform-Sandboxes

## Adobe Analytics Virtual Report Suites

Weitere Informationen finden Sie unter [Virtual Report Suites – Übersicht](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=de).

Virtual Report Suite:

* Kann auf Adobe Analytics-Segmenten basieren.
* Kann auf zerstörungsfreie Weise auf historische und neue Daten angewendet werden.
* Ermöglicht die Erstellung einer oder mehrerer virtueller Ansichten auf Basis einer Adobe Analytics-Report Suite zur Verwendung durch verschiedene Unternehmens-Teams.
* Kann verwendet werden, um den Zugriff auf verschiedene Arten von Daten für verschiedene Benutzer in Adobe Analytics zu steuern und diese Daten zu kuratieren.
* Bietet optional Funktionen für die [Berichtszeitverarbeitung](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=de) für Adobe Analytics. In diesem Fall kann eine Virtual Report Suite verwendet werden, um eine benutzerdefinierte Definition für &quot;Besuch&quot;zu erstellen.
* Wird zur Berichtslaufzeit angewendet, ähnlich wie die Segmentauswertung. Dies geschieht, _nachdem_ die Daten in Adobe Analytics erfasst und gespeichert wurden.
* Ist für [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=de) in Adobe Analytics erforderlich.
* Hat dieselbe Anzahl von Variablen für die Verwendung als Standard-Analytics Report Suite (250 eVars, 250 Props, 1000 Ereignisse) zur Verfügung, obwohl die Kuratierung der Virtual Report Suite die Benutzerexponierung begrenzen kann.
* Unterstützt benutzerdefinierte Kalenderoptionen.

Was eine Virtual Report Suite nicht ist/kann:

* Eine Möglichkeit bieten, Report Suites miteinander zu kombinieren.
* Sie ist nicht in Adobe Analytics Data Warehouse verfügbar.
* Sie ist nicht als Quelle für Datenflüsse in Adobe Experience Platform über den Analytics-Quell-Connector verfügbar. Nur vollständige (nicht virtuelle) Report Suites sind für die Verwendung mit dem Analytics-Quell-Connector verfügbar.


## Customer Journey Analytics-Datenansichten

Weitere Informationen finden Sie unter [Datenansichten – Übersicht](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de).

Eine Datenansicht:

* Kann auf Customer Journey Analytics-Filtern basieren.
* Kann auf zerstörungsfreie Weise auf historische und neue Daten angewendet werden.
* Ermöglicht die Erstellung einer oder mehrerer virtueller Ansichten über eine Customer Journey Analytics-Verbindung, die von verschiedenen Geschäftsteams verwendet werden können.
* Kann verwendet werden, um den Zugriff auf verschiedene Arten von Daten für verschiedene Benutzende in Customer Journey Analytics zu steuern und diese Daten zu kuratieren.
* Bietet leistungsstarke, zerstörungsfreie Optionen zum Transformieren und Verbessern von Daten, die über eine Customer Journey Analytics-Verbindung in Customer Journey Analytics eingehen.
* Basiert auf den Customer Journey Analytics-Funktionen für die Verarbeitung zum Zeitpunkt der Berichtserstellung.
* Ermöglicht Benutzern das Erstellen einer benutzerdefinierten Definition für „Sitzung“.
* Wird zur Berichtslaufzeit angewendet, ähnlich wie bei der Filterauswertung. Dies geschieht, _nachdem_ der Quell-Connector (z. B. Adobe Analytics) Daten in einen Datensatz im Adobe Experience Platform Data Lake geschrieben hat und _nachdem_ die Daten über eine Customer Journey Analytics-Verbindung in Customer Journey Analytics aufgenommen wurden.
* Ermöglicht eine unbegrenzte Anzahl von Variablen, allerdings kann die Kuratierung einschränken, welche Variablen für Benutzer verfügbar sind.
* Ermöglicht die benutzerdefinierte Benennung von Containern für Ereignisse, Sitzungen und Personen.
* Unterstützt benutzerdefinierte Kalenderoptionen.

Einschränkungen einer Datenansicht:

* Sie stellt direkt keine Möglichkeit bereit, Report Suites oder andere Datensätze zu kombinieren. Stattdessen werden Datensätze in einer Customer Journey Analytics-Verbindung kombiniert. Die kombinierten Daten aus der Customer Journey Analytics-Verbindung können in allen Datenansichten verwendet werden, die auf dieser Verbindung basieren.

## Adobe Experience Platform-Sandboxes

Weitere Informationen finden Sie unter [Sandboxes – Übersicht](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=de).

Eine Adobe Experience Platform-Sandbox:

* Bietet eine Möglichkeit, eine einzelne Adobe Experience Platform-Instanz in getrennte virtuelle Umgebungen (Entwicklung, Test, Staging, Produktion usw.) zu unterteilen, um die Entwicklung und Weiterentwicklung von Programmen für digitale Erlebnisse zu unterstützen.
* Kann als Container betrachtet werden, der alle Daten und Programme für eine bestimmte Umgebung enthält.

Einschränkungen einer Adobe Experience Platform-Sandbox:

* Sie bietet keine vergleichbaren Funktionen wie Virtual Report Suites, Customer Journey Analytics-Verbindungen oder -Datenansichten.
* Report Suites können damit nicht mit oder ohne andere Datensätze kombiniert werden. Die Datensätze innerhalb einer Sandbox können jedoch innerhalb einer Customer Journey Analytics-Verbindung kombiniert werden.

Weiter:

* Daten aus verschiedenen Sandboxes können nicht in Customer Journey Analytics kombiniert werden.
* Der Analytics-Quell-Connector sendet Report Suite-Daten _in_ eine bestimmte Sandbox. Jede Report Suite kann als Quelle für eine einzelne Sandbox konfiguriert werden. Weitere Details finden Sie in der [Dokumentation zum Analytics-Quell-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de).
