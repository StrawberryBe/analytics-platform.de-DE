---
title: Marketo Engage-Daten in Adobe Experience Platform erfassen und in Customer Journey Analytics berichten
description: Erfahren Sie, wie Sie Marketo Engage-Daten in Customer Journey Analytics importieren
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 63%

---

# Marketo Engage-Daten in Adobe Experience Platform erfassen und in Customer Journey Analytics berichten

Sie können die neu verfügbaren Marketo Engage-Datensätze in Adobe Experience Platform (Adobe Experience Platform) nutzen, um B2B-Marketingexperten wertvolle Analyse- und Berichterstellungslösungen bereitzustellen. Erstellen Sie dann einen Bericht zu diesen Datensätzen in Adobe Customer Journey Analytics.

## Schritt 1: Ordnen Sie Marketo-Quelldatenfeldern ihren XDM-Zielen zu

Ordnen Sie die Objekte [Personen](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=de#persons) und [Aktivitäten](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=de#activities) den jeweiligen XDM-Schema-Zielfeldern zu.

## Schritt 2: Erfassen von Marketo-Daten in Adobe Experience Platform

Verwenden Sie den [Marketo Engage-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=de), um Daten aus Marketo in Experience Platform zu übertragen und mithilfe von Anwendungen, die mit Platform verbunden sind, auf dem neuesten Stand zu halten.

## Schritt 3: Herstellen einer Verbindung zu diesem Datensatz in Customer Journey Analytics

Um über Experience Platform-Datensätze zu berichten, müssen Sie zunächst eine Verbindung zwischen Datensätzen in Experience Platform und Customer Journey Analytics herstellen. Weitere Informationen finden Sie unter [Verbindung erstellen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de).

## Schritt 4: Erstellen Sie eine oder mehrere Datenansichten.

Eine [Datenansicht](/help/data-views/data-views.md) ist ein für Customer Journey Analytics spezifischer Container, mit dem Sie bestimmen können, wie Daten aus einer Verbindung interpretiert werden. Sie enthält alle in Analysis Workspace verfügbaren Dimensionen und Metriken, in diesem Fall für Marketo spezifische Metriken und Dimensionen. Die Datenansicht gibt auch an, aus welchen Spalten diese Dimensionen und Metriken ihre Daten beziehen. Datenansichten werden in Vorbereitung auf das Reporting in Analysis Workspace definiert.

## Schritt 5: Erstellen Sie einen Bericht in Analysis Workspace.

Ein möglicher Anwendungsfall ist: Wie viele Web-Seitenbesuche durch Leads hatten wir im April/Juni 2020?

1. Öffnen Sie [Analysis Workspace](/help/analysis-workspace/home.md) und erstellen Sie ein neues Projekt.
Kunden mit B2B/B2P CDP können eine B2C-Analyse im Customer Journey Analytics durchführen. B2B-Objekte sind noch nicht verfügbar.

1. Erstellen Sie einen [Filter](/help/components/filters/create-filters.md) für Web-Seitenansichten wie folgt: Ereignistyp = web.webpagedetails.pageViews :

   ![Definitionsfenster mit Ereignis- und Ereignistyp](../assets/marketo-filter.png)

1. Ziehen Sie den von Ihnen erstellten Filter (Web-Seitenansichten) und danach den Datumsbereich „Monat“ in die Freiformtabelle. So erhalten Sie die monatlichen Web-Seitenbesuche nach Leads:

   ![Freiformtabelle mit Ereignissen nach Monat](../assets/marketo-freeform.png)

1. Oder ziehen Sie die folgenden Dimensionen in die Tabelle: Personen-Schlüssel oder geschäftliche E-Mail-Adresse. Dadurch erhalten Sie die Web-Seitenbesuche nach Lead:

   ![Freiformtabelle mit Ereignissen und workEmail.Address und Webseitenansichten.](../assets/marketo-freeform2.png)
