---
title: Vergleichen von CJA mit BI-Lösungen
description: Customer Journey Analytics mit BI-Lösungen vergleichen
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 955f4543a132126deee52b7dfe3398b742022069
workflow-type: tm+mt
source-wordcount: '1609'
ht-degree: 0%

---


# Vergleichen von CJA mit BI-Lösungen

Mit dem aktuellen Fokus auf Kundenerlebnisse benötigen Marken fortschrittliche Lösungen, um die ganzheitliche Journey der Kunden besser zu verstehen. Wenn Sie diese vollständige Journey verstehen, können Sie wertvolle Einblicke in die Interaktion von Online- und Offline-Kanälen mit Kunden gewinnen und so Konversionen, Kundenbindung und Loyalität steigern. Eine Journey in diesem Zusammenhang kann die einfache Online-Bestellung einer Mahlzeit in einer Sushi-Nahrungskette sein. Oder der Kauf eines neuen Autos, bei dem der Kunde Online-Recherchen mit Besuchen im Händlerraum und einem endgültigen persönlichen Kauf kombiniert.

Viele Unternehmen haben ihre kanalübergreifenden Daten in einem Data Lake oder Data Warehouse konsolidiert. Business Intelligence (BI)-Tools werden auf diesen Datenspeichern verwendet, um Berichte, Visualisierungen und Einblicke bereitzustellen, die das Unternehmen benötigt, um die Journey zu verstehen. Häufig ist diese Kombination von Lösungen und Tools von Natur aus ein allgemeiner Zweck und nicht explizit auf den Kunden ausgerichtet. Customer Journey Analytics (CJA) konzentriert sich auf die Stärkung der Verantwortlichen für das Kundenerlebnis, z. B. Marketingexperten, Datenanalysten und Datenwissenschaftler. Das Tool ermöglicht es ihnen, die Journey in Echtzeit im vollen Kontext über alle Kanäle hinweg zu visualisieren, ohne Einschränkungen zu haben, die viele andere BI-Tools haben.

In diesem Abschnitt der Dokumentation werden die grundlegenden Unterschiede zwischen CJA und häufig verwendeten BI-Tools erläutert. Zunächst wird der allgemeine Workflow zur Erreichung des oben genannten Ziels untersucht: diese Journey verstehen. Anschließend werden weitere Details dazu bereitgestellt, wie Daten zwischen CJA- und BI-Tools unterschiedlich gespeichert, erfasst und abgefragt werden. Schließlich werden die Unterschiede bei den Visualisierungsfunktionen erklärt.

## Traditioneller BI-Workflow

Ein häufiges Hindernis bei herkömmlichen Ansätzen zur Analyse von Journey besteht darin, dass sie nicht kundenorientiert sind. Jedes Team erfasst Daten in Siloes, analysiert und optimiert Erlebnisse basierend auf den Daten, auf die es Zugriff hat.

![Typischer BI-Workflow](./assets/biworkflow.png)

Wenn Sie verstehen möchten, wie eine bestimmte digitale Kampagne eine Offline-Aktion beeinflusst, die in einem anderen Datensilo gespeichert ist, senden Sie eine Anfrage an die Warteschlange des BI-Teams. Das BI-Team schreibt die erforderliche Abfrage, um die Daten zu erfassen und umzuwandeln. Nachdem die Rohdaten abgerufen wurden, erstellt das BI-Team die Visualisierung. Die Daten werden für Sie freigegeben und Sie verbringen Zeit damit, durch die Einblicke zu kämmen und Daten zur Aktivierung in anderen Systemen zu extrahieren.

Jeder dieser Schritte kann Stunden, Tage oder sogar Wochen dauern. Wenn Folgefragen oder Probleme mit den abgefragten Daten auftreten, kann es noch mehr Zeit dauern, bis diese Fragen behandelt werden, und der Zyklus wird fortgesetzt. Für die laufende Analyse, Untersuchung und Kenntnis der Journey ist dieser Vorgang ineffizient und nicht skalierbar. Außerdem befassen sich BI-Teams normalerweise mit mehr als nur Journey-bezogenen Fragen von Kunden.

