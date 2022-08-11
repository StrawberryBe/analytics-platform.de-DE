---
title: Anwendungsfälle für Datenansichten in Customer Journey Analytics
description: Mehrere Anwendungsfälle, die die Flexibilität und Leistungsfähigkeit von Datenansichten in Customer Journey Analytics zeigen
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 684918af270a77355b7cefab4ae2e32720a71cae
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 87%

---

# Anwendungsfälle von Datenansichten

Diese Anwendungsfälle zeigen die Flexibilität und Leistungsfähigkeit von Datenansichten in Customer Journey Analytics.

## 1. Erstellen Sie eine Metrik aus einem Zeichenfolgen-Schemafeld {#string}

Wenn Sie beispielsweise eine Datenansicht erstellen, können Sie eine Metrik [!UICONTROL Bestellungen] aus einem Schemafeld [!UICONTROL pageTitle] erstellen, das eine Zeichenfolge ist. Hierzu sind folgende Schritte notwendig:

1. Ziehen Sie auf der Registerkarte „Komponenten“ den Abschnitt [!UICONTROL pageTitle] in den Abschnitt [!UICONTROL Metriken] unter [!UICONTROL Eingeschlossene Komponenten].
   ![](assets/use-case1a.png)
1. Markieren Sie nun die Metrik, die Sie gerade in den Bereich gezogen haben, und benennen Sie sie unter [!UICONTROL Komponenteneinstellungen] auf der rechten Seite um:
   ![](assets/orders.png)
1. Öffnen Sie das Dialogfeld [!UICONTROL Werte einschließen/ausschließen] auf der rechten Seite und geben Sie Folgendes an:
   ![](assets/orders2.png)

   Der Zusatz „Bestätigung“ gibt an, dass es sich um eine Bestellung handelt. Nach Überprüfung aller Seitentitel, bei denen diese Kriterien erfüllt sind, wird für jede Instanz „1“ gezählt. Das Ergebnis ist eine neue Metrik (keine berechnete Metrik). Eine Metrik mit eingeschlossenen/ausgeschlossenen Werten kann überall dort verwendet werden, wo auch jede andere Metrik eingesetzt werden kann. Sie funktioniert mit Attribution IQ, Filtern und überall sonst, wo Sie Standardmetriken verwenden können.
1. Sie können darüber hinaus ein Zuordnungsmodell für diese Metrik angeben, beispielsweise [!UICONTROL Letztkontakt] mit einem [!UICONTROL Lookback-Fenster] von [!UICONTROL Sitzung].
Sie können auch eine weitere Metrik [!UICONTROL Bestellungen] aus demselben Feld erstellen und dafür ein anderes Zuordnungsmodell festlegen, beispielsweise [!UICONTROL Erstkontakt], und ein anderes [!UICONTROL Lookback-Fenster], beispielsweise [!UICONTROL 30 Tage].

Ein weiteres Beispiel wäre die Verwendung der Besucher-ID, also einer Dimension, als Metrik zur Bestimmung der Anzahl der Besucher-IDs in Ihrem Unternehmen.

## 2. Verwenden Sie Ganzzahlen als Dimensionen {#integers}

Zuvor wurden Ganzzahlen in Customer Journey Analytics automatisch als Metriken behandelt. Jetzt können numerische Zeichen (einschließlich benutzerdefinierter Ereignisse aus Adobe Analytics) als Dimensionen behandelt werden. Siehe folgendes Beispiel:

1. Ziehen Sie die Ganzzahl [!UICONTROL call_length_min] in den Abschnitt [!UICONTROL Dimensionen] unter [!UICONTROL Eingeschlossene Komponenten]:

   ![](assets/integers.png)

1. Sie können jetzt [!UICONTROL Wertgruppierung] hinzufügen, um diese Dimension in Berichten in zusammengefasster Form darzustellen. (Ohne Gruppierung würde jede Instanz dieser Dimension als Zeilenelement im Arbeitsbereich-Reporting angezeigt.)

   ![](assets/bucketing.png)

## 3. Verwenden Sie numerische Dimensionen als „Metriken“ in Flussdiagrammen {#numeric}

Sie können eine numerische Dimension verwenden, um „Metriken“ in Ihre [!UICONTROL Fluss]-Visualisierung zu übertragen.

