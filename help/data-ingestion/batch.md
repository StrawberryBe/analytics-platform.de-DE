---
title: Batch-Daten erfassen und verwenden
description: Erläuterung der Erfassung und Verwendung von Batch-Daten in Customer Journey Analytics
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: dd46adee-821f-489c-9350-abcfffe7cc3c
source-git-commit: 3331f41590509ef38cb67802335414ca3de5ff94
workflow-type: tm+mt
source-wordcount: '1954'
ht-degree: 7%

---

# Batch-Daten erfassen und verwenden

In dieser Kurzanleitung wird erläutert, wie Sie Batch-Daten in Adobe Experience Platform erfassen und diese Daten dann in Customer Journey Analytics verwenden können.

Gehen Sie dazu folgendermaßen vor:

- **Einrichten eines Schemas und eines Datensatzes** in Adobe Experience Platform das Modell (Schema) der Daten definieren, die Sie erfassen möchten, und wo die Daten (Datensatz) tatsächlich erfasst werden sollen.

- **Workflows verwenden** , um Ihre Batch-Daten einfach in den in Adobe Experience Platform konfigurierten Datensatz hochzuladen.

- **Verbindung einrichten** in Customer Journey Analytics. Diese Verbindung sollte (zumindest) Ihren Adobe Experience Platform-Datensatz enthalten.

- **Datenansicht einrichten** in Customer Journey Analytics , um Metriken und Dimensionen zu definieren, die Sie in Analysis Workspace verwenden möchten.

- **Einrichten eines Projekts** in Customer Journey Analytics , um Ihre Berichte und Visualisierungen zu erstellen.

>[!NOTE]
>
>Dies ist eine vereinfachte Anleitung zur Aufnahme von Batch-Daten in Adobe Experience Platform und zur Verwendung in Customer Journey Analytics. Es wird dringend empfohlen, die zusätzlichen Informationen zu untersuchen, wenn darauf verwiesen wird.

## Einrichten eines Schemas und eines Datensatzes

Um Daten in Adobe Experience Platform zu erfassen, müssen Sie zunächst definieren, welche Daten Sie erfassen möchten. Alle in Adobe Experience Platform erfassten Daten müssen einer standardmäßigen denormalisierten Struktur entsprechen, damit sie erkannt und von nachgelagerten Funktionen genutzt werden können. Experience-Datenmodell (XDM) ist das Standard-Framework, das diese Struktur in Form von Schemas bereitstellt.

Nachdem Sie ein Schema definiert haben, verwenden Sie einen oder mehrere Datensätze, um die Datenerfassung zu speichern und zu verwalten. Ein Datensatz ist ein Konstrukt zur Datenspeicherung und -verwaltung, in dem Daten (in der Regel) in einer Tabelle erfasst werden, die ein Schema (Spalten) und Felder (Zeilen) beinhaltet.

Alle Daten, die in Adobe Experience Platform erfasst werden, müssen einem vordefinierten Schema entsprechen, bevor es als Datensatz beibehalten werden kann.

### Einrichten eines Schemas

Für diesen Schnellstart möchten Sie einige Treuedaten erfassen, z. B. Treueprogramm-ID, Treuepunkte und Treuestatus.
Dazu müssen Sie zunächst ein Schema definieren, das diese Daten modelliert.

So richten Sie Ihr Schema ein:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Schemas]** Innerhalb [!UICONTROL DATENVERWALTUNG].

2. Auswählen **[!UICONTROL Schema erstellen]**. Auswählen **[!UICONTROL XDM Individual Profile]** aus der Liste der Optionen.

   ![Erstellen eines Schemas](./assets/create-schema.png)

   >[!INFO]
   >
   >    Das Modell des Profils wird mithilfe eines individuellen Profilschemas erstellt _attributes_ (z. B. E-Mail, Treuestatus, Treuepunkte). Ein Erlebnisereignis-Schema wird zum Modellieren der _Verhalten_ eines Profils (z. B. Seitenansicht, Zum Warenkorb hinzufügen).


