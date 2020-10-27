---
description: Faktoren, die sich auf die Leistung von Workspace und empfohlene Optimierungen auswirken
title: Leistungsfaktoren und Optimierung von Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: 3928307fb51d1bde628773a91d5f4e2d4e5c2a5c
workflow-type: tm+mt
source-wordcount: '2026'
ht-degree: 82%

---


# Optimieren der Analysis Workspace-Leistung

Mehrere Faktoren können die Leistung eines Projekts in Analysis Workspace beeinflussen. Damit Sie Ihr Projekt optimal planen und erstellen können, sollten Sie vor Beginn diese Faktoren kennen. Auf dieser Seite finden Sie eine Liste von Faktoren, die sich auf die Leistung auswirken und empfohlene Optimierungen, die Sie vornehmen können, um eine Spitzenleistung in Analysis Workspace sicherzustellen.

>[!IMPORTANT]
>
>Die Leistungsseite in Analysis Workspace ist in limitierter Version verfügbar. [Weitere Infos](https://docs.adobe.com/content/help/de-DE/analytics/landing/an-releases.html)

## Hilfe > Leistung in Analysis Workspace

Unter **[!UICONTROL Analysis Workspace > Hilfe > Leistung]** können Sie die Faktoren sehen, die sich auf die Leistung Ihres Projekts auswirken, einschließlich Netzwerk-, Browser- und Projektfaktoren. Um möglichst genaue Ergebnisse zu erzielen, müssen Sie das Projekt vor dem Öffnen der Seite „Leistung“ vollständig laden. Darüber hinaus können Sie die Leistungsinhalte **als CSV-Datei herunterladen**, um sie einfach mit der Adobe-Kundenunterstützung oder Ihren IT-Teams zu teilen.

>[!NOTE]
>
>Die Informationen auf der Seite „Leistung“ variieren bei jedem Öffnen des Modells, da sich Faktoren ändern können. Darüber hinaus wird die Adobe die empfohlenen Schwellenwerte weiter verfeinern, sobald mehr Daten verfügbar sind.

![](assets/performance-modal.png)

## Netzwerkfaktoren

**[!UICONTROL Hilfe > Leistungsnetzwerkfaktoren beinhalten:]**

| Faktor | Definition | Beeinflusst durch | Optimierung |
| --- | --- |--- | --- |
| Verbindung mit Adobe | Adobe sendet 10 Testaufrufe, wenn die Leistungsseite geöffnet wird. Dies stellt den Prozentsatz der erfolgreichen Aufrufe zu Adobe dar. | Lokale Netzwerkprobleme oder Probleme mit der Adobe wirken sich auf diesen Faktor aus. | Überprüfen Sie status.adobe.com, ob bekannte Service-Probleme vorliegen. Überprüfen Sie dann Ihre lokale Netzwerkverbindung. |
| Internetbandbreite | Die Schätzung der Bandbreite an Ihrem Standort durch Ihren Browser, die nur für Google Chrome getestet wurde. Der empfohlene Schwellenwert ist 2,0 MB/s. | Ihre lokale Netzwerkverbindung wirkt sich auf diesen Faktor aus. | Überprüfen Sie die lokale Netzwerkverbindung. |
| Internetlatenz | Adobe sendet 10 Testaufrufe, wenn die Leistungsseite geöffnet wird. Dies stellt die Zeitdauer dar, die durchschnittlich eine Anfrage an Adobe und deren Antwort benötigt. Einfach gesagt, es ist ein Maß dafür, wie schnell das Internet zwischen Ihrem Standort und Adobe ist. Der empfohlene Schwellenwert ist &lt; 1 Sekunde. | Lokale Netzwerkprobleme, viele offene Browser-Registerkarten oder Probleme bei Adobe wirken sich auf diesen Faktor aus. | Überprüfen Sie status.adobe.com, ob bekannte Service-Probleme vorliegen. Überprüfen Sie dann Ihre lokale Netzwerkverbindung und schließen Sie nicht verwendete Browser-Registerkarten. |

## Browser-Faktoren

**[!UICONTROL Hilfe > Leistungs-Browser-Faktoren beinhalten:]**

| Faktor | Definition | Beeinflusst durch | Optimierung |
| --- | --- | --- | --- |
| Berechnungsgeschwindigkeit | Wie schnell Ihr Computer einen Verarbeitungstest durchführt. Der empfohlene Schwellenwert ist &lt; 750 ms. | Ihre Hardware sowie gleichzeitige Programme wirken sich auf diesen Faktor aus. | Öffnen Sie den Task-Manager (PC) oder die Aktiviätsanzeige (Mac) Ihres Computers, um zu ermitteln, ob Programm geschlossen werden können. Schließen Sie dann nicht verwendete Browser-Registerkarten oder andere Programme. <br><br>Wenn diese Aktionen nicht hilfreich sind, besprechen Sie Hardware-Details mit Ihrem IT-Team. |
| Speicher verwendet | Jede Workspace-Registerkarte in einem Google Chrome-Browser verfügt über 4 GB Arbeitsspeicher (Firefox hat einen höheren Schwellenwert). Dies entspricht dem Prozentsatz des Speicherlimits, das vom aktuellen Projekt belegt wird. Der empfohlene Schwellenwert beträgt 3500 MB. Dies ist der Zeitpunkt, an dem Workspace Speicherfehler aufdeckt. | Das Arbeiten mit mehreren Registerkarten oder das Herunterladen von 50.000 Zeilen mit Daten bedeutet eine höhere Speicherbelegung. | Wenn Sie einen Speicherfehler erhalten, wird empfohlen, andere Workspace-Registerkarten zu schließen und/oder 50000 Zeilen-Downloads einzeln auszuführen. |
| Lokaler Speicher verwendet | Daten, die lokal auf Ihrem Computer zur Verwendung im Browser gespeichert werden. Jede Herkunft (z. B. experience.adobe.com) verfügt über ein Limit von 10 MB. | Analysis Workspace verwendet lokale Datenspeicherung für verschiedene Funktionen, unter anderem zum Speichern automatisch gespeicherter (vorhandener) Projekte, Benutzereinstellungen und Feature Flags. | Um sicherzustellen, dass Analysis Workspace-Funktionen nicht gestört werden, sollten Sie die lokale Datenspeicherung für die Domain „experience.adobe.com“ löschen. |
| Rendering-Geschwindigkeit | &quot;FPS&quot;steht für &quot;Frames pro Sekunde&quot;, d. h., wie oft der Browser die Seite auf Ihrem Bildschirm zeichnet. 24 FPS sind häufig das, was das menschliche Auge als Bewegung wahrnimmt. Wenn der FPS-Wert niedriger ist, treten in Workspace Rendering-Probleme auf. | Der FPS-Wert wird durch das gleichzeitige Bearbeiten vieler Workspace-Projekte auf einmal und die Größe des angezeigten Projekts beeinflusst. Andere auf Ihrem Computer ausgeführte Programme können Auswirkungen haben, wie Streaming, Hintergrund-Scanner usw. Darüber hinaus wirkt sich Ihre Hardware auf diesen Faktor aus. | Öffnen Sie den Task-Manager (PC) oder die Aktiviätsanzeige (Mac) Ihres Computers, um zu ermitteln, ob Programm geschlossen werden können. Schließen Sie dann nicht verwendete Browser-Registerkarten oder andere Programme. <br><br>Wenn diese Aktionen nicht hilfreich sind, besprechen Sie Hardware-Details mit Ihrem IT-Team. |

## Projektfaktoren

**[!UICONTROL Hilfe > Leistungsprojektfaktoren beinhalten:]**

| Faktor | Definition | Optimierung |
| --- | --- | --- |
| Anzahl der Abfragen | Die Gesamtzahl der Abfragen (Anfragen) an Adobe, die zum Abrufen der im Projekt angezeigten Daten vorgenommen wurden. Zu den Abfragen gehören Ranganfragen für Tabellen, Anomalieerkennung, Wortgrafiken, Komponenten in der linken Leiste und mehr. Schließt ausgeblendete Bedienfelder und Visualisierungen aus. Der empfohlene Schwellenwert ist 100. | Vereinfachen Sie Ihr Projekt nach Möglichkeit, indem Sie Daten in verschiedene Projekte aufteilen, die einem bestimmten Zweck oder Interessenten dienen. Verwenden Sie Tags, um Projekte in Themen zu organisieren, und verwenden Sie [direkte Verknüpfungen](/help/analysis-workspace/curate-share/shareable-links.md), um ein internes Inhaltsverzeichnis zu erstellen, damit die Interessierte leichter finden können, wonach sie suchen. |
| Erweiterte Bedienfelder (von der Gesamtzahl der Bedienfelder) | Die Anzahl der erweiterten Bedienfelder von der Gesamtzahl der Bedienfelder im Projekt. Der empfohlene Schwellenwert ist 5. | Nachdem Sie Schritte zur Vereinfachung des Projekts unternommen haben, reduzieren Sie die Bedienfelder im Projekt, die beim Laden nicht angezeigt werden müssen. Wenn das Projekt geöffnet wird, werden nur erweiterte Bedienfelder verarbeitet. Reduzierte Felder werden erst verarbeitet, wenn der Nutzer sie erweitert. |
| Erweiterte Visualisierungen (aus der Gesamtzahl der Visualisierungen) | Die Anzahl der erweiterten Tabellen und Visualisierungen aus der Gesamtsumme im Projekt. Schließt verborgene Datenquellen aus. Der empfohlene Schwellenwert ist 15. | Nachdem Sie Schritte zur Vereinfachung des Projekts unternommen haben, reduzieren Sie die Visualisierungen in Ihrem Projekt, die beim Laden nicht angezeigt werden müssen. Priorisieren Sie die Visuals, die für den Verbraucher des Berichts am wichtigsten sind, und teilen Sie die unterstützenden Visuals bei Bedarf in ein separates, detaillierteres Bedienfeld oder Projekt auf. |
| Anzahl der Freiformzellen | Die Gesamtzahl der Freiform-Tabellenzellen im Projekt, berechnet durch Zeilen * Spalten in allen Tabellen. Schließt verborgene Datenquellen aus. Der empfohlene Schwellenwert ist 4000. | Reduzieren Sie die Anzahl der Spalten in Ihrer Tabelle auf die relevantesten Datenpunkte. Reduzieren Sie die Anzahl der Zeilen in Ihrer Tabelle, indem Sie die Anzahl der angezeigten Zeilen anpassen, einen Tabellenfilter oder ein Segment anwenden. |
| Verfügbare Komponenten | Die Gesamtzahl der in der linken Leiste des Projekts abgerufenen Komponenten für alle Report Suites im Projekt. Der empfohlene Schwellenwert ist 2000. | Sprechen Sie mit Ihrem Produktadministrator über das Erstellen einer kuratierten Virtual Report Suite, die über einen stärker auf Ihre Bedürfnisse zugeschnittenen Satz an Komponenten verfügt. |
| Verwendete Komponenten | Die Gesamtzahl der im Projekt verwendeten Komponenten. Der empfohlene Schwellenwert ist 100. | Die Anzahl der verwendeten Komponenten hat keinen direkten Einfluss auf die Leistung. Die Komplexität dieser Komponenten wird jedoch zur Leistung des Projekts beitragen. Siehe empfohlene Optimierungen im Abschnitt &quot;Weitere Faktoren&quot;. |
| Längster Datumsbereich | Dieser Faktor zeigt den längsten Datumsbereich an, der für das Projekt verwendet wurde. Der empfohlene Schwellenwert ist 1 Jahr. | Rufen Sie möglichst nicht mehr Daten ab, als Sie benötigen. Schränken Sie den Kalender des Bedienfelds auf die relevanten Daten für Ihre Analyse ein oder verwenden Sie Datumsbereichskomponenten (violette Komponenten) in Ihren Freiform-Tabellen. In einer Tabelle verwendete Datumsbereiche überschreiben den Datumsbereich des Bedienfelds. Beispielsweise können Sie den Tabellenspalten „Letzter Monat“, „Letzte Woche“ und „Gestern“ hinzufügen, um diese spezifischen Datenbereiche anzufordern. Weitere Informationen zu Datumsbereichen in Analysis Workspace erhalten Sie in [diesem Video](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/date-ranges-and-calendar-in-analysis-workspace.html). <br><br>Minimieren Sie außerdem die Anzahl der im Projekt verwendeten Jahresvergleiche. Bei der Berechnung eines Jahresvergleichs werden die gesamten 13 Monate von Daten zwischen den betrachteten Monaten berücksichtigt. Dies hat die gleiche Auswirkung wie die Änderung des Datumsbereichs des Bedienfelds auf 13 Monate. |

## Zusätzliche Faktoren

Zu den weiteren Faktoren, die nicht unter Hilfe > Leistung aufgeführt sind, zählen:

| Faktor | Definition | Beeinflusst durch | Optimierung |
| --- | --- | --- | --- |
| Filterkomplexität | Komplexe Filter können sich erheblich auf die Projektleistung auswirken. | Zu den Faktoren, die einem Filter Komplexität hinzufügen (in absteigender Reihenfolge der Auswirkungen) gehören: <ul><li>Operatoren von „enthält“, „enthält beliebige von“, „stimmt überein mit“, „beginnt mit“ oder „endet mit“ </li><li>Sequenzielle Filter, insbesondere wenn Dimensionsbeschränkungen (In/Nach) verwendet werden </li><li>Anzahl der eindeutigen Dimensionselemente innerhalb der Dimensionen, die im Segment verwendet werden (z. B.: Seite = „A“, wenn Seite 10 eindeutige Elemente hat, ist schneller als Seite = „A“, wenn Seite 100000 eindeutige Elemente hat) </li><li>Anzahl der verschiedenen verwendeten Dimensionen (z. B.: Seite = „Startseite“ und Seite = „Suchergebnisse“ sind schneller als eVar 1 = „rot“ und eVar 2 = „blau“)</li><li>Viele OR-Operatoren (anstelle von AND)</li><li>Verschachtelte Container mit unterschiedlichem Umfang (z. B. Hit innerhalb des Besuchs innerhalb des Besuchers)</li></ul> | Einige der Komplexitätsfaktoren können nicht verhindert werden, aber suchen Sie nach Möglichkeiten, die Komplexität Ihrer Filter zu reduzieren. Im Allgemeinen gilt, je spezifischer Sie mit Ihren Filterkriterien sein können, desto besser. Beispiel:<ul><li>Bei Containern ist die Verwendung eines einzelnen Containers am oberen Rand des Segments schneller als die Verwendung einer Reihe verschachtelter Container</li><li>Bei Operatoren ist „stimmt überein mit“ schneller als „enthält“ und „entspricht beliebigen von“ ist schneller als „enthält beliebige von“</li><li>Mit vielen Kriterien sind AND-Operatoren schneller als eine Reihe von OR-Operatoren.</li><li>Suchen Sie nach Möglichkeiten, viele OR-Anweisungen in eine einzelne Anweisung „entspricht einem von“ zu reduzieren </li></ul> |
| Komplexität der Visualisierung (Filter, Metriken) | Die Art der Visualisierung (z. B. Fallout oder Freiform-Tabelle), die einem Projekt hinzugefügt wird, hat keinen großen Einfluss auf die Projektleistung. Die Komplexität der Visualisierung erhöht die Verarbeitungszeit. | U. a. machen folgende Faktoren eine Visualisierung komplexer:<ul><li>Angeforderter Datenbereich</li><li>Anzahl der angewandten Filter; zum Beispiel Filter, die als Zeilen einer Freiformtabelle verwendet werden</li><li>Einsatz komplexer Filter</li><li>[Statische Elementzeilen oder Spalten in Freiformtabellen](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md)</li><li>Auf Zeilen angewandte Filter in Freiformtabellen</li><li>Anzahl der enthaltenen Metriken, insbesondere berechnete Metriken, die Filter verwenden</li></ul> | Wenn Sie bemerken, dass Ihre Projekte nicht so schnell geladen werden, wie Sie möchten, versuchen Sie, einige Filter nach Möglichkeit durch eVars und Filter zu ersetzen.<br><br>Wenn Sie ständig Segmente und berechnete Metriken für Datenpunkte verwenden, die für Ihr Unternehmen wichtig sind, sollten Sie versuchen, Ihre Implementierung zu verbessern, um diese Datenpunkte direkter zu erfassen. Mit einem Tag-Manager wie Adobe Experience Platform Launch und den Verarbeitungsregeln von Adobe sind Änderungen an der Implementierung schneller und leichter umzusetzen. |

## Allgemeine Fehlermeldungen

Bei der Interaktion mit Analysis Workspace können Fehler auftreten, die auch die Leistung beeinflussen. Im Folgenden sind die häufigsten Fehlertypen, die Gründe dafür und Optimierungen aufgeführt, die vorgenommen werden können.

| Fehlermeldung | Grund | Optimierung |
| --- | --- | --- |
| [!UICONTROL Die Report Suite verzeichnet derzeit ein ungewöhnlich hohes Aufkommen von Berichtsdaten. Versuchen Sie es später erneut.] | Ihr Unternehmen versucht, zu viele Anfragen gleichzeitig für eine bestimmte Report Suite auszuführen. Zu diesem Fehler gehören API-Anfragen, geplante Projekte, terminierte Berichte, terminierte Warnhinweise und gleichzeitige Benutzer, die Reporting-Anfragen ausführen. | Verteilen Sie Ihre Anfragen und Zeitpläne für die Report Suite gleichmäßig über den Tag. |
| [!UICONTROL Es ist ein Systemfehler aufgetreten. Melden Sie eine Anfrage an den Kundendienst unter Hilfe > senden Sie ein Support-Ticket und geben Sie Ihren Fehler-Code an.] | Adobe hat ein Problem, das behoben werden muss. | Senden Sie den Fehler-Code an die Kundenunterstützung. |
| [!UICONTROL Die Anfrage ist zu komplex.] | Ihre Reporting-Anfrage ist zu groß und kann nicht ausgeführt werden. Gründe für diesen Fehler sind Zeitüberschreitungen aufgrund der Anfragengröße, zu viele übereinstimmende Elemente in einem Segment oder Suchfilter, zu viele eingeschlossene Metriken, inkompatible Dimensions- und Metrikkombinationen usw. | Vereinfachen Sie Ihre Anfrage, indem Sie einige Spalten oder Zeilen in der Tabelle entfernen oder die Tabelle in separate Anfragen aufteilen. |
| [!UICONTROL Eines der Segmente oder die Suche in dieser Visualisierung enthält eine Textsuche, die zu viele Ergebnisse zurückgab.] | Ihre Segmentkriterien oder Berichtsfilter sind zu breit angelegt. | Schränken Sie die Suchtextkriterien ein und führen Sie die Anfrage erneut aus. |
| [!UICONTROL Diese Dimension unterstützt nicht-standardmäßige Zuordnungsmodelle derzeit nicht.] | Nicht standardmäßige Zuordnung wird für die verwendete Dimension nicht unterstützt. | Ersetzen Sie die Dimension in Ihrer Tabelle durch eine Dimension, die mit [Attribution IQ](/help/analysis-workspace/attribution/overview.md) kompatibel ist. |
| [!UICONTROL Ihre Anfrage schlug aufgrund zu vieler Spalten oder vorkonfigurierter Zeilen fehl.] | Ihre Tabelle enthält zu viele Freiformzellen (Zeile * Spalten). | Entfernen Sie Spalten oder Zeilen in der Tabelle oder erwägen Sie, die Tabelle in separate Anfragen zu unterteilen. |
