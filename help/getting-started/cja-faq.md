---
title: FAQ zu Customer Journey Analytics
description: Customer Journey Analytics – häufig gestellte Fragen
translation-type: tm+mt
source-git-commit: 65b51ff6a792a0407d8c73794c1bab4a6e3f0fa1
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 43%

---


# Häufig gestellte Fragen

## Voraussetzungen

| Frage | Antwort |
| --- | --- |
| Benötige ich [!UICONTROL Private Device Graph] oder [!UICONTROL Device Coop] für [!UICONTROL Customer Journey Analytics]? | Nein, [!UICONTROL Private Device Graph] oder [!UICONTROL Device Coop] sind für [!UICONTROL Customer Journey Analytics] nicht erforderlich. Sie werden aktuell noch nicht unterstützt. |
| Benötige ich [!UICONTROL Experience Cloud-ID] (ECID) für [!UICONTROL Customer Journey Analytics]? | Nein, [!UICONTROL Customer Journey Analytics] unterstützt alle IDs in einem Datensatz, unabhängig davon, ob es sich um eine ECID oder eine andere ID handelt. |
| Was ist, wenn ich meine Daten vor [!UICONTROL Customer Journey Analytics] ETL (Extrahieren, Transformieren, Laden) hochladen muss? | Wenn Sie Ihre Daten transformieren müssen, bevor sie in AEP eingefügt werden, arbeiten Sie mit einem ETL-Partner (Unifi oder Informatica) zusammen. Wenn Sie ETL benötigen, nachdem die Daten bereits erfasst wurden, stehen Ihnen [!UICONTROL Adobe Experience Platform Abfrage Services] einige eingeschränkte Optionen zur Verfügung. |

## Sticken von Daten

| Frage | Antwort |
| --- | --- |
| Kann [!UICONTROL Customer Journey Analytics] Daten über Geräte oder über Datensätze hinweg zusammenfügen? | Ja. [!UICONTROL Customer Journey Analytics] ist ein Analysesystem, in dem die eigene ID verwendet werden muss. Im November 2020 haben wir eine Heftlösung herausgegeben. Weitere Infos. |
| Wird das Stitching vom anonymen Verhalten zum authentifizierten Verhalten unterstützt? | Nein, noch nicht. |

## Daten in [!UICONTROL Customer Journey Analytics] einbringen

