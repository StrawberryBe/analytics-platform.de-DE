---
title: Häufig gestellte Fragen zu Customer Journey Analytics
description: Customer Journey Analytics - Häufig gestellte Fragen.
translation-type: tm+mt
source-git-commit: 336adb3762258cc657ffa5c74a50d28e6f63c7db

---


# Häufig gestellte Fragen

| Frage | Antwort |
|---|---|
| **Voraussetzungen** |  |
| Benötigen Sie Gerätediagramm oder Gerätecoop für Customer Journey Analytics? | Nein, für Customer Journey Analytics sind kein eigenes Gerätediagramm oder keine Gerätekopie erforderlich. Tatsächlich werden sie noch nicht unterstützt. |
| Benötigen Sie Experience Cloud ID (ECID) für Customer Journey Analytics? | Nein, Customer Journey Analytics unterstützt alle IDs in einem Datensatz, unabhängig davon, ob es sich um ECID oder eine andere ID handelt, die Sie auswählen. |
| Was ist, wenn Sie Ihre Daten vor der Customer Journey Analytics ETL (Extract, Transform, Load) ausgeben müssen? | Heute müssen Sie mit einem ETL-Partner (Unifi oder Informatica) zusammenarbeiten, wenn Sie Ihre Daten umwandeln müssen, bevor Sie sie in AEP einfügen. Wenn Sie ETL benötigen, nachdem die Daten bereits erfasst wurden, bietet AEP Abfrage Services einige eingeschränkte Optionen. |
| **Sticken** |  |
| Kann die Customer Journey Analytics geräteübergreifend oder über Datensätze hinweg &quot;zuordnen&quot;? | Nein. Customer Journey Analytics ist ein &quot;bring-your-own-ID&quot;-Analysesystem. Pläne für einen guten Nähansatz liegen in der Arbeit. |
| Wird das Zuordnen vom anonymen Verhalten zum authentifizierten Verhalten unterstützt? | Nein, das ist noch nicht möglich. |
| **Daten in Customer Journey Analytics einbringen** |  |
| Welche Latenz wird für Customer Journey Analytics auf der Plattform erwartet? | <ul><li>Unter normaler Belastung: &lt; 60<br>**MinutenHinweis:**Bei ungewöhnlich hohem Datenfluss durch die Pipeline kann es bis zu 24 Stunden dauern.</li><li>Aufstockungsdaten (bis zu 10 Mrd. Ereignis): &lt; 4 Wochen</li></ul> |
| Wie verbinden Sie Online-Daten mit Offlinedaten in Customer Journey Analytics? | Customer Journey Analytics ist ein Analysesystem, das Ihre eigene ID anbietet. Solange die Personen-ID mit den Daten übereinstimmt, kann Customer Journey Analytics Segmente, Zuordnungen, Fluss, Trichteranalyse usw. verbinden. über Datensätze hinweg. |
| Wie bringe ich meine Offline-Daten in Customer Journey Analytics ein? | Kunden müssen zunächst Daten an AEP übermitteln, bevor sie diese mit Customer Journey Analytics verwenden können. Das Datenerfassungsteam der Experience Platform kann bei Bedarf Empfehlungen oder Beratung für Kunden bereitstellen. |
| Wie erhalte ich Analytics-Daten in Customer Journey Analytics? | Analytics-Daten können über den Analytics Data Connector mit AEP verbunden werden. Die meisten Analytics-Felder werden im XDM-Format bereitgestellt, andere Felder sind jedoch noch nicht verfügbar (z. B. die Dimensionen der Marketing-Kanal). |
| Wie lange dauert es, bis Datensatzelemente in eine Ansicht eingefügt werden? | Ein paar Stunden, um damit zu beginnen, und ein paar Tage, um die letzten 13 Monate Daten aufzustocken. |
| Muss man PII-Daten mitbringen, um Verbindungen zwischen den Daten herzustellen? | Nein, Sie können eine beliebige ID verwenden, einschließlich eines Hashs mit einer Kunden-ID, bei der es sich nicht um eine PII handelt. |
| **Traditionelle Analytics-Komponenten** |  |
| Was bedeutet dies für unser traditionelles Adobe Analytics-Produkt? | Customer Journey Analytics ist unser Analytics-Produkt der nächsten Generation. Die Entwicklung von unseren aktuellen Produkten zu Customer Journey Analytics wird Jahre dauern und viel Koordinierung erfordern. Diese Version ist ein großer Schritt von vielen in diese Richtung. |
| Kann ich Segmente von Customer Journey Analytics für AEP oder andere Lösungen freigeben? | Noch nicht. Wir untersuchen neue, innovative Möglichkeiten, Segmente von Customer Journey Analytics an AEP weiterzugeben, die keine so lange Verzögerung aufweisen. Sie können die Ausgabe von Abfrage Services für Unified Profil freigeben, um eine Lösung zu finden. |
| Was ist mit meiner alten eVar-Einstellung passiert? | eVars, Props und Ereignis im klassischen Adobe Analytics-Sinne gibt es in Customer Journey Analytics nicht mehr. Sie haben unbegrenzte Schema-Elemente (Dimensionen, Metriken, Listen-Felder). Alle Zuordnungseinstellungen, die Sie während des Datenerfassungsprozesses angewendet haben, werden jetzt zur Abfrage angewendet. |
| Wo sind jetzt alle Einstellungen für die Sitzungs- und Variablenpersistenz? | Customer Journey Analytics wendet alle diese Einstellungen zur Berichtszeit an, und diese Einstellungen sind jetzt in Data Ansichten verfügbar. Änderungen an diesen Einstellungen sind jetzt rückwirkend, und Sie können mehrere Ansichten verwenden, indem Sie mehrere Datenversionen verwenden! |
| Was passiert mit unseren vorhandenen Segmenten/berechneten Metriken? | Customer Journey Analytics verwendet keine eVars, Props oder Ereignis mehr und verwendet stattdessen ein AEP-Schema. Das bedeutet, dass keine der vorhandenen Segmente oder Berechnungsmetriken mit Customer Journey Analytics kompatibel sind. |
| Wie geht Customer Journey Analytics mit `Uniques Exceeded` Einschränkungen um? | Customer Journey Analytics hat keine einzigartigen Werteinschränkungen, sodass Sie sich keine Sorgen machen müssen! |
| Kann ich als bestehender [!DNL Data Workbench] Kunde jetzt zu Customer Journey Analytics wechseln? | Es kommt darauf an. Wenn Sie sich stark auf den Unified Customer Process (UCP) verlassen, sollten Sie warten, bis die Heften implementiert sind. Wenn Sie bereits hohe Authentifizierungsraten von Kunden haben oder wenn Sie alle Ihre Daten an einem Ort speichern möchten oder wenn Sie eVars loswerden möchten, ist Customer Journey Analytics möglicherweise eine gute Wahl. |

