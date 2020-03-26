---
title: Unterstützung der Customer Journey Analytics-Funktion
description: Funktionen von Customer Journey Analytics im Vergleich zu Adobe Analytics-Funktionen.
translation-type: tm+mt
source-git-commit: 1d65b22ab2323bebf42b2782b2bab2ed52869a02

---


# Unterstützung der Customer Journey Analytics-Funktion

Die folgende Tabelle enthält eine Liste, die Funktionen in Adobe Analytics unterstützt, teilweise unterstützt oder nicht unterstützt wird. Diese Listen ändern sich mit der Zeit, da CJA neue Funktionen hinzugefügt werden.

## Vollständig unterstützte Funktionen/Komponenten

| Funktion | Hinweise |
| --- | --- |
| Metriken | CJA nutzt das Experience Data Model (XDM) und unterstützt unbegrenzte Metriken und ist nicht an die benutzerspezifischen Erfolgsereignisse von herkömmlicher Analytics gebunden. Beachten Sie, dass einige Standardmetriken aus herkömmlicher Analytics umbenannt wurden: Besucher = Personen, Besuche = Sitzungen, Treffer = Ereignis. |
| Dimensionen | CJA nutzt XDM und unterstützt unbegrenzte Dimensionen und ist nicht an die benutzerspezifischen Erfolgsereignisse von Analytics gebunden. |
| Liste Variablen/Liste Props | CJA nutzt XDM und unterstützt unbegrenzte Listen |
| Datumsbereiche | Unterstützung für benutzerspezifische Kalender ist geplant. |
| Berechnete Metriken | Beachten Sie, dass vorhandene Berechnungsmetriken im Arbeitsbereich für herkömmliche Analysen nicht in CJA portiert werden. |
| Segmente | Jetzt als &quot;Filter&quot;bezeichnet - Beachten Sie, dass vorhandene Segmente im Arbeitsbereich für herkömmliche Analysen nicht in CJA portiert werden. |
| Attribution IQ | Vollständige Unterstützung |
| Projektkuratierung | Vollständige Unterstützung |
| Projektverknüpfung | Vollständige Unterstützung |
| Datumsvergleiche | Vollständige Unterstützung |
| Virtual Report Suites | Nun als [Data Ansichten](/help/data-views/create-dataview.md)bezeichnet. |
| VRS-Komponentenkuratierung | Jetzt Teil der Data-Ansichten. |
| Berichtszeitverarbeitung | CJA basiert ausschließlich auf der Verarbeitung der Berichtszeit. |
| GDPR-Löschung | Beachten Sie, dass GDPR jetzt in Abstimmung mit Adobe Experience Platform - CJA verarbeitet wird, unabhängig davon, welche Daten von Experience Platform an zugrunde liegenden Datensätzen geändert werden. |

## Mit Einschränkungen unterstützt

| Funktion | Hinweise |
| --- | --- |
| Produktvariable | Die Produktvariable, die derzeit für den Berichte von Daten verfügbar ist, die dem Experience Ereignis-Schema entsprechen (insbesondere mit dem productListItems-Objekt). |
| Visualisierungen | Mit Ausnahme der Imagemap-Visualisierung werden alle Visualisierungen unterstützt. |
| AAM-Audiencen | Wenn Kunden Analytics Data Connector-Datensätze verwenden, sind diese Daten Teil der ADC-Daten. |
| Projektfreigabe | Die Projektfreigabe wird nur von CJA-Anwendern unterstützt. Die Projektfreigabe erfolgt nicht über CJA und den herkömmlichen Arbeitsbereich für Analysen. |
| Benutzerdefinierte Sitzung | Unterstützung für alle benutzerdefinierten Sitzungsfunktionen außer mobilen Hintergrundschlägen. |
| eVar-Persistenzeinstellungen | eVars sind nicht mehr Teil von CJA. Persistenzeinstellungen gehören jetzt jedoch zu den Data Ansichten und stehen für alle Dimensionen zur Verfügung. Denken Sie daran, dass die Persistenz auf der Verarbeitung der Berichtszeit und nicht auf der Verarbeitung der Datenerfassung basiert. Dies bedeutet, dass die gesamte Persistenz auf dem Datumsbereich des Berichte und nicht auf der Gesamtheit der Daten basiert. |
| Classifications | Diese so genannten &quot;Lookup-Datensätze&quot;werden nicht automatisch aus herkömmlichen Analytics importiert. Sie müssen in AEP hochgeladen werden, bevor sie in CJA verfügbar sind. |
| Kundenattribute | Jetzt als &quot;Profil-Datasets&quot;bezeichnet, werden sie nicht automatisch aus Experience Cloud importiert, sondern müssen in AEP hochgeladen werden, bevor sie in CJA verfügbar sind. |

