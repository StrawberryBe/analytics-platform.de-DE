---
title: Veröffentlichung von CJA-Zielgruppen - Überblick
description: Erfahren Sie mehr über das Konzept der Zielgruppenveröffentlichung in Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: cfc4824c214ba8b60877bebe10a697f706f9c2fb
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 8%

---

# Überblick über die Veröffentlichung von CJA-Zielgruppen

>[!NOTE]
>
>Diese Funktion ist derzeit in [begrenzte Tests](/help/release-notes/releases.md).

Sie können jetzt Zielgruppen erstellen und veröffentlichen, die in Customer Journey Analytics (CJA) in [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) (RTCP) in Adobe Experience Platform für Kundenansprache und -personalisierung. Mit dem Echtzeit-Kundenprofil können Sie eine ganzheitliche Ansicht jedes einzelnen Kunden anzeigen, indem Sie Daten aus mehreren Kanälen, einschließlich Online, Offline, CRM und Drittanbieter, kombinieren. Mit dem Profil können Sie Ihre Kundendaten in einer zentralen Ansicht zusammenführen, die eine aussagekräftige Darstellung jeder Kundeninteraktion mit Zeitstempel bietet.

Das Veröffentlichen von Zielgruppen bietet eine klare Möglichkeit, um auf Einblicken in CJA zu reagieren. Diese Aktionen können Folgendes umfassen:

* E-Mails an diese Audience senden
* Push-Nachrichten an diese Zielgruppe senden
* Verwenden der Zielgruppe für eine Journey in Adobe Journey Optimizer.
* Exportieren der Zielgruppe in ein Drittanbieter über ein Experience Platform-Ziel.
* Anreicherung des Echtzeit-Kundenprofils mit nützlichen Attributen, die aus ereignisbasierten Daten in CJA abgeleitet wurden, ohne alle Ereignisdaten zu RTCP hinzufügen zu müssen.

## Wichtige Terminologie

**Zielgruppe**: Ein Satz oder eine Liste von Identitäten, die sowohl einen Namespace als auch eine spezifische ID für diesen Namespace aufweisen. Zielgruppen können aus der Adobe Experience Platform übertragen werden und Anwendungen, die darauf platziert sind (z. B. CJA). Zielgruppen können gemischte Namespaces enthalten.

**Filter**: Ein Regelsatz, der bei der Auswertung über einen Datensatz für einen Zeitraum eine Teilmenge von Daten erzeugt. Ein Filter kann bei der Erstellung einer Audience verwendet werden, wenn er mit anderen unterstützenden Diensten kombiniert wird. Filter werden in CJA definiert und verwaltet.

**Filter** versus **Segmente**: CJA verwendet nicht das Konzept &quot;Segmente&quot;- stattdessen verwendet es &quot;Filter&quot;. Beide sind zwar ein Regelsatz, der eine ähnliche Logik enthalten kann, sie erzeugen jedoch unterschiedliche Ausgaben. Ein Filter wird verwendet, um einen Datensatz für Analysezwecke einzugrenzen. Ein Segment wird verwendet, um eine Liste von Identitäten zu erstellen, die für die Aktivierung verwendet werden können. Segmente erzeugen Zielgruppen im Echtzeit-Kundenprofil, Filter (allein) dagegen nicht. Bei der Veröffentlichung von CJA-Zielgruppen verwenden wir einen CJA-Filter, um eine Zielgruppe zu erstellen, die vom Echtzeit-Kundenprofil genutzt werden kann.

## Zugriffsberechtigungen

Administratoren erhalten automatisch die [!UICONTROL Zielgruppenveröffentlichung] -Berechtigung in Adobe Admin Console. Sie können diese Berechtigung einzelnen Benutzern erteilen.

## Nächste Schritte

* [Erstellen und Veröffentlichen von Zielgruppen](/help/components/audiences/publish.md)
* [Zielgruppen verwalten](/help/components/audiences/manage.md)
