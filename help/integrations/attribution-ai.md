---
description: Erfahren Sie, wie AEP Attribution AI in CJA mit Workspace integriert wird.
title: Integrieren von Attribution AI mit CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: 195a89588d83e27eceb58fec8c66c098f1971250
workflow-type: ht
source-wordcount: '889'
ht-degree: 100%

---

# Integrieren von Attribution AI mit CJA

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=de) ist Teil von Adobe Experience Platform Intelligent Services und bietet einen mehrere Kanäle umfassenden algorithmischen Attributions-Service, der den Einfluss und die inkrementelle Auswirkung von Kundeninteraktionen auf bestimmte Ergebnisse berechnet. Mit Attribution AI können Marketing-Experten die Ausgaben für Marketing und Werbung messen und optimieren, indem sie die Auswirkungen einzelner Kundeninteraktionen in einzelnen Phasen der Customer Journey untersuchen.

Attribution AI kann mit Customer Journey Analytics (CJA) integriert werden, sodass mit Attribution AI Modelle anhand von Marketing-Touchpoints und Konversionsdatenquellen von Kunden ausgeführt werden können. CJA importiert dann das Ergebnis dieser Modelle als Datensatz. Das Ergebnis kann auch mit dem Rest Ihrer CJA-Datensätze integriert werden. Attribution AI-Datensätze können dann in Datenansichten und Berichten in CJA genutzt werden.

Attribution AI unterstützt 3 Experience Platform-Schemas: Erlebnisereignis, Adobe Analytics und Kundenerlebnisereignis.

Attribution AI verfügt über zwei Kategorien von Scores: algorithmische und regelbasierte.

## Algorithmische Scores

Algorithmische Scores umfassen inkrementelle und beeinflusste Scores.

* **[!UICONTROL Beeinflusste] Scores** teilen 100 % der Konversion auf die Marketing-Kanäle auf.
* **[!UICONTROL Inkrementelle] Scores** berücksichtigen auch einen Konversions-Basiswert, der auch ohne Marketing erreicht werden hätte können. Dieser Basiswert ergibt sich aus KI-Beobachtungen von Mustern, Saisonalität usw., die durch den Marken-Erkennungswert, die Markenloyalität und Mundpropaganda entstehen. Der verbleibende Anteil wird auf die Marketing-Kanäle aufgeteilt.

## Regelbasierte Scores

Regelbasierte Scores umfassen

* **[!UICONTROL Erstkontakt]**: 100 % werden dem Touchpoint zugeschrieben, der zuerst im Attributions-Lookback-Fenster angezeigt wird.
* **[!UICONTROL Letztkontakt]**: 100 % werden dem Touchpoint zugeschrieben, der zuletzt vor der Konversion aufgetreten ist.
* **[!UICONTROL Linear]**: Gibt jedem Touchpoint vor der Konversion dieselbe Gewichtung.
* **[!UICONTROL U-förmig]**: Der ersten und letzten Interaktion werden je 40 % zugeschrieben. Die verbleibenden 20 % werden auf alle dazwischen liegenden Touchpoints aufgeteilt. Bei Konversionen mit einem einzigen Touchpoint werden diesem 100 % zugeschrieben. Bei Konversionen mit zwei Touchpoints werden jedem 50 % zugeschrieben.
* **[!UICONTROL Time-Decay]**: Folgt einem exponentiellen Abfall mit einem benutzerdefinierten Halbwertszeit-Parameter, wobei der Standardwert 7 Tage ist. Die Gewichtung der einzelnen Kanäle hängt von der Zeit ab, die zwischen dem Beginn des Touchpoints und der letztendlichen Konversion verstrichen ist. Die Formel, die zur Bestimmung der Gewichtung verwendet wird, lautet `2^(-t/halflife)`, wobei `t` die Zeit zwischen einem Touchpoint und einer Konversion ist. Alle Touchpoints werden dann auf 100 % normalisiert.

## Workflow

Einige der Schritte werden in Adobe Experience Platform ausgeführt, bevor die Ausgabe in CJA verwendet wird. Die Ausgabe besteht aus einem Datensatz mit einem angewendeten Attribution AI-Modell.

### Schritt 1: Erstellen einer Attribution AI-Instanz

Erstellen Sie in Experience Platform eine Attribution AI-Instanz, indem Sie wie [hier](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html?lang=de) beschrieben Daten auswählen und zuordnen, Ereignisse definieren und Ihre Daten trainieren.

![AAI-Instanz](assets/aai-instance.png)

### Schritt 2: Einrichten einer CJA-Verbindung zu Attribution AI-Datensätzen

