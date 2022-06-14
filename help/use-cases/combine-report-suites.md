---
title: Report Suites mit verschiedenen Schemata kombinieren
description: Erfahren Sie, wie Sie mit der Datenvorbereitung Report Suites mit verschiedenen Schemata kombinieren
source-git-commit: 02483345326180a72a71e3fc7c60ba64a5f8a9d6
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 4%

---


# Report Suites mit verschiedenen Schemas kombinieren

Die [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de) bringt Report Suite-Daten aus Adobe Analytics in Adobe Experience Platform (AEP) zur Verwendung durch AEP-Anwendungen wie Real-time Customer Data Platform und Customer Journey Analytics (CJA). Jede Report Suite, die in AEP importiert wird, wird als Datenfluss der individuellen Quellverbindung konfiguriert und jeder Datenfluss wird als Datensatz im AEP-Data Lake landet. Der Analytics Source Connector erstellt einen Datensatz pro Report Suite.

CJA-Kunden verwenden [Verbindungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=de) , um Datensätze aus dem AEP Data Lake in die Analysis Workspace von CJA zu integrieren. Wenn Sie jedoch Report Suites innerhalb einer Verbindung kombinieren, müssen Schemaunterschiede zwischen Report Suites mithilfe der von [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de) Funktionalität. Damit soll sichergestellt werden, dass Adobe Analytics-Variablen wie Props und eVars in CJA eine einheitliche Bedeutung haben.

## Schemaunterschiede zwischen Report Suites sind problematisch

Angenommen, Ihr Unternehmen möchte Daten aus zwei verschiedenen Report Suites in AEP zur Verwendung durch CJA importieren und geht davon aus, dass die Schemata für die beiden Report Suites Unterschiede aufweisen:

| Report Suite A | Report Suite B |
| --- | --- |
| eVar1 = Suchbegriff | eVar1 = Geschäftseinheit |
| eVar2 = Kundenkategorie | eVar2 = Suchbegriff |

Aus Gründen der Einfachheit sollten wir sagen, dass dies die einzigen definierten eVars für beide Report Suites sind.

Angenommen, Sie führen die folgenden Aktionen durch:

- Erstellen einer Analytics-Quellverbindung (ohne Verwendung von Data Prep), die erfasst **Report Suite A** in den AEP Data Lake als **Datensatz A**.
- Erstellen einer Analytics-Quellverbindung (ohne Verwendung von Data Prep), die erfasst **Report Suite B** in den AEP Data Lake als **Datensatz B**.
- Erstellen Sie eine [CJA-Verbindung](/help/connections/create-connection.md) aufgerufen **Alle Report Suites** , der Datensatz A und Datensatz B kombiniert.
- Erstellen Sie eine [CJA-Datenansicht](/help/data-views/create-dataview.md) aufgerufen **Globale Ansicht** , der auf der Verbindung Alle Report Suites basiert.

Ohne die Verwendung von Data Prep zur Auflösung der Schemaunterschiede zwischen Datensatz A und Datensatz B enthalten die eVars in der Datenansicht der globalen Ansicht eine Mischung aus Werten:

| Datenansicht der globalen Ansicht in CJA |
| --- |
| eVar1 => eine Mischung aus Suchbegriffen und Geschäftseinheiten |
| eVar2 => eine Mischung aus Kundenkategorien und Suchbegriffen |

Dies führt zu sinnlosen Berichten für eVar1 und eVar2:

- Die eVar enthalten eine Mischung aus Werten mit unterschiedlicher semantischer Bedeutung.
- Suchbegriffe werden zwischen eVar1 und eVar2 verteilt.
- Es ist nicht möglich, verschiedene Attributionsmodelle für die einzelnen Suchbegriffe, Geschäftseinheiten und Kundenkategorien zu verwenden.

## AEP-Datenvorbereitung verwenden, um Schemaunterschiede zwischen Report Suites zu beheben

