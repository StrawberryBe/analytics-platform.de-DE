---
title: Daten über Adobe Experience Platform Web SDK und Edge Network erfassen
description: Erläuterung der Datenerfassung in Customer Journey Analytics über das Adobe Experience Platform Web SDK und das Edge Network
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 0b595e9e-0dcf-4c70-ac6d-5a2322824328
source-git-commit: 43f77ffb3538e96798e68b35ec4541ba650c2090
workflow-type: tm+mt
source-wordcount: '3587'
ht-degree: 9%

---

# Daten über Adobe Experience Platform Web SDK und Edge Network erfassen

In dieser Kurzanleitung wird erläutert, wie Sie Website-Tracking-Daten mithilfe des Adobe Experience Platform Web SDK und Edge Network direkt in Adobe Experience Platform erfassen und dann in Customer Journey Analytics verwenden können.

Gehen Sie dazu folgendermaßen vor:

- **Einrichten eines Schemas und eines Datensatzes** in Adobe Experience Platform das Modell (Schema) der Daten definieren, die Sie erfassen möchten, und wo die Daten (Datensatz) tatsächlich erfasst werden sollen.

- **Einrichten eines Datastreams** , um das Adobe Experience Platform Edge Network so zu konfigurieren, dass Ihre erfassten Daten an den in Adobe Experience Platform konfigurierten Datensatz weitergeleitet werden.

- **Verwenden von Tags** um Regeln und Datenelemente einfach mit den Daten in Ihrer Datenschicht auf Ihrer Website zu konfigurieren. Stellen Sie dann sicher, dass die Daten an den im Adobe Experience Platform Edge Network konfigurierten Datastream gesendet werden.

- **Bereitstellen und Überprüfen**. Sie verfügen über eine Umgebung, in der Sie die Entwicklung von Tags iterieren können. Sobald alles validiert ist, veröffentlichen Sie es live in Ihrer Produktionsumgebung.

- **Verbindung einrichten** in Customer Journey Analytics. Diese Verbindung sollte (zumindest) Ihren Adobe Experience Platform-Datensatz enthalten.

- **Datenansicht einrichten** in Customer Journey Analytics , um Metriken und Dimensionen zu definieren, die Sie in Analysis Workspace verwenden möchten.

- **Einrichten eines Projekts** in Customer Journey Analytics , um Ihre Berichte und Visualisierungen zu erstellen.

>[!NOTE]
>
>Dies ist eine vereinfachte Anleitung zur Erfassung von Daten, die von Ihrer Site in Adobe Experience Platform erfasst und in Customer Journey Analytics verwendet werden. Es wird dringend empfohlen, die zusätzlichen Informationen zu untersuchen, wenn darauf verwiesen wird.


## Einrichten eines Schemas und eines Datensatzes

Um Daten in Adobe Experience Platform zu erfassen, müssen Sie zunächst definieren, welche Daten Sie erfassen möchten. Alle in Adobe Experience Platform erfassten Daten müssen einer standardmäßigen denormalisierten Struktur entsprechen, damit sie erkannt und von nachgelagerten Funktionen genutzt werden können. Experience-Datenmodell (XDM) ist das Standard-Framework, das diese Struktur in Form von Schemas bereitstellt.

Nachdem Sie ein Schema definiert haben, verwenden Sie einen oder mehrere Datensätze, um die Datenerfassung zu speichern und zu verwalten. Ein Datensatz ist ein Konstrukt zur Datenspeicherung und -verwaltung, in dem Daten (in der Regel) in einer Tabelle erfasst werden, die ein Schema (Spalten) und Felder (Zeilen) beinhaltet.

Alle Daten, die in Adobe Experience Platform erfasst werden, müssen einem vordefinierten Schema entsprechen, bevor es als Datensatz beibehalten werden kann.

### Einrichten eines Schemas

