---
title: FAQ zu Customer Journey Analytics
description: Customer Journey Analytics – häufig gestellte Fragen
translation-type: ht
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: ht
source-wordcount: '1235'
ht-degree: 100%

---


# Häufig gestellte Fragen

## Voraussetzungen

| Frage | Antwort |
| --- | --- |
| Benötige ich [!UICONTROL Private Device Graph] oder [!UICONTROL Device Coop] für [!UICONTROL Customer Journey Analytics]? | Nein, [!UICONTROL Private Device Graph] oder [!UICONTROL Device Coop] sind für [!UICONTROL Customer Journey Analytics] nicht erforderlich. Sie werden aktuell noch nicht unterstützt. |
| Benötige ich eine [!UICONTROL Experience Cloud ID] (ECID) für [!UICONTROL Customer Journey Analytics]? | Nein, [!UICONTROL Customer Journey Analytics] unterstützt alle IDs in einem Datensatz, unabhängig davon, ob es sich um eine [!UICONTROL ECID] oder eine andere ID handelt. |
| Wie gehe ich vor, wenn ich meine Daten vor [!UICONTROL Customer Journey Analytics] einem ETL-Prozess (Extract, Transform, Load) unterziehen muss? | Wenn Sie Ihre Daten transformieren müssen, bevor sie in AEP eingefügt werden, arbeiten Sie mit einem ETL-Partner (Unifi oder Informatica) zusammen. Wenn die Daten nach der Aufnahme einem ETL-Prozess unterzogen werden müssen, bietet [!UICONTROL Adobe Experience Platform Query Services] einige eingeschränkte Optionen. |

## Zuordnung von Daten

| Frage | Antwort |
| --- | --- |
| Kann [!UICONTROL Customer Journey Analytics] Daten über Geräte oder über Datensätze hinweg zusammenfügen? | Ja. [!UICONTROL Customer Journey Analytics] ist ein Analysesystem, in dem die eigene ID verwendet werden muss. Im November 2020 haben wir eine Zuordnungslösung zur Verfügung veröffentlicht. Weitere Infos. |
| Wird das Stitching vom anonymen Verhalten zum authentifizierten Verhalten unterstützt? | Nein, noch nicht. |

## Daten in [!UICONTROL Customer Journey Analytics] einbringen

