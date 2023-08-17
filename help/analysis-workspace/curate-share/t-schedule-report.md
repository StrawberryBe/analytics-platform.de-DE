---
description: Versenden Sie ein Projekt aus Analysis Workspace per E-Mail oder planen Sie die Bereitstellung.
keywords: Analysis Workspace
title: Planen von Projekten
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
source-git-commit: 6f3ae14e4d34de17ed64ae30cee4611e4d6f3226
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 79%

---

# Planen von Projekten

Aus dem Arbeitsbereich **[!UICONTROL Freigeben]** können Sie Analysis Workspace-Projekte per E-Mail an ausgewählte Empfänger senden. Dateien können im CSV- oder PDF-Format gesendet werden.

## Datei jetzt senden {#now}

So senden Sie eine Datei sofort per E-Mail an die Empfänger:

1. Klicks **[!UICONTROL Freigeben] > [!UICONTROL Datei exportieren]**.
1. Geben Sie den Dateityp an:
   * [!UICONTROL **CSV**]: Wählen Sie diese Option, wenn Sie Daten in Textform benötigen.
   * [!UICONTROL **PDF**]: Wählen Sie diese Option, wenn die heruntergeladene Datei alle angezeigten (sichtbaren) Tabellen und Visualisierungen im Projekt enthalten soll.
1. (Optional) Fügen Sie eine Beschreibung hinzu, die in die E-Mail aufgenommen werden soll, um die empfangene Datei zu erklären.
1. Fügen Sie Empfänger oder Gruppen hinzu. E-Mail-Adressen können auch eingegeben werden.
1. (Nur für Kunden von Health Care Shield) Geben Sie ein Passwort an. Siehe Abschnitt „Passwortschutz für terminierte Berichte“.
1. Klicken Sie auf **[!UICONTROL Jetzt senden]**.
1. (Optional) Klicken Sie auf **[!UICONTROL Planungsoptionen anzeigen]**, um einen Zeitplan für den Versand festzulegen.

![Datei jetzt senden](assets/send-file-no-scheduling-options.JPG)

## Datei planmäßig senden {#schedule}

So senden Sie eine Datei basierend auf einem wiederkehrenden Zeitplan per E-Mail an die Empfänger:

1. Klicks **[!UICONTROL Freigeben] > [!UICONTROL Dateiexport planen]**.
1. Geben Sie den Dateityp an (CSV oder PDF).
1. (Optional) Fuegen Sie eine Beschreibung hinzu, die in der E-Mail enthalten sein wird, um die empfangene Datei zu erklären.
1. Fügen Sie Empfänger oder Gruppen hinzu. E-Mail-Adressen können auch eingegeben werden.
1. (Nur für Kunden von Health Care Shield) Geben Sie ein Passwort an. Siehe Abschnitt „Passwortschutz für terminierte Berichte“.
1. Geben Sie den Datumsbereich an, über den anhand des Zeitplans gesendet werden soll, indem Sie die Einstellungen „Start am“ und „Ende am“ ändern. Das Enddatum muss innerhalb eines Jahres ab dem Tag liegen, an dem der Zeitplan erstellt oder geändert wurde.
1. Geben Sie die Versandhäufigkeit an. Jede Häufigkeit ermöglicht unterschiedliche Anpassungen.
1. Klicken Sie auf **[!UICONTROL Planmäßig senden]**.

![](assets/send-file.JPG)

## Manager für geplante Projekte {#manager}

Geplante Analysis Workspace-Projekte können unter **[!UICONTROL Analytics] > [!UICONTROL Komponenten] > [!UICONTROL Geplante Projekte]**.

Weitere Informationen finden Sie unter [Geplante Projekte](/help/components/scheduled-projects-manager.md)

## Passwortschutz für ein geplantes Projekt {#password}

>[!NOTE]
>
>Die Option zum Kennwortschutz für ein geplantes Projekt wird nur für Customer Journey Analytics-Kunden angezeigt, die die [Gesundheitsschild](https://business.adobe.com/de/solutions/experience-cloud-for-healthcare.html) Add-On-Produkt.

Adobe verwendet das Passwort zum Verschlüsseln geplanter Projekte, unabhängig davon, ob sie im .pdf- oder .csv-Format gesendet werden.

Nachdem Ihr Unternehmen die Healthcare Shield-Produktnummer erworben und mit ihr verknüpft wurde, wird die Aufforderung zur Erstellung eines Passworts für ein geplantes Projekt unter zwei Bedingungen angezeigt:

* Wenn jemand ein neues geplantes Projekt erstellt.

* Wenn ein vorhandenes geplantes Projekt kurz vor dem Senden steht. Das aktuell geplante Projekt wird deaktiviert, bis der Passwortschutz eingerichtet ist. Der Eigentümer des geplanten Projekts erhält zu diesem Zweck eine E-Mail.

![Passwortschutz](assets/password.png)

### Passwortanforderungen

Die Passwortanforderungen entsprechen dem Adobe-Standard und schreiben mindestens acht Zeichen mit mindestens einer Zahl und einem Sonderzeichen vor.

### Passwortschutz für ein neues geplantes Projekt

1. Nachdem Sie Ihr Projekt gespeichert haben, gehen Sie zu **[!UICONTROL Freigeben]** > **[!UICONTROL Datei jetzt senden]** oder [!UICONTROL Freigeben] > **[!UICONTROL Datei planmäßig senden]**.
1. Befolgen Sie die oben stehenden Anweisungen unter [Datei jetzt senden](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=de#now) oder [Datei planmäßig senden](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html?lang=de#schedule).

### Passwortschutz für ein vorhandenes geplantes Projekt

Vor dem Zeitpunkt, für den ein Projekt geplant ist, erhält der Projekteigentümer eine E-Mail wie die folgende:

![email](assets/email-password.png)

1. Melden Sie sich wieder bei Customer Journey Analytics an.
1. Klicken Sie auf **[!UICONTROL Geplantes Projekt anzeigen]**.
1. Geben Sie in **[!UICONTROL Geplantes Projekt bearbeiten]** ein Passwort ein und bestätigen Sie es.
1. Teilen Sie (nur) den Empfängern des geplanten Projekts dieses Passwort mit.