## CJA: Demokratisierter Workflow für Online- und Offline-Daten

CJA bietet eine Umgebung, in der kanalübergreifende Online- und Offline-Daten auf übergeordneter Kundenebene miteinander verbunden werden können, um nur die Journey des Kunden zu verstehen. Es ist eine Ersteinrichtung erforderlich, um [connect](/help/connections/overview.md) und [Ansichten definieren](/help/data-views/data-views.md) zu den Daten hinzu, die Sie als relevant qualifizieren. Nach Abschluss dieser Daten stehen diese Daten jedoch jederzeit für die laufende Analyse und Untersuchung zur Verfügung. Sie können schrittweise Einblicke in die Journey gewinnen und diese verstehen. Durch die Demokratisierung von kombinierten Online- und Offline-Daten können Sie kundenbezogene Journey-Fragen in Sekundenschnelle beantworten.

![CJA-Workflow](./assets/cjaworkflow.png)

Sie können CJA verwenden, um Fragen mithilfe der visuellen Analysis Workspace-Umgebung zu stellen und fast sofort Einblicke zu erhalten. Kanalübergreifende Daten und Berichte sind sofort verfügbar, ohne dass SQL-Code erforderlich ist. Zusätzliche Abfragen und Analysen können mit einem einfachen Drag &amp; Drop in der Benutzeroberfläche und vollständig korrelierten Daten durchgeführt werden. Sie können weiterhin Fragen stellen und nach Bedarf weitere Details erkunden. Sie können dann sofort auf die Einblicke reagieren, die Sie entdecken, z. B. durch die Freigabe von Zielgruppen für die Aktivierung und Orchestrierung.

## Die leistungsstarke Reporting-Engine von CJA

CJA verwendet eine leistungsstarke proprietäre Architektur, die die Analyse auf Hunderte oder sogar Tausende von Servern verteilt, um Daten in Analysis Workspace innerhalb von Sekunden anzuzeigen. Zu den wichtigen Eigenschaften dieser Verarbeitungsarchitektur gehören:

* **Optimiert für individuelle kundenbezogene Abfragen**: Technisch betrachtet speichert CJA die Daten in einer verteilten Reporting-Engine, die das Caching umfassend nutzt. Diese Engine ist auf responsive Abfragen von Ereignisdaten auf individueller Ebene abgestimmt und daher perfekt für kundenbezogene Abfragen optimiert. Die Reporting-Engine speichert Daten in spaltenorientierten Bitmap-Indizes, die eine schnelle On-the-Fly-Berechnung der aggregierten Metriken ermöglichen. Es verfügt über eine umfangreiche Filtermaschine, die eine leistungsstarke Segmentierung/Zielgruppenanalyse ermöglicht. Und es besitzt ein grundlegendes Verständnis der Sequenz zwischen Datenpunkten, das bei der Analyse des Verhaltens über diese Datenpunkte hinweg (die Reihenfolge, in der die Dinge aufgetreten sind) und für die Zuweisung der Attribution mithilfe verschiedener, komplexer Modelle nützlich ist.

* **Schnelle Anwendung komplexer Pfade und Filter**: Die Reporting-Engine arbeitet mit teilweise sortierten, hierarchischen Datensätzen (z. B. person -> sessions -> events). Alle Daten für ein Objekt der obersten Ebene (einzelne Profile) befinden sich auf einem einzigen Verarbeitungsknoten, um präzise Ergebnisse zu erzielen. Diese Partitionierung ermöglicht die schnelle Anwendung komplexer Pfade und Filter. Komplexe Vorgänge wie Sitzungserstellung, Attribution, stateful Persistenz von Datenattributen und komplexe Datenbearbeitungsoptionen werden skaliert und mit schneller Berichtszeit ausgeführt. In der BI-Welt erfordern diese Arten von Vorgängen normalerweise, dass für jeden Anwendungsfall neue OLAP-Cubes erstellt werden. Die Reporting-Engine von CJA ermöglicht den ungehinderten Zugriff auf den gesamten Datensatz in jeder Abfrage, was zu vollständig korrelierten Daten führt, ohne dass die Cubing-Funktion vorzeitig erforderlich ist.