Sie möchten einige Mindestdaten aus Profilen verfolgen, die Ihre Website besuchen, z. B. Seitenname und Identifizierung.
Dazu müssen Sie zunächst ein Schema definieren, das diese Daten modelliert.

So richten Sie Ihr Schema ein:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Schemas]** Innerhalb [!UICONTROL DATENVERWALTUNG].

2. Auswählen **[!UICONTROL Schema erstellen]**. Auswählen **[!UICONTROL XDM ExperienceEvent]** aus der Liste der Optionen.

   ![Erstellen eines Schemas](./assets/create-ee-schema.png)

   >[!INFO]
   >
   >    Ein Erlebnisereignis-Schema wird zum Modellieren der _Verhalten_ eines Profils (z. B. Seitenansicht, Zum Warenkorb hinzufügen). Das Modell des Profils wird mithilfe eines individuellen Profilschemas erstellt _attributes_ (z. B. Name, E-Mail, Geschlecht).


3. Im [!UICONTROL Unbenanntes Schema] screen:

   1. Geben Sie einen Anzeigenamen für Ihr Schema und (optional) eine Beschreibung ein.

      ![Benennen Sie Ihr Schema.](./assets/name-schema.png)

   2. Auswählen **[!UICONTROL + Hinzufügen]** in [!UICONTROL Feldergruppen].

      ![Feldergruppe hinzufügen](./assets/add-field-group-button.png)

      Feldergruppen sind wiederverwendbare Sammlungen von Objekten und Attributen, mit denen Sie Ihr Schema einfach erweitern können.

   3. Im [!UICONTROL Feldergruppen hinzufügen] wählen Sie das **[!UICONTROL AEP Web SDK ExperienceEvent]** Feldergruppe aus der Liste.

      ![ExperienceEvent-Feldgruppe des AEP Web SDK](./assets/select-aepwebsdk-experienceevent.png)

      Sie können die Vorschau-Schaltfläche auswählen, um eine Vorschau der Felder anzuzeigen, die zu dieser Feldergruppe gehören, z. B. `web > webPageDetails > name`.

      ![AEP Web SDK ExperienceEvent-Feldgruppenvorschau](./assets/aepwebsdk-experiencevent-preview.png)

      Auswählen **[!UICONTROL Zurück]** , um die Vorschau zu schließen.

   4. Auswählen **[!UICONTROL Feldergruppen hinzufügen]**.

4. Auswählen **[!UICONTROL +]** neben Ihrem Schemanamen im [!UICONTROL Struktur] Bereich.

   ![Beispiel für die Schaltfläche &quot;Schema hinzufügen&quot;](./assets/example-schema-plus.png)

5. Im [!UICONTROL Feldeigenschaften] Bereich, eingeben `Identification` als Namen, **[!UICONTROL Bezeichnung]** als [!UICONTROL Anzeigename]auswählen **[!UICONTROL Objekt]** als [!UICONTROL Typ] und wählen Sie **[!UICONTROL ExperienceEvent Core v2.1]** als [!UICONTROL Feldergruppe].

   ![Identifizierungsobjekt](./assets/identification-field.png)

   Dadurch werden Ihrem Schema Identifizierungsfunktionen hinzugefügt. In Ihrem Fall möchten Sie Profile, die Ihre Site besuchen, mithilfe der Experience Cloud-ID und der E-Mail-Adresse identifizieren. Es stehen viele weitere Attribute zur Verfolgung der Besucheridentifizierung zur Verfügung (z. B. Kunden-ID, Treueprogramm-ID).

   Auswählen **[!UICONTROL Anwenden]** , um dieses Objekt Ihrem Schema hinzuzufügen.

