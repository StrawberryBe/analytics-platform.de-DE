---
title: Schätzung der CJA-Verbindungsgröße
description: Bericht zur aktuellen Nutzung von Customer Journey Analytics
exl-id: 5599b34f-342d-4c68-b7c9-2ac3ea50d078
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: ht
source-wordcount: '615'
ht-degree: 100%

---

# Verbindungsgröße schätzen

Möglicherweise müssen Sie die derzeitige Anzahl von Datenzeilen in [!UICONTROL Customer Journey Analytics] kennen. In diesem Thema erfahren Sie, wie Sie Berichte zur aktuellen Nutzung von [!UICONTROL Customer Journey Analytics] erstellen.

1. Rufen Sie in [!UICONTROL Customer Journey Analytics] den Tab **[!UICONTROL Verbindungen]** auf.
1. Wählen Sie im Bildschirm [!UICONTROL Verbindung bearbeiten] eine Verbindung aus, für die Sie die Nutzung/Verbindungsgröße bestimmen möchten.

   ![Verbindung bearbeiten](assets/edit-connection.png)

1. Wählen Sie in der linken Leiste einen Datensatz aus, der Ihrem Teil der Verbindung entspricht. In diesem Fall handelt es sich um den Datensatz „B2B-Impression“.

   ![Datensatz](assets/dataset.png)

1. Klicken Sie auf das blaue Symbol (i) neben dem Namen. Der Datensatz enthält 38.000 Zeilen/Ereignisse. Klicken Sie außerdem bezüglich der genauen Anzahl der Zeilen unter der Vorschautabelle auf **[!UICONTROL In Experience Platform bearbeiten]**. Sie werden dann zu den Datensätzen in [!UICONTROL Adobe Experience Platform] weitergeleitet.

   ![Adobe Experience Platform-Datensatz-Info](assets/data-size.png)

1. Beachten Sie, dass die Anzahl der **[!UICONTROL Gesamten Aufzeichnungen]** für diesen Datensatz 3.830 beträgt, wobei die Größe der Daten 388,59 KB beträgt.

1. Wiederholen Sie die Schritte 1 bis 5 für andere Datensätze in Ihrer Verbindung und addieren Sie die Anzahl der Aufzeichnungen/Zeilen. Die letzte aggregierte Zahl entspricht der Nutzungsmetrik Ihrer Verbindung. Dies ist die Zeilenanzahl der Datensätze Ihrer Verbindung, die Sie von [!UICONTROL Adobe Experience Platform] aufnehmen werden.

## Ermitteln der Anzahl der aufgenommenen Zeilen

Die Anzahl der tatsächlich in [!UICONTROL Customer Journey Analytics] aufgenommenen Ereignisse hängt von Ihrer Verbindungskonfiguration ab. Wenn Sie außerdem die falsche Personen-ID ausgewählt haben oder diese ID für einige Zeilen in den Datensätzen nicht verfügbar ist, werden diese Zeilen von [!UICONTROL Customer Journey Analytics] ignoriert. Gehen Sie wie folgt vor, um die tatsächlichen Zeilen der aufgenommenen Ereignisse zu ermitteln:

1. Nachdem Sie die Verbindung gespeichert haben, erstellen Sie eine Datenansicht derselben Verbindung ohne Filter.
1. Erstellen Sie ein Arbeitsbereich-Projekt und wählen Sie die korrekte Datenansicht aus. Erstellen Sie eine Freiformtabelle und ziehen Sie die Metrik **[!UICONTROL Ereignisse]** mit der Dimension **[!UICONTROL Jahr]** per Drag und Drop. Wählen Sie einen ausreichend großen Datumsbereich in Ihrem Datumsauswahlkalender aus, um alle Daten in Ihrer Verbindung einzuschließen. Auf diese Weise können Sie die Anzahl der Ereignisse sehen, die in [!UICONTROL Customer Journey Analytics] aufgenommen werden.

   ![Arbeitsbereich-Projekt](assets/event-number.png)

   >[!NOTE]
   >
   >Auf diese Weise können Sie sehen, wie viele Ereignisse aus dem Ereignisdatensatz aufgenommen werden. Profil- und Lookup-Datensätze sind darin nicht enthalten. Führen Sie unter „Geschätzte Verbindungsgröße“ die Schritte 1 bis 3 für Profil- und Lookup-Datensätze aus und addieren Sie die Zahlen, um die Gesamtanzahl der Zeilen für diese Verbindung zu erhalten.

## Diskrepanzen diagnostizieren

In einigen Fällen kann es vorkommen, dass die Gesamtanzahl der von Ihrer Verbindung erfassten Ereignisse sich von der Anzahl der Zeilen im Datensatz in [!UICONTROL Adobe Experience Platform] unterscheidet. In diesem Beispiel enthält der Datensatz „B2B Impression“ 7650 Zeilen, der Datensatz enthält jedoch 3830 Zeilen in [!UICONTROL Adobe Experience Platform]. Es kann mehrere Gründe für Diskrepanzen geben. Die folgenden Schritte können für die Diagnose hilfreich sein:

1. Schlüsseln Sie diese Dimension nach **[!UICONTROL Platform Datensatz-ID]** auf. Sie werden feststellen, dass es zwei Datensätze mit derselben Größe, aber unterschiedlichen **[!UICONTROL Platform Datensatz-IDs]** gibt. Jeder Datensatz enthält 3.825 Aufzeichnungen. Das bedeutet, dass [!UICONTROL Customer Journey Analytics] fünf Datensätze aufgrund fehlender Personen-IDs oder fehlender Zeitstempel ignoriert hat:

   ![Aufschlüsselung](assets/data-size2.png)

1. Wenn wir uns dies in [!UICONTROL Adobe Experience Platform] anschauen, gibt es keinen Datensatz mit der ID „5f21c12b732044194bffc1d0“. Jemand hat also diesen Datensatz bei der Erstellung der ersten Verbindung aus [!UICONTROL Adobe Experience Platform] gelöscht. Später wurde er erneut zu [!UICONTROL Customer Journey Analytics] hinzugefügt, es wurde jedoch eine andere [!UICONTROL Platform-Datensatz-ID] von [!UICONTROL Adobe Experience Platform] generiert.

Weitere Informationen über die [Implikationen beim Löschen von Datensätzen und Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de#implications-of-deleting-data-components) erhalten Sie in [!UICONTROL Customer Journey Analytics] und [!UICONTROL Adobe Experience Platform].
