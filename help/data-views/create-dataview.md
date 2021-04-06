---
title: Datenansicht erstellen
description: Beschreibt, wie in Customer Journey Analytics (CJA) eine Datenansicht für einen Plattform-Datensatz erstellt wird.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
translation-type: tm+mt
source-git-commit: a0ea2be203aa2e0df7b195e259b6d98c0c027652
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 97%

---

# Datenansicht erstellen

Eine Datenansicht ähnelt einer Virtual Report Suite in Analytics, da es sich in gewissem Sinne um eine „gefilterte“ Ansicht der Daten handelt. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Attribution usw. erstellen. Sie können für einen Datensatz mehrere Datenansichten erstellen. Beispielsweise könnten Sie eine Datenansicht haben, in der alle Dimensionen auf „Letztkontakt“ eingestellt sind, und gleichzeitig eine andere Datenansicht (basierend auf demselben Datensatz), in der alle Dimensionen auf „Erstkontakt“ eingestellt sind.

Workspace-Projekte in Customer Journey Analytics basieren auf Datenansichten.

Eine Videoübersicht finden Sie [hier](https://docs.adobe.com/content/help/de-DE/platform-learn/tutorials/cja/basic-configuration-for-data-views.html).

## Voraussetzung

Bevor Sie Datenansichten erstellen können, müssen Sie [eine oder mehrere Verbindungen zu Experience Platform-Datensätzen einrichten](/help/connections/create-connection.md).

## Einstellungen konfigurieren

1. Gehen Sie in Customer Journey Analytics zur Registerkarte **[!UICONTROL Datenansichten]**.

1. Klicken Sie auf **[!UICONTROL Hinzufügen]**, um eine Datenansicht hinzuzufügen und deren Einstellungen zu konfigurieren.

   | Sitzungseinstellungen | Definition |
   |---|---|
   | Verbindung | In diesem Feld wird die Datenansicht mit der zuvor eingerichteten Verbindung verknüpft, die die [!UICONTROL Experience Platform]-Datensätze enthält. |
   | Name | Geben Sie der Datenansicht einen Namen. Dies ist ein Pflichtfeld. |
   | Beschreibung | Eine detaillierte Beschreibung ist nicht zwingend erforderlich, wird jedoch empfohlen. |
   | Tags hinzufügen | Mit Tags können Sie Ihre Datenansichten in Kategorien organisieren. |
   | Zeitzone | Wählen Sie die Zeitzone für Ihre Datenansicht aus. |
   | Sitzungs-Timeout | Wählen Sie Ihre Definition einer „Sitzung“ aus. Die Einstellung des Sitzungs-Timeouts definiert den Umfang der Inaktivität, der für einen Unique Visitor erforderlich ist, bevor automatisch eine neue Sitzung gestartet wird. Die Standardeinstellung lautet 30 Minuten. Wenn Sie beispielsweise das Sitzungs-Timeout auf 45 Minuten festlegen, wird für jede Sequenz mit erfassten Treffern eine neue Sitzungsgruppierung erstellt, die durch 45 Minuten Inaktivität getrennt ist. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Neue Sitzung mit Ereignis starten | Eine neue Sitzung beginnt dann, wenn ein Ereignis ausgelöst wird – unabhängig davon, ob bei einer Sitzung eine Zeitüberschreitung auftrat oder nicht. Zur neuen Sitzung gehört auch das Ereignis, das sie ausgelöst hat. Zudem können Sie mehrere Ereignisse nutzen, um eine Sitzung zu starten, und eine neue Sitzung wird dann begonnen, wenn beliebige dieser Ereignisse in den Daten auftreten. Diese Einstellung wirkt sich auf Ihre Besuchszählung, den Sitzungs- (früher Besuchs-) Segmentierungs-Container sowie die Besuchsgültigkeitslogik von Dimensionen aus. |
   | Filter hinzufügen | „Filter“ ist der Begriff für „Segmente“ in Customer Journey Analytics. Wenn Sie Ihre Daten filtern möchten, ziehen Sie den entsprechenden Filter aus der linken Leiste. Wenn Sie keinen Filter auswählen, enthält die Datenansicht alle Daten. |

1. Klicken Sie auf **[!UICONTROL Weiter]**.

## Komponenten hinzufügen

1. Jetzt ist es an der Zeit, Komponenten (Dimensionen, Metriken) zur Ansicht der Daten hinzuzufügen. Beachten Sie, dass jetzt alle Felder in den Datensätzen in Dimensionen oder Metriken übersetzt werden. Ziehen Sie Dimensionen und Metriken in den Bereich. Sie können auch **[!UICONTROL Alle auswählen]**, um alle Komponenten hinzuzufügen.

   ![](assets/add-all-components.png)

1. Klicken Sie auf die Registerkarte **[!UICONTROL Komponenten hinzufügen]**, um der Datenansicht Dimensionen und Metriken hinzuzufügen.

   ![](assets/add-all-components2.png)

1. (Optional) Sie können eine Komponente in einen benutzerfreundlichen Namen (Anzeigenamen) umbenennen oder ihre Attributionseinstellungen ändern, indem Sie sie auswählen und ihre Einstellung bearbeiten. Beachten Sie, dass der zugrunde liegende Name beibehalten wird. Weitere Informationen finden Sie unter [Ansichten und Attribution von Daten konfigurieren](/help/data-views/configure-dataviews.md).

1. In den nächsten Schritten [legen Sie die Komponenten- und Attributionseinstellungen fest](/help/data-views/configure-dataviews.md).

## Löschen von Datenansichten

Wenn Sie eine Datenansicht in [!UICONTROL Customer Journey Analytics] löschen, wird eine Fehlermeldung angezeigt, die besagt, dass alle Workspace-Projekte, die von dieser gelöschten Datenansicht abhängig sind, nicht mehr funktionieren.