* **Effiziente Abfrage komplexer Datenströme**: Einer der größten Unterschiede der Reporting-Engine gegenüber herkömmlichen SQL- und NoSQL-Datenbanken besteht in der Fähigkeit, Vorhersagen auf Basis sequenzorientierter Beziehungen auf einer grundlegenden Ebene zu bestimmen. Diese grundlegenden Abfrageoperationen können sich auf den Datensatz-Stream beziehen, der aus vielen interaktiven (und sogar verschachtelten) Sequenzen besteht. Sie führen eine Abfrage für all diese miteinander verbundenen Datenströme durch, mit der Effizienz eines einzigen, zusammenhängenden Sequenzvorgangs.

* **Entwickelt für die schnelle Beantwortung großer Abfragen**: Die Reporting-Engine ist nicht so allgemein wie herkömmliche Big-Data-Systeme. Sie wurde jedoch speziell für die Beantwortung von Abfragen entwickelt, die Millionen oder sogar Milliarden von Datensätzen (Ereignisdaten/Erlebnisereignisse) umfassen, im Allgemeinen in weniger als einer Sekunde. Im Gegensatz zu anderen Big-Data-Systemen erfolgt dies nicht durch Stichproben der Daten oder durch Vorberechnung der Antworten auf alle Fragen, die sie stellen könnten. Stattdessen können die Antworten schnell genug berechnet werden, um die interaktive Abfrage von Anwendungsfällen zu unterstützen. Diese spezielle Gestaltung der Reporting-Engine von CJA erleichtert die schnelle Verfügbarkeit und schnelle Datenanalyse und ermöglicht es Ihnen so, schrittweise Einblicke in die Journey der Kunden zu gewinnen.

* **Funktioniert als Headless BI-Lösung**: Sie definieren Ihre Dimensionen, Metriken und Filter an einem Ort, und dann kann jeder CJA-Client (einschließlich unserer öffentlichen CJA-API) auf diese Komponenten zugreifen. Dadurch werden komplexe Abfragen von Endbenutzern abstrahiert und sichergestellt, dass die Ergebnisse unabhängig vom verwendeten Berichts- oder Visualisierungsclient identisch sind.

## Die einzigartigen Visualisierungsfunktionen von CJA

Die Reporting-Engine ist von grundlegender Bedeutung für CJA, damit Sie schrittweise mit allen Journey-Daten der Kunden innerhalb dieser Reporting-Engine interagieren und darauf reagieren können. CJA verfügt über einen umfangreichen Satz an Komponenten, mit denen Sie dies visuell und durch Drag &amp; Drop erreichen können. Mit BI-Visualisierungs-Tools können Sie innerhalb der Grenzen von SQL-vorbereiteten Daten (wie von IT definiert) erkunden. Mit CJA können Sie beliebig viele Teile zerlegen und auseinanderschneiden, ohne zur IT zurückkehren zu müssen, um eine weitere SQL-Ansicht zu erstellen.

&quot;Progressiv&quot;ist hier ein Schlüsselkonzept: Im Gegensatz zu den meisten Visualisierungen in BI-Tools können Sie mit der visuellen Drag &amp; Drop-Benutzeroberfläche in CJA Ihre Daten kontinuierlich für Ihre spezifischen Anforderungen aufschlüsseln: Sie können visuelle Abfragen interaktiv mit relevanten Metriken, Dimensionen, Filtern (Segmenten), Berechnungen, Zeitlinien, Anmerkungen und anderen Analysewerten erstellen.

