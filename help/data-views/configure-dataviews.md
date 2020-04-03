---
title: Ansichten und Attribution von Daten konfigurieren
description: Beschreibt das Erstellen einer Ansicht zu einem Plattformdatensatz in Customer Journey Analytics
translation-type: tm+mt
source-git-commit: 71d666b89860813d4e578c2f3c786da8d471a874

---


# Komponenten- und Zuordnungseinstellungen

eVars, Props und Ereignisse im herkömmlichen Adobe Analytics-Sinne gibt es in Customer Journey Analytics nicht mehr. Stattdessen verfügen Sie über unbegrenzte Schema-Elemente (Dimensionen, Metriken, Listen). Alle Zuordnungseinstellungen, die Sie während des Datenerfassungsprozesses für eVars und Props verwendet haben, werden jetzt zur Abfrage angewendet - auch als Berichtszeitverarbeitung bezeichnet.

Klicken Sie [hier](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/attribution-settings-in-data-views.html) , um eine Videoübersicht zu erhalten.

Berücksichtigen Sie dies, bevor Sie Zuordnungseinstellungen anwenden:

* In der Benutzeroberfläche &quot;Data Ansichten&quot;geben Sie die Standardzuordnung an. **Hinweis**: Zu einem späteren Zeitpunkt können Sie diese Einstellungen in Workspace-Projekten überschreiben. Diese Funktion ist jedoch derzeit nicht verfügbar.

* Zuordnungseinstellungen in Customer Journey Analytics sind nicht destruktiv und rückwirkend. Mit anderen Worten, Sie können Ihren Datensätzen in Customer Journey Analytics keinen irreparablen Schaden zufügen. Auch wenn Sie versehentlich etwas löschen, können Sie jederzeit zu Experience Platform zurückkehren und den Datensatz wieder in das Programm aufnehmen. (Beachten Sie jedoch, dass die Wiedereinsetzung des Datensatzes zusätzliche Kosten verursacht.)

* Wenn Sie eine Dimension wie eine herkömmliche eVar (Konversionsvariable) &quot;benehmen&quot;möchten, sollten Sie sie standardmäßig mit der Zuordnung &quot;Last Touch-Besuch&quot;konfigurieren.

* Wenn Sie eine Dimension wie eine herkömmliche Prop (Traffic-Variable) &quot;benehmen&quot;möchten, sollten Sie sie standardmäßig mit &quot;Gleich Touch&quot;-Zuordnung konfigurieren.

* Wenn Sie möchten, dass sich eine Metrik wie eine Standardmetrik &quot;verhält&quot;, sollten Sie nichts ändern.

* Zuordnungseinstellungen für Metriken setzen die Zuordnungseinstellungen für Dimensionen außer Kraft.

## Festlegen von Komponenten- und Zuordnungseinstellungen

Nachdem Sie die Einstellungen [für die Ansicht der Daten](/help/data-views/create-dataview.md) festgelegt und gespeichert und Komponenten hinzugefügt haben, können Sie, falls gewünscht, Zuordnungseinstellungen angeben. Sie können Zuordnungs-/Ablauf-/Lookback-Einstellungen für Dimensionen und Metriken angeben. Wenn Sie z. B. möchten, dass die Zuordnung einer Dimension beibehalten wird, sollten Sie eine benutzerdefinierte Ablaufzeit festlegen. Wenn Sie z. B. die Dimension &quot;Rückverfolgungscode&quot;(eine Variable der Kampagne) auf &quot;Letztkontakt&quot;-Zuordnung setzen möchten, um eine Woche lang bestehen zu bleiben, fügen Sie einen benutzerdefinierten Ablauf von 1 Woche hinzu.

>[!IMPORTANT]
>Sie können festlegen, dass keine Zuordnung/kein Ablauf festgelegt wird. In diesem Fall verhalten sich Dimensionen wie Props (&quot;Same Touch&quot;-Zuordnungsmodell). Metriken ohne Zuordnungseinstellungen übernehmen die Einstellungen für die Dimension, auf die diese Metrik angewendet wird.

![](assets/edit-component.png)

1. Geben Sie Komponenten- und Zuordnungseinstellungen für Dimensionen und Metriken an. Informationen zu den einzelnen Einstellungen finden Sie unten.

1. Klicken Sie auf **[!UICONTROL Save]** , um Ihre Daten-Ansicht zu speichern.


### Komponenteneinstellung

Sie können den Namen der Metrik oder Dimension in etwas benutzerfreundlicheres ändern. Beachten Sie, dass sich der zugrunde liegende Name nicht ändert, sondern nur der Anzeigename.

### Zuordnungsmodell

Das Modell beschreibt die Verteilung der Konvertierungen an die Ereignis einer Gruppe. Zum Beispiel Erstkontakt oder Letztkontakt Legt fest, wie Customer Journey Analytics Gutschriften für ein Erfolgsereignis zuweist, wenn eine Variable mehrere Ereignis vor dem Ereignis erhält.