| Frage | Antwort |
| --- | --- |
| Kann ich Daten aus verschiedenen [!UICONTROL Adobe Experience Platform]-Sandboxen in einer [!UICONTROL Customer Journey Analytics]-Verbindung kombinieren? | Nein, Sie können nicht über Sandboxes hinweg auf Daten zugreifen. Sie können nur Datensätze kombinieren, die sich innerhalb derselben Sandbox befinden. [Weitere Informationen ...](https://docs.adobe.com/content/help/de-DE/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Wie hoch ist die erwartete Latenz für [!UICONTROL Customer Journey Analytics] auf [!UICONTROL Adobe Experience Platform]? | <ul><li>Unter normaler Belastung: &lt; 60 Minuten <br>**Hinweis:** Bei ungewöhnlich hohem Datenfluss durch die Pipeline kann es bis zu 24 Stunden dauern.</li><li>Aufstockungsdaten (bis zu 13 Monate Daten, unabhängig von der Größe): &lt; 4 Wochen</li></ul> |
| Wie werden in [!UICONTROL Customer Journey Analytics] Online-Daten mit Offline-Daten verbunden? | [!UICONTROL Customer Journey Analytics] ist ein Analysesystem, in dem die eigene ID verwendet werden muss. Solange die Personen-ID zwischen Datensätzen übereinstimmt, kann [!UICONTROL Customer Journey Analytics] Segmente, Zuordnungen, Flüsse, Fallout usw. verbinden. über Datensätze hinweg miteinander verbinden. |
| Wie integriere ich meine Offline-Daten in [!UICONTROL Customer Journey Analytics]? | Sie müssen zunächst alle Daten an Experience Platform übermitteln, bevor Sie diese für [!UICONTROL Customer Journey Analytics] verwenden können. Das Datenerfassungs-Team der Experience Platform bietet bei Bedarf Empfehlungen oder eine Beratung für Sie an. |
| Wie integriere ich [!UICONTROL Adobe Analytics]-Daten in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics]-Daten können über [Adobe Analytics Source Connector](https://docs.adobe.com/content/help/de-DE/experience-platform/sources/connectors/adobe-applications/analytics.html) mit Experience Platform verbunden werden. Die meisten [!UICONTROL Adobe Analytics]-Felder werden im XDM-Format übermittelt, andere Felder (wie beispielsweise [!UICONTROL Marketing Channels]-Dimensionen) sind jedoch noch nicht verfügbar. |
| Wie lange dauert es, bis Datensatzelemente in einer Datenansicht zusammengefasst werden? | Ein paar Stunden für eine erste Ansicht und ein paar Tage, um die Daten der letzten 13 Monate einzufügen. |
| Sind PII-Daten notwendig, um Verbindungen zwischen den Daten herzustellen? | Nein, Sie können eine beliebige ID verwenden, einschließlich eines Hash einer Kunden-ID, bei der es sich nicht um personenbezogene Daten handelt. |

## Herkömmliche [!UICONTROL Adobe Analytics]-Komponenten

| Frage | Antwort |
| --- | --- |
| Was bedeutet dies für unser herkömmliches [!UICONTROL Adobe Analytics]-Produkt? | [!UICONTROL Customer Journey Analytics] ist ein Analytics-Produkt der nächsten Generation. Die Weiterentwicklung unserer aktuellen Produkte zu [!UICONTROL Customer Journey Analytics] wird noch Jahre dauern und einiges an Koordinierung erfordern. Weitere Informationen finden Sie unter [Customer Journey Analytics-Funktionsunterstützung](/help/getting-started/cja-aa.md). |
| Kann ich Segmente von [!UICONTROL Customer Journey Analytics] für Adobe Experience Platform oder andere Lösungen freigeben? | Noch nicht. Wir arbeiten an neuen innovativen Möglichkeiten, Segmente von [!UICONTROL Customer Journey Analytics] künftig für Adobe Experience Platform freizugeben, die eine geringere Verzögerung aufweisen. Sie können diese Einschränkung umgehen, indem Sie das Ergebnis von Abfragediensten für Unified Profil freigeben. |
| Was ist mit meiner alten eVar-Einstellung passiert? | eVars, Props und Ereignisse im Sinne vom herkömmlichen Adobe Analytics gibt es in [!UICONTROL Customer Journey Analytics] nicht mehr. Es gibt unbegrenzte Schemaelemente (Dimensionen, Metriken, Listenfelder). Alle Zuordnungseinstellungen, die Sie bisher während des Datenerfassungsprozesses angewendet haben, werden jetzt bei der Abfrage angewendet. |
| Wo sind jetzt meine Einstellungen für die Sitzungs- und Variablenpersistenz? | [!UICONTROL Customer Journey Analytics] verwendet alle diese Einstellungen zur Berichtszeit. Diese Einstellungen sind jetzt in Datenansichten verfügbar. Änderungen an diesen Einstellungen sind jetzt rückwirkend. Jetzt sind mehrere Versionen verfügbar, indem Sie mehrere Datenansichten verwenden. |
| Was passiert mit den bereits vorhandenen Segmenten/berechneten Metriken? | [!UICONTROL Customer Journey Analytics] verwendet keine eVars, Props oder Ereignisse mehr und verwendet stattdessen ein AEP-Schema. Das bedeutet, dass keine der vorhandenen Segmente oder Berechnungsmetriken mit [!UICONTROL Customer Journey Analytics] kompatibel sind. |
| Wie werden in [!UICONTROL Customer Journey Analytics] `Uniques Exceeded`-Einschränkungen behandelt? | [!UICONTROL In Customer Journey Analytics] gibt es keine Beschränkungen hinsichtlich eindeutiger Werte, sodass Sie sie nicht beachten müssen. |
| Kann ich als bestehender [!DNL Data Workbench]-Kunde jetzt zu [!UICONTROL Customer Journey Analytics] wechseln? | Das hängt von Ihrer aktuellen Situation ab. Wenn Sie den Unified Customer Process (UCP) häufig benötigen, sollten Sie warten, bis Stitching implementiert wurde. Wenn Sie bereits eine hohe Kundenauthentifizierungsrate haben, wenn Sie alle Ihre Daten an einem Ort speichern möchten oder wenn Sie eVars eliminieren möchten, ist Customer Journey Analytics möglicherweise eine gute Wahl. |

## Auswirkungen des Löschens von Datenkomponenten

In Bezug auf das Löschen sollten folgende 6 Komponenten beachtet werden: Sandbox, Schema, Datensatz, Verbindung, Datenansicht und Workspace-Projekte. Im Folgenden sind einige Szenarien für das Löschen der jeweiligen Komponenten aufgeführt:

| Was ist, wenn ich... | Dies geschieht... |
| --- | --- |
| eine Sandbox in [!UICONTROL Adobe Experience Platform] lösche? | Durch das Löschen einer Sandbox wird der Datenfluss aller [!UICONTROL Customer Journey Analytics]-Verbindungen zu Datensätzen in dieser Sandbox angehalten. Derzeit werden Verbindungen in Customer Journey Analytics, die sich auf diese Sandbox beziehen, nicht automatisch gelöscht. |
| ein Schema in [!UICONTROL Adobe Experience Platform] lösche, aber nicht den Datensatz bzw. die Datensätze, die diesem Schema zugeordnet sind? | [!UICONTROL Adobe Experience Platform] ermöglicht nicht das Löschen von Schemata, denen ein oder mehrere Datensätze zugeordnet sind. Ein Administrator mit den entsprechenden Berechtigungen kann jedoch zuerst die Datensätze und dann das Schema löschen. |
| einen Datensatz in [!UICONTROL Adobe Experience Platform] lösche? | Durch das Löschen eines Datensatzes in Adobe Experience Platform wird der Datenfluss von diesem Datensatz zu allen Verbindungen, die diesen Datensatz enthalten, angehalten. Daten aus diesem Datensatz werden nicht automatisch aus zugehörigen Customer Journey Analytics-Verbindungen gelöscht. |
| einen Datensatz in [!UICONTROL Customer Journey Analytics] lösche? | Derzeit ist es nicht möglich, einen Datensatz in einer gespeicherten Verbindung zu löschen. Dazu müssten Sie die gesamte Verbindung löschen und von Neuem beginnen. (In [!UICONTROL Adobe Experience Platform] können Sie jedoch einen Datensatz löschen.) |
| einen Batch eines Datensatzes (in [!UICONTROL Adobe Experience Platform]) lösche? | Wenn ein Batch in einem [!UICONTROL Adobe Experience Platform]-Datensatz gelöscht wird, wird er auch aus allen Customer Journey Analytics-Verbindungen entfernt, die diesen Batch enthalten.  Customer Journey Analytics wird über das Löschen von Batches in [!UICONTROL Adobe Experience Platform] benachrichtigt. |
| einen Batch lösche, **während er** in [!UICONTROL Customer Journey Analytics] aufgenommen wird? | Wenn in dem Datensatz nur ein Batch vorhanden ist, erscheinen keine Daten oder nur teilweise Daten aus diesem Batch in [!UICONTROL Customer Journey Analytics]. Die Aufnahme wird zurückgesetzt. Wenn es in dem Datensatz beispielsweise 5 Batches gibt und 3 davon bereits aufgenommen wurden, als der Datensatz gelöscht wurde, erscheinen die Daten dieser 3 Batches in [!UICONTROL Customer Journey Analytics]. |
| eine Verbindung in [!UICONTROL Customer Journey Analytics] lösche? | Eine Fehlermeldung weist darauf hin, dass<ul><li>für die gelöschte Verbindung erstellte Datenansichten nicht mehr funktionieren.</li><li> Ebenso funktionieren alle Workspace-Projekte nicht mehr, die von den Datenansichten der gelöschten Verbindung abhängig sind.</li></ul> |
| eine Datenansicht in [!UICONTROL Customer Journey Analytics] lösche? | Eine Fehlermeldung weist darauf hin, dass alle Workspace-Projekte, die von dieser gelöschten Datenansicht abhängen, nicht mehr funktionieren. |
