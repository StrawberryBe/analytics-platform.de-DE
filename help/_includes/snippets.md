---
source-git-commit: c202effa3b25b1703cad38975786252637291b48
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 55%

---
# Snippets

## Eingeschränkte Testphase der Veröffentlichung {#release-limited-testing}

>[!AVAILABILITY]
>
>Die in diesem Artikel beschriebene Funktion befindet sich in der eingeschränkten Testphase der Version und ist möglicherweise noch nicht in Ihrer Umgebung verfügbar. Diese Anmerkung wird entfernt, wenn die Funktion allgemein verfügbar ist. Informationen zum Analytics-Veröffentlichungsprozess finden Sie unter [Veröffentlichung von Funktionen für Customer Journey Analytics](/help/release-notes/releases.md).

## Abschnitt zur eingeschränkten Testphase der Veröffentlichung {#release-limited-testing-section}

>[!AVAILABILITY]
>
>Die in diesem Abschnitt beschriebene Funktion befindet sich in der eingeschränkten Testphase der Version und ist möglicherweise noch nicht in Ihrer Umgebung verfügbar. Diese Anmerkung wird entfernt, wenn die Funktion allgemein verfügbar ist. Informationen zum Analytics-Veröffentlichungsprozess finden Sie unter [Veröffentlichung von Funktionen für Customer Journey Analytics](/help/release-notes/releases.md).

## Filterkriterien für Datenwörterbuch {#dd-filter-criteria}

1. (Optional) Wählen Sie das Symbol **Filter** ![Datenwörterbuchfilter-Symbol](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png) und wählen Sie dann eine der folgenden Filteroptionen, um die Liste der Komponenten zu filtern:

   | Option | Funktion |
   |---------|----------|
   | [!UICONTROL **Genehmigt**] | Nur Komponenten anzeigen, die von Admins als genehmigt markiert wurden. |
   | [!UICONTROL **Favoriten**] | Nur Komponenten anzeigen, die sich in Ihrer Favoritenliste befinden. Informationen zum Hinzufügen von Komponenten zur Favoritenliste finden Sie unter [Komponentenübersicht](/help/components/overview.md). |
   | [!UICONTROL **Dimensionen**] | Nur Komponenten anzeigen, die Dimensionen sind. (Diese Option ist auch auf der Registerkarte [!UICONTROL **Schnellfilter**] verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) |
   | [!UICONTROL **Metriken**] | Nur Komponenten anzeigen, die Metriken sind. (Diese Option ist auch auf der Registerkarte [!UICONTROL **Schnellfilter**] verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) |
   | [!UICONTROL **Filter**] | Nur Komponenten anzeigen, die Filter sind. (Diese Option ist auch auf der Registerkarte [!UICONTROL **Schnellfilter**] verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) <!--this is Filters in CJA--> |
   | [!UICONTROL **Datumsbereiche**] | Zeigt nur Komponenten an, die Datumsbereiche sind. (Diese Option ist auch auf der Registerkarte [!UICONTROL **Schnellfilter**] verfügbar, wenn Sie das Datenwörterbuch zum ersten Mal aufrufen.) |
   | [!UICONTROL **Alle anzeigen**] | Alle Komponenten anzeigen. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Nicht genehmigt**] | Nur Komponenten anzeigen, die noch nicht von einem Administrator als genehmigt gekennzeichnet wurden. Als Administrator ist dies hilfreich, wenn Sie Komponenten identifizieren, die Ihre Überprüfung und Genehmigung erfordern. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Fehlende Beschreibung**] | Nur Komponenten anzeigen, die noch keine Beschreibung im Feld „Beschreibung“ haben. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Duplikate anzeigen**] | Nur Komponenten anzeigen, die in der ausgewählten Report Suite denselben Namen oder dieselbe Beschreibung wie eine andere Komponente haben. Dazu gehören Komponenten, die Sie erstellen, sowie Komponenten, die von Adobe bereitgestellt werden. Namen oder Beschreibungen müssen exakt übereinstimmen, damit sie als Duplikate angezeigt werden. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Keine aktuellen Daten**] | Nur Komponenten anzeigen, die in den letzten 90 Tagen keine Daten erfasst haben. Diese Option steht nur Admins zur Verfügung. |
   | [!UICONTROL **Erstellt von Adobe**] <!-- I don't see this option--> | Nur Komponenten anzeigen, die von Adobe erstellt wurden. Komponenten, die von Admins oder anderen Benutzenden in deren Organisation erstellt wurden, werden nicht angezeigt. |

   {style="table-layout:auto"}

## Komponenteninformationen für Datenwörterbuch {#dd-component-information}

