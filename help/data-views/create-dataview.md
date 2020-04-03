---
title: Datenschicht erstellen
description: Beschreibt das Erstellen einer Ansicht von Daten zu einem Plattformdatensatz in Customer Journey Analytics (CJA).
translation-type: tm+mt
source-git-commit: c85b5d2e702a38aa6569da893a25bacd39604f8a

---


# Datenschicht erstellen

Eine Ansicht von Daten ähnelt einer Virtual Report Suite in Analytics insofern, als es sich um eine &quot;gefilterte&quot;Ansicht der Daten handelt. Sie können verschiedene Ansichten für die gleiche Verbindung erstellen, mit unterschiedlichen Einstellungen für Besuchs-Timeout, Zuordnung usw. Sie können mehrere Ansichten für einen Datensatz erstellen. Sie können beispielsweise eine Datendimensionen mit der Einstellung &quot;Letztkontakt&quot;und gleichzeitig eine andere Ansicht mit einer Ansicht (basierend auf demselben Datensatz) mit allen Dimensionen mit der Einstellung &quot;Erstkontakt&quot;festlegen.

Workspace-Projekte in Customer Journey Analytics basieren auf Ansichten von Daten.

Klicken Sie [hier](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) , um eine Videoübersicht zu erhalten.

## Voraussetzung

Bevor Sie Daten-Ansichten erstellen können, müssen Sie eine oder mehrere Verbindungen zu Adobe Experience Platform-Datensätzen [einrichten](/help/connections/create-connection.md).

## Einstellungen konfigurieren

1. Gehen Sie in Customer Journey Analytics zur **[!UICONTROL Data Views]** Registerkarte.

1. Klicken Sie auf , **[!UICONTROL Add]** um eine Ansicht hinzuzufügen und deren Einstellungen zu konfigurieren.

   | Sitzungseinstellungen | Definition |
   |---|---|
   | Verbindung | In diesem Feld wird die Ansicht der Daten mit der Verbindung verknüpft, die Sie zuvor hergestellt haben und die den/die Plattformdatensatz/s enthält. |
   | Name | Die Benennung der Ansicht ist obligatorisch. |
   | Beschreibung | Eine detaillierte Beschreibung ist nicht obligatorisch, wird jedoch empfohlen. |
   | Hinzufügen Tags | Mit Tags können Sie Ihre Daten-Ansichten in Kategorien organisieren. |
   | Zeitzone | Wählen Sie die Zeitzone für die Ansicht Ihrer Daten aus. |
   | Sitzungs-Timeout | Wählen Sie aus, was Ihre Definition von &quot;Sitzung&quot;ist. Die Einstellung für den Sitzungs-Timeout definiert die Inaktivität, die ein eindeutiger Besucher haben muss, bevor eine neue Sitzung automatisch gestartet wird. Der Standardwert ist 30 Minuten. Wenn Sie beispielsweise den Sitzungs-Timeout auf 45 Minuten setzen, wird für jede gesammelte Treffersequenz eine neue Sitzungsgruppierung erstellt, die durch 45 Minuten Inaktivität getrennt wird. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Beginn Neue Sitzung mit Ereignis | Eine neue Sitzung Beginn, wenn ein Ereignis ausgelöst wird, unabhängig davon, ob eine Sitzung abgelaufen ist. Die neu erstellte Sitzung enthält das Ereignis, das sie gestartet hat. Darüber hinaus können Sie mehrere Ereignis verwenden, um eine Sitzung Beginn, und eine neue Sitzung wird ausgelöst, wenn eines dieser Ereignis in den Daten beobachtet wird. Diese Einstellung wirkt sich auf Ihre Besuchszahl, den Segmentwert Sitzung (früher Besuch) und die Besuchsablauflogik auf Dimensionen aus. |
   | Filter hinzufügen | &quot;Filter&quot;ist der Begriff &quot;Segmente&quot;in Customer Journey Analytics. Wenn Sie Ihre Daten filtern möchten, ziehen Sie den entsprechenden Filter hier aus der linken Leiste. Wenn Sie keinen Filter auswählen, enthält die Ansicht alle Daten. |

1. Klicken Sie auf **[!UICONTROL Continue]**.

## Komponenten hinzufügen

1. Jetzt ist es an der Zeit, der Ansicht der Daten Komponenten (Dimensionen, Metriken) hinzuzufügen (ähnlich wie bei der Kuratierung in Virtual Report Suites). Beachten Sie, dass alle Felder in den Datensätzen jetzt in Dimensionen oder Metriken übersetzt werden. Ziehen Sie Dimensionen und Metriken in den Bereich oder **[!UICONTROL Alle** auswählen, um alle Komponenten hinzuzufügen.

   ![](assets/add-all-components.png)

1. Klicken Sie auf die **[!UICONTROL Add Components]** Registerkarte, um der Ansicht Dimensionen und Metriken hinzuzufügen.

   ![](assets/add-all-components2.png)

1. (Optional) Sie können eine Komponente in einen benutzerfreundlichen Namen umbenennen oder ihre Zuordnungseinstellungen ändern, indem Sie sie auswählen und ihre Einstellung bearbeiten. Beachten Sie, dass der zugrunde liegende Name beibehalten wird. Weitere Informationen finden Sie unter Ansichten und Zuordnung [von Daten konfigurieren](/help/data-views/configure-dataviews.md).

1. Die nächsten Schritte sind die [Angabe der Komponenten- und Zuordnungseinstellungen](/help/data-views/configure-dataviews.md).