---
title: Erstellen und Veröffentlichen von Zielgruppen im Echtzeit-Kundenprofil
description: Erfahren Sie, wie Sie Audiences aus Customer Journey Analytics veröffentlichen
source-git-commit: 7895342fb33118f0bbe97ce4a7adc22664adf000
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 10%

---


# Erstellen und Veröffentlichen von Zielgruppen

In diesem Thema wird beschrieben, wie Sie in Customer Journey Analytics (CJA) gefundene Zielgruppen in veröffentlichen. [Echtzeit-Kundenprofil](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=de) in Adobe Experience Platform für Kunden-Targeting und Personalisierung.

## Zielgruppe erstellen

1. Zur Erstellung von Zielgruppen haben Sie drei Möglichkeiten:

   | Erstellungsmethode | Details |
   | --- | --- |
   | Von **[!UICONTROL Komponenten] > [!UICONTROL Zielgruppen]** | Die Seite &quot;Zielgruppen-Manager&quot;wird geöffnet. Klicken **[!UICONTROL Zielgruppe erstellen]** und [!UICONTROL Audience Builder] geöffnet. |
   | Aus einer Freiformtabelle | Klicken Sie mit der rechten Maustaste auf ein Element in einer Freiformtabelle und wählen Sie **[!UICONTROL Erstellen einer Zielgruppe aus einer Auswahl]**. Mit dieser Methode wird der Filter vorab mit der Dimension oder dem Dimensionselement ausgefüllt, die bzw. das Sie in der Tabelle ausgewählt haben. |
   | In der Benutzeroberfläche zur Filterbearbeitung | Markieren Sie das Kästchen mit der Angabe **[!UICONTROL Erstellen einer Zielgruppe aus diesem Filter]**. Mit dieser Methode wird der Filter vorab ausgefüllt. |

   {style=&quot;table-layout:auto&quot;}

1. Konfigurieren Sie die Zielgruppe.

   | Einstellung | Beschreibung |
   | --- | --- |
   | [!UICONTROL Name] | Der Name der Zielgruppe. |
   | [!UICONTROL Tags] | Alle Tags, die Sie der Zielgruppe für organisatorische Zwecke zuweisen möchten. Sie können ein bereits vorhandenes Tag verwenden oder ein neues eingeben. |
   | [!UICONTROL Beschreibung] | Fügen Sie eine gute Beschreibung der Zielgruppe hinzu, um sie von anderen zu unterscheiden. |
   | [!UICONTROL Häufigkeit der Aktualisierung] | Die Häufigkeit, mit der Sie die Zielgruppe aktualisieren möchten.<ul><li>Sie können eine einmalige Zielgruppe (Standard) erstellen, die nicht aktualisiert werden muss. Dies wäre beispielsweise bei bestimmten einmaligen Kampagnen hilfreich.</li><li>Sie können auch andere Aktualisierungsintervalle auswählen. Für die 4-Stunden-Frequenz gibt es eine Beschränkung von 150 Zielgruppen, da diese Aktualisierungsrate sehr verarbeitungsintensiv ist. Für andere Intervalle gibt es keine maximale Anzahl von Zielgruppen.</li></ul> |
   | Ablaufdatum | Wann die Aktualisierung der Audience beendet wird. Der Standardwert liegt bei 1 Jahr ab dem Erstellungsdatum. |
   | Lookback-Fenster aktualisieren | Gibt an, wie weit Sie im Datenfenster bei der Erstellung dieser Audience zurückgehen möchten. Die maximale ist 90 Tage. Das Auslaufen von Zielgruppen wird ähnlich wie das Auslaufen geplanter Berichte behandelt - der Administrator erhält einen Monat vor Ablauf des Zeitplans eine E-Mail. |
   | [!UICONTROL Einmaliger Datumsbereich] | Datumsbereich, in dem die einmalige Zielgruppe veröffentlicht werden soll. |
   | [!UICONTROL Filter] | Filter sind die Haupteingaben für die Zielgruppe. Sie können bis zu 20 Filter hinzufügen. Diese Filter können mit `And` oder `Or` Operatoren. |

   {style=&quot;table-layout:auto&quot;}

1. Interpretieren Sie die Datenvorschau.

   Die Zielgruppenvorschau wird in der rechten Leiste angezeigt.

   | Vorschaueinstellung | Beschreibung |
   | --- | --- |
   | Datenvorschaufenster | Der Datumsbereich für die Zielgruppe. |
   | Personen in der Zielgruppe insgesamt | Eine Zusammenfassungszahl, die bis zu 100 Millionen betragen kann. |
   | Zielgruppen-Limit | Zeigt an, wie weit diese Zielgruppe von der Beschränkung von 100 Millionen entfernt ist. |
   | Geschätzte Zielgruppenrendite |  |
   | Voraussichtliche Rückkehr | Eine Zusammenfassungsnummer... |
   | Metriken in der Vorschau anzeigen |  |

   {style=&quot;table-layout:auto&quot;}