3. Im [!UICONTROL Unbenanntes Schema] screen:

   1. Geben Sie einen Anzeigenamen für Ihr Schema und (optional) eine Beschreibung ein.

      ![Benennen Sie Ihr Schema.](./assets/name-loyalty-schema.png)

   2. Auswählen **[!UICONTROL + Hinzufügen]** in [!UICONTROL Feldergruppen].

      ![Feldergruppe hinzufügen](./assets/add-field-group-button.png)

      Feldergruppen sind wiederverwendbare Sammlungen von Objekten und Attributen, mit denen Sie Ihr Schema einfach erweitern können.

   3. Im [!UICONTROL Feldergruppen hinzufügen] wählen Sie das **[!UICONTROL Treuedetails]** Feldergruppe aus der Liste.

      ![ExperienceEvent-Feldgruppe des AEP Web SDK](./assets/loyalty-fieldgroup.png)

      Sie können die Vorschau-Schaltfläche auswählen, um eine Vorschau der Felder anzuzeigen, die zu dieser Feldergruppe gehören.

      ![AEP Web SDK ExperienceEvent-Feldgruppenvorschau](./assets/loyalty-fieldgroup-preview.png)

      Auswählen **[!UICONTROL Zurück]** , um die Vorschau zu schließen.

   4. Auswählen **[!UICONTROL Feldergruppen hinzufügen]**.

4. Auswählen **[!UICONTROL +]** neben Ihrem Schemanamen im [!UICONTROL Struktur] Bereich.

   ![Beispiel für die Schaltfläche &quot;Schema hinzufügen&quot;](./assets/example-loalty-schema-plus.png)

5. Im [!UICONTROL Feldeigenschaften] Bereich, eingeben `Identification` als Namen, **[!UICONTROL Bezeichnung]** als [!UICONTROL Anzeigename]auswählen **[!UICONTROL Objekt]** als [!UICONTROL Typ] und wählen Sie **[!UICONTROL Profil Core v2]** als [!UICONTROL Feldergruppe].

   ![Identifizierungsobjekt](./assets/identifcation-loyalty-field.png)

   Dadurch werden Ihrem Schema Identifizierungsfunktionen hinzugefügt. In Ihrem Fall möchten Sie Treueinformationen anhand der E-Mail-Adresse aus Ihren Batch-Daten identifizieren.

   Auswählen **[!UICONTROL Anwenden]** , um dieses Objekt Ihrem Schema hinzuzufügen.

6. Wählen Sie die **[!UICONTROL email]** im soeben hinzugefügten Identifizierungsobjekt ein und wählen Sie **[!UICONTROL Identität]** und **[!UICONTROL Email]** von [!UICONTROL Identitäts-Namespace] im [!UICONTROL Feldeigenschaften] Bereich.

   ![E-Mail als Identität angeben](./assets/specify-email-loyalty-id.png)

   Sie geben die E-Mail-Adresse als Identität an, die der Adobe Experience Platform Identity-Dienst zum Kombinieren (Zuordnen) von Profilen verwenden kann.

   Auswählen **[!UICONTROL Anwenden]**. Im E-Mail-Attribut wird ein Fingerabdrucksymbol angezeigt.

   Wählen Sie **[!UICONTROL Speichern]** aus.

7. Wählen Sie die Stammebene Ihres Schemas (mit dem Schemanamen) aus und wählen Sie dann die **[!UICONTROL Profil]** umschalten.

   Sie werden aufgefordert, das Schema für das Profil zu aktivieren. Nach der Aktivierung werden diese Daten bei der Erfassung von Daten in Datensätzen, die auf diesem Schema basieren, mit dem Echtzeit-Kundenprofil zusammengeführt.

   Siehe [Aktivieren des Schemas zur Verwendung im Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) für weitere Informationen.

   >[!IMPORTANT]
   >
   >    Nachdem Sie ein für ein Profil aktiviertes Schema gespeichert haben, kann es für das Profil nicht mehr deaktiviert werden.

   ![Schema für Profil aktivieren](./assets/enable-for-profile.png)

8. Auswählen **[!UICONTROL Speichern]** , um Ihr Schema zu speichern.

Sie haben ein Minimalschema erstellt, das die Treuedaten modelliert, die Sie in Adobe Experience Platform erfassen können. Mithilfe des Schemas können Profile anhand der E-Mail-Adresse identifiziert werden. Durch Aktivierung des Schemas für das Profil stellen Sie sicher, dass Daten aus Ihrer Batch-Datei zum Echtzeit-Kundenprofil hinzugefügt werden.

Siehe [Erstellen und Bearbeiten von Schemata in der Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html?lang=de) für weitere Informationen zum Hinzufügen und Entfernen von Feldergruppen und einzelnen Feldern zu einem Schema.

