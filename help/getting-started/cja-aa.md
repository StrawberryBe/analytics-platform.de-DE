---
title: Customer Journey Analytics-Funktionen
description: Customer Journey Analytics-Funktionen im Vergleich zu Adobe Analytics-Funktionen.
translation-type: ht
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# Customer Journey Analytics-Funktionen

In den folgenden Tabellen ist aufgeführt, welche Funktionen in Adobe Analytics in Customer Journey Analytics (CJA) unterstützt, teilweise unterstützt oder nicht unterstützt werden. Diese Listen ändern sich im Laufe der Zeit, wenn CJA Funktionen hinzugefügt werden.

## Vollständig unterstützte Funktionen/Komponenten

| Funktion | Hinweise |
| --- | --- |
| Metriken | CJA nutzt das Experience-Datenmodell (XDM) und unterstützt unbegrenzte Metriken und ist nicht an die benutzerspezifischen Erfolgsereignisse traditioneller Analytics gebunden. Beachten Sie, dass einige Standardmetriken aus der traditionellen Analytics umbenannt wurden: Besucher = Personen, Besuche = Sitzungen, Treffer = Ereignisse. |
| Dimensionen | CJA nutzt XDM und unterstützt unbegrenzte Dimensionen und ist nicht an die benutzerspezifischen Erfolgsereignisse traditioneller Analytics gebunden. |
| Listenvariablen/Listen-Props | CJA nutzt XDM und unterstützt unbegrenzte Listenvariablen. |
| Datumsbereiche | Die Unterstützung benutzerdefinierter Kalender ist geplant. |
| Berechnete Metriken | Beachten Sie, dass vorhandene Berechnungsmetriken im herkömmlichen Analysis Workspace nicht auf CJA portiert werden. |
| Segmente | Jetzt „Filter“ genannt. Beachten Sie, dass keine vorhandenen Segmente im traditionellen Analysis Workspace auf CJA portiert werden. |
| Attribution IQ | Vollständige Unterstützung. |
| Projektkuration | Vollständige Unterstützung. |
| Projektverknüpfung | Vollständige Unterstützung. |
| Datumsvergleiche | Vollständige Unterstützung. |
| Virtual Report Suites | Jetzt [Datenansichten](/help/data-views/create-dataview.md) genannt. |
| Kuration von VRS-Komponenten | Jetzt Teil der Datenansichten. |
| Berichtszeitverarbeitung | CJA basiert ausschließlich auf der Berichtszeitverarbeitung. |
| DSGVO-Löschung | Beachten Sie, dass DSGVO jetzt in Abstimmung mit [!UICONTROL Experience Platform] gehandhabt wird. CJA erbt alle Datenänderungen, die [!UICONTROL Experience Platform] an den zugrunde liegenden Datensätzen vornimmt. |

## Mit Einschränkungen unterstützt

| Funktion | Hinweise |
| --- | --- |
| Produktvariable | Die Produktvariable, die derzeit für die Berichterstellung für Daten verfügbar ist, die dem Schema der Erlebnisereignisse entsprechen (insbesondere unter Verwendung des productListItems-Objekts). |
| Visualisierungen | Alle Visualisierungen mit Ausnahme der Zuordnungsvisualisierung werden unterstützt. |
| AAM-Audiences | Wenn Kunden [!UICONTROL Analytics Data Connector]-Datensätze verwenden, sind diese Daten Teil der ADC-Daten. |
| Projektfreigabe | Die Projektfreigabe wird nur von zwischen CJA-Anwendern unterstützt. Es gibt keine Projektfreigabe zwischen CJA und dem traditionellen Analysis Workspace. |
| Benutzerdefinierte Sitzungen | Unterstützung aller benutzerdefinierten Sitzungsfunktionen außer mobilen Hintergrundtreffern, |
| eVar-Persistenzeinstellungen | eVars sind nicht mehr Teil von CJA. Die Persistenzeinstellungen sind jetzt jedoch Teil der Datenansichten und für alle Dimensionen verfügbar. Beachten Sie, dass die Persistenz auf der Berichtszeitverarbeitung und nicht auf der Datenerfassungsverarbeitung basiert. Dies bedeutet, dass die gesamte Persistenz auf dem Berichtszeitraum und nicht auf der Gesamtheit der Daten basiert. |
| Klassifizierungen | Jetzt als „Suchdatensätze“ bezeichnet, werden sie nicht automatisch aus der traditionellen Analytics importiert. Sie müssen in AEP hochgeladen werden, bevor sie in CJA verfügbar sind. |
| Kundenattribute | Jetzt als „Profildatensätze“ bezeichnet, werden sie nicht automatisch aus Experience Cloud importiert, sondern müssen in AEP hochgeladen werden, bevor sie in CJA verfügbar sind. |

