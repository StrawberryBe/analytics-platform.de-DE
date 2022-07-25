---
description: Erläutert, welche Faktoren die Konsistenz von Metriken und die Anzahl der Zielgruppenzugehörigkeiten zwischen Real-time Customer Data Platform (Echtzeit-Kundendatenplattform) und CJA beeinflussen.
title: Konsistenz der Metriken und Anzahl der Zielgruppenzugehörigkeiten zwischen der Echtzeit-Kundendatenplattform und CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: cf4e2136f5ab4e0ed702820e52e9a62ea8251860
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---


# Konsistenz der Metriken und Anzahl der Zielgruppenzugehörigkeiten zwischen der Echtzeit-Kundendatenplattform und CJA

In realen Szenarien kann die Konsistenz von Metriken und die Anzahl der Zielgruppenmitgliedschaften in Real-time Customer Data Platform (Echtzeit-Kundendatenplattform) und Customer Journey Analytics (CJA) nicht garantiert werden. In diesem Dokument wird erläutert, warum.

## Unterschiede in Identitätskonfigurationen

Die Echtzeit-Kundendatenplattform und die Customer Journey Analytics verwenden heute nicht dieselbe Definition einer Person. Die Echtzeit-Kundendatenplattform beruht ausschließlich auf den Informationen im [Identitätsdiagramm](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=en) um ein zusammengeführtes Profil zu erstellen.

CJA kann für die Verwendung konfiguriert werden [Kanalübergreifende Analyse](/help/connections/cca/overview.md) , das IDs aus Datensätzen im Data Lake extrahiert und benutzerdefinierte Logik anwendet, um sie miteinander zu verknüpfen.
Künftig kann CJA Identitätsdiagramme verwenden.

## Unterschiede bei der Datensatzkonfiguration

Sie können einige Daten in die Echtzeit-Kundendatenplattform aufnehmen und einige in Customer Journey Analytics verwenden. Kunden entscheiden sich häufig dafür, mehr historische Daten in Customer Journey Analytics einzufügen, als für die Echtzeit-Kundendatenplattform relevant ist. Andere Datensätze sind möglicherweise für die Echtzeit-Kundendatenplattform relevanter als für CJA.

## Unterschiede bei der Verarbeitungskonfiguration

CJA ermöglicht eine umfangreiche Datenmodifikation zum Zeitpunkt der Abfrage, z. B. die Kombination von Feldern, die Aufteilung von Feldern und andere Manipulationen wie Einschluss-/Ausschlüsse-, Unterzeichenfolgen, Wertdeduplizierung, Sitzungserstellung und Filterung auf Zeilenebene.

Die Echtzeit-Kundendatenplattform bietet verschiedene Tools zur Datenbearbeitung. Es gilt [Zusammenführungsrichtlinien](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) um zu bestimmen, welche Daten priorisiert werden und welche Daten kombiniert werden, um eine einheitliche Sicht auf eine Person zu schaffen.

## Unterschiede bei TTL (Time to Live) und Datenerfassung

Selbst wenn die Datensätze in der Echtzeit-Kundendatenplattform und in CJA identisch sind, behält die Echtzeit-Kundendatenplattform möglicherweise nur ein sehr begrenztes Zeitfenster der Geschichte bei. Im Gegensatz dazu verfügt CJA wahrscheinlich über Daten aus Jahren. Zusätzlich:

* Kunden von CJA und Echtzeit-Kundendatenplattform können benutzerdefinierte Aufbewahrungsfenster für Daten festlegen, unabhängig voneinander.

* Die Echtzeit-Kundendatenplattform und die Customer Journey Analytics haben unterschiedliche Logiken für die Aufnahme von Daten. CJA ignoriert Datensätze ohne Personen-ID oder Zeitstempel und begrenzt die Anzahl der Datensätze, die ein einzelnes Profil/eine einzelne Person aufweisen kann, streng.

* Kunden mit Echtzeit-Kundendatenplattform erhalten 7 Tage Zugriff auf Daten im See, um in erster Linie das Onboarding von Daten in Profile und Ad-hoc-Abfragen zu erleichtern.

* Es gibt keine TTLs für die Daten im See für CJA-Kunden. CJA-Benutzer können jedoch beim Erstellen einer Verbindung selbst ein benutzerdefiniertes Aufbewahrungsfenster in CJA festlegen.

* Der Profilspeicher in der Echtzeit-Kundendatenplattform ermöglicht kundenkonfigurierbare TTLs. Kunden können diese TTL in die Werte ändern, die sie benötigen, um in ihren Lizenzberechtigungen zu bleiben.

## Unterschiede in der Datenerfassungslatenz

CJa verfügt noch nicht über die Echtzeitfunktionen der Echtzeit-Kundendatenplattform. Daher beinhaltet die CJA-Berichterstellung eine gewisse Latenz, bevor Daten für die Berichterstellung oder Zielgruppenerstellung verfügbar sind. Die Echtzeit-Kundendatenplattform verarbeitet Daten über verschiedene Systeme mit unterschiedlicher Latenz.
