---
description: Erfahren Sie, wie AEP-Kunden-KI-Daten in CJA mit Workspace integriert werden.
title: Integrieren von Kunden-KI-Daten in CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: fdd8d96eeca90ac13c035ace4a010c016681bac7
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 73%

---

# Integrieren von Kunden-KI-Daten in CJA

>[!NOTE]
>
>Diese Funktion wird derzeit  [eingeschränkt getestet](/help/release-notes/releases.md) und ist nicht allgemein verfügbar.

[Customer AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=de) als Teil von Adobe Experience Platform Intelligent Services bietet Marketing-Experten die Möglichkeit, individuelle Kundenvorhersagen zu treffen.

Mithilfe von Einflussfaktoren kann Customer AI vorhersagen, was ein Kunde wahrscheinlich tun wird und warum. Darüber hinaus können Marketing-Experten von Prognosen und Einblicken durch Customer AI profitieren, um Kundenerlebnisse durch Bereitstellung der am besten geeigneten Angebote und Botschaften zu personalisieren.

Customer AI nutzt bei der Tendenzauswertung individuelle Verhaltensdaten und Profildaten. Customer AI ist flexibel und ermöglicht die Aufnahme aus mehreren Datenquellen, einschließlich Adobe Analytics, Adobe Audience Manager, Customer-Experience-Ereignisdaten und Erlebnisereignisdaten. Wenn Sie den Quell-Connector von Experience Platform verwenden, um Adobe Audience Manager- und Adobe Analytics-Daten aufzunehmen, zieht das Modell automatisch die standardmäßigen Ereignistypen heran, um das Modell zu trainieren und zu bewerten. Wenn Sie Ihren eigenen Erlebnisereignis-Datensatz ohne standardmäßige Ereignistypen aufnehmen, müssen alle relevanten Felder als benutzerdefinierte Ereignisse oder Profilattribute zugeordnet werden, wenn Sie ihn im Modell verwenden möchten. Dies kann im Customer AI-Konfigurationsschritt in Experience Platform durchgeführt werden.

Customer AI kann in Customer Journey Analytics (CJA) integriert werden, soweit für Customer AI aktivierte Datensätze in Datenansichten und Berichten in CJA genutzt werden können. Sie können:

* **Tendenz-Scores für ein Segment von Benutzern im Zeitverlauf verfolgen**.
   * Anwendungsfall: die Wahrscheinlichkeit verstehen, dass Kunden in einem bestimmten Segment konvertiert werden.
   * Beispiel: Ein Marketer in einer Hotelkette möchte wissen, wie wahrscheinlich es ist, dass ein Hotelkunde ein Showticket am Konzertplatz des Hotels kauft.
* **Analysieren, welche Erfolgsereignisse oder Attribute mit Tendenz-Scores verknüpft sind**.
   * Anwendungsfall: die Attribute oder Erfolgsereignisse verstehen, die mit Tendenzwerten verknüpft sind.
   * Beispiel: Ein Marketer in einer Hotelkette möchte verstehen, wie die Käufe von Show-Tickets in einem Konzerthaus eines Hotels mit Tendenzwerten verbunden sind.
* **Den Eintrittsfluss für die Kundentendenz über verschiedene Scoring-Durchgänge hinweg verfolgen.**. 
   * Anwendungsfall: Menschen zu verstehen, die anfangs wenig Neigung hatten und im Laufe der Zeit zu Nutzern mit hoher Tendenz wurden.
   * Beispiel: Ein Marketer in einer Hotelkette möchte wissen, welche Hotelkunden ursprünglich als Kunden identifiziert wurden, die nur mit geringer Tendenz ein Showticket zu erwerben hatten, aber mit der Zeit zu Kunden wurden, die eine hohe Tendenz hatten, ein Showticket zu kaufen.
