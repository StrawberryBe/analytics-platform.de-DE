---
title: Veröffentlichung von CJA-Zielgruppen – Überblick
description: Erfahren Sie mehr über das Konzept der Zielgruppenveröffentlichung in Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: c851a07a456fa033b37e45a3d182a8fc80988b82
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Überblick über die Veröffentlichung von CJA-Zielgruppen

Sie können jetzt in Customer Journey Analytics (CJA) verfügbare Zielgruppen erstellen und im [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) (RTCP) in Adobe Experience Platform veröffentlichen, um sie zum Targeting und zur Personalisierung zu verwenden.

Das Veröffentlichen von Zielgruppen bietet die Möglichkeit, die in CJA vorhandenen Einblicke zu aktivieren und entsprechende Maßnahmen zu ergreifen. Zu diesen Maßnahmen zählen:

* Verwenden der Zielgruppe für eine Journey in Adobe Journey Optimizer
* Exportieren der Zielgruppe zu einem Drittanbieter über ein Experience Platform-Ziel.
* Anreichern des Echtzeit-Kundenprofils mit nützlichen Attributen, die aus ereignisbasierten Daten in CJA abgeleitet wurden.
* Dies alles geschieht mit minimaler Verzögerung nach der Veröffentlichung der Zielgruppe (einige Minuten)
* Veröffentlichen einmaliger oder wiederkehrender Zielgruppen

## Wichtige Terminologie

**Zielgruppe**: Ein Satz oder eine Liste von Identitäten, die sowohl einen Namespace als auch eine spezifische ID für diesen Namespace haben. Zielgruppen können aus Adobe Experience Platform und Anwendungen, die darauf aufsetzen (z. B. CJA), extrahiert werden. Zielgruppen können gemischte Namespaces enthalten.

**Filter**: Ein Regelsatz, mit dem bei der Auswertung eines Datensatzes über einen bestimmten Zeitraum eine Teilmenge von Daten erzeugt wird. Bei der Erstellung einer Zielgruppe kann ein Filter verwendet werden, wenn auch andere unterstützende Services genutzt werden. Filter werden in CJA definiert und verwaltet.

**Filter** im Vergleich zu **Segmenten**: CJA verwendet „Filter“ anstelle von „Segmenten“. Bei beiden handelt es sich zwar um einen Regelsatz, der eine ähnliche Logik enthalten kann, das erzeugte Ergebnis ist jedoch ein anderes. Ein Filter wird verwendet, um einen Datensatz für Analysezwecke einzugrenzen. Ein Segment wird verwendet, um eine Liste von Identitäten zu erstellen, die zur Aktivierung verwendet werden können. Segmente erzeugen Zielgruppen im Echtzeit-Kundenprofil, Filter (allein) dagegen nicht. Bei der Veröffentlichung von CJA-Zielgruppen wird ein CJA-Filter verwendet, um eine Zielgruppe zu erstellen, die vom Echtzeit-Kundenprofil genutzt werden kann.

## Zugriffsberechtigungen

* Administratoren erhalten automatisch die Berechtigung **[!UICONTROL Zielgruppenveröffentlichung]** in Adobe Admin Console.

* Administratoren können diese Berechtigung einzelnen Benutzern gewähren.

* Administratoren benötigen außerdem die **[!UICONTROL Profile verwalten]** -Berechtigung in Adobe Experience Platform.

## Nächste Schritte

* [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md)
* [Verwalten von Audiences](/help/components/audiences/manage.md)
