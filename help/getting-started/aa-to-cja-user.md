---
title: CJA-Benutzerhandbuch für Adobe Analytics-Benutzer
description: Was Benutzer beachten müssen, wenn ihr Unternehmen Daten von Adobe Analytics nach Customer Journey Analytics verschiebt
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: a9009c44a8e739add7fbcb9f9c31676d38af0094
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 98%

---

# CJA-Benutzerhandbuch für Adobe Analytics-Benutzer

Wenn Ihr Unternehmen mit der Verwendung von Customer Journey Analytics (CJA) beginnt, werden Sie möglicherweise einige Ähnlichkeiten und Unterschiede zwischen herkömmlichem Analytics und CJA feststellen. Auf dieser Seite werden diese Unterschiede erläutert, um Ihr Unternehmen beim neuen Implementierungs- und Reporting-Workflow zu unterstützen. Auf dieser Seite finden Sie außerdem zusätzliche Ressourcen zu neuen Konzepten sowie weitere Schritte, um Ihre Arbeit als Analytiker einfacher und erfolgreicher zu gestalten.

Einige Funktionen in CJA werden umbenannt und entsprechend den Branchenstandards neu gestaltet. Zu den aktualisierten Begriffen gehören Segmente, Virtual Report Suites, Klassifizierungen, Kundenattribute und Container-Namen. Es gibt keine Einschränkungen von eVars und Props mehr. Stattdessen stehen flexible benutzerdefinierte Dimensionen und Metriken zur Verfügung.

## Was sich nicht geändert hat

Vieles beim Reporting hat sich nicht geändert.

* Sie können weiterhin die Funktionen von [Analysis Workspace](/help/analysis-workspace/home.md) verwenden, um Ihre Daten zu analysieren. Der Arbeitsbereich funktioniert genauso wie im herkömmlichen Adobe Analytics.
* Dieselbe Version von [Adobe Analytics-Dashboards](/help/mobile-app/home.md) ist verfügbar und funktioniert ähnlich in CJA wie in herkömmlichem Analytics.
* [Report Builder](/help/report-builder/report-buider-overview.md) verfügt über eine neue Benutzeroberfläche und läuft unter MS Windows, macOS und der Web-Version von Excel. (Vor dieser Version von Report Builder konnten Sie Report Builder nur dann auf Mac-Geräten verwenden, wenn das Programm auf VMware ausgeführt wurde.) Diese Version unterstützt die herkömmliche AA-Datenanfrage noch nicht.

## Änderungen beim Reporting

Sie haben jetzt Zugriff auf viel mehr kanalübergreifende Daten, die Sie analysieren können. Sie können beispielsweise ein Arbeitsbereich-Projekt erstellen, das die Leistung mehrerer Kanäle analysiert, sofern diese Datensätze von Ihrem Unternehmen erfasst und in die von CJA verwendeten Datenansichten einbezogen werden (siehe „Änderungen an der Datenarchitektur“).

![Mehrkanal-Visualisierungen](assets/cross-channel.png)

## Änderungen an der Datenarchitektur {#architecture}

CJA erhält seine Daten von Adobe Experience Platform. Mit Experience Platform können Sie Kundendaten und Inhalte aus beliebigen Systemen oder Kanälen zentral zusammenführen und standardisieren sowie mithilfe von Datenwissenschaft und maschinellem Lernen die Gestaltung und Bereitstellung personalisierter Erlebnisse verbessern.

Kundendaten in Experience Platform werden als Datensätze gespeichert, die aus einem [Schema](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=de) und Datenstapeln bestehen. Weitere Informationen zu Platform finden Sie unter [Übersicht über die Adobe Experience Platform-Architektur](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=de).

Ihr CJA-Administrator richtet [Verbindungen](/help/connections/create-connection.md) zu Datensätzen in Experience Platform ein. Anschließend erstellen sie mithilfe dieser Verbindungen [Datenansichten](/help/data-views/data-views.md). Datenansichten ähneln konzeptionell den Virtual Report Suites und bilden die Grundlage für die Berichterstellung in CJA. Da Experience Platform alle Daten für die Berichterstellung bereitstellt, fungieren Report Suites nicht mehr als Daten-Container.

Mit einer Verbindung kann Ihr Analytics-Administrator Datensätze von Adobe Experience Platform in Customer Journey Analytics integrieren, wie im folgenden Video gezeigt wird:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobe bietet mehrere Möglichkeiten, um Daten in Adobe Experience Platform zu importieren, wie etwa Report Suite-Daten über den Adobe Analytics-Quell-Connector oder das Web SDK. Vorhandene Implementierungen aus mehreren Report Suites können in Experience Platform zusammengefasst werden. Die Verbindungen und Datenansichten, die auf diesen Datensätzen basieren, können Daten kombinieren, die zuvor in separaten Report Suites vorhanden waren.