Die Experience Platform Data Prep-Funktion ist in den Analytics Source Connector integriert und kann verwendet werden, um die im obigen Szenario beschriebenen Schemaunterschiede zu beheben. Dies führt zu eVars mit konsistenter Bedeutung in der CJA-Datenansicht. (Die unten verwendeten Benennungskonventionen können Ihren Bedürfnissen entsprechend angepasst werden.)

1. Bevor Sie die Datenflüsse für die Quellverbindung für Report Suite A und Report Suite B erstellen, [Erstellen einer benutzerdefinierten Feldergruppe](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail.) in AEP (nennen wir es **Einheitliche Felder** in unserem Beispiel), das die folgenden Felder enthält:

   | Benutzerdefinierte Feldergruppe &quot;Einheitliche Felder&quot;  |
   | --- |
   | Suchbegriff |
   | Geschäftseinheit |
   | Kundenkategorie |

1. [Neues Schema erstellen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=de) in AEP (nennen wir es **Einheitliches Schema** in unserem Beispiel.) Fügen Sie dem Schema die folgenden Feldergruppen hinzu:

   | Feldergruppen für &quot;Einheitliches Schema&quot; |
   | --- |
   | XDM-Erlebnisereignis |
   | Adobe Analytics-Erlebnisereignisvorlage |
   | Einheitliche Felder |

   Beim Erstellen des Datenflusses für die Quellverbindung für **Report Suite A** auswählen **Einheitliches Schema** zur Verwendung im Datenfluss.

1. Fügen Sie benutzerdefinierte Zuordnungen wie folgt hinzu:

   | Report Suite A Quellfeld | Zielfeld aus der Feldergruppe &quot;Einheitliche Felder&quot; |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >Der XDM-Pfad für Ihre Zielfelder hängt davon ab, wie Sie Ihre benutzerdefinierte Feldergruppe einrichten.

1. Beim Erstellen des Datenflusses für die Quellverbindung für **Report Suite B** erneut auswählen **Einheitliches Schema** zur Verwendung im Datenfluss.

   Der Workflow zeigt an, dass zwei Felder einen Konflikt mit dem Deskriptornamen aufweisen. Der Grund dafür ist, dass sich die Deskriptoren für eVar 1 und eVar 2 in Report Suite B von denen in Report Suite A unterscheiden. Wir wissen dies jedoch bereits, sodass wir den Konflikt ignorieren und benutzerdefinierte Zuordnungen wie folgt verwenden können:

   | Quellenfeld Report Suite B | Zielfeld aus der Feldergruppe &quot;Einheitliche Felder&quot; |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. Erstellen Sie jetzt eine **Alle Report Suites** Verbindung für CJA verwenden, indem Datensatz A und Datensatz B kombiniert werden.

1. Erstellen Sie eine **Globale Ansicht** Datenansicht in CJA.

   Ignorieren Sie die ursprünglichen Felder und schließen Sie nur die eVar aus der Feldergruppe &quot;Einheitliche Felder&quot;ein.

   Ansicht der globalen Daten in CJA:

   | Quellfeld | In Datenansicht einschließen? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | Nein |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Nein |
   | _\&lt;path>_.Search_term | Ja |
   | _\&lt;path>_.Customer_category  | Ja |
   | _\&lt;path>_.Business_unit | Ja |

   Sie haben nun die eVar 1 und eVar 2 aus den Quell-Report Suites drei neuen Feldern zugeordnet. Beachten Sie, dass ein weiterer Vorteil der Verwendung von Datenvorbereitung darin besteht, dass die Zielfelder jetzt auf semantisch aussagekräftigen Namen (Suchbegriff, Geschäftseinheit, Kundenkategorie) statt auf den weniger aussagekräftigen eVar (eVar1, eVar2) basieren.

   >[!NOTE]
   >
   >Die benutzerdefinierte Feldergruppe &quot;Unified Fields&quot;und die zugehörigen Feldzuordnungen können vorhandenen Analytics Source Connector-Datenflüssen und -Datensätzen jederzeit hinzugefügt werden. Dies wirkt sich jedoch nur auf künftige Daten aus.

