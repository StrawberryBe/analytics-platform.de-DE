---
title: Komponenteneinstellungen für die Metrikdeduplizierung
description: Zählen Sie nur das erste Vorkommen einer Metrik in Berichten.
source-git-commit: 86522f1ea5ae241351514d954672ec5fd7990944
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 9%

---


# Komponenteneinstellungen für die Metrikdeduplizierung

Mit der Metrikdeduplizierung können Sie eine Metrik so konfigurieren, dass Werte nicht wiederholt gezählt werden.

| Einstellung | Beschreibung |
| --- | --- |
| Deduplizierung der Metrik | Ein Kontrollkästchen, mit dem Sie die Metrikdeduplizierung aktivieren können. Standardmäßig deaktiviert. |
| Umfang der Deduplizierung | Hiermit können Sie bestimmen, wie weit die eindeutige Prüfung zurückliegt.<br>**Sitzung**: Es wird nur das erste Metrikereignis der Sitzung gezählt.<br>**Person**: Es wird nur das erste Metrikereignis im Berichtsfenster gezählt. |
| Deduplizierungs-ID | Ermöglicht es Ihnen, anstelle der Deduplizierung auf die Metrik selbst die Metrikdeduplizierung auf Grundlage einer Dimension anzuwenden. Wertvoll für Dimensionen wie Kauf-ID, um eine Deduplizierung anzuwenden. |
