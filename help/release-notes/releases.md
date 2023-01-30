---
description: Erläutert die Strategie zur kontinuierlichen Veröffentlichung von Funktionen für Customer Journey Analytics
title: Versionen von Customer Journey Analytics-Funktionen
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
source-git-commit: 40f145d20125c41f3399ab0690a673f01c1817e3
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 90%

---

# Versionen von Customer Journey Analytics-Funktionen

Customer Journey Analytics-Versionen basieren auf einem Modell der kontinuierlichen Bereitstellung, das einen besser skalierbaren, schrittweisen Ansatz für die Implementierung von Funktionen ermöglicht.

## Veröffentlichungsstrategie

[!UICONTROL Analysis Workspace] verwendet Funktionsmarkierungen (auch als „Umschalter“ bezeichnet), um die Sichtbarkeit neuer Funktionen zu steuern, sodass vor der Vollversion ein kontrollierter Skalierungstest durchgeführt werden kann. Diese Veröffentlichungsstrategie umfasst die folgenden Phasen:

* **Eingeschränktes Testen**: Eine schrittweise Veröffentlichung beginnt mit Tests durch interne Adobe-Benutzer. Sie wird dann einer kleinen Gruppe von Kundenkonten zur Verfügung gestellt, um sicherzustellen, dass die Funktion den Kundenanforderungen und Erwartungen entspricht.

* **Start des Rollouts**: Der Rollout einer stufenweisen Veröffentlichung beginnt mit der Phase des eingeschränkten Testens. Die Verfügbarkeit der Version für Kunden wird dann im Laufe einiger Monate von 0 % auf 100 % skaliert. Die schrittweise Einführung erfolgt auf der Organisationsebene in Experience Cloud, sodass alle Benutzer mit Berechtigung in einem Unternehmen dasselbe Erlebnis erhalten.

* **Allgemeine Verfügbarkeit (GA)**: Die Funktion steht 100 % der berechtigten Experience Cloud-Organisationen zur Verfügung und die Veröffentlichung der Funktion ist abgeschlossen.

Bei jeder Funktionsveröffentlichung kann die Timeline von RTP bis GA variieren. Ziel ist es, die Veröffentlichungen kurz zu halten, sodass innerhalb von 2 Monaten nach Beginn der Veröffentlichung (RTP) eine Funktion allgemein verfügbar (GA) ist.

## Funktionsmarkierungen

Mithilfe von Funktionsmarkierungen wird die Sichtbarkeit neuer Funktionen während der Veröffentlichung gesteuert. Adobe empfiehlt, `app.launchdarkly.com` zur [Zulassungsliste](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=de) Ihrer Firewall hinzuzufügen, um eine optimale Funktionalität bei der Veröffentlichung zu erzielen. Kurz nach der allgemeinen Verfügbarkeit wird die Markierung entfernt.

Sie können sich Ihre aktiven Funktionsmarkierungen jederzeit unter **Hilfe > Über den Workspace > Aktive Funktionsmarkierungen** ansehen.

## Vorteile

Die stufenweise Veröffentlichung ermöglicht es Adobe, den Software-Implementierungsprozess besser zu skalieren und sicherzustellen, dass die Funktionen vor der allgemeinen Verfügbarkeit vollständig gehärtet sind. Außerdem können Funktionen veröffentlicht werden, sobald sie verfügbar sind, anstatt sich an ein festes monatliches Veröffentlichungsfenster zu halten.

## Häufig gestellte Fragen (FAQ)

| Frage | Antwort |
| --- | --- |
| Kann ich frühzeitigen Zugriff auf eine Funktion anfordern? | Nein. Es wird kein frühzeitiger Zugriff gewährt.<br>Wenn Sie frühe Analytics-Konzepte testen möchten, empfehlen wir Ihnen, [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html?lang=de) zu testen, um Feedback zu unseren branchenführenden Innovationen zu geben. |
| Hat diese Veröffentlichungsstrategie Auswirkungen auf meinen Zugriff auf Funktionen? | Nein. Sobald eine Funktion GA erreicht hat, haben Sie Zugriff auf die Funktion, wenn sie in Ihrem Analytics-Paket enthalten ist. |
