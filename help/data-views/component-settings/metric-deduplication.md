---
title: Komponenteneinstellungen für die Metrik-Deduplizierung
description: Zählen Sie nur das erste Vorkommen einer Metrik in Berichten.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 9a31b1dcba4015f00dd7ae8c43b317e1c5679a2c
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 41%

---

# Komponenteneinstellungen für die Metrik-Deduplizierung

Mit der Metrik-Deduplizierung können Sie eine Metrik so konfigurieren, dass Werte nicht wiederholt gezählt werden.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Deduplizierung der Metrik] | Ein Kontrollkästchen, mit dem Sie die Metrik-Deduplizierung aktivieren können. Standardmäßig deaktiviert. |
| [!UICONTROL Umfang der Deduplizierung] | Hiermit können Sie bestimmen, wie weit die eindeutige Prüfung in die Vergangenheit reicht.<br>**Sitzung**: Es wird nur das erste Metrikereignis der Sitzung gezählt.<br>**Person**: Es wird nur das erste Metrikereignis im Reporting-Fenster gezählt. |
| [!UICONTROL Deduplizierungs-ID] | Ermöglicht es Ihnen, anstelle der Deduplizierung in der Metrik selbst die Metrik-Deduplizierung auf Grundlage einer Dimension anzuwenden. Wertvoll für Dimensionen wie Kauf-ID, um eine Deduplizierung anzuwenden. |
| [!UICONTROL Beizubehaltender Wert] | <ul><li>**Erste Instanz beibehalten**: Verwenden Sie dies in Situationen, in denen die ursprüngliche Instanz der Metrik die gültige ist. Die häufigste wäre wahrscheinlich eine Kaufbestätigung. Selbst wenn jemand versehentlich die Seite neu lädt und wir eine weitere Instanz einer Kaufbestätigung erhalten, ist das erste Ereignis das gültige.</li><li>**Letzte Instanz beibehalten**: Verwenden Sie dies in Situationen, in denen die letzte Instanz sinnvoller zu erfassen ist. Beispiel: Jemand aktualisiert sein Online-Profil. Wir möchten nur eines dieser Updates pro Sitzung zählen. Sie können ihr Profil jedoch mehrmals während der Sitzung aktualisieren. Wenn wir die erste Instanz beibehalten, kann es Aktivitäten geben, die nicht mit dem Ereignis verknüpft sind. In diesem Fall ist es sinnvoller, die letzte Instanz zu behalten.</li></ul> |

{style=&quot;table-layout:auto&quot;}

>[!CAUTION]
>
>Deduplizierung bei einer _person_ Der Umfang wird nach vollständigen Monaten in UTC-Zeit bewertet. Ein Berichtsfenster für einen Teil des Monats zeigt möglicherweise nicht alle ersten oder letzten Instanzen an, wenn einige innerhalb des ganzen Monats, aber außerhalb der Berichtsdaten aufgetreten sind.
