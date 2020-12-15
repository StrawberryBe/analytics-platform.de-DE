---
description: Liste der Fehlermeldungen in Analysis Workspace und der zugehörigen Komponenten
title: Fehlermeldungen
translation-type: tm+mt
source-git-commit: a991dce6abaf90cbca06de75606a2517cb5b6484
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 95%

---


# Fehlermeldungen

Bei der Interaktion mit Analysis Workspace können Fehler auftreten, die auch die Leistung beeinflussen. Im Folgenden sind die häufigsten Fehlertypen, die Gründe dafür und Optimierungen aufgeführt, die vorgenommen werden können.

>[!NOTE]
>
>Dies ist die Dokumentation zu Analysis Workspace in Customer Journey Analytics. Seine Funktionen unterscheiden sich geringfügig von denen in [Analysis Workspace im herkömmlichen Adobe Analytics](https://docs.adobe.com/content/help/de-DE/analytics/analyze/analysis-workspace/home.html). [Weitere Informationen ...](/help/getting-started/cja-aa.md)

| Fehlermeldung | Grund | Optimierung |
| --- | --- | --- |
| [!UICONTROL Es ist ein Systemfehler aufgetreten. Melden Sie eine Anfrage an die Kundenunterstützung unter **[!UICONTROL Hilfe > senden Sie ein Support-Ticket]** und geben Sie Ihren Fehler-Code an.] | Adobe hat ein Problem, das behoben werden muss. | Senden Sie den Fehler-Code an die Kundenunterstützung. |
| [!UICONTROL Fehler 500: Seite konnte nicht geladen werden] | Probleme mit Ihrem lokalen Netzwerk, wie z. B. die [Firewall-Einstellungen](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=de-DE) der Firma, tragen zu diesem Fehler bei. Darüber hinaus tritt bei der Adobe möglicherweise ein Problem auf, das behoben werden muss. | Versuchen Sie nach einigen Minuten erneut sich anzumelden. Wenn das Problem weiterhin besteht, senden Sie den EIM-Instanz-ID-Code an die Kundenunterstützung. |
| [!UICONTROL Eines der Segmente oder die Suche in dieser Visualisierung enthält eine Textsuche, die zu viele Ergebnisse zurückgab.] | Ihre Segmentkriterien oder Berichtsfilter sind zu breit angelegt. | Schränken Sie die Suchtextkriterien ein und führen Sie die Anfrage erneut aus. |
| [!UICONTROL Die Report Suite verzeichnet derzeit ein ungewöhnlich hohes Aufkommen von Berichtsdaten. Versuchen Sie es später erneut.] | Ihr Unternehmen versucht, zu viele Anfragen gleichzeitig für eine bestimmte Report Suite auszuführen. Zu diesem Fehler gehören API-Anfragen, geplante Projekte, terminierte Berichte, terminierte Warnhinweise und gleichzeitige Benutzer, die Reporting-Anfragen ausführen. | Verteilen Sie Ihre Anfragen und Zeitpläne für die Report Suite gleichmäßig über den Tag. |
| [!UICONTROL Die Anfrage ist zu komplex.] | Ihre Reporting-Anfrage ist zu groß und kann nicht ausgeführt werden. Gründe für diesen Fehler sind Zeitüberschreitungen aufgrund der Anfragengröße, zu viele übereinstimmende Elemente in einem Segment oder Suchfilter, zu viele eingeschlossene Metriken, inkompatible Dimensions- und Metrikkombinationen usw. | Vereinfachen Sie Ihre Anfrage, indem Sie einige Spalten oder Zeilen in der Tabelle entfernen oder die Tabelle in separate Anfragen aufteilen. |
| [!UICONTROL Diese Dimension unterstützt nicht-standardmäßige Zuordnungsmodelle derzeit nicht.] | Nicht standardmäßige Zuordnung wird für die verwendete Dimension nicht unterstützt. | Ersetzen Sie die Dimension in Ihrer Tabelle durch eine Dimension, die mit [Attribution IQ](/help/analysis-workspace/attribution/overview.md) kompatibel ist. |
| [!UICONTROL Ihre Anfrage schlug aufgrund zu vieler Spalten oder vorkonfigurierter Zeilen fehl.] | Ihre Tabelle enthält zu viele Freiformzellen (Zeile * Spalten). | Entfernen Sie Spalten oder Zeilen in der Tabelle oder erwägen Sie, die Tabelle in separate Anfragen zu unterteilen. |