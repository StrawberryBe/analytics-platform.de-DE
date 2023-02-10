---
title: Handbuch für Customer Journey Analytics
description: Landingpage von Customer Journey Analytics.
exl-id: c2d9b758-42a4-4b58-9bab-095518efb86d
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 9eae32c75218a9fd84da42593f4bd202757b4403
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 82%

---

# Handbuch für Customer Journey Analytics

Diese technische Dokumentation bietet Hilfe zur Selbsthilfe für Customer Journey Analytics. Customer Journey Analytics ermöglicht es Ihnen, Kundendaten von beliebigen Kanälen – sowohl online als auch offline – in Adobe Experience Platform zusammenzuführen und genauso zu analysieren wie vorhandene digitale Daten mithilfe von Analysis Workspace.

Mit Customer Journey Analytics können Sie steuern, wie Sie Ihre Online- und Offline-Daten in Analysis Workspace mit jeder beliebigen Kunden-ID verbinden. Dadurch können Sie Aufgaben wie Attribution, Filterung, Fluss- und Fallout-Steuerung usw. endlich durchführen. über Ihren gesamten Kundendatensatz hinweg in Customer Journey Analytics durchführen.

Kunden von Analytics Select, Prime und Ultimate sind zum Erwerb dieses Zusatzprodukts qualifiziert. Weitere Informationen erhalten Ihren Ansprechpartnern beim Adobe Account Team.

<table frame="none"> 
 <tbody> 
  <tr> 
   <td colname="col1" colsep="0" rowsep="0" valign="top"> <p class="head"> <b>Neue oder vorgestellte Funktionen</b> </p> <p> 
     <ul>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cca/overview.html?lang=de#cja-connections"> Cross-Channel Analytics (Zusammenfügen von IDs in Customer Journey Analytics) </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=en">Verwenden von Daten aus Report Suites von Adobe Analytics in Customer Journey Analytics </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=de"> Kombinieren von Report Suites mit unterschiedlichen Schemata </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/pr-vista-dataprep.html?lang=en"> Verarbeitungsregeln, VISTA und Klassifizierungen versus Datenvorbereitung </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html?lang=en"> Vergleich der Datenverarbeitung zwischen den Reporting-Funktionen von Adobe Analytics und CJA </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html?lang=en"> Virtual Report Suites, Datenansichten, AEP-Sandboxes und der Analytics-Quell-Connector </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html"> Umstieg von Adobe Analytics auf Customer Journey Analytics </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja-user.htm"> CJA-Benutzerhandbuch für Adobe Analytics-Benutzer </a> </li>
     <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html?lang=de#connection-detail"> Verwenden der erweiterten Funktionen zur Verbindungsverwaltung </a> </li>
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=de#cja-dataviews"> Verwenden der erweiterten Funktionen für Datenansichten </a> </li>
   <td colname="col2" valign="top"><p class="head"> <b>Erste Schritte</b> </p> 
      <ul> 
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-getting-started.html?lang=de"> Erste Schritte mit Customer Journey Analytics </a> </li> 
      <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=de"> Häufig gestellte Fragen</a> </li> 
   </ul> <p class="head"><b>Versionshinweise</b> </p> 
     <li>Alles über neue Funktionen und Fehlerbehebungen finden Sie in den neuesten <a href="https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=de" format="https" scope="external">Customer Journey Analytics-Versionshinweisen</a>. </li>
    <td colname="col3" valign="top"> <p class="head"><b>Customer Journey Analytics-API</b> </p> 
    <ul> 
     <li>Sehen Sie sich alle <a href="https://developer.adobe.com/cja-apis/docs/" format="https" scope="external"> Customer Journey Analytics-APIs</a> an. </li>
      <li>Sehen Sie sich die neueste <a href="https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API" format="https" scope="external"> Customer Journey Analytics-Reporting-API</a> an. </li>
    </ul> <p class="head"> <b>Ressourcen zu Adobe Experience Platform</b> </p> 
    <ul> 
     <li><a href="https://www.adobe.com/de/experience-platform.html" format="http" scope="external"> Adobe Experience Platform</a> </li> 
     <li> <a href="https://experienceleague.adobe.com/docs/platform-learn/tutorials/overview.html?lang=de" format="https" scope="external"> Tutorials zu Adobe Experience Platform</a> </li> 
     <li><a href="https://www.adobe.io/apis/experienceplatform/home/api-reference.html" format="https" scope="external"> API-Referenz</a> </li> 
     <li><a href="https://www.adobe.com/de/experience-platform/documentation-and-developer-resources.html" format="https" scope="external"> Dokumentation und Entwicklerressourcen</a> </li>
     <li><a href="https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html" format="https" scope="external"> Kurzanleitung zur Erfassung und Verwendung von Daten aus dem herkömmlichen Adobe Analytics
     <li><a href="https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de" format="https" scope="external"> Adobe Analytics-Quell-Connector für Report Suite-Daten</a> </li>
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
