---
title: Komponenteneinstellungen für die Metrik-Deduplizierung
description: Zählen Sie nur das erste Vorkommen einer Metrik in Berichten.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: b353983b13cbbfb4c846e75aecc1b78da26ddeb2
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 100%

---

# Komponenteneinstellungen für die Metrik-Deduplizierung

Mit der Metrik-Deduplizierung können Sie eine Metrik so konfigurieren, dass Werte nicht wiederholt gezählt werden.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Deduplizierung der Metrik] | Ein Kontrollkästchen, mit dem Sie die Metrik-Deduplizierung aktivieren können. Standardmäßig deaktiviert. |
| [!UICONTROL Umfang der Deduplizierung] | Hiermit können Sie bestimmen, wie weit die eindeutige Prüfung in die Vergangenheit reicht.<br>**Sitzung**: Es wird nur das erste Metrikereignis der Sitzung gezählt.<br>**Person**: Es wird nur das erste Metrikereignis im Reporting-Fenster gezählt. |
| [!UICONTROL Deduplizierungs-ID] | Ermöglicht es Ihnen, anstelle der Deduplizierung in der Metrik selbst die Metrik-Deduplizierung auf Grundlage einer Dimension anzuwenden. Wertvoll für Dimensionen wie Kauf-ID, um eine Deduplizierung anzuwenden. |

{style=&quot;table-layout:auto&quot;}