| Option | Funktion |
|---------|----------|
| [!UICONTROL **Genehmigt**] | <p>Zeigt an, dass die Komponente vom Admins geprüft und genehmigt wurde.</p><p>Administratoren erhalten eine Option zum [!UICONTROL **Nicht genehmigen**]. Wenn Sie diese Option auswählen, wird die Komponente für Benutzer als &quot;Nicht genehmigt&quot;gekennzeichnet.</p> |
| [!UICONTROL **Nicht genehmigt**] | <p>Gibt an, dass die Komponente noch nicht vom Administrator überprüft und genehmigt wurde.</p><p>Administratoren erhalten eine Option zum [!UICONTROL **Genehmigen**]. Wenn Sie diese Option auswählen, wird die Komponente Benutzern als &quot;Genehmigt&quot;gekennzeichnet.</p> |
| [!UICONTROL **Beschreibung**] | Beschreibt die beabsichtigte Funktion der Komponente. (Diese Informationen werden vom Analytics-Admins hinzugefügt, wie unter [Komponentenbeschreibungen hinzufügen](/help/components/add-component-descriptions.md) beschrieben.) |
| [!UICONTROL **Häufig verwendet mit**] | <p>Zeigt Komponenten an, die am häufigsten mit der Komponente verwendet werden, die Sie anzeigen.</p><p>Bis zu 5 Komponenten werden für die fünf primären Komponententypen angezeigt: Metrik, berechnete Metrik, Dimension, Filter und Datumsbereich.</p><p>Diese Liste basiert auf Daten aus den letzten 90 Tagen. Es werden nur Komponenten angezeigt, auf die Sie Zugriff haben.</p><p>Administratoren können die Komponenten, die Benutzer in diesem Abschnitt sehen, kuratieren, indem sie die gewünschten Komponenten im [!UICONTROL **Immer einschließen**] und [!UICONTROL **Immer ausschließen**] Dropdown-Felder. Bevor Sie die Komponenten kuratieren, die Benutzern angezeigt werden, wenden Sie zunächst die **Alle anzeigen** zu filtern, um sicherzustellen, dass Sie alle Komponenten sehen, die nicht für Sie freigegeben sind und die möglicherweise von einem anderen Administrator hinzugefügt wurden.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Ähnlich wie**] | <p>Zeigt Komponenten mit ähnlichen Namen wie die angezeigte Komponente an.</p><p>Bis zu 5 Komponenten werden für die fünf primären Komponententypen angezeigt: Metrik, berechnete Metrik, Dimension, Filter und Datumsbereich.</p><p>Es werden nur Komponenten angezeigt, auf die Sie Zugriff haben.</p><p>Hier werden alle doppelten Komponenten in Ihrer Report Suite angezeigt. Analytics-Administratoren sollten alle doppelten Komponenten identifizieren und entfernen, wie unter [Überwachen des Zustands von Datenwörterbüchern](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administratoren können die Komponenten, die Benutzer in diesem Abschnitt sehen, kuratieren, indem sie die gewünschten Komponenten im [!UICONTROL **Immer einschließen**] und [!UICONTROL **Immer ausschließen**] Dropdown-Felder. Bevor Sie die Komponenten kuratieren, die Benutzern angezeigt werden, wenden Sie zunächst die **Alle anzeigen** zu filtern, um sicherzustellen, dass Sie alle Komponenten sehen, die nicht für Sie freigegeben sind und die möglicherweise von einem anderen Administrator hinzugefügt wurden.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**HINWEIS:** Derzeit wird die **Ähnlich wie** enthält nur von Ihnen erstellte Komponenten und nicht die von Adobe bereitgestellten Komponenten. Adobe-bereitgestellte Komponenten werden in einer zukünftigen Version hinzugefügt.</p> |
| [!UICONTROL **Tags**] | Zeigt alle Tags an, die auf die Komponente angewendet werden. Benutzende mit Adminrechten können bei der Bearbeitung der Komponente Tags hinzufügen. |
| [!UICONTROL **Typ der Komponente**] | Listet den Komponententyp auf, der es ist, unabhängig davon, ob es sich um eine Dimension, eine Metrik, einen Filter oder einen Datumsbereich handelt. |
| [!UICONTROL **Erstellt von**] | Zeigt den Namen der Person an, die die Komponente erstellt hat. |
| [!UICONTROL **Vorschau**] | Zeigt eine Vorschau davon an, wie die Komponente im Analysis Workspace aussieht. |
| [!UICONTROL **Datum der letzten Änderung**] | Zeigt den Tag an, an dem die Komponente zuletzt geändert wurde. Dieser Abschnitt wird beim Anzeigen von Filtern, Metriken, berechneten Metriken und Datumsbereichen angezeigt. |

{style="table-layout:auto"}