## Änderungen am Konzept von Virtual Report Suites {#data-views}

[!UICONTROL Datenansichten] übernehmen das Konzept der heutigen Virtual Report Suites und erweitern es, sodass [die über die Verbindungen verfügbar gemachten Daten besser kontrolliert werden können](/help/data-views/create-dataview.md). Durch diese Änderungen können allgemeine Einstellungen wie Zeitzonen und Sitzungs-Timeout-Intervalle konfiguriert werden und diese Konfigurationen gelten auch rückwirkend. Einzelne Variableneinstellungen wie Attribution und Gültigkeit können auch auf Berichts- oder Datenansichtsebene angepasst werden. Diese Einstellungen sind nicht destruktiv und gelten auch rückwirkend.

Beachten Sie, dass Sie mit der Report Suite-Auswahl oben rechts jetzt aus den verfügbaren Datenansichten wählen können:

![Datenansichts-Auswahl](assets/data-views.png)

Weitere Informationen zu diesem Konzept finden Sie unter [Anwendungsbeispiele für Datenansichten](/help/use-cases/data-views/data-views-usecases.md).

## Änderungen am Konzept von eVars und Props

Die Konzepte von [!UICONTROL eVars], [!UICONTROL Props] und [!UICONTROL Ereignisse] im traditionellen Adobe Analytics existieren in [!UICONTROL Customer Journey Analytics] nicht mehr. In Adobe Analytics speichern eVars und Props Beschreibungen von Inhalten, Kunden, Kampagnen usw. und Ereignisse zählen Dinge wie Umsatz, Abonnements oder generierte Leads. In Customer Journey Analytics bleiben beide Datentypen erhalten, und Sie können auf dieselbe Weise darauf zugreifen - über die linke Leiste in Analysis Workspace unter Dimensionen bzw. Metriken.

In CJA sind unbegrenzte Schemaelemente verfügbar, einschließlich Dimensionen, Metriken und Listenfelder. Diese werden unbegrenzten Schemaelementen wie Dimensionen, Metriken und Listenfeldern in Experience Platform zugeordnet. Alle Besuchs- und Attributionseinstellungen, die nach den Verarbeitungsregeln in Adobe Analytics angewendet werden, gelten jetzt zur Abfragezeit in Customer Journey Analytics.

Mit dieser Flexibilität könnten Situationen auftreten, in denen ein einzelnes Schemafeld sowohl als Dimension als auch Metrik verwendet werden kann, um unterschiedliche Tracking-Anforderungen zu ermöglichen.

## Änderungen am Konzept der Segmente

Adobe hat die Komponente „Segmente“ in „Filter“ umbenannt, um sie an Branchenstandards anzupassen und eine einfache Unterscheidung zu Segmenten in Adobe Experience Platform zu gewährleisten.

[!UICONTROL Customer Journey Analytics] verwendet keine eVars, Eigenschaften oder Ereignisse mehr, sondern verwendet stattdessen den Feldnamen des Experience Platform-Schemas, dem sie zugeordnet wurden. Diese Änderung bedeutet, dass keines der vorhandenen Segmente in Adobe Analytics mit [!UICONTROL Customer Journey Analytics] kompbatibel sind. Wenn Sie vorhandene Adobe Analytics-Segmente in Customer Journey Analytics verschieben möchten, sehen Sie sich das folgende Video an:

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

Sie können [!UICONTROL Filter] ([!UICONTROL Segmente]) von [!DNL Customer Journey Analytics] zwar noch nicht für Experience Platform Unified Profile freigeben oder dort veröffentlichen, diese Funktion ist aber schon in Entwicklung.

Zusätzlich zum geänderten Konzept der Segmente wurden auch Segment-Container aktualisiert.

* **Treffer-Container sind jetzt [!UICONTROL Ereignis]-Container**. Mit dem [!UICONTROL Ereignis]-Container können Sie die Besucherinformationen auf der Grundlage einzelner Seitenansichten/Treffer aufschlüsseln.
* **Besucher-Container sind jetzt [!UICONTROL Sitzungs]-Container**. Mit dem [!UICONTROL Sitzungs]-Container können Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte Sitzung identifiziert werden.
* **Besucher-Container sind jetzt [!UICONTROL Person]-Container**. Der Container [!UICONTROL Person] enthält sämtliche Sitzungen und Ereignisse für einen Besucher innerhalb eines bestimmten Zeitraums.

## Änderungen am Konzept der berechneten Metriken

