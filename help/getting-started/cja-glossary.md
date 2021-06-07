---
title: Glossar zu Customer Journey Analytics
description: Glossar zu Customer Journey Analytics.
exl-id: 7f8aac93-0103-4ead-b25b-3d9994a271af
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 95%

---

# Glossar zu Customer Journey Analytics

Einige Begriffe in Customer Journey Analytics weichen von der bisherigen Verwendung in Adobe Analytics ab:

| Neuer Begriff in Customer Journey Analytics | Begriff in Adobe Analytics | Beschreibung |
|---|---|---|
| Lookup-Datensatz | Klassifizierung | Mit „Lookup“ können Sie den Wert eines bestimmten Datensatzes anhand eines Schlüssels/übereinstimmenden Schlüssels (in einem Ereignisdatensatz) abrufen, wenn eine Eins-zu-Eins-Beziehung vorliegt. So können Sie z. B. „tracking_code“ als den mit „tracking_code“ im Ereignis-Datensatz übereinstimmenden Schlüssel angeben. |
| Profildatensatz | Kundenattribut | Wenn Sie Daten von Unternehmenskunden in einer CRM-Datenbank (CRM = Customer Relationship Management) erfassen, können Sie diese Daten in einen Profildatensatz in Adobe Experience Platform hochladen. Nachdem Sie eine Verbindung zu diesem Datensatz in Customer Journey Analytics hergestellt und eine Datenansicht erstellt haben, können Sie die Daten in Workspace nutzen. |
| Anmeldeunternehmen | Experience Cloud-Organisation | Siehe [Organisationen und Kontoverknüpfung](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#topic_C31CB834F109465A82ED57FF0563B3F1). |
| nicht angegeben | Report Suite | Report Suites im traditionellen Sinne von Adobe Analytics existieren nicht mehr. Stattdessen erstellen Sie (virtuelle) [Datenansichten](/help/data-views/create-dataview.md) aus den Platform-Datensätzen, mit denen Sie Verbindungen hergestellt haben. |
| Filter | Segment | Segmente sind jetzt Filter. Filter in Customer Journey Analytics verhalten sich wie Segmente. Nur die Terminologie wurde geändert. |
| Datenansicht | Virtual Report Suite | In Adobe Analytics ist eine Virtual Report Suite eine gefilterte Ansicht einer übergeordneten Report Suite. Der Hauptunterschied zwischen einer Virtual Report Suite und einer Datenansicht in CJA besteht darin, dass die Virtual Report Suite eine Untergruppe einer „Basis“- oder „übergeordneten“ Report Suite ist und daher einige ihrer Einstellungen übernimmt. Da es keine übergeordneten/Basis-Report Suites mehr gibt, definieren Sie Datenansichten mit ihren eigenen Einstellungen. |

## Glossar zu Adobe Experience Platform

In Adobe Experience Platform werden die Daten und Inhalte im gesamten Unternehmen standardisiert. Damit werden Echtzeitprofile für Verbraucher und Datenwissenschaft ermöglicht und Content Velocity beschleunigt, um die Personalisierung von Erlebnissen während der gesamten Customer Journey voranzutreiben.
Weitere Informationen finden Sie im [Glossar zu Adobe Experience Platform](https://docs.adobe.com/content/help/de-DE/experience-platform/landing/glossary.html).
