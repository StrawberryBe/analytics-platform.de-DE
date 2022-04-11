---
title: CJA-Benutzerhandbuch für Adobe Analytics-Benutzer
description: Was aus der Sicht eines Benutzers zu beachten ist, wenn Ihr Unternehmen Daten von Adobe Analytics in Customer Journey Analytics verschiebt
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 6981a7a68d8a517f6b842cb36382f543c80f4582
workflow-type: tm+mt
source-wordcount: '1460'
ht-degree: 6%

---

# CJA-Benutzerhandbuch für Adobe Analytics-Benutzer

Wenn Ihr Unternehmen mit der Verwendung von Customer Journey Analytics (CJA) beginnt, werden Sie möglicherweise einige Ähnlichkeiten und Unterschiede zwischen herkömmlichem Analytics und CJA feststellen. Auf dieser Seite werden diese Unterschiede erläutert, um Ihr Unternehmen bei der Implementierung und dem Reporting-Workflow zu unterstützen. Auf dieser Seite finden Sie außerdem zusätzliche Ressourcen zu neuen Konzepten und weiteren Schritten, um Ihre Journey als Analytiker einfacher und erfolgreicher zu machen.

Einige Funktionen in CJA werden umbenannt und entsprechend den Branchenstandards neu gestaltet. Einige aktualisierte Begriffe umfassen Segmente, Virtual Report Suites, Klassifizierungen, Kundenattribute und Container-Namen. Die Einschränkungen von eVars und Props existieren nicht mehr zugunsten flexibler benutzerdefinierter Dimensionen und Metriken.

## Was sich nicht geändert hat

Vieles, was Sie auf der Berichtsseite kennen, hat sich nicht geändert.

* Sie können weiterhin die [Analysis Workspace](/help/analysis-workspace/home.md) um Ihre Daten zu analysieren. Workspace funktioniert genauso wie im herkömmlichen Adobe Analytics.
* Dieselbe Version von [Adobe Analytics-Dashboards](/help/mobile-app/home.md) ist verfügbar und funktioniert ähnlich zwischen CJA und herkömmlichem Analytics.
* [Report Builder](/help/report-builder/report-buider-overview.md) verfügt über eine neue Benutzeroberfläche und läuft unter MS Windows, iOS und der Webversion von Excel. (Vor dieser Version von Report Builder konnten Sie in nicht in auf Mac verwenden, es sei denn, Sie haben es auf VMware ausgeführt.) Diese Version unterstützt die herkömmliche AA-Datenanforderung noch nicht.

## Berichtsänderungen

Sie haben Zugriff auf viel mehr kanalübergreifende Daten, die Sie analysieren können. Sie können beispielsweise ein Workspace-Projekt erstellen, das die Leistung mehrerer Kanäle analysiert, sofern diese Datensätze von Ihrer Organisation erfasst und in von CJA verwendeten Datenansichten enthalten sind (siehe &quot;Änderungen an der Datenarchitektur&quot;unten).

![Mehrkanal-Visualisierungen](assets/cross-channel.png)

## Änderungen an der Datenarchitektur {#architecture}

CJA erhält seine Daten von Adobe Experience Platform. Mit Experience Platform können Sie Kundendaten und -inhalte aus beliebigen Systemen oder Kanälen zentralisieren und standardisieren sowie mithilfe von Datenwissenschaft und maschinellem Lernen die Gestaltung und Bereitstellung personalisierter Erlebnisse verbessern.