### Datensatz einrichten

Mit Ihrem Schema haben Sie Ihr Datenmodell definiert. Jetzt müssen Sie das Konstrukt definieren, um diese Daten zu speichern und zu verwalten. Dies erfolgt über Datensätze.

So richten Sie Ihren Datensatz ein:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Datensätze]** Innerhalb [!UICONTROL DATENVERWALTUNG].

2. Auswählen **[!UICONTROL Datensatz erstellen]**.

   ![Datensatz erstellen](./assets/create-dataset.png)

3. Wählen Sie **[!UICONTROL Datensatz aus Schema erstellen]** aus.

   ![Datensatz aus Schema erstellen](./assets/create-dataset-from-schema.png)

4. Wählen Sie das zuvor erstellte Schema aus und wählen Sie **[!UICONTROL Nächste]**.

5. Benennen Sie Ihren Datensatz und geben Sie (optional) eine Beschreibung ein.

   ![Datensatz benennen](./assets/name-your-datatest.png)

6. Auswählen **[!UICONTROL Beenden]**.

7. Wählen Sie die **[!UICONTROL Profil]** umschalten.

   Sie werden aufgefordert, den Datensatz für das Profil zu aktivieren. Nach der Aktivierung reichert der Datensatz Echtzeit-Kundenprofile mit den erfassten Daten an.

   >[!IMPORTANT]
   >
   >    Sie können einen Datensatz für ein Profil nur aktivieren, wenn das Schema, dem der Datensatz entspricht, auch für das Profil aktiviert ist.

   ![Schema für Profil aktivieren](./assets/loyalty-dataset-profile.png)

Siehe [Handbuch zur Benutzeroberfläche von Datensätzen](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=de) für viele weitere Informationen zum Anzeigen, Anzeigen, Erstellen, Löschen eines Datensatzes in der Vorschau. Und wie Sie einen Datensatz für das Echtzeit-Kundenprofil aktivieren.


## Workflows verwenden

Sie verwenden die Workflow-Funktion, um Ihre Batch-Daten in Adobe Experience Platform hochzuladen. Die von Ihnen verwendete Beispiel-Batch-Datei ist eine CSV-Datei mit folgendem Inhalt:

```
email,loyaltyID,points,status
abrocking0@blog.com,793406,82.16,Silver
wnichol1@ycombinator.com,988654,40.39,Gold
paisbett2@slideshare.net,444897,91.25,Bronze
bdiamant3@xinhuanet.com,239658,57.87,Gold
ppales4@nsw.gov.au,365384,82.71,Silver
...
```

So verwenden Sie Workflows:

1. Wählen Sie in der Platform-Benutzeroberfläche die Option **[!UICONTROL Workflows]** in der linken Leiste.

2. Auswählen **[!UICONTROL Zuordnen von CSV zu XDM-Schema]**. Auswählen **[!UICONTROL Launch]**.

   ![Zuordnen von CSV zu XDN](./assets/workflow-mapcsvtoxdm.png)

3. Im [!UICONTROL Zuordnen von CSV zu XDM-Schema] im [!UICONTROL Datenflussdetails] step:

   Auswählen **[!UICONTROL Vorhandener Datensatz]**, wählen Sie Ihren Datensatz aus der Datensatzliste aus und benennen Sie Ihre [!UICONTROL Dataflow-Name].

   ![Dataflow](./assets/workflow-dataflowdetail.png)

   Klicken Sie auf **[!UICONTROL Weiter]**.

4. Im [!UICONTROL Daten auswählen] step:

   Ziehen und Ablegen oder Auswählen **[!UICONTROL Dateien auswählen]** , um Ihre CSV-Datei mit Treuedaten auszuwählen. Sie sehen eine Vorschau Ihrer Treuedaten.

   ![Auswählen von Daten](./assets/workflow-selectdata.png)

   Klicken Sie auf **[!UICONTROL Weiter]**.

5. Im [!UICONTROL Zuordnung] step:

   Ordnen Sie Ihre Daten aus der CSV-Datei den Daten in Ihrem Schema zu. Mit AI versucht die Workflow-Funktion, die Batch-Datenfelder automatisch den Schemafeldern zuzuordnen.

   ![Daten zuordnen](./assets/workflow-dataflow-mapping.png)

   Sie können **[!UICONTROL Datenvorschau]** um eine Vorschau der zugeordneten Daten anzuzeigen.

   ![Vorschau-Mapping](./assets/workflow-dataflow-mapping-preview.png)

