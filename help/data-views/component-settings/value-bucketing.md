---
title: Komponenteneinstellungen für WertBuffering
description: Kombinieren Sie numerische Werte in einer Dimension.
source-git-commit: 0c27f75eed8f1f3dec3f287cfe35ab748bbfc1bb
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 12%

---


# [!UICONTROL Einstellungen ] der Value Bucketingcomponent

Beim Erstellen oder Bearbeiten einer Datenansicht können Sie mit der Wertaufschlüsselung numerische Werte basierend auf einem Bereich kombinieren. Sie ist nur für Dimensionen verfügbar, die Datentypen vom Typ Integer oder Doppeltes Schema verwenden.

Die Wertesammlung ist nützlich, wenn Sie Bereiche gruppieren möchten, anstatt jede eindeutige Zahl als separate Dimensionselemente zu behandeln. Beispielsweise wird ein Bucket vom Typ &quot;Zwischen 5 und bis zu 10&quot;in Analysis Workspace als Zeileneintrag &quot;5 bis 10&quot;angezeigt.

![Wert-Bucketing](../assets/value-bucketing.png)

Wenn Sie die Flexibilität bei der Berichterstellung für eine zusammengefasste und nicht zusammengefasste Dimension wünschen, ziehen Sie zwei Kopien der Komponente in die Liste der verfügbaren Dimensionen. Aktivieren Sie die Zusammenfassung für eine Dimension und deaktivieren Sie sie für die andere.

| Einstellung | Beschreibung |
| --- | --- |
| [!UICONTROL Bucket-Wert] | Ein Kontrollkästchen, mit dem Sie die Zusammenfassung aktivieren können. |
| [!UICONTROL Kleiner als] | Die obere Grenze des ersten Dimensionsbehälters. |
|  [!UICONTROL Einschließlich und weniger als] | Grenzen der nachfolgenden Behälter. |
| [!UICONTROL Größer oder gleich] | Die untere Grenze des letzten Dimensionsbehälters. |
| [!UICONTROL Bucket hinzufügen] | Ermöglicht das Hinzufügen eines weiteren Behälters zu numerischen Dimensionsbehältern. Sie können bis zu 20 Behälter in einer Dimension hinzufügen. |