In diese Visualisierungskomponenten integriert sind intelligente Funktionen wie:

* **Virtual Analytics-Funktionen** wie [Anomalieerkennung](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) , die mithilfe von Prognosealgorithmen und maschinellem Lernen Einblicke in die Ursachen für ungewöhnliche Verhaltensweisen in Ihren Daten liefern.

* **Erweiterte Analysefunktionen** , die sich speziell auf Journey-Einblicke von Kunden konzentrieren, z. B. [Flussdiagramme](/help/analysis-workspace/visualizations/c-flow/flow.md), [Attribution IQ](/help/analysis-workspace/attribution/overview.md), [Fallout-Diagramme](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)und [Dimensionsaufschlüsselungen](/help/components/dimensions/t-breakdown-fa.md). Beispiele für vordefinierte Visualisierungen:

   * [Kundenbindungsanalyse über Kohorten-/Latenztabellen](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md), wo Sie einfach Metriken/Dimensionen per Drag-and-Drop in einem Builder ablegen und in weniger als 30 Sekunden fertig sind,

   * [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md) / [Fluss](/help/analysis-workspace/visualizations/c-flow/create-flow.md) Visualisierungen. In weniger als einer Minute einrichten.

   * [Attributionsmodelle](/help/analysis-workspace/attribution/algorithmic.md) zum Beispiel Erstkontakt, Letztkontakt, Teilnahme, Zeitverfall, selbst benutzerspezifische Einstellungen, für deren Einrichtung einige Klicks erforderlich sind.

* **Segmentierungsfunktion in jedem Schritt Ihrer progressiven Exploration**: wann immer Sie dies für sinnvoll halten, können Sie Ihre Zielgruppe wieder in Experience Platform veröffentlichen und von dort an einem der unterstützten Ziele veröffentlichen.

* **Sessionization** vollständig [anpassbar](/help/data-views/component-settings/persistence.md): Sie bestimmen, wann eine Sitzung als Teil eines Kanals in einer Journey beginnt und endet.

* **Kuratierung und Demokratisierung**: Die in CJA erstellten Dashboards können wie folgt aussehen:

   * [Kuratiert](/help/analysis-workspace/curate-share/curate.md) an andere Personen in der Organisation zur kontinuierlichen Exploration,
   * Exportiert in Excel mit [Report Builder](/help/report-builder/report-buider-overview.md) (ein dediziertes Plug-in),
   * [Freigegeben](/help/analysis-workspace/curate-share/share-projects.md) in verschiedenen Formaten, einschließlich [PDF](/help/analysis-workspace/curate-share/download-send.md), [CSV](/help/analysis-workspace/curate-share/download-send.md) und [dedizierte mobile App](/help/mobile-app/home.md), für diejenigen, die an den endgültigen Berichten und/oder Visualisierungen interessiert sind.

Der Vergleich der Visualisierungsfunktionen von CJA mit den von BI-Tools angebotenen Funktionen ist aufgrund der Vielzahl der verfügbaren Visualisierungen schwierig. Einige BI-Tools verfügen über erweiterte Visualisierungen, CJA konzentriert sich jedoch auf interaktive und interoperable Journey-Visualisierungen für Kunden, mit denen Sie die Daten innerhalb von Sekunden aufschlüsseln können, ohne Sie für jede zusätzliche Abfrage &quot;aufladen&quot;zu müssen.


## Zusammenfassung

CJA unterscheidet sich von BI-Tools insofern, als es eine hochoptimierte kundenorientierte Berichterstellungsmodul nahtlos mit benutzerfreundlichen Tools und Komponenten integriert, um Analysen durchzuführen und Berichte und erweiterte Visualisierungen zu erstellen. Alles aus einer einzigen Benutzeroberfläche, ohne dass Sie zwischen der Abfragemaschine und der Visualisierungsumgebung hin- und herwechseln müssen.