In Customer Journey Analytics können Sie jetzt [eine oder mehrere Verbindungen](/help/connections/create-connection.md) zu Experience Platform-Datensätzen erstellen, die für Attribution AI vorbereitet wurden. Diese Datensätze werden wie im folgenden Beispiel mit dem Präfix „Attribution AI Scores“ dargestellt:

![AAI Scores](assets/aai-scores.png)

![Verbindung herstellen](assets/aai-create-connection.png)

### Schritt 3: Erstellen von Datenansichten basierend auf diesen Verbindungen

Erstellen Sie in Customer Journey Analytics: [eine oder mehrere Datenansichten](/help/data-views/create-dataview.md), die die Attribution AI-XDM-Felder enthalten.

Hier finden Sie die XDM-Schemafelder für Touchpoints:

![Touchpoint-XDM-Felder](assets/touchpoint-fields.png)

Hier finden Sie die XDM-Schemafelder für die Konversion:

![Konversions-XDM-Felder](assets/conversion-fields.png)

### Schritt 4: Erstellen eines Berichts zu AAI-Daten in CJA Workspace

In einem CJA Workspace-Projekt können Sie Metriken wie „AAI-Bestellungen“ und Dimensionen wie „AAI-Kampagnenname“ oder „AAI-Marketing-Kanal“ abrufen.

![AAI-Dimensionen](assets/aai-dims.png)

>[!IMPORTANT]
>
>Diese Dimensionen und Metriken tragen nicht ursprünglich diese Bezeichnungen. Hierbei handelt es sich um „Anzeigenamen“. Die [Namenskonvention in Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/input-output.html?lang=de#attribution-ai-output-data) folgt dem Schemapfad. Es wird empfohlen, die langen AAI-Schemapfadnamen in CJA in kurze, benutzerfreundlichere Namen (Dimensionen/Metriken) umzubenennen. Gehen Sie dazu in **[!UICONTROL Datenansichten]** > **[!UICONTROL Datenansicht bearbeiten]** > die Registerkarte **[!UICONTROL Komponenten]** > **[!UICONTROL Schemafelder]** > Klicken Sie auf ein Schemafeld > **[!UICONTROL Komponentenname]**.

![Dimensionsnamen ändern](assets/change-name.png)

**Bestellungen mit beeinflussten und inkrementellen Scores**

Hier sehen wir ein Workspace-Projekt mit AAI-Daten, in dem Bestellungen mit beeinflussten und inkrementellen Scores zu sehen sind. Schlüsseln Sie eine beliebige Dimension auf, um die Attribution nach Kampagne, Produktgruppe, Benutzersegment, Geografie usw. darzustellen.

![AAI-Projekt](assets/aai-project.png)

![AAI-Projekt](assets/aai-project2.png)

**Marketing-Performance**

Vergleichen Sie die Touchpoint-Attribution zwischen verschiedenen Attributionsmodellen:

![Vergleichen](assets/compare.png)

**Kanalinteraktion**

Verstehen Sie die Kanalinteraktion mithilfe eines Venn-Diagramms, um zu erkennen, welcher Kanal am effektivsten mit anderen Kanälen verwendet werden kann:

![Marketing-Kanalüberschneidung](assets/mc-overlap.png)

**Top-Pfade zur Konversion**

Diese Tabelle zeigt die wichtigsten Konversionspfade (dedupliziert), die Sie bei der Erstellung und Optimierung von Touchpoints unterstützen:

![Top-Kanäle](assets/top-channels.png)

**Vorlaufzeit bis zur Konversion**

Hier finden Sie die Vorlaufzeit für die Konversion, wenn ein Touchpoint im Mix enthalten ist. Dies hilft bei der Optimierung der Vorlaufzeit:

![Vorlaufzeit](assets/lead-time.png)

## Unterschiede zwischen Attribution AI und Attribution IQ

Wann sollten Sie also Attribution AI-Daten anstatt [Attribution IQ](/help/analysis-workspace/attribution/overview.md), eine native CJA-Funktion, verwenden? Die folgende Tabelle zeigt einige Funktionsunterschiede:

| Funktionalität | Attribution AI | Attribution IQ |
| --- | --- | --- |
| Führt inkrementelle Attribution durch | Ja | Nein |
| Ermöglicht Benutzern, das Modell anzupassen | Ja | Ja |
| Wendet Attribution kanalübergreifend an (Hinweis: AAI verwendet nicht dieselben verknüpften Daten wie CJA.) | Ja | Ja |
| Beinhaltet beeinflusste Werte | Ja | Ja |
| Ermöglicht ML-Modellierung | Ja | Ja |
| Regionale Attributionsmodelle | Ja | Ja |
| Kann Marketing-Touchpoints in einem Modell konfigurieren | Ja | Nein |

{style=&quot;table-layout:auto&quot;}