* **Die Verteilung der Tendenz betrachten**.
   * Anwendungsfall: die Verteilung der Tendenzwerte zu verstehen, um bei der Definition von Segmenten präziser zu sein.
   * Beispiel: Ein Einzelhändler möchte eine spezifische Promotion für 50 US-Dollar pro Produkt durchführen. Da sein Budget begrenzt ist, möchte er nur eine sehr eingeschränkte Promotion durchführen. Sie analysieren die Daten und entscheiden, nur die 80 %+ der Kunden als Ziel festzulegen.
* **Die Konsumtendenz betrachten, um im Laufe der Zeit eine Maßnahme für eine bestimmte Kohorte zu ergreifen**.
   * Anwendungsfall: eine bestimmte Kohorte im Zeitverlauf verfolgen.
   * Beispiel: Ein Marketer in einer Hotelkette möchte ihre Bronzestufe im Laufe der Zeit im Vergleich zu ihrer Silberstufe oder Silberstufe im Vergleich zu ihrer Goldstufe nachverfolgen. So können sie die Neigung jeder Kohorte sehen, das Hotel im Laufe der Zeit zu buchen.

Gehen Sie wie folgt vor, um Customer AI-Daten in CJA zu integrieren:

>[!NOTE]
>
>Einige der Schritte werden in Adobe Experience Platform ausgeführt, bevor die Ausgabe in CJA verwendet wird.


## Schritt 1: Konfigurieren einer Customer AI-Instanz

Nachdem Sie Ihre Daten vorbereitet und alle Ihre Anmeldedaten und Schemata eingerichtet haben, folgen Sie der Anleitung [Konfigurieren einer Customer AI-Instanz](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=de) in Adobe Experience Platform.

## Schritt 2: Einrichten einer CJA-Verbindung mit Customer AI-Datensätzen

In Customer Journey Analytics können Sie jetzt [eine oder mehrere Verbindungen](/help/connections/create-connection.md) mit Experience Platform-Datensätzen erstellen, die für Customer AI eingerichtet wurden. Jede Vorhersage, z. B. „Wahrscheinlichkeit für ein Konto-Upgrade“, entspricht einem Datensatz. Diese Datensätze werden mit dem Präfix „Customer AI Scores in EE Format – Name_der_Anwendung“ angezeigt.

>[!IMPORTANT]
>
>Jede Customer AI-Instanz verfügt über zwei Ausgabedatensätze, vorausgesetzt der Umschalter zur Aktivierung von Scores für CJA wurde bei der Konfiguration in Schritt 1 aktiviert. Ein Ausgabedatensatz wird im Profil-XDM-Format und einer im Experience Event XDM-Format angezeigt.

![CAI Scores](assets/cai-scores.png)

![Verbindung herstellen](assets/create-conn.png)

Hier ist ein Beispiel für ein XDM-Schema, das als Teil eines vorhandenen oder neuen Datensatzes über CJA übermittelt werden würde:

![CAI-Schema](assets/cai-schema.png)

(Beachten Sie, dass das Beispiel ein Profildatensatz ist. Derselbe Satz von Schemaobjekten wäre Teil eines Erlebnisereignis-Datensatzes, der von CJA erfasst werden würde. Der Erlebnisereignis-Datensatz würde Zeitstempel als Score-Datum enthalten.) Jeder in diesem Modell bewertete Kunde hätte einen Score und ein mit ihm verknüpftes Score-Datum usw.

## Schritt 3: Erstellen von Datenansichten basierend auf diesen Verbindungen

In CJA können Sie jetzt mit den Dimensionen (z. B. Score, Score-Datum, Wahrscheinlichkeit usw.) und Metriken, die gemeinsam mit der von Ihnen eingerichteten Verbindung übermittelt wurden, [Datenansichten erstellen](/help/data-views/create-dataview.md).

![Datenansicht erstellen](assets/create-dataview.png)

## Schritt 4: Erstellen von Berichten zu CAI-Scores in Workspace

Erstellen Sie ein neues Projekt in CJA Workspace und rufen Sie Visualisierungen ab.

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