| Frage | Antwort |
| --- | --- |
| Kann ich Daten aus verschiedenen [!UICONTROL Adobe Experience Platform]-Sandboxen in einer [!UICONTROL Customer Journey Analytics]-Verbindung kombinieren? | Nein, Sie können nicht über Sandboxes hinweg auf Daten zugreifen. Sie können nur Datensätze kombinieren, die sich innerhalb derselben Sandbox befinden. [Weitere Informationen ...](https://docs.adobe.com/content/help/de-DE/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| Welche Latenz wird für [!UICONTROL Customer Journey Analytics] bei [!UICONTROL Adobe Experience Platform] erwartet? | <ul><li>Unter normaler Belastung: &lt; 60 Minuten <br>**Hinweis:** Bei ungewöhnlich hohem Datenfluss durch die Pipeline kann es bis zu 24 Stunden dauern.</li><li>Aufstockungsdaten (bis zu 13 Monate Daten, unabhängig von der Größe): &lt; 4 Wochen</li></ul> |
| Wie werden in [!UICONTROL Customer Journey Analytics] Online-Daten mit Offline-Daten verbunden? | [!UICONTROL Customer Journey Analytics] ist ein Analysesystem, in dem die eigene ID verwendet werden muss. Solange die Personen-ID zwischen Datensätzen übereinstimmt, kann [!UICONTROL Customer Journey Analytics] Segmente, Zuordnungen, Flüsse, Fallout usw. verbinden. über Datensätze hinweg miteinander verbinden. |
| Wie bringe ich meine Offline-Daten in [!UICONTROL Customer Journey Analytics] ein? | Sie müssen zuerst alle Daten in die Experience Platform bringen, bevor Sie sie mit [!UICONTROL Customer Journey Analytics] verwenden können. Das Datenerfassungs-Team der Experience Platform bietet bei Bedarf Empfehlungen oder eine Beratung für Sie an. |
| Wie erhalte ich [!UICONTROL Adobe Analytics]-Daten in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe ] Analytics-Daten können über den  [Adobe Analytics Source Connector](https://docs.adobe.com/content/help/de-DE/experience-platform/sources/connectors/adobe-applications/analytics.html) mit der Experience Platform verbunden werden. Die meisten [!UICONTROL Adobe Analytics]-Felder werden im XDM-Format übertragen, andere Felder sind jedoch noch nicht verfügbar (z. B. [!UICONTROL Marketing-Kanal]-Dimensionen). |
| Wie lange dauert es, bis Datensatzelemente in einer Datenansicht zusammengefasst werden? | Ein paar Stunden für eine erste Ansicht und ein paar Tage, um die Daten der letzten 13 Monate einzufügen. |
| Sind PII-Daten notwendig, um Verbindungen zwischen den Daten herzustellen? | Nein, Sie können eine beliebige ID verwenden, einschließlich eines Hash einer Kunden-ID, bei der es sich nicht um personenbezogene Daten handelt. |

## Traditionelle Komponenten [!UICONTROL Adobe Analytics]

| Frage | Antwort |
| --- | --- |
| Was bedeutet das für unser traditionelles [!UICONTROL Adobe Analytics] Produkt? | [!UICONTROL Customer Journey Analytics ist ein Analytics-Produkt der nächsten Generation. ] Die Umstellung von unseren aktuellen Produkten auf [!UICONTROL Customer Journey Analytics] wird Jahre dauern und viel Koordinierung erfordern. Weitere Informationen finden Sie unter [Customer Journey Analytics-Funktionsunterstützung](/help/getting-started/cja-aa.md). |
| Kann ich Segmente von [!UICONTROL Customer Journey Analytics] für AEP oder andere Lösungen freigeben? | Noch nicht. Wir untersuchen neue, innovative Möglichkeiten, Segmente von [!UICONTROL Customer Journey Analytics] in AEP zu teilen, die keine so lange Verzögerung aufweisen. Sie können diese Einschränkung umgehen, indem Sie das Ergebnis von Abfragediensten für Unified Profil freigeben. |
| Was ist mit meiner alten eVar-Einstellung passiert? | eVars, Props und Ereignis im klassischen Adobe Analytics-Sinne existieren nicht mehr in [!UICONTROL Customer Journey Analytics]. Es gibt unbegrenzte Schemaelemente (Dimensionen, Metriken, Listenfelder). Alle Zuordnungseinstellungen, die Sie bisher während des Datenerfassungsprozesses angewendet haben, werden jetzt bei der Abfrage angewendet. |
| Wo sind jetzt meine Einstellungen für die Sitzungs- und Variablenpersistenz? | [!UICONTROL Customer Journey Analytics verwendet alle diese Einstellungen zur Berichtszeit. Diese Einstellungen sind jetzt in Datenansichten verfügbar. ] Änderungen an diesen Einstellungen sind jetzt rückwirkend. Jetzt sind mehrere Versionen verfügbar, indem Sie mehrere Datenansichten verwenden. |
| Was passiert mit den bereits vorhandenen Segmenten/berechneten Metriken? | [!UICONTROL Customer Journey Analytics verwendet keine eVars, Props oder Ereignisse mehr und verwendet stattdessen ein AEP-Schema. ] Das bedeutet, dass keine der vorhandenen Segmente oder Berechnungsmetriken mit [!UICONTROL Customer Journey Analytics] kompatibel sind. |
| Wie behandelt [!UICONTROL Customer Journey Analytics] `Uniques Exceeded` Einschränkungen? | [!UICONTROL In Customer Journey Analytics gibt es keine Beschränkungen hinsichtlich eindeutiger Werte, sodass Sie sie nicht beachten müssen.] |
| Kann ich als bestehender [!DNL Data Workbench]-Kunde jetzt zu Customer Journey Analytics wechseln? | Das hängt von Ihrer aktuellen Situation ab. Wenn Sie den Unified Customer Process (UCP) häufig benötigen, sollten Sie warten, bis Stitching implementiert wurde. Wenn Sie bereits eine hohe Kundenauthentifizierungsrate haben, wenn Sie alle Ihre Daten an einem Ort speichern möchten oder wenn Sie eVars eliminieren möchten, ist Customer Journey Analytics möglicherweise eine gute Wahl. |

## Auswirkungen des Löschens von Datenkomponenten

Was die Streichung betrifft, so geht es um sechs Komponenten: Sandbox-, Schema-, Dataset-, Verbindungs-, Daten-Ansicht- und Workspace-Projekte. Im Folgenden sind einige mögliche Szenarios zum Löschen einer dieser Komponenten aufgeführt:

| Was ist, wenn ich... | Dies geschieht... |
| --- | --- |
| Eine Sandbox in [!UICONTROL Adobe Experience Platform] löschen? | Durch Löschen einer Sandbox wird der Datenfluss zu allen [!UICONTROL Customer Journey Analytics]-Verbindungen zu Datensätzen in dieser Sandbox gestoppt. Derzeit werden Verbindungen in CJA, die an diese Sandbox gebunden sind, nicht automatisch gelöscht. |
| Löschen Sie ein Schema in [!UICONTROL Adobe Experience Platform], aber nicht den Datensatz/die Daten, die diesem Schema zugeordnet sind? | [!UICONTROL Adobe Experience ] Plattform ermöglicht nicht das Löschen von Schemas, denen ein oder mehrere Datasets zugeordnet sind. Ein Administrator mit den entsprechenden Rechten kann die Datensätze jedoch zuerst löschen und dann das Schema löschen. |
| Löschen Sie einen Datensatz in [!UICONTROL Adobe Experience Platform]? | Durch das Löschen eines Datensatzes in AEP wird der Datenfluss von diesem Datensatz zu allen Verbindungen, die diesen Datensatz enthalten, gestoppt. Daten aus diesem Datensatz werden nicht automatisch aus den zugehörigen CJA-Verbindungen gelöscht. |
| Löschen Sie einen Datensatz in [!UICONTROL Customer Journey Analytics]? | Derzeit ist es nicht möglich, einen Datensatz in einer gespeicherten Verbindung zu löschen. Sie müssen die gesamte Verbindung und den Beginn löschen. (Sie können einen Datensatz jedoch unter [!UICONTROL Adobe Experience Platform] löschen.) |
| Stapel aus einem Datensatz löschen (in [!UICONTROL Adobe Experience Platform])? | Wenn ein Stapel aus einem [!UICONTROL Adobe Experience Platform]-Datensatz gelöscht wird, wird derselbe Stapel aus allen CJA-Verbindungen entfernt, die diesen spezifischen Stapel enthalten.  CJA wird über Löschungen von Stapeln in [!UICONTROL Adobe Experience Platform] benachrichtigt. |
| Löschen Sie einen Stapel **während er in [!UICONTROL Customer Journey Analytics] aufgenommen wird?** | Wenn der Datensatz nur einen Stapel enthält, werden keine Daten oder Teildaten aus diesem Stapel in [!UICONTROL Customer Journey Analytics] angezeigt. Die Erfassung wird rückgängig gemacht. Wenn der Datensatz beispielsweise 5 Stapel enthält und 3 davon bereits beim Löschen des Datensatzes aufgenommen wurden, werden die Daten aus diesen 3 Stapeln in [!UICONTROL Customer Journey Analytics] angezeigt. |
| Löschen Sie eine Verbindung in [!UICONTROL Customer Journey Analytics]? | Eine Fehlermeldung weist darauf hin, dass<ul><li>Für die gelöschte Verbindung erstellte Ansichten funktionieren nicht mehr.</li><li> Ebenso funktionieren alle Workspace-Projekte, die von den Ansichten der gelöschten Verbindung abhängig sind, nicht mehr.</li></ul> |
| Löschen Sie eine Daten-Ansicht in [!UICONTROL Customer Journey Analytics]? | Eine Fehlermeldung gibt an, dass alle Workspace-Projekte, die von dieser gelöschten Ansicht abhängen, nicht mehr funktionieren. |