Kundendaten in der Experience Platform werden als Datensätze gespeichert, die aus einer [schema](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=de) und Datenstapeln. Weitere Informationen zu Platform finden Sie unter [Übersicht über die Adobe Experience Platform-Architektur](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Ihr CJA-Administrator richtet [Verbindungen](/help/connections/create-connection.md) auf Datensätze in Experience Platform. Anschließend erstellen sie [Datenansichten](/help/data-views/data-views.md) diese Verbindungen verwenden. Datenansichten ähneln konzeptionell den Virtual Report Suites und bilden die Grundlage für die Berichterstellung in CJA. Da Experience Platform alle Daten für die Berichterstellung bereitstellt, existieren Report Suites nicht mehr als Datencontainer.

Mit einer Verbindung kann Ihr Analytics-Administrator Datensätze aus Adobe Experience Platform in Customer Journey Analytics integrieren, die im folgenden Video enthalten sind:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobe bietet mehrere Möglichkeiten, Daten in Adobe Experience Platform zu importieren, einschließlich Report Suite-Daten über den Adobe Analytics Source Connector oder das Web SDK. Vorhandene Implementierungen aus mehreren Report Suites können in Experience Platform kombiniert werden. Die Verbindungen und Datenansichten, die auf diesen Datensätzen basieren, können Daten kombinieren, die zuvor in separaten Report Suites vorhanden waren.

## Änderungen am Konzept von Virtual Report Suites {#data-views}

[!UICONTROL Datenansichten] Nehmen Sie das Konzept der Virtual Report Suites so auf, wie es heute existiert, und erweitern Sie es auf [zusätzliche Datenkontrollen aktivieren](/help/data-views/create-dataview.md) über Verbindungen zur Verfügung gestellt werden. Diese Änderungen machen allgemeine Einstellungen wie Zeitzonen- und Sitzungs-Timeout-Intervalle konfigurierbar und rückwirkend. Individuelle Variableneinstellungen wie Attribution und Ablauf können auch auf Berichts- oder Datenansichtsebene angepasst werden. Diese Einstellungen sind zerstörungsfrei und rückwirkend.

Beachten Sie, dass Sie mit der Report Suite-Auswahl oben rechts jetzt aus den verfügbaren Datenansichten wählen können:

![data-view-selector](assets/data-views.png)

Siehe [Anwendungsbeispiele für Datenansichten](/help/data-views/data-views-usecases.md) für weitere Informationen zu diesem Konzept.

## Änderungen am Konzept von eVars und Props

Die Konzepte von [!UICONTROL eVars], [!UICONTROL props]und [!UICONTROL events] im herkömmlichen Adobe Analytics nicht mehr in [!UICONTROL Customer Journey Analytics]. In Adobe Analytics speichern eVars und Props Beschreibungen von Inhalten, Kunden, Kampagnen usw. und -Ereignisse zählen Dinge wie Umsatz, Abonnements oder generierte Leads. In Customer Journey Analytics bleiben beide Datentypen erhalten, und Sie können auf dieselbe Weise darauf zugreifen - von der linken Leiste in Analysis Workspace aus unter Dimensionen bzw. Metriken.

In CJA sind unbegrenzte Schemaelemente verfügbar, einschließlich Dimensionen, Metriken und Listenfeldern. Diese werden unbegrenzten Schemaelementen wie Dimensionen, Metriken und Listenfeldern in der Experience Platform zugeordnet. Alle Besuchs- und Attributionseinstellungen, die nach den Verarbeitungsregeln in Adobe Analytics angewendet werden, gelten jetzt zur Abfragezeit in Customer Journey Analytics.

Mit dieser Flexibilität können Sie in Situationen geraten, in denen ein einzelnes Schemafeld sowohl als Dimension als auch als Metrik verwendet werden kann, um unterschiedliche Tracking-Anforderungen zu unterstützen.

## Änderungen am Segmentkonzept

Adobe hat die Komponente &quot;Segmente&quot;in &quot;Filter&quot;umbenannt, um sie besser an Branchenstandards anzupassen und Segmenten in Adobe Experience Platform besser zu unterscheiden.

[!UICONTROL Customer Journey Analytics] verwendet keine eVars, Props oder Experience Platformen mehr und verwendet stattdessen den Feldnamen des Schemas, dem sie zugeordnet wurden. Diese Änderung bedeutet, dass keines der vorhandenen Segmente in Adobe Analytics mit [!UICONTROL Customer Journey Analytics]. Wenn Sie vorhandene Adobe Analytics-Segmente in Customer Journey Analytics verschieben möchten, sehen Sie sich das folgende Video an:

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

Sie können zwar noch keine Freigabe oder Veröffentlichung vornehmen [!UICONTROL Filter] ([!UICONTROL Segmente]) von [!DNL Customer Journey Analytics] zur Experience Platform von Unified Profile, diese Funktion wird derzeit entwickelt.

Neben dem Konzept der sich ändernden Segmente werden auch Segmentcontainer aktualisiert.

* **Trefferbehälter sind jetzt &#39;Ereignis&#39;-Container**. Der Container [!UICONTROL Person] enthält sämtliche Sitzungen und Ereignisse für Besucher innerhalb eines bestimmten Zeitraums.
* **Besuchebehälter sind jetzt Sitzungs-Container**. Mit dem Sitzungs-Container können Seiteninteraktionen, Kampagnen oder Konversionen für eine bestimmte [!UICONTROL Sitzung] identifiziert werden.
* **Besuchercontainer sind jetzt [!UICONTROL Person] container**. Der Container [!UICONTROL Person] enthält sämtliche Sitzungen und Ereignisse für Besucher innerhalb eines bestimmten Zeitraums.

## Änderungen am Konzept der berechneten Metriken

Berechnete Metriken werden auf ähnliche Weise zwischen herkömmlichem Analytics und CJA benannt. Allerdings [!UICONTROL Customer Journey Analytics] verwendet keine eVars, Props oder Ereignisse mehr und verwendet stattdessen ein Experience Platform-Schemaelement. Diese grundlegende Änderung bedeutet, dass keine der vorhandenen berechneten Metriken mit [!UICONTROL Customer Journey Analytics]. Wenn Sie berechnete Adobe Analytics-Metriken in Customer Journey Analytics verschieben möchten, sehen Sie sich das folgende Video an:

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## Änderungen an den Einstellungen für die Variablenzuordnung und -gültigkeit

[!UICONTROL Customer Journey Analytics] wendet alle Variableneinstellungen, einschließlich Attribution und Gültigkeit, zum Zeitpunkt des Berichts an. Diese Einstellungen befinden sich jetzt in [Datenansichten](/help/data-views/component-settings/persistence.md)und einige Variableneinstellungen (wie Attribution) können in Workspace-Projekten geändert werden.

Sie können mehrere Versionen derselben Variablen in derselben Datenansicht haben. Sie können beispielsweise eine Dimension &quot;Trackingcode&quot;verwenden, die nach 30 Tagen abläuft, eine andere Dimension, die am Ende einer Sitzung abläuft. Beide Dimensionen des Trackingcodes verwenden dieselben Quelldaten, verwenden jedoch unterschiedliche Attributionseinstellungen.

Sie können auch mehrere Datenansichten haben, die auf derselben Verbindung basieren. Beispielsweise können Sie eine Datenansicht mit einem Sitzungs-Timeout von 30 Minuten und eine andere mit einem Sitzungs-Timeout von 15 Minuten haben. Beide Datenansichten werden in der oberen rechten Auswahl angezeigt, sodass Sie nahtlos zwischen ihnen wechseln können.

## Änderungen am Konzept der Klassifizierungen

&quot;Classifications&quot;werden jetzt als &quot;Lookup-Datensätze&quot;bezeichnet. Lookup-Datensätze werden verwendet, um nach Werten oder Schlüsseln in Ihren Ereignis- oder Profildaten zu suchen. Beispielsweise können Sie Suchdaten hochladen, die numerische IDs in Ihren Ereignisdaten Produktnamen zuordnen. Siehe [Hinzufügen von Daten auf Kontoebene als Lookup-Datensatz](/help/use-cases/b2b.md) für einen Anwendungsfall.

## Änderungen am Konzept der Kundenattribute

&quot;Kundenattribute&quot;werden jetzt als &quot;Profildatensätze&quot;bezeichnet. Profildatensätze enthalten Daten, die auf Ihre Besucher, Benutzer oder Kunden im [!UICONTROL Ereignis] Daten. So können Sie beispielsweise CRM-Daten zu Ihren Kunden hochladen. Sie können auswählen, welche Personen-ID Sie einbeziehen möchten. Jeder Datensatz, der in [!DNL Experience Platform] verfügt über einen eigenen Satz von einer oder mehreren definierten Personen-IDs.

## Änderungen bei der Besucheridentifizierung durch die Adobe

CJA erweitert die Identitätskonzepte über ECIDs hinaus und umfasst alle IDs, die Sie verwenden möchten, einschließlich Kunden-ID, Cookie-ID, zugeordnete ID, Benutzer-ID, Trackingcode usw. Verwenden einer gemeinsamen Namespace-ID für mehrere Datensätze oder Verwenden von [Kanalübergreifende Analyse](/help/connections/cca/overview.md) hilft, Personen über verschiedene Datensätze hinweg miteinander zu verknüpfen. Benutzer, die ein Workspace-Projekt in CJA einrichten, müssen die in den Datensätzen verwendeten IDs verstehen. Sehen Sie sich das folgende Video an, in dem die Verwendung von Identitäten in CJA hervorgehoben wird:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Änderungen am Konzept des Dimensionselements &quot;Geringer Datenverkehr&quot;

Im herkömmlichen Adobe Analytics beginnt eine Variable, die zu viele eindeutige Werte erhält, Dimensionselemente unter [!UICONTROL Geringer Traffic]. CJA hat weniger Einschränkungen für Felder mit hoher Kardinalität. Aufgrund von Änderungen an der Berichtsarchitektur kann Analysis Workspace Berichte zu vielen weiteren eindeutigen Dimensionselementen erstellen. Siehe [Long Tail](../analysis-workspace/workspace-faq/long-tail.md) Weitere Informationen dazu, wie CJA die Berichterstellung für Dimensionen mit vielen eindeutigen Werten optimiert.
