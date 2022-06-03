---
title: In Customer Journey Analytics erstellte Zielgruppen verwalten
description: Erfahren Sie, wie Sie Zielgruppen in Customer Journey Analytics verwalten
source-git-commit: 9d19e1ea55a6c2de701d38cb417d6d39e753c640
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 8%

---


# In Customer Journey Analytics erstellte Zielgruppen verwalten

>[!NOTE]
>
>Diese Funktion ist derzeit in [begrenzte Tests](/help/release-notes/releases.md).

Die Verwaltung zuvor erstellter Audiences ermöglicht Ihnen Folgendes:

* **Planung oder Aufhebung des Zeitplans** automatische Aktualisierung/Aktualisierung der Zielgruppe. Die maximale Gültigkeit des Zeitplans beträgt 1 Jahr.
* **Audience-Aktualisierungszeitplan erneuern** wenn sie bald abläuft. Das Auslaufen von Zielgruppen wird ähnlich wie das Auslaufen geplanter Berichte behandelt - der Administrator erhält einen Monat vor Ablauf des Zeitplans eine E-Mail.
* Anzeigen der **letzte Aktualisierung einer Zielgruppe**
* Gewinnen Sie Einblicke in **Dauer der Erstellung einer Audience** von Customer Journey Analytics (CJA) aus und die Zeit, die benötigt wurde, um die Zielgruppe zur Aktivierung im Echtzeit-Kundenprofil erscheinen zu lassen.
* Überprüfen Sie, ob die Zielgruppen in CJA **aktiv vom Echtzeit-Kundenprofil verwendet werden** oder (im Idealfall) alle Experience Platform Apps, die die von CJA erstellten Zielgruppen nutzen.

## Management-Benutzeroberfläche

Screenshot

| UI-Einstellung | Definition |
| --- | --- |
| Ausblenden/Anzeigen von Filtern | Hiermit können Sie die folgenden Filter in der linken Leiste ein- oder ausblenden: <ul><li>Datenansicht</li><li>Verantwortlicher</li><li>Häufigkeit der Aktualisierung</li><li>Tags</li></ul> |
| Titel und Beschreibung |  |
| Datenansicht |
| Zielgruppengröße |  |
| Verantwortlicher |  |
| Aktualisierungshäufigkeit |  |
| Tags |  |
| Zuletzt aktualisiert |  |
| Zuletzt geändert |  |

{style=&quot;table-layout:auto&quot;}

## Anzeigen und Verwenden von CJA-Zielgruppen in Experience Platform

Sie können CJA-Zielgruppen in Platform anzeigen, indem Sie [!UICONTROL Segmente] > [!UICONTROL Segmente erstellen] > [!UICONTROL Zielgruppen] tab > [!UICONTROL CJA-Zielgruppen].

Sie können CJA-Zielgruppen in die Segmentdefinition für AEP-Segmente ziehen.

![](assets/audiences-aep.png)

Wenn Sie sich dafür entscheiden, diese Zielgruppe in den AEP Data Lake zu exportieren, wird sie als Datensatz angezeigt, der der XDM Individual Profile Schema Class entspricht:

![](assets/aep-datalake.png)

