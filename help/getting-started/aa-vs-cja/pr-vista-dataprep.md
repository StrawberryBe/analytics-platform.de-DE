---
title: Verarbeitungsregeln, VISTA und Klassifizierungen vs. Datenvorbereitung für den Analytics Source Connector
description: Erfahren Sie mehr über die Datenumwandlung mithilfe von Verarbeitungsregeln und VISTA im Vergleich zur Datenvorbereitung.
source-git-commit: f6b8c5f1e8e82d0eb856b5cfed63b72c7ecfe3db
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 6%

---


# Verarbeitungsregeln, VISTA und Classifications versus Datenvorbereitung

Adobe Analytics [Verarbeitungsregeln und VISTA-Regeln](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) stellt eine Möglichkeit bereit, Daten, die an Adobe Analytics übergeben werden, umzuwandeln und zu bearbeiten [Datenerfassung](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). Diese Transformationen werden im Rahmen der Datenverarbeitung der Adobe vorgenommen, bevor die Daten zu Berichts- und Analysezwecken in Adobe Analytics gespeichert werden.

[Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) ist ein Tool, mit dem Sie row-basierte Zuordnungen und Transformationen auf Daten anwenden können, die in [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en). Anschließend werden die Daten für Experience Platform Apps, einschließlich CJA und andere, bereitgestellt. Die Datenvorbereitung ist in viele Platform integriert [Quell-Connectoren](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en)sowie mit den [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de). Dieser Connector bietet eine Möglichkeit, Report Suite-Daten aus Adobe Analytics in Platform zu erfassen.

## Weitere Transformation mithilfe der Datenvorbereitung {#data-prep}

Daten, die von Adobe Analytics erfasst und in gespeichert werden, können entweder durch Verarbeitungsregeln oder VISTA-Regeln oder beides umgewandelt werden. Report Suites, die dann über Analytics Source Connector an Platform weitergeleitet werden, können jedoch mithilfe der Datenvorbereitung erneut umgewandelt werden. Dies kann aus verschiedenen Gründen wünschenswert sein:

* **Beheben von Schemaunterschieden zwischen Report Suites zur Verwendung in CJA und/oder RTCDP**. Beispiel: Report Suite A definiert `eVar1` als &quot;Suchbegriff&quot;und Report Suite B definiert `eVar2` als &quot;Suchbegriff&quot;. Sie können die Datenvorbereitung verwenden, um die beiden verschiedenen eVars einem gemeinsamen Feld zuzuordnen, das Daten aus beiden eVars enthält. Dies ermöglicht [Report Suites mit verschiedenen Schemas kombinieren](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) in [CJA-Verbindung](/help/connections/overview.md) oder zur Verwendung in [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=de).
* **Zuordnung `eVars` Felder zu semantisch aussagekräftigen Namen**. `eVars` und `props` über den Analytics Source Connector gelangen, werden Feldern wie _\_experience.analytics.customDimensions.eVars.eVar1_. Die Datenvorbereitung kann für die Zuordnung verwendet werden `eVar` und `prop` Felder neuen Feldern zuordnen, die aussagekräftigere Namen für Ihre Benutzer haben oder mit Namen übereinstimmen, die aus anderen Datenquellen stammen. (Dies lässt sich auch auf andere Weise erreichen, z. B. durch Umbenennen der Felder in einer [CJA-Datenansicht](/help/data-views/create-dataview.md).
* **Daten im Allgemeinen transformieren**. Die Datenvorbereitung verfügt über Hunderte von Zuordnungsfunktionen, mit denen neue Felder basierend auf den Daten, die über den Analytics Source Connector kommen, berechnet und berechnet werden können. Sie können getrennte Felder in separate Felder aufteilen. Sie können Felder kombinieren. Sie können Zeichenfolgen bearbeiten. Sie können Informationen aus einem Feld extrahieren, das auf regulären Ausdrücken basiert, und vieles mehr.

## Datenvorbereitung und -klassifizierung {#classifications}

Die Datenvorbereitung hat Crossover mit [Klassifizierungen](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=de) in bestimmten Situationen.

Beispielsweise können Sie in einem getrennten Feld mithilfe der Datenvorbereitung dieses Feld in mehrere einzelne Felder aufteilen, ohne Klassifizierungen zu verwenden. Im Allgemeinen bieten Klassifizierungen die Möglichkeit, einem Feld Metadaten hinzuzufügen, indem eine Lookup-Datei hochgeladen wird, die außerhalb des Streams eingehender Analytics-Treffer bereitgestellt wird.

Sie können beispielsweise eine Classification-Datei hochladen, in der SKUs in &quot;Größe&quot;, &quot;Marke&quot;, &quot;Farbe&quot;usw. gruppiert werden. Ein weiterer Unterschied zwischen Classifications und Data Prep besteht darin, dass Classifications für Daten gelten _sowohl historisch als auch zukünftig_. Datenvorbereitung-Zuordnungen hingegen werden angewendet _forward_ auf Daten aus dem Zeitpunkt, zu dem die Zuordnung erstellt wurde.

