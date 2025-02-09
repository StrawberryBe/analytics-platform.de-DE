---
title: Sitzungseinstellungen
description: Mit den Einstellungen in einer Datenansicht können Sie die Sitzungslänge und den Trigger zum Initiieren einer neuen Sitzung festlegen
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: bb2061f9119b8391bf3cedce4029685537d1e239
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 100%

---


# Sitzungseinstellungen

Sitzungseinstellungen in Datenansichten verändern die Art und Weise, wie Customer Journey Analytics Sitzungen aus den Daten in Ihrer Verbindung berechnet.

Auf der Registerkarte **[!UICONTROL Einstellungen]** von Datenansichten können Sie eine Sitzung entsprechend dessen definieren, wie Personen mit Ihren digitalen Erlebnissen interagieren. Definitionen von Sitzungseinstellungen sind zerstörungsfrei und verändern die zugrunde liegenden Daten nicht. Sie können mehrere Datenansichten (jede mit ihrer spezifischen Definition von Sitzungseinstellungen) als Grundlage für Ihre Workspace-Projekte einrichten.

So definieren Sie den Kontext einer Sitzung für eine Datenansicht:

1. Wählen Sie **[!UICONTROL Datenansichten]** in der Customer Journey Analytics-Benutzeroberfläche.

2. Erstellen Sie eine neue oder bearbeiten Sie eine vorhandene Datenansicht. Weitere Informationen finden Sie unter [Erstellen oder Bearbeiten einer Datenansicht](create-dataview.md).

3. Wählen Sie die Registerkarte **[!UICONTROL Einstellungen]** aus. Unter [!UICONTROL Sitzungseinstellungen]:

   1. Geben Sie einen Wert für ein **[!UICONTROL Sitzungs-Timeout]** in [!UICONTROL Minute(n)], [!UICONTROL Stunde(n)], [!UICONTROL Tag(en) ] oder [!UICONTROL Woche(n)] ein. Durch das Sitzungs-Timeout ist festgelegt, wie lange eine Sitzung inaktiv sein kann (es treten keine Ereignisse auf), bevor eine neue Sitzung gestartet wird.

      Verwenden Sie ein kurzes Sitzungs-Timeout (z. B. 30 Minuten), wenn Sie hauptsächlich Online-Interaktionen analysieren möchten. Wenn Sie beispielsweise analysieren, ob Profile, die Ihre Online-Store-Produktseiten besucht haben, Produkte zum Warenkorb hinzugefügt oder sogar online gekauft haben.

      Verwenden Sie einen langes Sitzungs-Timeout (z. B. 3 Monate), wenn Sie Online- und Offline-Daten kombinieren und analysieren möchten, ob Kundinnen bzw. Kunden, die eines oder mehrere Ihrer Produkte gekauft haben, innerhalb der ersten drei Monate nach dem Kauf Ihr Kontaktzentrum angerufen haben.


   2. Wählen Sie eine Metrik aus der Liste **[!UICONTROL Metrik hier ablegen]** unter **[!UICONTROL Neue Sitzung mit einer Metrik starten]** aus. Alternativ können Sie per Drag-and-Drop eine Metrik aus dem linken Bereich auf den Bereich **[!UICONTROL Metrik ablegen]** ziehen. Die ausgewählte Metrik definiert den Beginn einer neuen Sitzung. Sie können mehr als eine Metrik definieren.

      Sie können eine beliebige Metrik verwenden, um eine neue Sitzung zu definieren. Angenommen, Sie möchten jedes Mal, wenn ein Profil Ihre Mobile App startet, eine neue Sitzung definieren. In **[!UICONTROL Datenansicht]** > **[!UICONTROL Komponenten]**, definieren Sie dazu eine Komponente des Typs Metrik namens **[!UICONTROL Starts]**, basierend auf der Aktion **[!UICONTROL appInteraction]** **[!UICONTROL Name]** Schemafeld. Sie können die Metrikkomponente **[!UICONTROL Starts]** weiter so spezifizieren, dass sie den Wert nur zählt, wenn er mit `launch` übereinstimmt.

      ![App-Interaktionsmetrik – Komponente „Starts“](assets/component-launches.png)

      Anschließend können Sie per Drag-and-Drop (oder indem Sie die Metrik **[!UICONTROL Starts]** auswählen) die Metrik für die Definition einer neuen Sitzung auswählen.

      ![Sitzungseinstellungen – Starts](assets/session-settings-launches-metric.png)



4. Wählen Sie **[!UICONTROL Speichern]** oder **[!UICONTROL Speichern und beenden]**, um die Definitionen der Sitzungseinstellungen zu speichern.