6. Auswählen **[!UICONTROL Beenden]** , um Ihre Batch-Daten in Adobe Experience Platform zu erfassen.

Siehe [CSV-Datei über einem vorhandenen XDM-Schema zuordnen](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema.html) Weitere Informationen zum Zuordnen von Daten, wenn Ihre eingehenden Daten nicht mit Ihrem XDM-Schema kompatibel sind, verwenden Sie Zuordnungsvorlagen, verwenden Sie das berechnete Feld, um sicherzustellen, dass Ihre Batch-Daten den Erwartungen des Schemas entsprechen, und vieles mehr.


## Verbindung einrichten

Um die Adobe Experience Platform-Daten in Customer Journey Analytics zu verwenden, erstellen Sie eine Verbindung, die die Daten enthält, die sich aus der Einrichtung Ihres Schemas, Datensatzes und Workflows ergeben.

Mithilfe einer Verbindung können Sie Datensätze aus Adobe Experience Platform in Arbeitsbereich integrieren. Um über diese Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen den Datensätzen in Adobe Experience Platform und Workspace herstellen.

So erstellen Sie Ihre Verbindung:

1. Wählen Sie in der Customer Journey Analytics-Benutzeroberfläche die Option **[!UICONTROL Verbindungen]** in der oberen Navigation.

2. Auswählen **[!UICONTROL Neue Verbindung erstellen]**.

3. Im [!UICONTROL Verbindung ohne Titel] screen:

   Benennen und beschreiben Sie Ihre Verbindung in [!UICONTROL Verbindungseinstellungen].

   Wählen Sie die richtige Sandbox aus der [!UICONTROL Sandbox] Liste in [!UICONTROL Dateneinstellungen] und wählen Sie die Anzahl der täglichen Ereignisse aus der [!UICONTROL Durchschnittliche Anzahl der täglichen Ereignisse] Liste.

   ![Verbindungseinstellungen](./assets/cja-connections-1.png)

   Auswählen **[!UICONTROL Hinzufügen von Datensätzen]**.

   Im [!UICONTROL Auswählen von Datensätzen] Schritt in [!UICONTROL Hinzufügen von Datensätzen]:

   - Wählen Sie den zuvor erstellten Datensatz aus (`Example Loyalty Dataset`) und einen anderen Datensatz, den Sie in Ihre Verbindung aufnehmen möchten.

      ![Hinzufügen von Datensätzen](./assets/cja-connections-2.png)

   - Klicken Sie auf **[!UICONTROL Weiter]**.
   Im [!UICONTROL Datensatzeinstellungen] Schritt in [!UICONTROL Hinzufügen von Datensätzen]:

   - Für jeden Datensatz:

      - Wählen Sie eine [!UICONTROL Personen-ID] aus den verfügbaren Identitäten, die in den Datensatzschemas in Adobe Experience Platform definiert sind.

      - Wählen Sie die richtige Datenquelle aus der [!UICONTROL Datenquellentyp] Liste. Wenn Sie **[!UICONTROL Sonstiges]** und fügen Sie dann eine Beschreibung für Ihre Datenquelle hinzu.

      - Satz **[!UICONTROL Alle neuen Daten importieren]** und **[!UICONTROL Aufstockung vorhandener Daten durch Datensätze]** entsprechend Ihren Vorlieben.

      ![Konfigurieren von Datensätzen](./assets/cja-connections-3.png)

   - Auswählen **[!UICONTROL Hinzufügen von Datensätzen]**.
   Wählen Sie **[!UICONTROL Speichern]** aus.

Siehe [Verbindungen - Übersicht](../connections/overview.md) Weitere Informationen zum Erstellen und Verwalten einer Verbindung und zum Auswählen und Kombinieren von Datensätzen.

## Datenansicht einrichten

Eine Datenansicht ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie Daten aus einer Verbindung interpretiert werden. Es werden alle in Analysis Workspace verfügbaren Dimensionen und Metriken sowie die Spalten angegeben, aus denen diese Dimensionen und Metriken ihre Daten abrufen. Datenansichten werden in Vorbereitung auf das Reporting in Analysis Workspace definiert.

