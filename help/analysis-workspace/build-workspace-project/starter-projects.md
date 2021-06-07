---
description: Verwenden Sie Vorlagen in Workspace und erstellen Sie benutzerdefinierte Vorlagen.
title: Vorlagen
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
exl-id: 464032a1-6dae-4df5-b4db-b277788e88c2
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 92%

---

# Vorlagen

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Weitere Informationen...](/help/getting-started/cja-aa.md)

Für die Erstellung eines Projekts gibt es folgende Ausgangspunkte:

* **Leeres Projekt (Standard)**: Anweisungen hierzu finden Sie unter [Erstellen eines Projekts in Analysis Workspace](/help/analysis-workspace/home.md).
* **Standardvorlage**: Diese Vorlagen werden von Adobe erstellt und mit dem Produkt geliefert.
* **Benutzerdefinierte Vorlage**: Diese Vorlagen können von Benutzern mit Administratorrechten oder von Nichtadministratoren erstellt, freigegeben oder gelöscht werden, sofern ihnen die Berechtigung [!UICONTROL Analysis Workspace: als Vorlage speichern] in der Admin Console erteilt wurde. [Weitere Informationen ...](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Erstellen einer benutzerdefinierten Vorlage {#create-custom-template}

Benutzer mit Administratorrechten können aus jedem erstellten Projekt eine benutzerdefinierte Vorlage machen. So geht’s:

1. Öffnen Sie das Projekt.
1. Wählen Sie **[!UICONTROL Projekt]** > **[!UICONTROL Als Vorlage speichern]**.

   ![](assets/save_project_template.png)

   Das Projekt wird unter dem aktuellen Projektnamen gefolgt von dem Wort (Vorlage) in Klammern gespeichert. Administratoren können diese Benennung durch Bearbeiten der Vorlage ändern.

   >[!NOTE]
   >
   >Projektvorlagen sind standardmäßig für jeden in Ihrer Organisation sichtbar. Sie können sie ordnen, indem Sie Tags auf sie anwenden. (Wählen Sie **[!UICONTROL Projekt]** > **[!UICONTROL Projektinfo und Einstellungen]** aus, um Tags und Beschreibungen zu bearbeiten.)

### Auf benutzerdefinierte Vorlagen anwendbare Aktionen

![](assets/custom_templates.png)

| Aktion | Beschreibung |
|--- |--- |
| Vorlage bearbeiten | Lässt einen Administrator die Vorlage durch Änderung der Datenquelle, Anpassung von Komponenten, Visualisierungen, Datumsbereichen usw. bearbeiten.  Um eine Standardvorlage zu bearbeiten, können Sie entweder<ul><li>die Liste von benutzerdefinierten Vorlagen in Analysis Workspace öffnen, eine auswählen und auf „Vorlage bearbeiten“ klicken oder</li><li>in Analytics „Komponenten“ > „Projekte“ auswählen und dann nach Vorlagen filtern. Klicken Sie auf den Namen der Vorlage, die Sie bearbeiten möchten.</li></ul>**Hinweis:** Nachdem Sie eine Vorlage bearbeitet haben, haben Sie je nach Situation zwei Optionen: „Speichern“ oder „Speichern unter“. Sie unterscheiden sich in Folgendem:<ul><li>**Speichern:** Die benutzerdefinierte Vorlage wird für alle Benutzer aktualisiert. Wenn jemand anderer ein Projekt aus dieser benutzerdefinierten Vorlage erstellt, sieht er die von Ihnen gemachten Änderungen.</li><li>**Speichern unter:** Erstellt eine Kopie der benutzerdefinierten Vorlage mit Ihren Änderungen. (Dass Sie im Bearbeitungsmodus sind, lässt sich daran erkennen, dass das Menüelement „Freigabe“ > „Projekt freigeben“ deaktiviert ist.)</li></ul> |
| Nach Vorlagen suchen | Klicken Sie im Dialogfeld „Benutzerdefinierte Vorlagen“ auf „Vorlagen suchen“. |
| Vorlagen ordnen | Sie können Vorlagen alphabetisch, nach Relevanz und nach Erstellungsdatum ordnen.  Klicken Sie im Dialogfeld „Benutzerdefinierte Vorlagen“ auf „Ordnen“. |
| Tags auf eine Vorlage anwenden | Öffnen Sie die Vorlage und wählen Sie „Projekt“ > „Projektinfo und Einstellungen“. Klicken Sie auf „Tags hinzufügen“. |
| Vorlagenbeschreibung ändern | Öffnen Sie die Vorlage und wählen Sie „Projekt“ > „Projektinfo und Einstellungen“. Doppelklicken Sie auf die Beschreibung und bearbeiten Sie sie. |


## Standardvorlagen

Wenn Sie einen Workspace zum ersten Mal öffnen, sind Vorlagen in der linken Leiste verfügbar. Analysis Workspace-Vorlagen decken häufige Anwendungsfälle ab. Sie werden nach der Vertikale gruppiert, zu der sie gehören, und je nach ausgewählter Datenansicht mit unterschiedlichen Dimensionen, Filtern, Metriken und Visualisierungen aufgefüllt.

Sie können diese fertig ausgefüllten Vorlagen unverändert übernehmen oder an Ihre spezifischen Anforderungen anpassen (indem Sie beispielsweise Metriken oder Visualisierungen hinzufügen oder austauschen) und dann unter einem neuen Namen speichern.

>[!VIDEO](https://video.tv.adobe.com/v/23960)

*(2:46)*

Im Folgenden finden Sie verfügbare Vorlagen und die Fragen, die die einzelnen Vorlagen beantworten.

### Schulung

Diese Standardvorlagen führen Sie durch die gängige Terminologie und die Schritte zum Erstellen Ihrer ersten Analyse in Workspace. Sie sind als Standardvorlage im Modal „Neues Projekt“ enthalten und ersetzen das Beispielprojekt, das bislang neuen Anwendern angeboten wurde, die keine anderen Projekte in ihrer Liste haben.

* **Schulungsanleitung – Internal Search Analysis**: Das Tutorial zur internen Suche hilft Ihnen zu verstehen, wonach Ihre Besucher auf der Website oder in der Mobile App suchen, jedoch nicht finden. Durch die Analyse dieser Art von Daten können sich Optimierungsmöglichkeiten für Inhalte offenbaren.

* **Schulungsanleitung – Marketing Analysis**: In diesem Tutorial erfahren Sie, wie Sie eine Marketing-Analyse für Ihre Führungskräfte erstellen, einschließlich der wichtigen Dimensionen und Metriken.

### Medien

* **Audio-Konsum**: Welche Inhalte werden von Benutzern am häufigsten aufgerufen?
* **Neuigkeit - Häufigkeit - Treue**: Wer sind meine treuen Leser?


### Einzelhandel

* **Kampagnenleistung:** Welche Kampagnen erzielen den höchsten Umsatz?
* **Produkte:** Welche Produkte schneiden am besten ab?

### Web

* **Akquise:** Was sind die wichtigsten Faktoren, durch die Traffic auf meine Website geleitet wird?
* **Content-Konsum:** Wohin navigieren Besucher auf meiner Website am häufigsten?
* **Bindungsgrad:** Welche Arten von Benutzern bleiben meiner Website wahrscheinlich treu?
* **Technologie:** Welche Technologien werden verwendet, um auf meine Website zu gelangen?

