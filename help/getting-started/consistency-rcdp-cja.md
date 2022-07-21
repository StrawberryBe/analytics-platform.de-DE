---
description: Erläutert, welche Faktoren die Konsistenz von Metriken zwischen Real-time Customer Data Platform (Echtzeit-Kundendatenplattform) und CJA beeinflussen.
title: Konsistenz der Metriken zwischen der Echtzeit-Kundendatenplattform und CJA
role: Admin
feature: CJA Basics
source-git-commit: 2318b303c981ad556dc61a3419af4cce9fbbf92b
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 2%

---


# Konsistenz der Metriken zwischen der Echtzeit-Kundendatenplattform und CJA

In Echtzeit-Szenarien kann die Konsistenz von Metriken in Real-time Customer Data Platform (Echtzeit-Kundendatenplattform) und Customer Journey Analytics (CJA) nicht garantiert werden. In diesem Dokument wird erläutert, warum.

## CJA verwendet Identitätsdiagramm noch nicht

Die Kundendatenplattform und die Customer Journey Analytics haben heute nicht die gleiche Definition wie eine Person. CJA verwendet noch nicht [Identitätsdiagramm](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=de) eine Person zu bestimmen. Die Echtzeit-Kundendatenplattform beruht vollständig auf den Informationen im Identitätsdiagramm, um ein zusammengeführtes Profil zu erstellen.

CJA verwendet eine Methode namens [Feldbasiertes Stitching](/help/connections/cca/overview.md) , das IDs aus Datensätzen im Data Lake extrahiert und benutzerdefinierte Logik anwendet, um sie miteinander zu verknüpfen. In der Zwischenzeit wird CJA voraussichtlich beginnen, [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) Exporte in den Data Lake, sodass eine gemeinsame Identitätsvorstellung über die Echtzeit-Kundendatenplattform und CJA hinweg möglich ist.

>[!IMPORTANT]
>
>Wenn der Adobe Experience Platform Identity-Dienst für alle Adobe Experience Platform-Anwendungen zur Identitätsquelle der Wahrheit wird, werden Metriken nicht automatisch anwendungsübergreifend konsistent. Lesen Sie weiter, um zu erfahren, warum.

## Flexibilität der Anwendungsdaten

Experience Platform wendet keine strikte Durchsetzung an, um die Daten zwischen Echtzeit-Kundenprofil und Data Lake gleich zu halten. In einigen Anwendungsfällen werden Daten in [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/profile/profile-overview.html?lang=en) (Aktivierung), während andere die [Datensee](https://business.adobe.com/blog/basics/data-lake) (Reporting- und Abfragedienst).

Kunden mit Echtzeit-Kundendatenplattform verfügen in der Regel nicht über 100 % der Daten im Adobe Experience Platform Data Lake, die in das Profil aufgenommen werden. Dies ist beabsichtigt - Kunden sollten speziell Daten im See für Profile aktivieren. Mit CJA können Datenanalysten aus dem Data Lake frei auswählen, welche Daten sie für die Analyse einbringen möchten, unabhängig davon, was für die Echtzeit-Kundendatenplattform aktiviert ist.

## Anwendungsspezifische Modifikatoren

CJA ermöglicht eine umfangreiche Datenmodifizierung zum Zeitpunkt der Abfrage, z. B. die Kombination von Feldern, die Aufteilung von Feldern und andere Manipulationen wie Währungskonversionen, Wertdeduplizierung, Sitzungserstellung und Filterung auf Zeilenebene. Diese Funktionen stehen der CDP nicht zur Verfügung.

Ebenso gilt die Echtzeit-Kundendatenplattform [Zusammenführungsrichtlinien](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) um zu bestimmen, welche Daten priorisiert werden und welche Daten kombiniert werden, um eine einheitliche Sicht auf eine Person zu schaffen. Diese Konfigurationen befinden sich fest in der Logik der jeweiligen Anwendung und sind nicht freigegeben.

## Lese- und Schreibzeitverhalten

Die Echtzeit-Kundendatenplattform erfordert die Echtzeit-Profilzuordnung unter Verwendung des neuesten ID-Diagramms.

* Die Echtzeit-Kundendatenplattform wurde entwickelt, um Profilinformationen in Echtzeit zur Aktivierung zusammenzuführen.

* Er kann alle Änderungen an den festgelegten Kennungen für einen bestimmten Benutzer in Echtzeit berücksichtigen.

* Das Lookback-Fenster wird durch die Segmentdefinition gesteuert.

CJA erfordert, dass Daten zur Schreibzeit mithilfe von ID-Diagrammexporten zugeordnet werden.

* CJA wendet komplexe Vorverarbeitungsschritte wie Indizierung, Freigabe und Gruppierung an, bevor die Daten zur Analyse bereit sind.

* Die Personen-ID für einen bestimmten Benutzer ist ein kritischer Input für die Vorab-Bearbeitungsetappen. Die nachträgliche Änderung der Personenkennung hat erhebliche Verarbeitungskosten.

* Das Lookback-Fenster wird auf Anwendungsebene gesteuert.

## Unterschiede bei TTL (Time to Live) und Datenerfassung

Selbst wenn die Datensätze in der Echtzeit-Kundendatenplattform und in CJA identisch sind, behält die Echtzeit-Kundendatenplattform möglicherweise nur ein sehr begrenztes Zeitfenster der Geschichte bei. Im Gegensatz dazu verfügt CJA wahrscheinlich über Daten aus Jahren. Zusätzlich:

* Kunden von CJA und Echtzeit-Kundendatenplattform können benutzerdefinierte Aufbewahrungsfenster für Daten festlegen, unabhängig voneinander.

* Die Echtzeit-Kundendatenplattform und die Customer Journey Analytics haben unterschiedliche Logiken für die Aufnahme von Daten. CJA ignoriert Datensätze ohne Personen-ID oder Zeitstempel und begrenzt die Anzahl der Datensätze, die ein einzelnes Profil/eine einzelne Person aufweisen kann, streng.

* Kunden mit Echtzeit-Kundendatenplattform erhalten 7 Tage Zugriff auf Daten im See, um in erster Linie das Onboarding von Daten in Profile und Ad-hoc-Abfragen zu erleichtern.

* Es gibt keine TTLs für die Daten im See für CJA-Kunden. CJA-Benutzer können jedoch beim Erstellen einer Verbindung selbst ein benutzerdefiniertes Aufbewahrungsfenster in CJA festlegen.

* Der Profilspeicher in der Echtzeit-Kundendatenplattform ermöglicht kundenkonfigurierbare TTLs. Kunden können diese TTL in die Werte ändern, die sie benötigen, um in ihren Lizenzberechtigungen zu bleiben.

## Unterschiede bei der Verarbeitung von DSGVO (Datenschutz-Grundverordnung)

Die Datenverarbeitungslogik für DSGVO und Datenhygiene in der Echtzeit-Kundendatenplattform und im Data Lake unterscheidet sich stark. Wir arbeiten an einem einheitlichen Ansatz.

## Unterschiede in der Datenerfassungslatenz

Die CJA-Berichterstellung beinhaltet eine gewisse Latenz, bevor Daten für die Berichterstellung oder Zielgruppenerstellung verfügbar sind. Die Echtzeit-Kundendatenplattform verarbeitet Daten über verschiedene Systeme mit unterschiedlicher Latenz.