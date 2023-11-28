---
description: Erfahren Sie, wie Adobe Experience Platform Customer AI-Daten in Workspace in Customer Journey Analytics integriert werden.
title: Integrieren von Customer AI-Daten mit Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
feature: Experience Platform Integration
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '980'
ht-degree: 51%

---

# Integrieren von Customer AI-Daten mit Adobe Customer Journey Analytics

{{release-limited-testing}}

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=de) als Teil von Adobe Experience Platform Intelligent Services bietet Marketing-Experten die Möglichkeit, individuelle Kundenvorhersagen zu treffen.

Mithilfe von Einflussfaktoren kann Customer AI vorhersagen, was ein Kunde wahrscheinlich tun wird und warum. Darüber hinaus können Marketing-Experten von Prognosen und Einblicken durch Customer AI profitieren, um Kundenerlebnisse durch Bereitstellung der am besten geeigneten Angebote und Botschaften zu personalisieren.

Customer AI nutzt bei der Tendenzauswertung individuelle Verhaltensdaten und Profildaten. Customer AI ist flexibel und ermöglicht die Aufnahme aus mehreren Datenquellen, einschließlich Adobe Analytics, Adobe Audience Manager, Customer-Experience-Ereignisdaten und Erlebnisereignisdaten. Wenn Sie den Quell-Connector von Experience Platform verwenden, um Adobe Audience Manager- und Adobe Analytics-Daten aufzunehmen, zieht das Modell automatisch die standardmäßigen Ereignistypen heran, um das Modell zu trainieren und zu bewerten. Wenn Sie Ihren eigenen Erlebnisereignis-Datensatz ohne standardmäßige Ereignistypen aufnehmen, müssen alle relevanten Felder als benutzerdefinierte Ereignisse oder Profilattribute zugeordnet werden, wenn Sie ihn im Modell verwenden möchten. Dies kann im Customer AI-Konfigurationsschritt in Experience Platform durchgeführt werden.

Customer AI kann in Customer Journey Analytics integriert werden, soweit für Customer AI aktivierte Datensätze in Datenansichten und Berichten in Customer Journey Analytics genutzt werden können. Sie haben folgende Möglichkeiten:

* **Tendenz-Scores für ein Segment von Benutzern im Zeitverlauf verfolgen**.
   * Anwendungsfall: Verstehen Sie die Wahrscheinlichkeit, dass Kunden in einem bestimmten Segment konvertieren.
   * Beispiel: Ein Marketing-Experte einer Hotelkette möchte die Wahrscheinlichkeit verstehen, dass ein Hotelkunde ein Showticket am Konzertplatz des Hotels kauft.
* **Analysieren, welche Erfolgsereignisse oder Attribute mit Tendenz-Scores verknüpft sind**.
   * Anwendungsfall: Erläuterung der Attribute oder Erfolgsereignisse im Zusammenhang mit Tendenzwerten.
   * Beispiel: Ein Marketing-Experte in einer Hotelkette möchte verstehen, wie der Kauf von Show-Tickets bei einem Konzerthaus eines Hotels mit Tendenzwerten verbunden ist.
* **Den Eintrittsfluss für die Kundentendenz über verschiedene Scoring-Durchgänge hinweg verfolgen.**. 
   * Anwendungsfall: Verstehen Sie Personen, die anfangs wenig Neigung hatten und im Laufe der Zeit zu Nutzern mit hoher Tendenz wurden.
   * Beispiel: Ein Marketing-Experte in einer Hotelkette möchte verstehen, welche Hotelkunden ursprünglich als Kunden identifiziert wurden, die mit geringer Tendenz ein Showticket zu erwerben hatten, aber mit der Zeit zu Kunden wurden, die eine hohe Tendenz hatten, ein Showticket zu erwerben.
* **Die Verteilung der Tendenz betrachten**.
   * Anwendungsfall: Verstehen Sie die Verteilung der Tendenzwerte, um bei der Definition von Segmenten präziser zu sein.
   * Beispiel: Ein Einzelhändler möchte eine bestimmte Promotion für 50 US-Dollar an einem Produkt durchführen. Da sein Budget begrenzt ist, möchte er nur eine sehr eingeschränkte Promotion durchführen. Sie analysieren die Daten und entscheiden, nur die 80 %+ der Kunden als Ziel festzulegen.
* **Die Konsumtendenz betrachten, um im Laufe der Zeit eine Maßnahme für eine bestimmte Kohorte zu ergreifen**.
   * Anwendungsfall: Verfolgen Sie eine bestimmte Kohorte im Zeitverlauf.
   * Beispiel: Ein Marketing-Experte in einer Hotelkette möchte ihre Bronzestufe im Laufe der Zeit im Vergleich zu ihrer Silberstufe oder Silberstufe im Vergleich zu ihrer Goldstufe nachverfolgen. Sie können die Neigung jeder Kohorte sehen, das Hotel im Laufe der Zeit zu buchen.