6. Wählen Sie die **[!UICONTROL ecid]** im soeben hinzugefügten Identifizierungsobjekt ein und wählen Sie **[!UICONTROL Identität]** und **[!UICONTROL Primäre Identität]** und **[!UICONTROL ECID]** von [!UICONTROL Identitäts-Namespace] im rechten Bereich.

   ![ECID als Identität angeben](./assets/specify-identity.png)

   Sie legen die Experience Cloud-Identität als primäre Identität fest, die der Adobe Experience Platform Identity-Dienst verwenden kann, um das Profilverhalten mit derselben ECID zu kombinieren (zuzuordnen).

   Auswählen **[!UICONTROL Anwenden]**. Sie sehen, dass ein Fingerabdruck-Symbol im ecid-Attribut angezeigt wird.

7. Wählen Sie die **[!UICONTROL email]** im soeben hinzugefügten Identifizierungsobjekt ein und wählen Sie **[!UICONTROL Identität]** und **[!UICONTROL Email]** von [!UICONTROL Identitäts-Namespace] in der [!UICONTROL Feldeigenschaften] Bereich.

   ![E-Mail als Identität angeben](./assets/specify-email-identity.png)

   Sie geben die E-Mail-Adresse als eine andere Identität an, die der Adobe Experience Platform Identity-Dienst verwenden kann, um das Profilverhalten zu kombinieren (zuzuordnen).

   Auswählen **[!UICONTROL Anwenden]**. Im E-Mail-Attribut wird ein Fingerabdrucksymbol angezeigt.

   Wählen Sie **[!UICONTROL Speichern]** aus.

