---
description: Erfahren Sie, wie AEP Attribution AI in Workspace in CJA integriert wird.
title: Attribution AI mit CJA integrieren
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: b82bf04bb09a38f1cd475ecd2036acc240b7ef38
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 3%

---

# Attribution AI mit CJA integrieren

>[!NOTE]
>
>Diese Funktion wird am 25. Mai 2022 veröffentlicht.

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en)ist als Teil von Adobe Experience Platform Intelligent Services ein algorithmischer Attributionsdienst mit mehreren Kanälen, der den Einfluss und die inkrementelle Auswirkung von Kundeninteraktionen auf bestimmte Ergebnisse berechnet. Mit Attribution AI können Marketing-Experten die Ausgaben für Marketing und Werbung messen und optimieren, indem sie die Auswirkungen jeder einzelnen Kundeninteraktion in jeder Phase der Journey verstehen.

Attribution AI unterstützt zwei Bewertungskategorien: algorithmisch und regelbasiert. Algorithmische Werte umfassen inkrementelle und beeinflusste Werte.

* **Beeinflusste Punktzahl** 100 % des Konversionsguthabens auf Marketingkanäle aufteilen.
* **Inkrementelle Werte** berücksichtigen Sie zunächst eine Konversionsgrundlinie, die Sie auch ohne Marketing erreicht hätten. Diese Grundlinie hängt von KI-Beobachtungen von Mustern, Saisonabhängigkeit usw. ab, die aufgrund der bestehenden Markenerkennung, -loyalität und der Mundpropaganda erfolgen. Der verbleibende Anteil wird auf die Marketing-Kanäle aufgeteilt.

Regelbasierte Werte umfassen [!UICONTROL Erstkontakt], [!UICONTROL Letztkontakt], [!UICONTROL Linear], [!UICONTROL U-förmig]und [!UICONTROL Zeitverfall]. Attribution AI unterstützt 3 Experience Platformen-Schemata: Erlebnisereignis, Adobe Analytics und Kundenerlebnisereignis.

Attribution AI kann in Customer Journey Analytics (CJA) integriert werden, soweit Attribution AI Modelle für Daten ausführt. Anschließend importiert CJA die Ausgabe dieser Modelle als Datensatz, der dann in den Rest Ihrer CJA-Datensätze integriert werden kann. Attribution AI-fähige Datensätze können dann in Datenansichten und Berichten in CJA genutzt werden.

## Workflow

Einige der Schritte werden in Adobe Experience Platform ausgeführt, bevor Sie mit der Ausgabe in CJA arbeiten. Die Ausgabe besteht aus einem Datensatz mit einem angewendeten Attribution AI-Modell.

### Schritt 1: Erstellen einer Attribution AI-Instanz

Erstellen Sie in Experience Platform eine Attribution AI-Instanz, indem Sie Daten auswählen und zuordnen, Ereignisse definieren und Ihre Daten trainieren, wie beschrieben [here](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### Schritt 2: Einrichten einer CJA-Verbindung zu Attribution AI-Datensätzen

In Customer Journey Analytics können Sie jetzt [eine oder mehrere Verbindungen erstellen](/help/connections/create-connection.md) zu Experience Platform-Datensätzen, die für Attribution AI instrumentiert wurden. Diese Datensätze werden mit dem Präfix &quot;Attribution AI Scores&quot;angezeigt, wie im folgenden Beispiel:

![AAI-Bewertungen](assets/aai-scores.png)

### Schritt 3: Erstellen von Datenansichten basierend auf diesen Verbindungen

In Customer Journey Analytics: [eine oder mehrere Datenansichten erstellen](/help/data-views/create-dataview.md) die die Attribution AI-XDM-Felder enthalten. (Es wäre toll, einen Screenshot hier zu haben.)

### Schritt 4: Bericht zu AAI-Daten in CJA Workspace

In einem CJA Workspace-Projekt können Sie Metriken wie &quot;AAI-Bestellungen&quot;und Dimensionen wie &quot;AAI-Kampagnenname&quot;oder &quot;AAI-Marketingkanal&quot;abrufen.

![AAI-Dimensionen](assets/aai-dims.png)

Hier sehen wir ein Workspace-Projekt mit AAI-Daten, das Bestellungen mit beeinflussten und inkrementellen Werten anzeigt.

![AAI-Projekt](assets/aai-project.png)

![AAI-Projekt](assets/aai-project2.png)


## Unterschiede zwischen Attribution AI und Attribution IQ

Wann sollten Sie also die Attribution AI-Daten im Vergleich zu [Attribution IQ](/help/analysis-workspace/attribution/overview.md), eine native CJA-Funktion? Die folgende Tabelle zeigt einige Funktionsunterschiede:

| Funktionalität | Attributions-KI | Attribution IQ |
| --- | --- | --- |
| Teilzuordnung | Ja | Nein |
| Ermöglicht Benutzern, das Modell anzupassen | Ja | Ja |
| Funktioniert die Attribution über Kanäle (Hinweis: AAI verwendet nicht dieselben zugeordneten Daten wie CJA.) | Ja | Ja |
| Umfasst inkrementelle und beeinflusste Ergebnisse | Ja | Nein |
| HTML-Modellierung | Ja | Ja |
| ML-Modellierung mit Prognosen | Ja | Nein |

{style=&quot;table-layout:auto&quot;}