## Mehr als nur Report Suites

Die Funktionen von Data Prep zum Kombinieren von Datensätzen mit verschiedenen Schemas gehen über Analytics Report Suites hinaus. Angenommen, Sie haben zwei Datensätze, die die folgenden Daten enthalten:

| Datensatz A = Analytics-Report Suite über Analytics Source Connector |
| --- |
| `eVar1` => Kundenkategorie |

| Datensatz B = Callcenter-Daten |
| --- |
| Some_field => Kundenkategorie |

Mithilfe der Datenvorbereitung können Sie die Kundenkategorie in eVar 1 der Analytics-Daten mit der Kundenkategorie in Some_field in den Callcenter-Daten kombinieren. Hier ist eine Möglichkeit, das zu tun. Auch hier kann die Namenskonvention Ihren Bedürfnissen entsprechend geändert werden.

1. Erstellen Sie eine benutzerdefinierte Feldergruppe:

   | Benutzerdefinierte Feldergruppe &quot;Kundeninformationen&quot;  |
   | --- |
   | Customer_category |

1. Erstellen Sie ein Schema in AEP. Fügen Sie dem Schema die folgenden Feldergruppen hinzu:

   | Feldergruppen für &quot;Erweitertes Schema&quot; |
   | --- | 
   | XDM-Erlebnisereignis |
   | Adobe Analytics-Erlebnisereignisvorlage |
   | Kundeninformationen |

1. Beim Erstellen des Datenflusses für **Datensatz A** auswählen **Erweitertes Schema** als Schema.

1. Fügen Sie benutzerdefinierte Zuordnungen wie folgt hinzu:

   | Datensatz Ein Quellfeld | Zielfeld aus der Feldergruppe &quot;Kundeninformationen&quot; |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. Beim Erstellen des Datenflusses für **Datensatz B** erneut auswählen **Erweitertes Schema** als Schema.

1. Fügen Sie benutzerdefinierte Zuordnungen wie folgt hinzu:

   | Quellfeld für Datensatz B | Zielfeld aus der Feldergruppe &quot;Kundeninformationen&quot; |
   | --- | --- |
   | _\&lt;path>_.Some_field | _\&lt;path>_.Customer_category |

   Erstellen Sie eine CJA-Verbindung, die Datensatz A und Datensatz B kombiniert. Erstellen Sie eine Datenansicht in CJA mithilfe der soeben erstellten CJA-Verbindung. Ignorieren Sie die ursprünglichen eVar und schließen Sie nur die Felder aus der Feldergruppe Kundeninformationen ein.

   Datenansicht in CJA:

   | Quellfeld | In Datenansicht einschließen? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | Nein |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Nein |
   | _\&lt;path>_.Customer_category | Ja |

## Datenvorbereitung vs. Komponenten-ID

Wie oben beschrieben, können Sie mit der Datenvorbereitung verschiedene Felder über mehrere Adobe Analytics Report Suites hinweg zuordnen. Dies ist in CJA hilfreich, wenn Sie Daten aus mehreren Datensätzen in einer CJA-Verbindung kombinieren möchten. Wenn Sie die Report Suites jedoch in separaten CJA-Verbindungen belassen möchten, aber ein Berichtssatz für diese Verbindungen und Datenansichten verwenden möchten, bietet eine Änderung der zugrunde liegenden Komponenten-ID in CJA eine Möglichkeit, Berichte kompatibel zu machen, selbst wenn die Schemata unterschiedlich sind. Siehe [Komponenteneinstellungen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) für weitere Informationen.

Das Ändern der Komponenten-ID ist eine Nur-CJA-Funktion und hat keine Auswirkungen auf Daten aus dem Analytics Source Connector, der an das Echtzeit-Kundenprofil und die RTCDP gesendet wird.

