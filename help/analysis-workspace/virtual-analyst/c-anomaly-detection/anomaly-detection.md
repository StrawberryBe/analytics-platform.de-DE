---
description: Datenanomalien können kontextbezogen in Analysis Workspace angezeigt und analysiert werden.
title: Übersicht über die Anomalieerkennung
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 95b8022db4c173b27327469fe8c34afa1ea27796
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 92%

---


# Übersicht über die Anomalieerkennung

Datenanomalien können kontextbezogen in Analysis Workspace angezeigt und analysiert werden.

[Videoschulung](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html)  zur Anomalieerkennung (4:53)

Die Anomalieerkennung bietet eine statistische Methode, mit der festgestellt wird, wie sich eine bestimmte Metrik in Bezug auf frühere Daten verändert hat.

Die Anomalieerkennung ermöglicht es Ihnen, „echte Signale“ von „Rauschen“ zu unterscheiden. Zudem hilft sie Ihnen anschließend dabei, potenzielle Faktoren zu bestimmen, die zu diesen Signalen oder Anomalien beigesteuert haben. Auf diese Weise können Sie feststellen, welche statistischen Schwankungen relevant sind, und anschließend die Ursache eines echten Fehlers feststellen. Zudem erhalten Sie eine zuverlässige Metrikvorhersage (KPI).

Zu Beispielen von Fehlern, die ein Eingreifen Ihrerseits erfordern, zählen:

* Erhebliche Verwerfungen im durchschnittlichen Bestellwert
* Spitzen in Bestellungen mit geringem Umsatz
* Spitzen oder Verwerfungen in Testprogrammregistrierungen
* Verwerfungen bei Landingpage-Aufrufen
* Spitzen in Videopufferereignissen
* Spitzen in niedrigen Video-Bitraten

Der Algorithmus der Analysis Workspace-Anomalieerkennung umfasst:

* Unterstützung für die Einstellungen „Stündlich“, „Wöchentlich“ und „Monatlich“ (zusätzlich zur vorhandenen Einstellung „Täglich“)
* Berücksichtigung von besonderen Tagen (wie z. B. Black Friday) und Feiertagen