| Benutzeroberflächensymbol | Attributionsmodell | Definition | Verwendungsbereiche |
| --- | --- | --- | --- |
| ![Letztkontakt](assets/last_touch1.png) | Letztkontakt | 100 % werden dem Touchpoint zugeschrieben, der zuletzt vor der Konversion aufgetreten ist. | Das einfachste und gängigste Attributionsmodell. Es wird häufig für Konversionen mit einem kurzen Überlegungszyklus verwendet. Letztkontakt wird häufig durch Teams verwendet, die Suchmaschinen-Marketing verwalten oder Schlüsselwörter für die interne Suche analysieren. |
| ![Erstkontakt](assets/first_touch.png) | Erstkontakt | 100 % werden dem Touchpoint zugeschrieben, der zuerst im Attributions-Lookback-Fenster angezeigt wird. | Ein weiteres allgemeines Attributionsmodell, das sich für die Analyse von Marketing-Kanälen eignet, die das Markenbewusstsein oder die Kundenakquise ankurbeln sollen. Es wird häufig von Teams für Display- oder Social-Media-Marketing verwendet, eignet sich jedoch auch für das Bewerten der Produktempfehlungseffektivität vor Ort. |
| ![Selber Kontakt](assets/same_touch.png) | Selber Kontakt | 100 % werden dem Hit zugeschrieben, bei dem die Konversion erfolgte. Wenn ein Touchpoint nicht bei demselben Hit erfolgt wie eine Konversion, wird er unter „Keine“ zusammengefasst. | Dies ist ein hilfreiches Modell beim Evaluieren des zum Zeitpunkt der Konversion angezeigten Inhalts oder Kundenerlebnisses. Produkt- oder Designteams verwenden dieses Modell oftmals, um die Effektivität einer Seite zu bewerten, auf der die Konversion auftritt. |
| ![Linear](assets/linear.png) | Linear | Ermöglicht dieselbe Gewichtung für jeden Touchpoint, der vor einer Konversion erfolgte. | Dieses Modell eignet sich für Konversionen mit längeren Überlegungszyklen oder Kundenerlebnissen, für die eine häufigere Kundeninteraktion erforderlich ist. Es wird oft von Teams genutzt, die die Benachrichtigungseffektivität von Apps messen, oder mit abonnementbasierten Produkten verwendet. |
| ![U-förmig](assets/u_shaped.png) | U-förmig | Der ersten Interaktion werden 40 % zugeschrieben, der letzten Interaktion 40 %. Die verbleibenden 20 % werden auf alle dazwischen liegenden Touchpoints aufgeteilt. Bei Konversionen mit einem einzigen Touchpoint werden diesem 100 % zugeschrieben. Bei Konversionen mit zwei Touchpoints werden jedem 50 % zugeschrieben. | Ein passendes Modell für diejenigen, die Interaktionen schätzen, die eine Konversion gestartet oder beendet haben, aber dennoch unterstützende Interaktionen erkennen möchten. Die U-förmige Attribution wird oft durch Teams verwendet, die einen ausgeglicheneren Ansatz verwenden, jedoch Kanälen mehr Gewichtung zuteilen möchten, die eine Konversion gestartet oder beendet haben. |
| ![J-förmig](assets/j_shaped.png) | J-förmig | Der letzten Interaktion werden 60 % zugeschrieben, der ersten Interaktion werden 20 % zugeschrieben. Die restlichen 20 % werden auf alle dazwischen liegenden Touchpoints aufgeteilt. Bei Konversionen mit einem einzigen Touchpoint werden diesem 100 % zugeschrieben. Bei Konversionen mit zwei Touchpoints der letzten Interaktion 75 % zu geschrieben und der ersten 25 %. | Dieses Modell ist ideal für diejenigen, die Eröffnung und Abschluss priorisieren, sich aber auf den Abschluss konzentrieren möchten. Die J-förmige Attribution wird oft durch Teams verwendet, die einen ausgeglicheneren Ansatz verwenden und Kanälen mehr Gewichtung zuteilen möchten, auf denen eine Konversion abgeschlossen wurde. |
| ![Umgekehrt J-förmig](assets/inverse_j.png) | Umgekehrtes J | Der ersten Interaktion werden 60 % zugeschrieben, der letzten Interaktion 20 %. Die verbleibenden 20 % werden auf alle dazwischen liegenden Touchpoints aufgeteilt. Bei Konversionen mit einem einzigen Touchpoint werden diesem 100 % zugeschrieben. Bei Konversionen mit zwei Touchpoints der ersten Interaktion 75 % zu geschrieben und der letzten 25 %. | Dieses Modell ist ideal für diejenigen, die Eröffnung und Abschluss priorisieren, sich aber auf die Eröffnung konzentrieren möchten. Die Attribution mit umgekehrtem J wird oft durch Teams verwendet, die einen ausgeglicheneren Ansatz verwenden und Kanälen mehr Gewichtung zuteilen möchten, auf denen eine Konversion begonnen wurde. |
| ![Benutzerspezifisch](assets/custom.png) | Benutzerspezifisch | Ermöglicht Ihnen die Angabe der Gewichtungen, die Sie für Erstkontakt-Punkte, Letztkontakt-Punkte und dazwischen liegende Touchpoints festlegen möchten. Die angegebenen Werte werden auf 100 % normalisiert, selbst wenn die eingegebenen benutzerdefinierten Zahlen zusammen nicht 100 ergeben. Bei Konversionen mit einem einzigen Touchpoint werden diesem 100 % zugeschrieben. Bei Interaktionen mit zwei Touchpoints wird der mittlere Parameter ignoriert. Die ersten und letzten Touchpoints werden dann auf 100 % normalisiert und die Gewichtung wird entsprechend zugeschrieben. | Dieses Modell ist perfekt für diejenigen, die eine vollständige Kontrolle über ihr Attributionsmodell wünschen und spezielle Bedürfnisse haben, die andere Zuordnungsmodelle nicht erfüllen. |
| ![Zeitverfall](assets/time_decay.png) | Zeitverfall | Folgt einem exponentiellen Abfall mit einem benutzerdefinierten Parameter für die Halbwertszeit, wobei der Standardwert 7 Tage ist. Die Gewichtung der einzelnen Kanäle hängt von der Zeit ab, die zwischen dem Beginn des Touchpoints und der letztendlichen Konversion verstrichen ist. Die Formel, die zur Bestimmung der Gewichtung verwendet wird, lautet `2`<sup>`(-t/halflife)`</sup>, wobei `t` die Zeit zwischen einem Touchpoint und einer Konversion ist. Alle Touchpoints werden dann auf 100 % normalisiert. | Ideal für Teams, die regelmäßig Videowerbung betreiben oder Marketing im Zusammenhang mit Ereignissen mit festem Datum durchführen. Je länger eine Konversion nach einem Marketing-Ereignis erfolgt, desto geringer ist die zugeschriebene Gewichtung. |
| ![Beitrag](assets/participation.png) | Beitrag | 100 % Gewichtung für alle eindeutigen Touchpoints. Die Gesamtanzahl der Konversionen ist im Vergleich zu anderen Attributionsmodellen überhöht. Durch den Beitrag werden Kanäle dedupliziert, die mehrmals angezeigt werden. | Ausgezeichnet, um zu verstehen, wie häufig Kunden einer bestimmten Interaktion ausgesetzt sind. Medienunternehmen verwenden dieses Modell häufig zur Berechnung der Content Velocity. Einzelhandelsunternehmen verwenden dieses Modell oft, um zu verstehen, welche Teile ihrer Site für die Konversion von entscheidender Bedeutung sind. |