Berechnete Metriken heißen im traditionellen Analytics und CJA gleich. Doch [!UICONTROL Customer Journey Analytics] verwendet keine eVars, Props oder Ereignisse mehr, sondern verwendet stattdessen ein Experience Platform-Schemaelement. Diese grundlegende Änderung bedeutet, dass keine der vorhandenen berechneten Metriken mit [!UICONTROL Customer Journey Analytics] kompatibel sind. Wenn Sie berechnete Adobe Analytics-Metriken in Customer Journey Analytics verschieben möchten, sehen Sie sich das folgende Video an:

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## Änderungen an Einstellungen der Variablenattribution und der Gültigkeit

[!UICONTROL Customer Journey Analytics] wendet alle Variableneinstellungen, einschließlich Attribution und Gültigkeit, zum Zeitpunkt der Berichterstellung an. Diese Einstellungen sind jetzt in den [Datenansichten](/help/data-views/component-settings/persistence.md) gespeichert und einige Variableneinstellungen (wie Attribution) können in Workspace-Projekten geändert werden.

Sie können mehrere Versionen derselben Variablen in derselben Datenansicht haben. Sie können beispielsweise eine Trackingcode-Dimension verwenden, die nach 30 Tagen abläuft, eine andere, die am Ende einer Sitzung abläuft. Beide Trackingcode-Dimensionen verwenden dieselben Quelldaten, jedoch unterschiedliche Attributionseinstellungen.

Sie können auch mehrere Datenansichten haben, die auf derselben Verbindung basieren. Beispielsweise können Sie eine Datenansicht mit einem Sitzungs-Timeout von 30 Minuten und eine andere mit einem Sitzungs-Timeout von 15 Minuten haben. Beide Datenansichten werden im Auswahlmenü oben rechts angezeigt, sodass Sie nahtlos zwischen ihnen wechseln können.

## Änderungen am Konzept der Klassifizierungen

„Klassifizierungen“ werden jetzt als „Lookup-Datensätze“ bezeichnet. Lookup-Datensätze werden verwendet, um nach Werten oder Schlüsseln in Ihren Ereignis- oder Profildaten zu suchen. Beispielsweise können Sie Suchdaten hochladen, die numerische IDs in Ihren Ereignisdaten den Produktnamen zuordnen. Ein Beispiel für einen Anwendungsfall finden Sie unter [Hinzufügen von Daten auf Kontoebene als Lookup-Datensatz](/help/use-cases/b2b/b2b.md).

## Änderungen am Konzept der Kundenattribute

„Kundenattribute“ werden jetzt als „Profildatensätze“ bezeichnet. Profildatensätze enthalten Daten, die auf Ihre Besucher, Benutzer oder Kunden in den [!UICONTROL Ereignisdaten] angewendet werden. So können Sie beispielsweise CRM-Daten über Ihren Kunden hochladen. Sie können auswählen, welche Personen-ID Sie einbeziehen möchten. Jeder Datensatz, der in [!DNL Experience Platform] definiert ist, verfügt über einen eigenen Satz von einer oder mehreren definierten Personen-IDs.

## Änderungen bei der Besucheridentifizierung durch die Adobe

CJA erweitert die Konzepte von Identitäten über ECIDs hinaus und umfasst alle IDs, die Sie verwenden möchten, einschließlich Kunden-ID, Cookie-ID, zusammengeführte ID, Benutzer-ID, Trackingcode usw. Durch die Verwendung einer gemeinsamen Namespace-ID für mehrere Datensätze oder die Verwendung von [Cross-Channel Analytics](/help/cca/overview.md) können Personen über verschiedene Datensätze hinweg miteinander verknüpft werden. Benutzer, die in CJA ein Workspace-Projekt einrichten, müssen wissen, welche IDs in den verschiedenen Datensätzen verwendet werden. Sehen Sie sich das folgende Video an, in dem die Verwendung von Identitäten in CJA erläutert wird:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Änderungen am Konzept des Dimensionselements „Low Traffic“

Im traditionellen Adobe Analytics beginnt eine Variable, die zu viele eindeutige Werte erhält, Dimensionselemente unter [!UICONTROL Low Traffic] zusammenzufassen. CJA hat weniger Einschränkungen für Felder mit hoher Kardinalität. Aufgrund von Änderungen an der Berichtsarchitektur kann Analysis Workspace Berichte zu vielen weiteren eindeutigen Dimensionselementen erstellen. Weitere Informationen dazu, wie CJA die Berichterstellung für Dimensionen mit vielen eindeutigen Werten optimiert, finden Sie unter [Long Tail](../analysis-workspace/workspace-faq/long-tail.md).