## Teilweise Unterstützung

| Funktion | Hinweise |
| --- | --- |
| Vordefinierte Analysis Workspace-Dimensionen (z. B. Browser-Typ, Referrer-Typ, Marketing-Kanäle, Besuchsnummer usw.) | CJA stellt diese Dimensionen nicht nativ bereit. Für Kunden, die Analytics Data Connector (ADC) verwenden, sind einige dieser Dimensionen verfügbar, jedoch nicht alle. Bitte lesen Sie in unserer [Dokumentation, welche Analytics-Variablen über ADC unterstützt werden](https://docs.adobe.com/content/help/de-DE/experience-platform/ingestion/home.translate.html#!api-specification/markdown/narrative/technical_overview/acp_connectors_overview/analytics_mapping_fields.md). |
| Bedienfelder | Leeres Bedienfeld, Attribution-Bedienfeld und Freiform-Bedienfeld werden vollständig unterstützt. Der Segmentvergleich wird nicht unterstützt. |
| Merchandising-eVars | Merchandising-eVars funktionieren nur mit ADC-basierten Datensätzen, es sei denn, sie entsprechen genau demselben XDM-Schema (ähnlich den oben genannten Einschränkungen der Produktliste). |
| Bot-Filterung | Bei Analytics Data Connector (ADC)-basierten Datensätzen wird die Bot-Filterung angewendet. Die allgemeine Bot-Filterlogik für andere Datensätze wird weder von [!UICONTROL Experience Platform] noch von CJA ausgeführt. |
| Verarbeitungsregeln | Bei ADC-basierten Datensätzen werden weiterhin Verarbeitungsregeln angewendet. |
| Geräteübergreifende Identitätszuordnung | Kunden sind auf eine „einmalige“ Datenzuordnung über den Abfragedienst beschränkt oder müssen diese Logik derzeit auf die Daten vor der Datenerfassung durch [!UICONTROL Experience Platform] anwenden. |

## Derzeit nicht unterstützt, aber geplant

| Funktion | Hinweise |
| --- | --- |
| Anomalieerkennung | Unterstützung ist geplant. |
| Beitragsanalyse | Unterstützung ist geplant. |
| Segment IQ | Unterstützung ist geplant. |
| Segmentveröffentlichung (Senden von Segmenten aus Workspace an Experience Cloud) | Unterstützung ist geplant. |
| Benutzerberechtigungen/Datenzugangssteuerung | Für alle CJA-Benutzer gilt dieselbe Zugangssteuerung. Das bedeutet, dass alle Benutzer Zugriff auf alle Verbindungen, Datenansichten usw. haben. Grundsätzlich sind alle Benutzer in CJA Administratoren. Die Unterstützung ist für 2020 geplant. |
| CSV-Download | Unterstützung ist geplant. |
| Terminierte Berichte/Projekte | Unterstützung ist geplant. |
| Warnhinweise | Unterstützung ist geplant. |
| Benutzerdefinierte Kalender | Unterstützung ist geplant. |
| Marketing-Kanäle | Unterstützung ist geplant. |
| PDF-Export | Unterstützung ist geplant. |
| Zugriff auf Reporting-API | Unterstützung ist geplant - wird nur mit API 2.0 verfügbar sein. |
| ID-Zuordnung über Gerätediagramm | Unterstützung ist geplant. |

## Unterstützung ist noch nicht geplant.

| Funktion | Hinweise |
| --- | --- |
| A4T | Unterstützung ist noch nicht geplant. |
| Video Analytics | Unterstützung ist noch nicht geplant. |
| Advertising Cloud | Unterstützung ist noch nicht geplant. |
| Report Builder (Excel-Plug-in) | Unterstützung ist noch nicht geplant. |
| Activity Map | Unterstützung ist noch nicht geplant. |
| Classification Rule Builder | Unterstützung ist noch nicht geplant. |
| Zusammenfassungs-Data-Sources | Unterstützung ist noch nicht geplant. |
| Echtzeitberichterstellung | Unterstützung ist noch nicht geplant. |

## Keine Unterstützung geplant.

| Funktion | Hinweise |
| --- | --- |
| Benutzermetriken mit Cross-Device Coop |  |
| Reports &amp; Analytics-Dashboards |  |
| Reports &amp; Analytics-Lesezeichen |  |
| Reports &amp; Analytics-Zielgruppen |  |
| Reports &amp; Analytics-Kalenderereignisse |  |
| Ad Hoc Analysis |  |
| Data Warehouse Berichterstellung | [!UICONTROL Experience Platform Query Service] wird die neue Schnittstelle für diese Anwendungsfälle in CJA sein. |
| Mobile Services |  |
| Daten-Feeds |  |
