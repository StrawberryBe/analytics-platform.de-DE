---
title: Ansichten und Attribution von Daten konfigurieren
description: Beschreibt, wie in Customer Journey Analytics eine Datenansicht für einen Platform-Datensatz erstellt wird.
translation-type: ht
source-git-commit: d6101371fc9c055a73c7b7bcd1a8d6d6fdc13322

---


# Komponenten- und Attributionseinstellungen

eVars, Props und Ereignisse im traditionellen Adobe Analytics-Sinne gibt es in Customer Journey Analytics nicht mehr. Stattdessen gibt es unbegrenzte Schemaelemente (Dimensionen, Metriken, Listenfelder). Alle Attributionseinstellungen, die Sie während des Datenerfassungsprozesses auf eVars und Props angewendet haben, werden jetzt bei der Abfrage angewendet. Dies wird auch als Berichtszeitverarbeitung bezeichnet.

Eine Videoübersicht finden Sie [hier](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/attribution-settings-in-data-views.html).

Beachten Sie dies, bevor Sie Attributionseinstellungen anwenden:

* In der Benutzeroberfläche für Datenansichten geben Sie die Standardattribution an. **Hinweis**: In der Zukunft werden Sie diese Einstellungen in Workspace-Projekten überschreiben können. Diese Funktion ist jedoch derzeit nicht verfügbar.

* Die Attributionseinstellungen in Customer Journey Analytics sind zerstörungsfrei und rückwirkend. Mit anderen Worten, Sie können Ihren Datensätzen in Customer Journey Analytics keinen irreparablen Schaden zufügen. Selbst wenn Sie versehentlich etwas löschen, können Sie jederzeit zu [!UICONTROL Experience Platform] zurückkehren und den Datensatz wieder einspielen. (Beachten Sie jedoch, dass dieses erneute Einspielen des Datensatzes zusätzliche Kosten verursacht.)

* Wenn Sie möchten, dass sich eine Dimension wie eine traditionelle eVar (Konversionsvariable) „verhält“, sollten Sie sie standardmäßig mit der Attribution „Letztkontakt – Besuch“ konfigurieren.

* Wenn Sie möchten, dass sich eine Dimension wie eine traditionelle Prop (Traffic-Variable) „verhält“, sollten Sie sie standardmäßig mit der Attribution „Selber Kontakt“ konfigurieren.

* Wenn Sie möchten, dass sich eine Metrik wie eine Standardmetrik „verhält“, sollten Sie nichts ändern.

* Attributionseinstellungen für Metriken überschreiben Attributionseinstellungen für Dimensionen.

## Komponenten- und Attributionseinstellungen festlegen

Nachdem Sie die [Einstellungen für die Datenansicht festgelegt und gespeichert](/help/data-views/create-dataview.md) und Komponenten hinzugefügt haben, können Sie bei Bedarf die Attributionseinstellungen festlegen. Sie können Attributions-/Gültigkeits-/Lookback-Einstellungen für Dimensionen und Metriken angeben. Wenn beispielsweise die Attribution für eine Dimension beibehalten werden soll, sollte wahrscheinlich auch eine benutzerdefinierte Gültigkeit festgelegt werden. Wenn z. B. eine Trackingcode-Dimension (eine Kampagnenvariable), die auf die Attribution „Letztkontakt“ gesetzt ist, eine Woche lange beibehalten werden soll, fügen Sie eine benutzerdefinierte Gültigkeit von 1 Woche hinzu.

>[!IMPORTANT]
>Sie müssen keine Zuordnung/Gültigkeit festlegen. In diesem Fall verhalten sich Dimensionen wie Props (Attributionsmodell „Selber Kontakt“). Metriken ohne Attributionseinstellungen übernehmen die Einstellungen der Dimension, auf die diese Metrik angewendet wird.

![](assets/edit-component.png)

1. Geben Sie Komponenten- und Attributionseinstellungen für Dimensionen und Metriken an. Informationen zu den einzelnen Einstellungen finden Sie weiter unten.

1. Klicken Sie auf **[!UICONTROL Save]**, um Ihre Datenansicht zu speichern.


### Komponenteneinstellung

Sie können den Namen der Metrik oder Dimension in etwas benutzerfreundlicheren Namen ändern. Beachten Sie, dass sich der zugrunde liegende Name nicht ändert, sondern nur der Anzeigename.

### Attributionsmodell

Das Modell beschreibt die Verteilung der Konversionen auf die Ereignisse in einer Gruppe. Zum Beispiel Erstkontakt oder Letztkontakt Legt fest, wie in Customer Journey Analytics Gutschriften für ein Erfolgsereignis zugewiesen werden, wenn eine Variable mehrere Werte vor dem Ereignis erhält.

| Benutzeroberflächensymbol | Attributionsmodell | Definition | Verwendungsbereiche |
| --- | --- | --- | --- |
| ![Letztkontakt](assets/last_touch1.png) | Letztkontakt | 100 % werden dem Touchpoint zugeschrieben, der zuletzt vor der Konversion aufgetreten ist. | Das einfachste und gängigste Attributionsmodell. Es wird häufig für Konversionen mit einem kurzen Überlegungszyklus verwendet. Letztkontakt wird häufig durch Teams verwendet, die Suchmaschinen-Marketing verwalten oder Keywords für die interne Suche analysieren. |
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

Gibt einen Zeitraum bzw. ein Ereignis an, nach dem der Dimensionswert abläuft (d. h. keine Gutschrift für Erfolgsereignisse mehr erhält). Sie können die Gültigkeit der Attribution auf Sitzungs-, Personen- oder benutzerdefinierter Ebene festlegen.

| Einstellung | Definition |
|---|---|
| Sitzung | Zuvor als „Besuchsebene“ bezeichnet. Konversionsereignisse, die über die Seitenansicht oder Sitzung hinausgehen, werden nicht mit der Dimension oder Metrik verknüpft. |
| Person (Berichterstellungsfenster) | Zuvor als „Besucher“ bezeichnet. Konversionsereignisse, die nicht an diese Person gebunden sind, werden nicht mit der Dimension oder Metrik verknüpft. |
| Benutzerdefinierte Zeit | Geben Sie die benutzerdefinierten Minuten, Stunden, Tage, Monate oder Quartale an. Konversionsereignisse, die über den festgelegten Zeitraum hinausgehen, werden nicht mit der Dimension oder Metrik verknüpft. |

Weitere Informationen finden Sie in der [Dokumentation zu Attribution IQ](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/panels/attribution/attribution.html).

### Lookback-Fenster

Ein Lookback-Fenster ist der Zeitraum, der für eine Konversion rückblickend bei der Erfassung von Touchpoints berücksichtigt werden sollte. Attributionsmodelle, die der ersten Interaktion mehr Gewicht zuschreiben, sehen bei der Anzeige verschiedener Lookback-Fenster größere Unterschiede.

* **Sitzung:** Blickt bis zum Beginn einer Sitzung zurück, in der eine Konversion stattgefunden hat. Besuchs-Lookback-Fenster sind klein, da sie nicht über die Sitzung hinausblicken. Sitzungs-Lookback-Fenster berücksichtigen die geänderte Besuchsdefinition in den Datenansichten.
* **Person (Berichterstellungsfenster):** Betrachtet alle Sitzungen bis zum 1. des Monats des aktuellen Datumsbereichs. Personen-Lookback-Fenster sind groß, da sie viele Sitzungen umfassen können. Wenn der Berichtszeitraum beispielsweise zwischen dem 15. September und dem 30. September liegt, liegt der Personen-Lookback-Datumsbereich zwischen dem 1. September und dem 30. September.
