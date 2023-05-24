---
description: Adobe bietet verschiedene berechnete Metriken, die Sie verwenden können. Auf dieser Seite werden diese Metriken und ihre Verwendungszwecke aufgelistet.
title: Standardmäßig berechnete Metriken
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 3f1112ebd2a4dfc881ae6cb7bd858901d2f38d69
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 31%

---

# Standardmäßig berechnete Metriken

Customer Journey Analytics bietet verschiedene berechnete Metriken, die die häufigsten Anwendungsfälle abdecken. Diese berechneten Metriken sind in Analysis Workspace standardmäßig verfügbar.

Im Folgenden finden Sie eine Liste aller berechneten Metriken, die von Adobe bereitgestellt werden, mit der beabsichtigten Funktion und der zugrunde liegenden Formel, die zur Berechnung verwendet wird:

>[!NOTE]
>
>Zusätzlich zu den auf dieser Seite beschriebenen standardmäßigen berechneten Metriken können Sie auch zusätzliche berechnete Metriken zu einer Datenansicht hinzufügen.
>
>Sie können:
> * Fügen Sie standardmäßige berechnete Metriken für Streaming-Medien hinzu, wie unter [Berechnete Metriken](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Erstellen Sie benutzerdefinierte berechnete Metriken aus vorhandenen Metriken, wie unter [Berechnete und erweiterte berechnete (abgeleitete) Metriken](/help/components/calc-metrics/cm-adv-functions.md).



| Name der berechneten Metrik | Funktion | Formel |
|---------|----------|---------|
| Absprungrate | Das Verhältnis der Besuche, die genau ein Ereignis enthielten, zur Anzahl der Besuche auf dieser Seite. Auf diese Weise können Sie erkennen, welche Dimensionselemente die höchste Absprungrate aufweisen, oder eine aggregierte Gesamtabsprungrate Ihrer Site im Zeitverlauf anzeigen. | `[Bounces] / [Entries]` |
| Umsatz/Besucher | Der durchschnittliche Umsatzbetrag, der von jeder einzelnen Person der Site generiert wurde. | `[Revenue] / [Unique Visitors]` |
| Bestellungen/Besucher | Durchschnittliche Anzahl von Bestellungen oder Transaktionen, die von jeder einzelnen Person der Site generiert wurden | `[Orders] / [Unique Visitors]` |
| Umsatz/Besuche | Die durchschnittliche Umsatzmenge, die durch einen einzelnen Besuch der Website generiert wird. | `[Revenue] / [Visits]` |
| Umsatz/Bestellung | Die durchschnittliche Umsatzmenge, die durch jede abgeschlossene Transaktion oder Bestellung auf der Website generiert wird. | `[Revenue] / [Orders]` |
| Bestellungen/Besuche | Der Prozentsatz der Besuche auf der Website, die zu einer abgeschlossenen Transaktion führen. | `[Orders] / [Visits]` |
| Seitenansichten/Besuche | Die durchschnittliche Anzahl von Seiten, die sich eine Benutzerin oder ein Benutzer bei einem einzelnen Besuch der Website ansieht. | `[Page Views] / [Visits]` |
| Besuche/Besucher | Die durchschnittliche Anzahl der Besuche einer eindeutigen Person auf der Site. | `[Visits] / [Unique Visitors]` |
| Neuladungen/Seitenansichten | Der Prozentsatz der Seitenansichten, die zu einem erneuten Laden oder Aktualisieren der Seite geführt haben. | `[Reloads] / [Page Views]` |
| Gewichtete Rücksendungsrate | Funktion | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| Bestellhilfen | Die Anzahl der Fälle, in denen ein Kanal oder eine Quelle zum Kauf einer Kundin oder eines Kunden im Zuge der Journey beigetragen, aber nicht zum endgültigen Kauf geführt hat. | `[Orders (Visit Participation)] - [Orders]` |
| Ausstiegsrate | Der Prozentsatz der Personen, die die Site nach Ansicht einer bestimmten Seite verlassen. | `[Exits] / [Visits]` |
| Einstiegsrate | Der Prozentsatz der Personen, die auf einer bestimmten Seite auf die Site zugegriffen haben, in Bezug auf die Gesamtzahl der Sitzungen auf der Site. | `[Entries] / [Visits]` |
| Durchschnittliche Besuchszeit pro Site | Die durchschnittliche Zeit, die eine Person auf der Site verbringt, bevor sie die Site verlässt oder wegnavigiert. | `[Average Time Spent on Site (Seconds)]` |
| Besuchszeit/Benutzer (Status) | Die Zeitdauer, die die durchschnittliche Person in einem bestimmten Staat auf der Site verbringt | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Benutzer (Mobil) | Die gesamte Anzahl der Benutzerinnen und Benutzer einer Mobile App | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| App-Benutzer | Die gesamte Anzahl der Benutzerinnen und Benutzer einer Mobile App | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| Statusansichten | Die Anzahl der Aufrufe verschiedener Status oder Bildschirme der Mobile App | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| Aktionen | Die Gesamtanzahl der in der App ausgeführten Aktionen | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| Akquise-Link-Klicks | Die Häufigkeit, mit der Besucherinnen und Besucher auf einen Link klicken, der dazu dient, den Traffic zur Website zu leiten. | `[Campaign Click-throughs]` |
| Seitengeschwindigkeit | Die Anzahl der zusätzlichen Seitenansichten, die ein Inhaltselement generiert. Auf diese Weise können Sie feststellen, welche Inhalte zusätzliche Interaktionen erfordern. | `[Page Views] / [Visits]` |
| Konversionsrate | Der Prozentsatz der Personen, die eine gewünschte Aktion durchgeführt haben, z. B. einen Kauf getätigt haben. | `[Orders] / [Visits]` |
| Durchschnittliche Sitzungslänge (Mobil) | Die durchschnittliche Zeit, die Personen während einer einzelnen Sitzung auf der Site verbringen. | Leer |
| Experience Cloud ID-Abdeckung | Der Prozentsatz der Personen, die über eine Experience Cloud-ID verfügen. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Content-Geschwindigkeit | Die Geschwindigkeit, mit der neue Inhalte auf der Website erstellt und veröffentlicht werden, und wie schnell dadurch Benutzerinteraktionen generiert werden. | `[Page Views] / [Visits]` |
| Unique Visitors (ITP 2.1) / Unique Visitors | Der Prozentsatz der Unique Users, die einen Browser verwenden, der von ITP 2.1-Cookie-Beschränkungen betroffen ist. Mit anderen Worten, Kunden, die keine CNAME-Implementierung verwenden. (Dies gilt für Kunden, die Cookies über clientseitiges JavaScript setzen.) | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| Unique Visitors/Unique Visitors, die nach 7 Tagen zurückkehren | Der Prozentsatz der individuellen Personen, die nach einem Zeitraum von 7 oder mehr Tagen zurückkehren. | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| Seitenansichten/Unique Visitor | Die durchschnittliche Anzahl der angezeigten Seiten für jede einzelne Person auf der Site. | `[Page Views] / [Unique Visitors]` |
| Besuche/Besucherinnen bzw. Besucher | Die durchschnittliche Anzahl der Besuche einer eindeutigen Person auf der Site . | `[Visits] / [Unique Visitors]` |
| Geschätzte Unique Visitors (ITP 2.1) | Für ITP-Personen (Benutzer in Safari-Browsern) teilen Sie Unique Visitors durch 2 oder weniger. Diese berechnete Metrik setzt voraus, dass Sie Cookies mit clientseitigem JavaScript setzen (ohne eine CNAME-Implementierung zu verwenden). Implementierungen, die Cookies mit clientseitigem JavaScript setzen, wurden ab ITP 2.1 beeinträchtigt. Siehe [Intelligente Tracking-Prävention](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) für Details. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| Seitenansichten/Geschätzte Unique Visitors (ITP 2.1) | Die durchschnittliche Anzahl der für „Geschätzte Unique Visitors“ (ITP 2.1) angezeigten Seiten. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
