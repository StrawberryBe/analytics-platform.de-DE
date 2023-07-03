---
title: Übersicht über die Veröffentlichung von Customer Journey Analytics-Zielgruppen
description: Erfahren Sie mehr über das Konzept der Zielgruppenveröffentlichung in Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 54%

---

# Übersicht über die Veröffentlichung von Customer Journey Analytics-Zielgruppen

Sie können jetzt Zielgruppen erstellen und veröffentlichen, die in Customer Journey Analytics in [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) (RTCDP) in Adobe Experience Platform für das Targeting und die Personalisierung von Kunden.

Das Veröffentlichen von Zielgruppen bietet eine klare Möglichkeit, innerhalb von Customer Journey Analytics vorhandene Einblicke zu aktivieren und Maßnahmen zu ergreifen. Zu diesen Maßnahmen zählen:

* Verwenden der Zielgruppe für eine Journey in Adobe Journey Optimizer.
* Exportieren der Zielgruppe zu einem Drittanbieter über ein Experience Platform-Ziel.
* Anreicherung des Echtzeit-Kundenprofils mit nützlichen Attributen, die aus ereignisbasierten Daten in Customer Journey Analytics abgeleitet wurden.
* Dies alles geschieht mit minimaler Latenz nach der Publikation der Zielgruppe. [Weitere Informationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=de#latency)
* Veröffentlichen einmaliger oder wiederkehrender Zielgruppen.

Die Zielgruppen, die Sie in Customer Journey Analytics erstellen, müssen nicht auf für das Profil aktivierten Datensätzen basieren. Sie können historische Daten in Experience Platform erfassen, ohne verknüpfte Datensätze und Schemas für Profile zu aktivieren. Verwenden Sie dann diese Datensätze, um relevante Zielgruppen in Customer Journey Analytics zu ermitteln und diese Zielgruppen in der RTCDP-Experience Platform zu Aktivierungszwecken zu veröffentlichen.

## Wichtige Terminologie

**Zielgruppe**: Ein Satz oder eine Liste von Identitäten, die sowohl einen Namespace als auch eine spezifische ID für diesen Namespace haben. Zielgruppen können aus der Adobe Experience Platform übertragen werden und Anwendungen, die darauf platziert sind (z. B. Customer Journey Analytics). Zielgruppen können gemischte Namespaces enthalten.

**Filter**: Ein Regelsatz, mit dem bei der Auswertung eines Datensatzes über einen bestimmten Zeitraum eine Teilmenge von Daten erzeugt wird. Bei der Erstellung einer Zielgruppe kann ein Filter verwendet werden, wenn auch andere unterstützende Services genutzt werden. Filter werden in Customer Journey Analytics definiert und verwaltet.

**Filter** versus **Segmente**: Customer Journey Analytics verwendet nicht das Konzept &quot;Segmente&quot;- stattdessen verwendet es &quot;Filter&quot;. Bei beiden handelt es sich zwar um einen Regelsatz, der eine ähnliche Logik enthalten kann, das erzeugte Ergebnis ist jedoch ein anderes. Ein Filter wird verwendet, um einen Datensatz für Analysezwecke einzugrenzen. Ein Segment wird verwendet, um eine Liste von Identitäten zu erstellen, die zur Aktivierung verwendet werden können. Segmente erzeugen Zielgruppen im Echtzeit-Kundenprofil, Filter (allein) dagegen nicht. Customer Journey Analytics Audience Publishing ist der Prozess, mit dem wir einen Customer Journey Analytics-Filter verwenden, um eine Zielgruppe zu erstellen, die vom Echtzeit-Kundenprofil genutzt werden kann.

## Zugriffsberechtigung

* Administratoren erhalten automatisch die Berechtigung **[!UICONTROL Zielgruppenveröffentlichung]** in Adobe Admin Console.

* Administratoren können diese Berechtigung für einzelne Benutzer erteilen.

* Admins benötigen außerdem die Berechtigung **[!UICONTROL Profile verwalten]** in Adobe Experience Platform.

## Data Governance und Einverständnis

Wenn Sie eine Zielgruppe in Customer Journey Analytics veröffentlichen, werden die mit den in der Zielgruppe verwendeten Feldern verknüpften Data Governance-Beschriftungen und -Richtlinien aufgezeichnet.  Wenn die Zielgruppe in einem Adobe Experience-Programm aktiviert wird, sind alle zugehörigen Data Governance-Beschriftungen und -Richtlinien für diese Zielgruppe verfügbar und es kann eine geeignete Durchsetzung angewendet werden. [Weitere Informationen über Einverständnis](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=de#consent-policy).

## Nächste Schritte

* [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md)
* [Verwalten von Audiences](/help/components/audiences/manage.md)
