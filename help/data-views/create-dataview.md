---
title: Datenansicht erstellen
description: Beschreibt, wie eine Datenansicht für einen Platform-Datensatz in Customer Journey Analytics (CJA) erstellt wird.
translation-type: tm+mt
source-git-commit: c85b5d2e702a38aa6569da893a25bacd39604f8a

---


# Datenansicht erstellen

Eine Datenansicht ähnelt einer Virtual Report Suite in Analytics insofern, als sie eine gefilterte Ansicht der Daten darstellt. Sie können verschiedene Datenansichten für dieselbe Verbindung mit unterschiedlichen Einstellungen für Besuchs-Timeout, Zuordnung usw. erstellen. Sie können mehrere Datenansichten für einen Datensatz erstellen. Sie können beispielsweise eine Datenansicht verwenden, in der alle Dimensionen auf &quot;Letztkontakt&quot;und gleichzeitig eine andere Datenansicht (basierend auf demselben Datensatz) mit allen Dimensionen auf &quot;Erstkontakt&quot;festgelegt sind.

Workspace-Projekte in Customer Journey Analytics basieren auf Datenansichten.

Klicken Sie [hier](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) , um eine Videoübersicht zu erhalten.

## Voraussetzung

Bevor Sie Datenansichten erstellen können, müssen Sie eine oder mehrere Verbindungen zu Adobe Experience Platform-Datensätzen [einrichten](/help/connections/create-connection.md).

## Einstellungen konfigurieren

1. Gehen Sie in Customer Journey Analytics zur **[!UICONTROL Data Views]** Registerkarte.

1. Klicken Sie auf **[!UICONTROL Add]** , um eine Datenansicht hinzuzufügen und die Einstellungen zu konfigurieren.

   | Sitzungseinstellungen | Definition |
   |---|---|
   | Verbindung | In diesem Feld wird die Datenansicht mit der Verbindung verknüpft, die Sie zuvor hergestellt haben und die den/die Plattformdataset/s enthält. |
   | Name | Die Datenansicht muss einen Namen erhalten. |
   | Beschreibung | Eine detaillierte Beschreibung ist nicht obligatorisch, wird jedoch empfohlen. |
   | Tags hinzufügen | Mit Tags können Sie Ihre Datenansichten in Kategorien unterteilen. |
   | Zeitzone | Wählen Sie die Zeitzone für Ihre Datenansicht aus. |
   | Sitzungs-Timeout | Wählen Sie aus, was Ihre Definition von &quot;Sitzung&quot;ist. Die Einstellung für den Sitzungs-Timeout definiert die Inaktivität, die ein Unique Visitor haben muss, bevor eine neue Sitzung automatisch gestartet wird. Die Standardeinstellung lautet 30 Minuten. For example, if you set the session timeout to 45 minutes, a new session grouping is created for each sequence of hits collected, separated by 45 minutes of inactivity. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | Neue Sitzung mit Ereignis starten | Eine neue Sitzung beginnt dann, wenn ein Ereignis ausgelöst wird – unabhängig davon, ob bei einer Sitzung eine Zeitüberschreitung auftrat oder nicht. Zur neuen Sitzung gehört auch das Ereignis, das sie ausgelöst hat. Zudem können Sie mehrere Ereignisse nutzen, um eine Sitzung zu starten, und eine neue Sitzung wird dann begonnen, wenn beliebige dieser Ereignisse in den Daten auftreten. Diese Einstellung wirkt sich auf Ihre Besuchszahl, den Segmentbehälter für Sitzung (früher Besuch) und die Logik zum Besuchsablauf auf Dimensionen aus. |
   | Filter hinzufügen | &quot;Filter&quot;ist der Begriff &quot;Segmente&quot;in Customer Journey Analytics. Wenn Sie Ihre Daten filtern möchten, ziehen Sie den entsprechenden Filter hier aus der linken Leiste. Wenn Sie keinen Filter auswählen, enthält die Datenansicht alle Daten. |

1. Klicken Sie auf **[!UICONTROL Continue]**.

## Komponenten hinzufügen

1. Jetzt ist es an der Zeit, Komponenten (Dimensionen, Metriken) zur Datenansicht hinzuzufügen (ähnlich wie bei der Kuratierung in Virtual Report Suites). Beachten Sie, dass alle Felder in den Datensätzen jetzt in Dimensionen oder Metriken übersetzt werden. Ziehen Sie Dimensionen und Metriken in den Bereich oder **[!UICONTROL Alle** auswählen, um alle Komponenten hinzuzufügen.

   ![](assets/add-all-components.png)

1. Klicken Sie auf die **[!UICONTROL Add Components]** Registerkarte, um der Datenansicht Dimensionen und Metriken hinzuzufügen.

   ![](assets/add-all-components2.png)

1. (Optional) Sie können eine Komponente in einen benutzerfreundlichen Namen umbenennen oder ihre Zuordnungseinstellungen ändern, indem Sie sie auswählen und ihre Einstellung bearbeiten. Beachten Sie, dass der zugrunde liegende Name beibehalten wird. Weitere Informationen finden Sie unter Datenansichten und Zuordnung [konfigurieren](/help/data-views/configure-dataviews.md).

1. Die nächsten Schritte sind die [Angabe der Komponenten- und Zuordnungseinstellungen](/help/data-views/configure-dataviews.md).