1. Ziehen Sie auf der Registerkarte [Komponenten](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=de#configure-component-settings) der Datenansichten das Schemafeld [!UICONTROL Marketing-Kanäle] in den Bereich [!UICONTROL Metriken] unter [!UICONTROL Eingeschlossene Komponenten].
2. In Arbeitsbereich-Berichten zeigt dieser Fluss [!UICONTROL Marketing-Kanäle], die in [!UICONTROL Bestellungen] fließen:

![](assets/flow.png)

## 4. Unterereignisfilterung durchführen {#sub-event}

Diese Funktion gilt speziell für Array-basierte Felder. Die Einschluss-/Ausschlussfunktion ermöglicht das Filtern auf Ebene der Unterereignisse, während im Filter Builder erstellte Filter (Segmente) nur die Filterung auf Ereignisebene erlauben. So können Sie die Filterung von Unterereignissen durchführen, indem Sie Einschließen/Ausschließen in Datenansichten verwenden und dann auf der Ereignisebene in einem Filter auf diese neue Metrik/Dimension verweisen.

Verwenden Sie beispielsweise die Ein-/Ausschlussfunktion in Datenansichten, um sich nur auf Produkte zu konzentrieren, die einen Umsatz von mehr als 50 Dollar generiert haben. Wenn Sie also eine Bestellung haben, die einen 50-Dollar-Produktkauf und einen 25-Dollar-Produktkauf beinhaltet, würden wir nur den 25-Dollar-Produktkauf entfernen, nicht die gesamte Bestellung.

1. Ziehen Sie auf der Registerkarte [Komponenten](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html#configure-component-settings) der Datenansichten das Schema [!UICONTROL Umsatz] in den Bereich [!UICONTROL Metriken] unter [!UICONTROL Eingeschlossene Komponenten].
1. Wählen Sie die Metrik aus und konfigurieren Sie rechts Folgendes:
a. Wählen Sie unter [!UICONTROL Format] die Option [!UICONTROL Währung] aus.
b. Wählen Sie unter [!UICONTROL Währung] die Option „USD“ aus.
c. Aktivieren Sie unter [!UICONTROL Werte einschließen/ausschließen] das Kontrollkästchen neben [!UICONTROL Ein-/Ausschlusswerte festlegen].
d. Wählen Sie unter [!UICONTROL Match] die Option [!UICONTROL Wenn alle Kriterien erfüllt sind].
e. Wählen Sie unter [!UICONTROL Kriterien] die Option [!UICONTROL ist größer oder gleich] aus.
f. Geben Sie als Wert „50“ an.

Mit diesen neuen Einstellungen können Sie nur Umsätze mit höheren Werten anzeigen und alles unter 50 Dollar herausfiltern.

## 5. Verwenden Sie die Einstellung [!UICONTROL Keine Wertoptionen] {#no-value}

Ihr Unternehmen hat vielleicht Zeit damit verbracht, Ihre Benutzer dahingehend zu schulen, dass sie in Berichten „Nicht angegeben“ erwarten. Der Standardwert in Datenansichten ist „Kein Wert“. Sie können in der Benutzeroberfläche für Datenansichten jetzt [„Kein Wert“ in „Nicht angegeben“ umbenennen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=de#configure-no-value-options-settings).

Ein weiteres Beispiel wäre eine Dimension für die Registrierung eines Abonnementprogramms. In diesem Fall können Sie „Kein Wert“ in „Keine Registrierung für ein Abonnementprogramm“ umbenennen.

## 6. Erstellen Sie mehrere Metriken mit unterschiedlichen Einstellungen für die [!UICONTROL Attribution] {#attribution}

Erstellen Sie dazu mithilfe der Funktion [!UICONTROL Duplizieren] oben rechts eine Reihe von Umsatzmetriken mit verschiedenen Attributionseinstellungen wie [!UICONTROL Erstkontakt], [!UICONTROL Letztkontakt] und [!UICONTROL Algorithmisch].

Vergessen Sie nicht, jeder Metrik einen neuen Namen zu geben, um die Unterschiede widerzuspiegeln, z. B. „Algorithmischer Umsatz“:

![](assets/algo-revenue.png)

Weitere Informationen zu anderen Datenansicht-Einstellungen finden Sie unter [Erstellen von Datenansichten](/help/data-views/create-dataview.md).
Eine konzeptionelle Übersicht über die Datenansichten finden Sie unter [Übersicht über Datenansichten](/help/data-views/data-views.md).

## 7. Reporting über neue und wiederholte Sitzungen {#new-repeat}

Sie können anhand des Berichtszeitraums, den Sie für diese Datenansicht definiert haben, und eines 13-monatigen Lookback-Fensters bestimmen, ob eine Sitzung tatsächlich die erste Sitzung für einen Benutzer ist oder nicht. Diese Berichterstellung ermöglicht Ihnen beispielsweise, Folgendes zu bestimmen:

* Welcher Prozentsatz Ihrer Bestellungen stammt aus neuen bzw. wiederholten Sitzungen?

* Richten Sie sich bei einem bestimmten Marketing-Kanal oder einer bestimmten Kampagne an Erstnutzende oder an Menschen, die wiedergekommen sind? Wie haben diese Entscheidungen die Konversionsraten beeinflusst?

Drei Komponenten erleichtern diese Berichterstellung:

* 1 Dimension: [Sitzungstyp](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=de#optional) – Diese Dimension hat zwei Werte: 1) [!UICONTROL Neu] und 2) [!UICONTROL Wiederkehrend]. Der Zeileneintrag [!UICONTROL Neu] enthält das gesamte Verhalten (d. h. die Metriken für diese Dimension) einer Sitzung, die als erste Sitzung einer Person definiert wurde. Alles andere ist im Zeileneintrag [!UICONTROL Wiederkehrend] enthalten (vorausgesetzt, dass alles zu einer Sitzung gehört). Wenn Metriken nicht Teil einer Sitzung sind, fallen sie in den Bucket „Nicht zutreffend“ für diese Dimension.

* 2 Metriken: [Neue Sitzungen, Rückkehrsitzungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=en#optional). Eine neue Sitzung wird als die erste Sitzung einer Person im Berichtszeitraum definiert. Rückkehrsitzungen ist die Anzahl der Sitzungen, die nicht die erste Sitzung einer Person waren.

So greifen Sie auf diese Komponenten zu:

1. Wechseln Sie zum Datenansichts-Editor.
1. Klicken Sie in der linken Leiste auf **[!UICONTROL Komponenten]** > **[!UICONTROL Optionale Standardkomponenten]**.
1. Ziehen Sie diese Komponenten in Ihre Datenansicht.

95 % bis 99 % der Zeit, werden neue Sitzungen korrekt berichtet. Die einzigen Ausnahmen sind:

* Wenn eine erste Sitzung vor dem 13-monatigen Lookback-Fenster stattgefunden hat. Diese Sitzung wird ignoriert.

* Wenn eine Sitzung sowohl das Lookback-Fenster als auch den Berichtszeitraum umfasst. Nehmen wir an, Sie führen einen Bericht vom 1. Juni bis zum 15. Juni 2022 durch. Das Lookback-Fenster würde die Zeit vom 1. Mai 2021 bis zum 31. Mai 2022 umfassen. Wenn eine Sitzung am 30. Mai 2022 beginnen und am 1. Juni 2022 enden sollte, werden alle Sitzungen im Berichtsfenster als Rückkehrsitzungen gezählt, da die Sitzung im Lookback-Fenster enthalten ist.

## Verwenden der Funktion Datum und Uhrzeit {#date}

>[!NOTE]
>
>Diese Funktion wird derzeit [eingeschränkt getestet](/help/release-notes/releases.md).

Beispielhafte Anwendungsfälle:

* Datum: Ein Reiseunternehmen erfasst in seinen Daten das Abreisedatum für Reisen als Feld. Sie möchten einen Bericht zum Vergleich der [!UICONTROL Wochentag] für alle Abreisedaten, um zu verstehen, welche am beliebtesten ist. Sie möchten dasselbe tun für [!UICONTROL Monat des Jahres].

* Date-Time: Ein Einzelhandelsunternehmen sammelt die Zeit für jeden seiner Einkäufe an Verkaufsstellen im Geschäft (POS). Über einen bestimmten Monat hinweg möchten sie die geschäftigsten Einkaufszeiten nachvollziehen, indem sie [!UICONTROL Stunde des Tages].

>[!MORELIKETHIS]
>[Datum und Uhrzeit in der Komponenteneinstellung &quot;Format&quot;](/help/data-views/component-settings/format.md)

