---
title: Unterstützung der Customer Journey Analytics-Funktion
description: Funktionen von Customer Journey Analytics im Vergleich zu Adobe Analytics-Funktionen.
translation-type: tm+mt
source-git-commit: 1d65b22ab2323bebf42b2782b2bab2ed52869a02

---


# Unterstützung der Customer Journey Analytics-Funktion

In den folgenden Tabellen sind die Funktionen von Adobe Analytics aufgeführt, die in Customer Journey Analytics (CJA) unterstützt, teilweise unterstützt oder nicht unterstützt werden. Diese Listen ändern sich mit der Zeit, da CJA Funktionen hinzugefügt werden.

## Vollständig unterstützte Funktionen/Komponenten

| Funktion | Hinweise |
| --- | --- |
| Metriken | CJA nutzt das Experience Data Model (XDM) und unterstützt unbegrenzte Metriken und ist nicht mit den benutzerspezifischen Erfolgsereignissen herkömmlicher Analytics verknüpft. Beachten Sie, dass einige Standardmetriken aus herkömmlicher Analytics umbenannt wurden: Besucher = Personen, Besuche = Sitzungen, Treffer = Ereignisse. |
| Dimensionen | CJA nutzt XDM und unterstützt unbegrenzte Dimensionen und ist nicht an die benutzerspezifischen Erfolgsereignisse herkömmlicher Analytics gebunden. |
| Listenvariablen/Listeneigenschaftsvariablen | CJA nutzt XDM und unterstützt unbegrenzte Listenvariablen |
| Datumsbereiche | Unterstützung für benutzerspezifische Kalender ist geplant. |
| Berechnete Metriken | Beachten Sie, dass vorhandene Berechnungsmetriken im herkömmlichen Arbeitsbereich für Analysen nicht in CJA portiert werden. |
| Segmente | &quot;Filter&quot;(Filter) - Beachten Sie, dass vorhandene Segmente im herkömmlichen Arbeitsbereich für Analysen nicht in CJA portiert werden. |
| Attribution IQ | Vollständige Unterstützung |
| Projektkuratierung | Vollständige Unterstützung |
| Projektverknüpfung | Vollständige Unterstützung |
| Datumsvergleiche | Vollständige Unterstützung |
| Virtual Report Suites | Jetzt [Datenansichten](/help/data-views/create-dataview.md)genannt. |
| VRS-Komponentenkuratierung | Jetzt Teil der Datenansichten. |
| Report Time Processing | CJA basiert ausschließlich auf der Verarbeitung der Berichtszeit. |
| GDPR-Löschung | Beachten Sie, dass GDPR jetzt in Abstimmung mit Adobe Experience Platform - CJA verarbeitet wird, unabhängig davon, welche Daten von Experience Platform an zugrunde liegenden Datensätzen geändert werden. |

## Mit Einschränkungen unterstützt

| Funktion | Hinweise |
| --- | --- |
| Produktvariable | Die Produktvariable, die derzeit für die Berichterstellung für Daten verfügbar ist, die dem Experience Event-Schema entsprechen (insbesondere mit dem productListItems-Objekt). |
| Visualisierungen | Mit Ausnahme der Imagemap-Visualisierung werden alle Visualisierungen unterstützt. |
| AAM-Zielgruppen | Wenn Kunden Analytics Data Connector-Datensätze verwenden, sind diese Daten Teil der ADC-Daten. |
| Projektfreigabe | Die Projektfreigabe wird nur von CJA-Benutzern unterstützt - es gibt keine Projektfreigabe zwischen CJA und dem herkömmlichen Analysis Workspace. |
| Benutzerdefinierte Sitzung | Unterstützung für alle benutzerdefinierten Sitzungsfunktionen außer mobilen Hintergrundschlägen. |
| eVar-Persistenzeinstellungen | eVars sind nicht mehr Teil von CJA. Persistenzeinstellungen sind jetzt jedoch Teil der Datenansichten und für alle Dimensionen verfügbar. Denken Sie daran, dass die Persistenz auf der Verarbeitung der Berichtszeit und nicht auf der Verarbeitung der Datenerfassung basiert. Dies bedeutet, dass die gesamte Persistenz auf dem Berichtsdatumsbereich und nicht auf der Gesamtheit der Daten basiert. |
| Classifications | Diese so genannten &quot;Lookup-Datensätze&quot;werden nicht automatisch aus herkömmlichen Analytics importiert. Sie müssen in AEP hochgeladen werden, bevor sie in CJA verfügbar sind. |
| Kundenattribute | Jetzt als &quot;Profildatenasets&quot;bezeichnet, werden sie nicht automatisch aus Experience Cloud importiert, sondern müssen in AEP hochgeladen werden, bevor sie in CJA verfügbar sind. |

