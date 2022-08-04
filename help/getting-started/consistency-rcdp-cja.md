---
description: Erläutert, welche Faktoren die Konsistenz von Metriken und die Anzahl der Zielgruppenzugehörigkeiten zwischen Real-time Customer Data Platform (Real-Time CDP) und CJA beeinflussen.
title: Konsistenz der Metriken und Anzahl der Zielgruppenzugehörigkeiten zwischen der Real-Time CDP und CJA
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 769eef205df32865874753859ce79e573db40641
workflow-type: ht
source-wordcount: '577'
ht-degree: 100%

---


# Konsistenz der Metriken und Anzahl der Zielgruppenzugehörigkeiten zwischen der Real-Time CDP und CJA

In realen Szenarien kann die Konsistenz von Metriken und die Anzahl der Zielgruppenmitgliedschaften zwischen Real-time Customer Data Platform (Real-Time CDP) und Customer Journey Analytics (CJA) nicht garantiert werden. In diesem Dokument wird erläutert, warum.

Beim Vergleich der Anzahl der Zielgruppenzugehörigkeiten zwischen der Real-Time CDP und CJA ist es wichtig, die verschiedenen Ziele dieser beiden Tools zu beachten. Die Real-Time CDP verwendet Kundenprofildaten, um digitale Erlebnisse auf einzelne Verbrauchende auszurichten, während CJA Benutzenden dabei hilft, Muster in wichtigen Geschäftsmetriken und Segmenten zu verstehen. Während die Veröffentlichung der Zielgruppe von CJA in der Real-Time CDP denen, die diese Tools verwenden, das einfache und native „Aktivieren“ eines Einblicks ermöglicht, indem sie die in CJA gewonnenen Erkenntnisse nutzen, dienen diese Tools dennoch grundlegend anderen Zwecken.

## Unterschiede in Identitätskonfigurationen

Die Real-Time CDP und Customer Journey Analytics verwenden heutzutage nicht dieselbe Definition einer Person. Die Real-Time CDP beruht ausschließlich auf den Informationen im [Identitätsdiagramm](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=de) um ein zusammengeführtes Profil zu erstellen.

CJA kann für die Verwendung der [Cross-Channel Analytics](/help/connections/cca/overview.md) konfiguriert werden, die IDs aus Datensätzen im Data Lake extrahiert und benutzerdefinierte Logik anwendet, um sie miteinander zu verknüpfen.

Künftig wird CJA Identitätsdiagramme verwenden können.

## Unterschiede bei der Datensatzkonfiguration

Sie können einige Daten in die Real-Time CDP aufnehmen und einige in Customer Journey Analytics verwenden. Kunden entscheiden sich häufig dafür, mehr historische Daten in Customer Journey Analytics einzufügen, als für die Real-Time CDP relevant ist. Andere Datensätze sind möglicherweise eher für die Real-Time CDP relevant als für CJA.

## Unterschiede bei der Verarbeitungskonfiguration

CJA ermöglicht eine umfangreiche Datenmodifikation zum Zeitpunkt der Abfrage, z. B. die Kombination von Feldern, die Aufteilung von Feldern und andere Manipulationen wie Einschlüsse/Ausschlüsse, Unterzeichenfolgen, Wertdeduplizierung, Sitzungserstellung und Filterung auf Zeilenebene.

Die Real-Time CDP bietet verschiedene Tools zur Datenmanipulation. Sie verwendet [Zusammenführungsrichtlinien](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=de), um zu bestimmen, welche Daten priorisiert werden und welche Daten kombiniert werden, um eine einheitliche Sicht auf eine Person zu schaffen.

## Unterschiede bei TTL (Time to Live) und Datenaufnahme

Selbst wenn die Datensätze in der Real-Time CDP und in CJA identisch sind, behält die Real-Time CDP möglicherweise nur ein sehr begrenztes Zeitfenster des Verlaufs bei. Im Gegensatz dazu verfügt CJA wahrscheinlich über Daten aus mehreren Jahren. Zusätzlich:

* Kunden von CJA und Real-Time CDP können benutzerdefinierte Aufbewahrungsfenster für Daten festlegen, und zwar unabhängig voneinander.

* Die Real-Time CDP und Customer Journey Analytics haben unterschiedliche Logiken für die Aufnahme von Daten. CJA ignoriert Datensätze ohne Personen-ID oder Zeitstempel und begrenzt die Anzahl der Datensätze, die ein einzelnes Profil/eine einzelne Person aufweisen kann, streng.

* Kunden der Real-Time CDP erhalten 7 Tage Zugriff auf Daten im Data Lake, um in erster Linie das Onboarding von Daten in Profile und Ad-hoc-Abfragen zu erleichtern.

* Für CJA-Kunden gibt es keine TTLs für die Daten im Data Lake. Wer CJA verwendet, kann jedoch beim Erstellen einer Verbindung selbst ein benutzerdefiniertes Aufbewahrungsfenster in CJA festlegen.

* Der Profilspeicher in der Real-Time CDP ermöglicht kundenkonfigurierbare TTLs. Kunden können diese TTL in diejenigen Werte ändern, die sie benötigen, um innerhalb ihrer Lizenzberechtigungen zu bleiben.

## Unterschiede in der Datenaufnahmelatenz

CJa verfügt noch nicht über die Echtzeitfunktionen der Real-Time CDP. Daher unterliegt die CJA-Berichterstellung einer gewissen Latenz, bevor Daten für die Berichterstellung oder Zielgruppenerstellung verfügbar sind. Die Real-Time CDP verarbeitet Daten über verschiedene Systeme mit unterschiedlichen Latenzzeiten.
