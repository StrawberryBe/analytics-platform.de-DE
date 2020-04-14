---
title: FAQ zu Customer Journey Analytics
description: Customer Journey Analytics – häufig gestellte Fragen
translation-type: tm+mt
source-git-commit: 69f9154387ec11e9b1ec6f867ebab6d556451a9a

---


# Häufig gestellte Fragen

| Frage | Antwort |
|---|---|
| **Voraussetzungen** |  |
| Do you need Device Graph or Device Coop for [!UICONTROL Customer Journey Analytics]? | No, Private Device Graph or Device Coop are not required for [!UICONTROL Customer Journey Analytics]. Dies wird aktuell noch nicht unterstützt. |
| Do you need Experience Cloud ID (ECID) for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supports any ID in a dataset, whether that&#39;s ECID or any other ID you choose. |
| Was ist, wenn meine Daten vor Customer Journey Analytics einem ETL-Prozess (Extract, Transform, Load) unterzogen werden müssen? | Wenn Sie Ihre Daten transformieren müssen, bevor sie in AEP eingefügt werden, arbeiten Sie mit einem ETL-Partner (Unifi oder Informatica) zusammen. Wenn die Daten nach der Erfassung einem ETL-Prozess unterzogen werden müssen, bieten die AEP-Abfragedienste einige eingeschränkte Optionen. |
| **Stitching** |  |
| Can [!UICONTROL Customer Journey Analytics] &quot;stitch&quot; across devices or across datasets? | Nein. [!UICONTROL Customer Journey Analytics] ist ein &quot;bring-your-own-ID&quot;-Analysesystem. Pläne für Stitching sind in Vorbereitung. |
| Wird das Stitching vom anonymen Verhalten zum authentifizierten Verhalten unterstützt? | Nein, noch nicht. |
| **Daten abrufen in[!UICONTROL Customer Journey Analytics]** |  |
| Wofür ist die erwartete Latenz [!UICONTROL Customer Journey Analytics] bei [!UICONTROL Experience Platform]? | <ul><li>Unter normaler Belastung: &lt; 60 Minuten <br>**Hinweis:** Bei ungewöhnlich hohem Datenfluss durch die Pipeline kann es bis zu 24 Stunden dauern.</li><li>Aufstockungsdaten (bis zu 10 Mrd. Ereignisse): &lt; 4 Wochen</li></ul> |
| How do you connect online data to offline data in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] ist ein &quot;bring your own ID&quot;-Analysesystem. As long as the person ID matches between datasets, [!UICONTROL Customer Journey Analytics] can connect segments, attribution, flow, fallout, etc. über Datensätze hinweg miteinander verbinden. |
| Wie integriere ich meine Offline-Daten in Customer Journey Analytics? | Kunden müssen zunächst Daten an Experience Platform übermitteln, bevor sie diese mit Customer Journey Analytics verwenden können. Das Datenerfassungsteam der Experience Platform bietet bei Bedarf Empfehlungen oder eine Beratung für Kunden an. |
| Wie importiere ich Analytics-Daten in Customer Journey Analytics? | Analytics-Daten können über den Analytics Data Connector mit der Experience Platform verbunden werden. Die meisten Analytics-Felder werden im XDM-Format übermittelt, andere Felder sind jedoch noch nicht verfügbar (z. B. Dimensionen für Marketing-Kanäle). |
| Wie lange dauert es, bis Datensatzelemente in einer Datenansicht zusammengefasst werden? | Ein paar Stunden für eine erste Ansicht und ein paar Tage, um die Daten der letzten 13 Monate einzufügen. |
| Sind PII-Daten notwendig, um Verbindungen zwischen den Daten herzustellen? | Nein, Sie können eine beliebige ID verwenden, einschließlich eines Hash einer Kunden-ID, bei der es sich nicht um personenbezogene Daten handelt. |
| **Herkömmliche Analytics-Komponenten** |  |
| Was bedeutet dies für unser herkömmliches Adobe Analytics-Produkt? | Customer Journey Analytics ist ein Analytics-Produkt der nächsten Generation. Die Weiterentwicklung unserer aktuellen Produkte in Customer Journey Analytics wird Jahre dauern und enorm viel Koordinierung erfordern. Die vorliegende Version ist ein großer Schritt von vielen in diese Richtung. |
| Kann ich Segmente von Customer Journey Analytics für AEP oder andere Lösungen freigeben? | Noch nicht. Wir suchen nach neuen, innovativen Möglichkeiten, Segmente von Customer Journey Analytics für AEP freizugeben, die künftig keine so lange Verzögerung aufweisen. Sie können diese Einschränkung umgehen, indem Sie das Ergebnis von Abfragediensten für Unified Profil freigeben. |
| Was ist mit meiner alten eVar-Einstellung passiert? | eVars, Props und Ereignisse im herkömmlichen Adobe Analytics-Sinne gibt es in Customer Journey Analytics nicht mehr. Es gibt unbegrenzte Schemaelemente (Dimensionen, Metriken, Listenfelder). Alle Zuordnungseinstellungen, die Sie bisher während des Datenerfassungsprozesses angewendet haben, werden jetzt bei der Abfrage angewendet. |
| Wo sind jetzt meine Einstellungen für die Sitzungs- und Variablenpersistenz? | Customer Journey Analytics verwendet alle diese Einstellungen zur Berichtszeit. Diese Einstellungen sind jetzt in Datenansichten verfügbar. Änderungen an diesen Einstellungen sind jetzt rückwirkend. Jetzt sind mehrere Versionen verfügbar, indem Sie mehrere Datenansichten verwenden. |
| Was passiert mit den bereits vorhandenen Segmenten/berechneten Metriken? | Customer Journey Analytics verwendet keine eVars, Props oder Ereignisse mehr und verwendet stattdessen ein AEP-Schema. Das bedeutet, dass keine der vorhandenen Segmente oder Berechnungsmetriken mit Customer Journey Analytics kompatibel sind. |
| Wie handhabt Customer Journey Analytics `Uniques Exceeded` Beschränkungen? | In Customer Journey Analytics gibt es keine Beschränkungen hinsichtlich eindeutiger Werte, sodass Sie sie nicht beachten müssen. |
| Kann ich als bestehender [!DNL Data Workbench]-Kunde jetzt zu Customer Journey Analytics wechseln? | Das hängt von Ihrer aktuellen Situation ab. Wenn Sie den Unified Customer Process (UCP) häufig benötigen, sollten Sie warten, bis Stitching implementiert wurde. Wenn Sie bereits eine hohe Kundenauthentifizierungsrate haben, wenn Sie alle Ihre Daten an einem Ort speichern möchten oder wenn Sie eVars eliminieren möchten, ist Customer Journey Analytics möglicherweise eine gute Wahl. |