## Teilweise Unterstützung

| Funktion | Hinweise |
| --- | --- |
| Vordefinierte Dimensionen des Arbeitsbereichs für Analysen (z. B. Browsertyp, Typ der verweisenden Stelle, Marketingkanäle, Besuchsnummer usw.) | CJA stellt diese Dimensionen nicht nativ bereit. Für Kunden, die Analytics Data Connector (ADC) verwenden, sind einige dieser Dimensionen verfügbar, jedoch nicht alle. Bitte lesen Sie unsere [Dokumentation darüber, welche Analytics-Variablen über ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)unterstützt werden. |
| Bedienfelder | Leeres Bedienfeld, Zuordnungs-Bedienfeld und Freiform-Bedienfeld werden vollständig unterstützt. Segmentvergleich wird nicht unterstützt. |
| Merchandising-eVars | Merchandising-eVars funktionieren nur mit ADC-basierten Datensätzen, es sei denn, sie entsprechen genau demselben XDM-Schema (ähnlich den Einschränkungen der Produktliste oben). |
| Bot-Filterung | Bei Analytics Data Connector (ADC)-basierten Datensätzen wird Bot-Filterung angewendet. Allgemeine Bot-Filterlogik für andere Datensätze wird nicht von der Experience Platform oder CJA ausgeführt. |
| Verarbeitungsregeln | Bei ADC-basierten Datensätzen werden weiterhin Verarbeitungsregeln angewendet. |
| Geräteübergreifende Identitätsfestsetzung | Kunden sind über den Abfragedienst auf &quot;einmalige&quot;Zusammenstellungen der Daten beschränkt oder müssen diese Logik derzeit vor der Datenerfassung mit Experience Platform auf Daten anwenden. |

## Derzeit nicht unterstützt, aber geplant

| Funktion | Hinweise |
| --- | --- |
| Anomalieerkennung | Unterstützung ist geplant. |
| Beitragsanalyse | Unterstützung ist geplant. |
| Segment IQ | Unterstützung ist geplant. |
| Segmentveröffentlichung (Senden von Segmenten aus Workspace an die Experience Cloud) | Unterstützung ist geplant. |
| Benutzerberechtigungen/Steuerelemente für den Datenzugriff | Alle Benutzer in CJA haben die gleichen Zugriffssteuerungen - das bedeutet, dass alle Benutzer Zugriff auf alle Verbindungen, Datenansichten usw. haben. Grundsätzlich sind alle Benutzer Benutzer Benutzer auf Administratorebene in CJA. Die Unterstützung ist für 2020 geplant. |
| CSV-Download | Unterstützung ist geplant. |
| Geplante Berichte/Projekte | Unterstützung ist geplant. |
| Warnhinweise | Unterstützung ist geplant. |
| Benutzerdefinierte Kalender | Unterstützung ist geplant. |
| Marketing-Kanäle | Unterstützung ist geplant. |
| PDF Export | Unterstützung ist geplant. |
| Zugriff auf die Berichterstellungs-API | Support ist geplant - nur mit API 2.0 verfügbar. |
| ID-Stiftung über Gerätediagramm | Unterstützung ist geplant. |

## Unterstützung noch nicht geplant

| Funktion | Hinweise |
| --- | --- |
| A4T | Die Unterstützung ist noch nicht geplant. |
| Video-Analytics | Die Unterstützung ist noch nicht geplant. |
| Advertising Cloud | Die Unterstützung ist noch nicht geplant. |
| ReportBuilder (Excel-Plugin) | Die Unterstützung ist noch nicht geplant. |
| Activity Map | Die Unterstützung ist noch nicht geplant. |
| Classification Rule Builder | Die Unterstützung ist noch nicht geplant. |
| Zusammenfassende Datenquellen | Die Unterstützung ist noch nicht geplant. |
| Echtzeit-Reporting | Die Unterstützung ist noch nicht geplant. |

## Wird nie unterstützt

| Funktion | Hinweise |
| --- | --- |
| Metrik für Personen mit geräteübergreifender Coop |  |
| Reports &amp; Analysen-Dashboards |  |
| Reports &amp; Analysen-Lesezeichen |  |
| Reports &amp; Analysen-Ziele |  |
| Reports &amp; Analysen Kalenderereignisse |  |
| Ad Hoc Analysis |  |
| Data Warehouse Berichterstellung | Adobe Experience Platform Query Service ist die neue Schnittstelle für diese Anwendungsfälle in CJA. |
| Mobile Services |  |
| Daten-Feeds |  |