Gehen Sie wie folgt vor, um Customer AI-Daten mit Customer Journey Analytics zu integrieren:

>[!NOTE]
>
>Einige der Schritte werden in Adobe Experience Platform ausgeführt, bevor die Ausgabe in Customer Journey Analytics verwendet wird.


## Schritt 1: Konfigurieren einer Customer AI-Instanz

Nachdem Sie Ihre Daten vorbereitet und alle Ihre Anmeldedaten und Schemata eingerichtet haben, folgen Sie der Anleitung [Konfigurieren einer Customer AI-Instanz](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=de) in Adobe Experience Platform.

## Schritt 2: Einrichten einer Customer Journey Analytics-Verbindung zu Customer AI-Datensätzen

Unter Customer Journey Analytics können Sie jetzt [eine oder mehrere Verbindungen erstellen](/help/connections/create-connection.md) zum Experience Platform von Datensätzen, die für Customer AI instrumentiert wurden. Jede Vorhersage, z. B. „Wahrscheinlichkeit für ein Konto-Upgrade“, entspricht einem Datensatz. Diese Datensätze werden mit dem Präfix „Customer AI Scores in EE Format – Name_der_Anwendung“ angezeigt.

>[!IMPORTANT]
>
>Jede Customer AI-Instanz verfügt über zwei Ausgabedatensätze, wenn der Umschalter aktiviert ist, um während der Konfiguration in Schritt 1 Bewertungen für Customer Journey Analytics zu aktivieren. Ein Ausgabedatensatz wird im Profil-XDM-Format und einer im Experience Event XDM-Format angezeigt.

![CAI Scores](assets/cai-scores.png)

![Verbindung herstellen](assets/create-conn.png)

Im Folgenden finden Sie ein Beispiel für ein XDM-Schema, das Customer Journey Analytics als Teil eines vorhandenen oder neuen Datensatzes einbringen würde:

![CAI-Schema](assets/cai-schema.png)

(Beachten Sie, dass es sich bei dem Beispiel um einen Profildatensatz handelt. Derselbe Satz von Schemaobjekten wäre Teil eines Erlebnisereignis-Datensatzes, den Customer Journey Analytics erfassen würde. Der Erlebnisereignis-Datensatz würde Zeitstempel als Score-Datum enthalten.) Jeder in diesem Modell bewertete Kunde hätte einen Score und ein mit ihm verknüpftes Score-Datum usw.

## Schritt 3: Erstellen von Datenansichten basierend auf diesen Verbindungen

Unter Customer Journey Analytics können Sie jetzt mit dem [Datenansichten erstellen](/help/data-views/create-dataview.md) mit den Dimensionen (z. B. Bewertung, Bewertungsdatum, Wahrscheinlichkeit usw.) und Metriken, die als Teil der von Ihnen eingerichteten Verbindung eingebunden wurden.

![Fenster &quot;Datenansicht erstellen&quot;](assets/create-dataview.png)

## Schritt 4: Erstellen von Berichten zu CAI-Scores in Workspace

Erstellen Sie in Customer Journey Analytics Workspace ein neues Projekt und ziehen Sie Visualisierungen ein.

### Verlauf der Tendenz-Scores

Im Folgenden finden Sie ein Beispiel für ein Workspace-Projekt mit CAI-Daten, in dem in einem gestapelten Balkendiagramm die Entwicklung von Tendenz-Scores für ein Benutzersegment im Zeitverlauf dargestellt wird:

![Score Buckets](assets/workspace-scores.png)

### Tabelle mit Ursachen-Codes

In der folgenden Tabelle finden Sie die Ursachen-Codes dafür, warum ein Segment eine hohe oder eine niedrige Tendenz hat:

![Ursachen-Codes](assets/reason-codes.png)

### Eintrittsfluss für die Kundentendenz

Dieses Flussdiagramm zeigt den Eintrittsfluss für die Kundentendenz in verschiedenen Scoring-Durchgängen:

![Eintrittsfluss](assets/flow.png)

### Verteilung der Tendenz-Scores

Dieses Balkendiagramm zeigt die Verteilung der Tendenz-Scores:

![Verteilung](assets/distribution.png)

### Tendenzüberschneidungen

Dieses Venn-Diagramm zeigt die Tendenzüberschneidungen in verschiedenen Scoring-Durchgängen:

![Tendenzüberschneidungen](assets/venn.png)