So erstellen Sie Ihre Datenansicht:

1. Wählen Sie in der Customer Journey Analytics-Benutzeroberfläche die Option **[!UICONTROL Datenansichten]** in der oberen Navigation.

2. Auswählen **[!UICONTROL Neue Datenansicht erstellen]**.

3. Im [!UICONTROL Konfigurieren] step:

   Wählen Sie Ihre Verbindung aus der [!UICONTROL Verbindung] Liste.

   Geben Sie einen Namen ein und beschreiben Sie (optional) Ihre Verbindung.

   ![Konfiguration der Datenansicht](./assets/cja-dataview-1.png)

   Auswählen **[!UICONTROL Speichern und fortfahren]**.

4. Im [!UICONTROL Komponenten] step:

   Fügen Sie jedes Schemafeld und/oder jede Standardkomponente hinzu, die Sie in die [!UICONTROL METRIKEN] oder [!UICONTROL Dimensionen] Komponentenfelder.

   ![Datenansichtskomponenten](./assets/cja-dataview-2.png)

   Auswählen **[!UICONTROL Speichern und fortfahren]**.

5. Im [!UICONTROL Einstellungen] step:

   ![Datenansichtseinstellungen](./assets/cja-dataview-3.png)

   Behalten Sie die Einstellungen bei und wählen Sie **[!UICONTROL Speichern und beenden]**.

Siehe [Datenansichten - Übersicht](../data-views/data-views.md) Weitere Informationen zum Erstellen und Bearbeiten einer Datenansicht, dazu, welche Komponenten in Ihrer Datenansicht verfügbar sind und wie Filter- und Sitzungseinstellungen verwendet werden.


## Einrichten eines Projekts

Analysis Workspace ist ein flexibles Browser-Tool, mit dem Sie schnell Analysen erstellen und basierend auf Ihren Daten Erkenntnisse austauschen können. Sie verwenden Workspace-Projekte, um Datenkomponenten, Tabellen und Visualisierungen zu kombinieren, um Ihre Analyse zu gestalten und für andere in Ihrer Organisation freizugeben.

So erstellen Sie Ihr Projekt:

1. Wählen Sie in der Customer Journey Analytics-Benutzeroberfläche die Option **[!UICONTROL Projekte]** in der oberen Navigation.

2. Auswählen **[!UICONTROL Projekte]** in der linken Navigation.

3. Auswählen **[!UICONTROL Projekt erstellen]**.

   ![Workspace-Projekt](./assets/cja-projects-1.png)

   Auswählen **[!UICONTROL Leeres Projekt]**.

   ![Workspace - Leeres Projekt](./assets/cja-projects-2.png)

4. Wählen Sie Ihre Datenansicht aus der Liste aus.

   ![Ansicht &quot;Workspace Select Data&quot;](./assets/cja-projects-3.png).

5. Ziehen und Ablegen von Dimensionen und Metriken auf die [!UICONTROL Freiformtabelle] im [!UICONTROL Bedienfeld] um Ihren ersten Bericht zu erstellen. Ziehen Sie als Beispiel `Program Points Balance` und `Page View` als Metriken und `email` als Dimension zu erhalten, um einen schnellen Überblick über die Profile zu erhalten, die Ihre Website besucht haben und Teil des Treueprogramms sind, das Treuepunkte sammelt.

   ![Workspace - Erster Bericht](./assets/cja-projects-5.png)

Siehe [Übersicht über Analysis Workspace](../analysis-workspace/home.md) Weitere Informationen zum Erstellen von Projekten und zum Erstellen Ihrer Analyse mithilfe von Komponenten, Visualisierungen und Bedienfeldern.

>[!SUCCESS]
>
>Sie haben alle Schritte ausgeführt. Sie haben zunächst definiert, welche Treuedaten Sie erfassen möchten (Schema) und wo Sie sie (Datensatz) in Adobe Experience Platform speichern möchten, und einen Workflow zum Hochladen von Treuedaten in einen Datensatz konfiguriert. Sie haben eine Verbindung in Customer Journey Analytics definiert, um die erfassten Treuedaten und anderen Daten zu verwenden. Mit Ihrer Datenansichtsdefinition können Sie festlegen, welche Dimension und Metriken verwendet werden sollen, und schließlich Ihre erste Projektvisualisierung und -analyse erstellen.