### Gültigkeit

Gibt einen Zeitraum oder ein Ereignis an, nach dem der Dimensionswert abläuft (d. h. keine Gutschrift mehr für Ereignis mit Erfolg erhält). Sie können den Zuordnungsablauf auf Sitzungs-, Personen- oder benutzerspezifischer Ebene festlegen.

| Einstellung | Definition |
|---|---|
| Sitzung | Zuvor als &quot;Besuchsebene&quot;bezeichnet. Umrechnungselemente, die über die Ansicht oder Sitzung hinausgehen, sind nicht mit der Dimension oder Metrik verknüpft. |
| Person (Berichte) | Zuvor als &quot;Besucher&quot;bezeichnet. Umrechnungselemente, die nicht mit dieser Person verbunden sind, sind nicht mit der Dimension oder Metrik verknüpft. |
| Benutzerdefinierte Zeit | Geben Sie die benutzerdefinierten Minuten, Stunden, Tage, Monate oder Quartale an. Konversionsdaten, die über den angegebenen Zeitraum hinausgehen, werden nicht mit der Dimension oder Metrik verknüpft. |

Weitere Informationen finden Sie im Dokument [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html).

### Lookback-Fenster

Ein Lookback-Fenster ist der Zeitraum, der für eine Konversion rückblickend bei der Erfassung von Touchpoints berücksichtigt werden sollte. Attributionsmodelle, die der ersten Interaktion mehr Gewicht zuschreiben, sehen bei der Anzeige verschiedener Lookback-Fenster größere Unterschiede.

* **Sitzung:** Sieht bis zum Beginn einer Sitzung zurück, in der eine Konversion stattgefunden hat. Die Lookback-Fenster für Besuche sind schmal, da sie nicht über die Sitzung hinausblicken. Sitzungs-Lookback-Fenster berücksichtigen die geänderte Besuchsdefinition in den Ansichten.
* **Person (Berichte):** Betrachtet alle Sitzungen bis zum 1. des Monats des aktuellen Datumsbereichs. Die Lookback-Fenster für Personen sind breit, da sie viele Sitzungen umfassen können. Wenn der Datumsbereich des Berichts beispielsweise der 15. September bis 30. September ist, umfasst der Datumsbereich für die Personensuche den 1. September bis den 30. September.