## Teilweise Unterstützung

| Funktion | Hinweise |
| --- | --- |
| Dimensionen des Arbeitsbereichs für Analysen (z. B. Browsertyp, Werber-Typ, Marketing-Kanal, Besuchsnummer usw.) | CJA stellt diese Dimensionen nicht nativ bereit. Für Kunden, die Analytics Data Connector (ADC) verwenden, sind einige dieser Dimensionen verfügbar, jedoch nicht alle. Bitte lesen Sie unsere [Dokumentation darüber, welche Analytics-Variablen über ADC](https://www.adobe.io/apis/experienceplatform/home/data-ingestion/data-ingestion-services.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md)unterstützt werden. |
| Bedienfelder | Leeres Bedienfeld, Zuordnungs-Bedienfeld und Freiform-Bedienfeld werden vollständig unterstützt. Segmentvergleich wird nicht unterstützt. |
| Merchandising eVars | Merchandising-eVars funktionieren nur mit ADC-basierten Datensätzen, es sei denn, sie entsprechen genau demselben XDM-Schema (ähnlich den Einschränkungen der Liste oben). |
| Bot-Filterung | Bei Analytics Data Connector (ADC)-basierten Datensätzen wird Bot-Filterung angewendet. Allgemeine Bot-Filterlogik für andere Datensätze wird nicht von der Experience Platform oder CJA ausgeführt. |
| Verarbeitungsregeln | Bei ADC-basierten Datensätzen werden weiterhin Verarbeitungsregeln angewendet. |
| Geräteübergreifende Identitätsfestsetzung | Kunden sind über den Abfrage Service auf &quot;einmalige&quot;Datenreihen beschränkt oder müssen diese Logik derzeit vor der Datenerfassung mit Experience Platform auf Daten anwenden. |

## Derzeit nicht unterstützt, aber geplant

| Funktion | Hinweise |
| --- | --- |
| Anomalieerkennung | Unterstützung ist geplant. |
| Beitragsanalyse | Unterstützung ist geplant. |
| Segment IQ | Unterstützung ist geplant. |
| Segmentveröffentlichung (Senden von Segmenten aus Workspace an die Experience Cloud) | Unterstützung ist geplant. |
| Benutzerberechtigungen/Zugriffskontrollen | Alle Nutzer von CJA haben die gleichen Zugriffskontrollen - das bedeutet, dass alle Nutzer Zugriff auf alle Verbindungen, Daten-Ansichten usw. haben. Grundsätzlich sind alle Benutzer Benutzer Benutzer auf Administratorebene in CJA. Die Unterstützung ist für 2020 geplant. |
| CSV-Download | Unterstützung ist geplant. |
| Geplante Berichte/Projekte | Unterstützung ist geplant. |
| Warnhinweise | Unterstützung ist geplant. |
| Benutzerdefinierte Kalender | Unterstützung ist geplant. |
| Marketing-Kanäle | Unterstützung ist geplant. |
| PDF Export | Unterstützung ist geplant. |
| Berichte-API-Zugriff | Support ist geplant - nur mit API 2.0 verfügbar. |
| ID-Stiftung über Gerätediagramm | Unterstützung ist geplant. |

## Unterstützung noch nicht geplant

| Funktion | Hinweise |
| --- | --- |
| A4T | Die Unterstützung ist noch nicht geplant. |
| Video Analytics | Die Unterstützung ist noch nicht geplant. |
| Advertising Cloud | Die Unterstützung ist noch nicht geplant. |
| ReportBuilder (Excel-Plugin) | Die Unterstützung ist noch nicht geplant. |
| Activity Map | Die Unterstützung ist noch nicht geplant. |
| Classification Rule Builder | Die Unterstützung ist noch nicht geplant. |
| Zusammenfassende Datenquellen | Die Unterstützung ist noch nicht geplant. |
| Echtzeit-Berichte | Die Unterstützung ist noch nicht geplant. |

## Wird nie unterstützt

| Funktion | Hinweise |
| --- | --- |
| Metrik für Personen mit geräteübergreifender Coop |  |
| Reports &amp; Analysen-Dashboard |  |
| Reports &amp; Analysen-Lesezeichen |  |
| Reports &amp; Analysen-Zielgruppen |  |
| Ereignis des Reports &amp; Analysen-Kalenders |  |
| Ad Hoc Analysis |  |
| Data Warehouse Berichterstellung  | Der Adobe Experience Platform Abfrage Service ist die neue Schnittstelle für diese Anwendungsfälle in CJA. |
| Mobile Services |  |
| Daten-Feeds |  |