8. Wählen Sie das Stammelement Ihres Schemas aus, das den Namen des Schemas anzeigt, und wählen Sie dann die **[!UICONTROL Profil]** umschalten.

   Sie werden aufgefordert, das Schema für das Profil zu aktivieren. Nach der Aktivierung werden diese Daten bei der Erfassung von Daten in Datensätzen, die auf diesem Schema basieren, mit dem Echtzeit-Kundenprofil zusammengeführt.

   Siehe [Aktivieren des Schemas zur Verwendung im Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=en#profile) für weitere Informationen.

   >[!IMPORTANT]
   >
   >    Nachdem Sie ein für ein Profil aktiviertes Schema gespeichert haben, kann es für das Profil nicht mehr deaktiviert werden.

   ![Schema für Profil aktivieren](./assets/enable-for-profile.png)

9. Auswählen **[!UICONTROL Speichern]** , um Ihr Schema zu speichern.

Sie haben ein Minimalschema erstellt, das die Daten modelliert, die Sie von Ihrer Website erfassen können. Mithilfe des Schemas können Profile anhand der Identität des Experience Cloud und der E-Mail-Adresse identifiziert werden. Durch Aktivierung des Schemas für das Profil stellen Sie sicher, dass aus Ihrer Website erfasste Daten zum Echtzeit-Kundenprofil hinzugefügt werden.

Neben den Verhaltensdaten können Sie auch Profilattributdaten aus Ihrer Site erfassen (z. B. Details zu Profilen, die einen Newsletter abonnieren).

Um diese Profildaten zu erfassen, gehen Sie folgendermaßen vor:

- Erstellen Sie ein Schema basierend auf der Klasse &quot;XDM Individual Profile&quot;.

- Fügen Sie die Feldergruppe Profil-Core v2 zum Schema hinzu.

- Fügen Sie ein Identifizierungsobjekt hinzu, das auf der Feldergruppe Profil Core v2 basiert.

- Definieren Sie ecid als primäre Kennung und E-Mail als Kennung.

- Aktivieren des Schemas für das Profil

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

   ![Schema für Profil aktivieren](./assets/aepwebsdk-dataset-profile.png)

Siehe [Handbuch zur Benutzeroberfläche von Datensätzen](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=de) für viele weitere Informationen zum Anzeigen, Anzeigen, Erstellen, Löschen eines Datensatzes in der Vorschau. Und wie Sie einen Datensatz für das Echtzeit-Kundenprofil aktivieren.

## Einrichten eines Datastreams

Ein Datenstrom stellt die Server-seitige Konfiguration bei der Implementierung der Adobe Experience Platform Web- und Mobile-SDKs dar. Beim Erfassen von Daten mit den Adobe Experience Platform SDK werden Daten an das Adobe Experience Platform Edge Network gesendet. Es ist der Datastream, der bestimmt, an welche Dienste diese Daten weitergeleitet werden.

Bei Ihrer Einrichtung möchten Sie, dass die von der Website erfassten Daten an Ihren Datensatz in Adobe Experience Platform gesendet werden.

So richten Sie Ihren Datenspeicher ein:

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche die Option **[!UICONTROL Datenspeicher]** von [!UICONTROL DATENERFASSUNG] in der linken Leiste.

2. Auswählen **[!UICONTROL Neuer Datenspeicher]**.

3. Benennen und beschreiben Sie Ihren Datastream. Wählen Sie Ihr Schema aus dem [!UICONTROL Ereignisschema] Liste.

   ![Neuer Datenspeicher](./assets/new-datastream.png)

4. Wählen Sie **[!UICONTROL Speichern]** aus.

5. Auswählen **[!UICONTROL Dienst hinzufügen]**.

6. Im [!UICONTROL Bildschirm &quot;Dienst hinzufügen&quot;]:

   1. Auswählen **[!UICONTROL Adobe Experience Platform]** von [!UICONTROL Diensleistung] Liste.

   2. Sichern **[!UICONTROL Aktiviert]** ausgewählt ist.

   3. Wählen Sie Ihren Datensatz aus der [!UICONTROL Ereignis-Datensatz] Liste.

      ![Datastream AEP-Dienst](./assets/datastream-aep-service.png)

   4. Belassen Sie die anderen Einstellungen und wählen Sie **[!UICONTROL Speichern]** , um den Datastream zu speichern.

Ihr Datenspeicher ist jetzt so konfiguriert, dass die von Ihrer Website erfassten Daten an Ihren Datensatz in Adobe Experience Platform weitergeleitet werden.

Siehe [Übersicht über Datenspeicher](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/overview.html?lang=de) Weitere Informationen zum Konfigurieren eines Datastreams und zum Umgang mit sensiblen Daten.



## Verwenden von Tags

Verwenden Sie die Funktion Tags in Adobe Experience Platform, um Code auf Ihrer Site zu implementieren, um Daten zu erfassen. Mit dieser Tag-Management-Lösung können Sie Code zusammen mit anderen Tagging-Anforderungen bereitstellen. Tags bieten eine nahtlose Integration mit Adobe Experience Platform mithilfe der Adobe Experience Platform Web SDK-Erweiterung.

### Tag erstellen

1. Wählen Sie in der Adobe Experience Platform-Benutzeroberfläche in der linken Leiste die Option **[!UICONTROL Tags]** Innerhalb [!UICONTROL DATENERFASSUNG].

2. Wählen Sie **[!UICONTROL Neue Eigenschaft]** aus.

   Benennen Sie das Tag, wählen Sie **[!UICONTROL Web]** und geben Sie einen Domänennamen ein. Auswählen **[!UICONTROL Speichern]** , um fortzufahren.

   ![Erstellen einer Eigenschaft](./assets/create-property.png)

### Tag konfigurieren

Nachdem Sie das Tag erstellt haben, müssen Sie es mit den richtigen Erweiterungen konfigurieren und Datenelemente und Regeln entsprechend der gewünschten Verfolgung Ihrer Site konfigurieren und Daten an Adobe Experience Platform senden.

Wählen Sie das neu erstellte Tag aus der Liste der [!UICONTROL Tag-Eigenschaften] um es zu öffnen.


#### **Erweiterungen**

Fügen Sie Ihrem -Tag die Adobe Platform Web SDK-Erweiterung hinzu, um sicherzustellen, dass Sie Daten (über Ihren Datenspeicher) an Adobe Experience Platform senden können.

So erstellen und konfigurieren Sie die Adobe Experience Platform Web SDK-Erweiterung:

1. Auswählen **[!UICONTROL Erweiterungen]** in der linken Leiste.

2. Auswählen **[!UICONTROL Katalog]** in der oberen Leiste.

3. Suchen Sie nach der Adobe Experience Platform Web SDK-Erweiterung oder blättern Sie zu ihr und wählen Sie **[!UICONTROL Installieren]** um es zu installieren.

   <img src="./assets/aepwebsdk-extension.png" width="35%"/>

4. Wählen Sie Ihre Sandbox und Ihren zuvor erstellten Datenspeicher für Ihre [!UICONTROL Produktionsumgebung] und (optional) [!UICONTROL Staging-Umgebung] und [!UICONTROL Entwicklungsumgebung].

   ![Konfiguration der AEP Web SDK-Erweiterung](./assets/aepwebsk-extension-datastreams.png)

   Wählen Sie **[!UICONTROL Speichern]** aus.

Siehe [Konfigurieren der Adobe Experience Platform Web SDK-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) für weitere Informationen.

Sie möchten auch die Experience Cloud-ID-Dienst-Erweiterung einrichten, damit Sie die Experience Cloud-ID einfach verwenden können. Der Experience Cloud-ID-Dienst identifiziert Besucher in allen Adobe Experience Cloud-Lösungen.

So erstellen und konfigurieren Sie die Experience Cloud ID Service-Erweiterung:

1. Auswählen **[!UICONTROL Erweiterungen]** in der linken Leiste.

2. Auswählen **[!UICONTROL Katalog]** in der oberen Leiste.

3. Suchen Sie nach der Experience Cloud ID Service-Erweiterung oder blättern Sie zu ihr und wählen Sie **[!UICONTROL Installieren]** um es zu installieren.

   <img src="./assets/ecid-extension.png" width="35%"/>

4. Behalten Sie alle Konfigurationen bei der Standardeinstellung bei.

5. Wählen Sie **[!UICONTROL Speichern]** aus.

#### **Datenelemente**

Datenelemente sind Bausteine für Ihr Datenwörterbuch (oder Ihre Datenkarte). Verwenden Sie Datenelemente zum Sammeln, Organisieren und Bereitstellen von Daten in Marketing- und Werbetechnologie. Sie richten Datenelemente in Ihrem Tag ein, die aus Ihrer Datenschicht gelesen werden und zur Bereitstellung von Daten in Adobe Experience Platform verwendet werden können.

Es gibt verschiedene Arten von Datenelementen. Sie richten zunächst ein Datenelement ein, um den Seitennamen zu erfassen, den Besucher auf Ihrer Site anzeigen.

So definieren Sie ein Datenelement für den Seitennamen:

1. Auswählen **[!UICONTROL Datenelemente]** in der linken Leiste.

2. Auswählen **[!UICONTROL Datenelement hinzufügen]**.

3. Im [!UICONTROL Datenelement erstellen] dialog:

   - Benennen Sie Ihr Datenelement, z. B. `Page Name`.

   - Auswählen **[!UICONTROL Core]** von [!UICONTROL Erweiterung] Liste.

   - Auswählen **[!UICONTROL Seiteninformationen]** von [!UICONTROL Datenelementtyp] Liste.

   - Auswählen **[!UICONTROL Titel]** von [!UICONTROL Attribut] Liste.

      ![Erstellen eines Datumselements mithilfe der Seiteninformationen](./assets/create-dataelement-1.png)

      Sie haben auch den Wert aus einer Variablen Ihrer Datenschicht verwenden können, z. B. `pageName` und [!UICONTROL JavaScript-Variable] Datenelementtyp zum Definieren des Datenelements.

      ![Erstellen eines Datenelements mit der JavaScript-Variablen](./assets/create-dataelement-2.png)

   - Wählen Sie **[!UICONTROL Speichern]** aus.

Sie möchten jetzt ein Datenelement einrichten, das auf die Experience Cloud-ID verweist, die automatisch vom Adobe Experience Platform Web SDK bereitgestellt und über die Experience Cloud ID Service-Erweiterung verfügbar ist.

So definieren Sie ein ECID-Datenelement:

1. Auswählen **[!UICONTROL Datenelemente]** in der linken Leiste.

2. Auswählen **[!UICONTROL Datenelement hinzufügen]**.

3. Im [!UICONTROL Datenelement erstellen] dialog:

   - Benennen Sie Ihr Datenelement, z. B. `ECID`.

   - Auswählen **[!UICONTROL Experience Cloud-ID-Dienst]** von [!UICONTROL Erweiterung] Liste.

   - Auswählen **[!UICONTROL ECID]** von [!UICONTROL Datenelementtyp] Liste.

      ![ECID-Datenelement](./assets/ecid-dataelement.png)

   - Wählen Sie **[!UICONTROL Speichern]** aus.

Schließlich möchten Sie jetzt jedes Ihrer spezifischen Datenelemente dem zuvor definierten Schema zuordnen. Sie definieren ein anderes Datenelement, das eine Darstellung Ihres XDM-Schemas bereitstellt.

So definieren Sie ein XDM-Objektdatenelement:

1. Auswählen **[!UICONTROL Datenelemente]** in der linken Leiste.

2. Auswählen **[!UICONTROL Datenelement hinzufügen]**.

3. Im [!UICONTROL Datenelement erstellen] dialog:

   - Benennen Sie Ihr Datenelement, z. B. `XDM - Page View`.

   - Auswählen **[!UICONTROL Adobe Experience Platform Web SDK]** von [!UICONTROL Erweiterung] Liste.

   - Auswählen **[!UICONTROL XDM-Objekt]** von [!UICONTROL Datenelementtyp] Liste.

   - Wählen Sie Ihre Sandbox aus der [!UICONTROL Sandbox] Liste.

   - Wählen Sie Ihr Schema aus dem [!UICONTROL Schema] Liste.

   - Ordnen Sie die `identification > core > ecid` -Attribut, das in Ihrem Schema definiert ist, dem ECID-Datenelement zuordnen. Wählen Sie das Zylindersymbol aus, um das ECID-Datenelement aus der Liste der Datenelemente einfach auszuwählen.

      ![ECID-Datenelement auswählen](./assets/pick-ecid-dataelement.png)

      ![ECID-Datenelement zuordnen](./assets/map-ecid.png)


   - Ordnen Sie die `web > webPageDetails > name` -Attribut, das in Ihrem Schema definiert ist, dem Datenelement &quot;Seitenname&quot;.

      ![Datenelement &quot;Seitenname zuordnen&quot;](./assets/map-pagename.png)

   - Wählen Sie **[!UICONTROL Speichern]** aus.


#### **Regeln**

Tags in Adobe Experience Platform folgen einem regelbasierten System. Sie suchen nach Benutzerinteraktionen und zugehörigen Daten. Wenn die in Ihren Regeln formulierten Kriterien erfüllt sind, löst die Regel die jeweils definierte Erweiterung, das Skript oder den Client-seitigen Code aus. Sie können mithilfe von Regeln Daten (wie ein XDM-Objekt) mithilfe der Adobe Experience Platform Web SDK-Erweiterung an Adobe Experience Platform senden.

So definieren Sie eine Regel:

1. Auswählen **[!UICONTROL Regeln]** in der linken Leiste.

2. Auswählen **[!UICONTROL Neue Regel erstellen]**.

3. Im [!UICONTROL Regel erstellen] dialog:

   - Benennen Sie die Regel beispielsweise . `Page View`.

   - Auswählen **[!UICONTROL + Hinzufügen]** darunter [!UICONTROL Veranstaltungen].

   - Im [!UICONTROL Ereigniskonfiguration] dialog:

      - Auswählen **[!UICONTROL Core]** von [!UICONTROL Erweiterung] Liste.

      - Auswählen **[!UICONTROL Fenster geladen]** von [!UICONTROL Ereignistyp] Liste.

         ![Regel - Ereigniskonfiguration](./assets/event-windowloaded-pageview.png)

      - Wählen Sie **[!UICONTROL Änderungen beibehalten]** aus.
   - Auswählen **[!UICONTROL + Hinzufügen]** darunter [!UICONTROL Aktionen].

   - Im [!UICONTROL Aktionskonfiguration] dialog:

      - Auswählen **[!UICONTROL Adobe Experience Platform Web SDK]** von [!UICONTROL Erweiterung] Liste.

      - Auswählen **[!UICONTROL Ereignis senden]** von [!UICONTROL Aktionstyp] Liste.

      - Auswählen **[!UICONTROL web.webpageDetails.pageViews]** von [!UICONTROL Typ] Liste.

      - Wählen Sie das Zylindersymbol neben  [!UICONTROL XDM-Daten] und auswählen **[!UICONTROL XDM - Seitenansicht]** aus der Liste der Datenelemente.

         ![Regel - Aktionskonfiguration](./assets/action-pageview-xdm.png)

      - Wählen Sie **[!UICONTROL Änderungen beibehalten]** aus.
   - Ihre Regel sollte wie folgt aussehen:

      ![Regel erstellen](assets/rule-pageview.png)

   - Wählen Sie **[!UICONTROL Speichern]** aus.





Dies ist nur ein Beispiel für die Definition einer Regel, die XDM-Daten sendet, die Werte aus anderen Datenelementen enthalten, an Adobe Experience Platform.

Sie können Regeln in Ihrem Tag auf verschiedene Weise verwenden, um Variablen zu bearbeiten (mithilfe Ihrer Datenelemente).

Siehe [ Rules](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=de) für weitere Informationen.

### Erstellen und Veröffentlichen Ihres Tags

Nachdem Sie Datenelemente und Regeln definiert haben, müssen Sie Ihr Tag erstellen und veröffentlichen. Wenn Sie einen Bibliotheks-Build erstellen, müssen Sie ihn einer Umgebung zuweisen. Die Erweiterungen, Regeln und Datenelemente des Builds werden dann kompiliert und in die zugewiesene Umgebung eingefügt. Jede Umgebung bietet einen eindeutigen Einbettungs-Code, mit dem Sie den zugewiesenen Build in Ihre Website integrieren können.

So erstellen und veröffentlichen Sie Ihr Tag:

1. Auswählen **[!UICONTROL Veröffentlichungsfluss]** über die linke Leiste.

2. Auswählen **[!UICONTROL Arbeitsbibliothek auswählen]**, gefolgt von **[!UICONTROL Bibliothek hinzufügen...]**.

3. Im [!UICONTROL Bibliothek erstellen] dialog:

   - Benennen Sie die Bibliothek.

   - Auswählen **[!UICONTROL Entwicklung (Entwicklung)]** von [!UICONTROL Umgebung] Liste.

   - Auswählen **[!UICONTROL + Alle geänderten Ressourcen hinzufügen]**.

      ![Veröffentlichen - Bibliothek erstellen](./assets/create-library-aep.png)

   - Auswählen **[!UICONTROL Speichern und in Entwicklung erstellen]**.

   Dadurch wird das -Tag für Ihre Entwicklungsumgebung gespeichert und erstellt. Ein grüner Punkt zeigt eine erfolgreiche Erstellung Ihres Tags in Ihrer Entwicklungsumgebung an.

4. Sie können **[!UICONTROL ...]** , um die Bibliothek neu zu erstellen oder in eine Staging- oder Produktionsumgebung zu verschieben.

   ![Veröffentlichen - Bibliothek erstellen](./assets/build-library.png)

Adobe Experience Platform-Tags unterstützen einfache, komplexe Veröffentlichungs-Workflows, die für Ihre Bereitstellung des Adobe Experience Platform Web SDK geeignet sind.

Siehe [Veröffentlichungsübersicht](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) für weitere Informationen.


### Tag-Code abrufen

Schließlich müssen Sie Ihr Tag auf der Website installieren, die Sie verfolgen möchten. Dies setzt die Platzierung von Code im Header-Tag der Vorlage Ihrer Website voraus.

So rufen Sie den Code ab, der auf Ihr Tag verweist:

1. Auswählen **[!UICONTROL Umgebungen]** in der linken Leiste.

2. Wählen Sie in der Liste der Umgebungen die Schaltfläche Installieren (Kästchen) aus.

   Im [!UICONTROL Web-Installationsanweisungen] Wählen Sie die Schaltfläche &quot;Kopieren&quot;neben dem Skriptcode aus, der wie folgt gelesen werden soll:

   ```javascript
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>
   ```

   ![Umgebung](./assets/environment.png)

3. Auswählen **[!UICONTROL Schließen]**.

Anstelle des Codes für die Entwicklungsumgebung hätten Sie eine andere Umgebung (Staging, Produktion) auswählen können, je nachdem, wo Sie das Adobe Experience Platform Web SDK bereitstellen.

Siehe [Umgebungen](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=de?) für weitere Informationen.

## Bereitstellen und Überprüfen

Sie können den Code jetzt auf der Entwicklungsversion Ihrer Website im `<head>` -Tag. Nach der Bereitstellung beginnt Ihre Website mit der Datenerfassung in Adobe Experience Platform.

Validieren Sie Ihre Implementierung, korrigieren Sie sie bei Bedarf und stellen Sie sie nach der korrekten Implementierung mithilfe der Publishing-Workflow-Funktion von Tags in Ihrer Staging- und Produktionsumgebung bereit.

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

   - Wählen Sie den zuvor erstellten Datensatz aus (`Example dataset`) und einen anderen Datensatz, den Sie in Ihre Verbindung aufnehmen möchten.

      ![Hinzufügen von Datensätzen](./assets/cja-connections-2b.png)

   - Klicken Sie auf **[!UICONTROL Weiter]**.
   Im [!UICONTROL Datensatzeinstellungen] Schritt in [!UICONTROL Hinzufügen von Datensätzen]:

   - Für jeden Datensatz:

      - Wählen Sie eine [!UICONTROL Personen-ID] aus den verfügbaren Identitäten, die in den Datensatzschemas in Adobe Experience Platform definiert sind.

      - Wählen Sie die richtige Datenquelle aus der [!UICONTROL Datenquellentyp] Liste. Wenn Sie **[!UICONTROL Sonstiges]** und fügen Sie dann eine Beschreibung für Ihre Datenquelle hinzu.

      - Satz **[!UICONTROL Alle neuen Daten importieren]** und **[!UICONTROL Aufstockung vorhandener Daten durch Datensätze]** entsprechend Ihren Vorlieben.

      ![Konfigurieren von Datensätzen](./assets/cja-connections-3b.png)

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
>Sie haben alle Schritte ausgeführt. Sie haben zunächst definiert, welche Daten (Schema) erfasst werden sollen und wo sie (Datensatz) in Adobe Experience Platform gespeichert werden sollen. Sie haben daraufhin einen Datastream im Edge-Netzwerk konfiguriert, um sicherzustellen, dass Daten an diesen Datensatz weitergeleitet werden können. Anschließend haben Sie Ihr Tag definiert und bereitgestellt, das die Erweiterungen (Adobe Experience Platform Web SDK, Experience Cloud-ID-Dienst), Datenelemente und Regeln enthält, um Daten von Ihrer Website zu erfassen und diese Daten an Ihren Datenspeicher zu senden. Sie haben eine Verbindung in Customer Journey Analytics definiert, um Ihre Website-Tracking-Daten und andere Daten zu verwenden. Mit Ihrer Datenansichtsdefinition können Sie festlegen, welche Dimension und Metriken verwendet werden sollen, und schließlich Ihre erste Projektvisualisierung und -analyse erstellen.
