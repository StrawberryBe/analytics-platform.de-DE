---
description: Verwenden Sie Schnellfilter in Analysis Workspace.
title: Schnellfilter
feature: Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: 23ae3185b29b72638e5ecdb4c9cf8a0680e48d5e
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 3%

---

# Schnellfilter

Sie können innerhalb eines Projekts schnelle Filter erstellen, um die Komplexität des vollständigen [Filter Builder](/help/components/filters/create-filters.md) zu umgehen. Schnellfilter

* Gilt nur für bestimmte Projekte (Sie können dies ändern).
* Bis zu drei Regeln zulassen
* Sie dürfen keine verschachtelten Container oder sequenziellen Regeln aufnehmen.
* Arbeiten in Bedienfeldern mit mehreren Report Suites

Einen Vergleich der Möglichkeiten von Schnellfiltern mit vollständigen Komponentenlistenfiltern finden Sie unter [hier](/help/components/filters/filters-overview.md).

>[!IMPORTANT]
> Schnellfilter werden derzeit nur eingeschränkt getestet und sind noch nicht allgemein verfügbar.

## Voraussetzungen

Benutzer benötigen die Berechtigung [!UICONTROL Segmenterstellung] in [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=en#analytics-tools), um Schnellfilter erstellen zu können.

## Schnellfilter erstellen

Klicken Sie in einer Freiformtabelle auf das Symbol filter+ in der Bedienfeldüberschrift:

![](assets/quick-seg1.png)

| Einstellung | Beschreibung |
| --- | --- |
| Name | Der Standardname eines Filters ist eine Kombination der Regelnamen im Filter. Sie können den Filter in einen benutzerfreundlicheren Namen umbenennen. |
| Ein-/Ausschließen | Sie können Komponenten in Ihrer Filterdefinition entweder ein- oder ausschließen, aber nicht beides. |
| Treffer-/Besuchs-/Besucherbehälter | Schnellfilter enthalten nur einen [Filter-Container](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=de#filter-containers) , mit dem Sie eine Dimension/Metrik/einen Datumsbereich in den Filter einbeziehen (oder ihn daraus ausschließen) können.  Besucher enthält übergreifende Daten, die für den Besucher über Besuche und Seitenansichten hinweg spezifisch sind. Mit einem [!UICONTROL Besuchsbehälter] können Sie Regeln festlegen, mit denen die Besucherdaten auf der Grundlage von Besuchen aufgeschlüsselt werden, und einen [!UICONTROL Trefferbehälter] , mit dem die Besucherinformationen auf der Grundlage einzelner Seitenansichten aufgeschlüsselt werden. Der Standardcontainer ist [!UICONTROL Hit]. |
| Komponenten (Dimension/Metrik/Datumsbereich) | Definieren Sie bis zu 3 Regeln, indem Sie Dimensionen und/oder Metriken und/oder Datumsbereiche und deren Werte hinzufügen. Es gibt 3 Möglichkeiten, die richtige Komponente zu finden:<ul><li>Beginnen Sie mit der Eingabe und der [!UICONTROL Schnellfilter]-Builder findet automatisch die entsprechende Komponente.</li><li>Verwenden Sie die Dropdownliste, um die Komponente zu finden.</li><li>Ziehen Sie Komponenten per Drag-and-Drop aus der linken Leiste.</li></ul> |
| Operator | Verwenden Sie das Dropdown-Menü, um Standardoperatoren und [!UICONTROL Unique Count]-Operatoren zu finden. [Weitere Infos](https://experienceleague.adobe.com/docs/analytics/components/filteration/segment-reference/seg-operators.html?lang=en) |
| Pluszeichen (+) | Eine weitere Regel hinzufügen |
| UND/ODER-Kennzahlen | Sie können den Regeln &quot;AND&quot;- oder &quot;OR&quot;-Kennungen hinzufügen, aber &quot;AND&quot;- und &quot;OR&quot;-Werte können nicht in einer einzigen Filterdefinition gemischt werden. |
| Übernehmen | Wenden Sie diesen Filter auf das Bedienfeld an. Wenn der Filter keine Daten enthält, werden Sie gefragt, ob Sie fortfahren möchten. |
| Builder öffnen | Öffnet den Filtergenerator. Nachdem Sie den Filter im Filtergenerator gespeichert haben, wird er nicht mehr als &quot;Schnellfilter&quot;betrachtet. Sie wird Teil der Komponentenlisten-Filterbibliothek. |
| Abbrechen | Abbrechen Sie diesen Schnellfilter - wenden Sie ihn nicht an. |
| Datumsbereich | Der Validator verwendet den Datumsbereich des Bedienfelds für die Datensuche. Jeder Datumsbereich, der in einem Schnellfilter angewendet wird, überschreibt jedoch den Datumsbereich des Bedienfelds oben im Bedienfeld. |
| Vorschau (oben rechts) | Hiermit können Sie sehen, ob Sie über einen gültigen Filter verfügen und wie breit der Filter ist. Stellt die Aufschlüsselung des Datensatzes dar, den Sie bei Anwendung dieses Filters erwarten können. Sie erhalten möglicherweise einen Hinweis, der anzeigt, dass dieser Filter keine Daten enthält. Sie können die Filterdefinition fortsetzen oder ändern. |

Im Folgenden finden Sie ein Beispiel für einen Filter, der Dimensionen und Metriken kombiniert:

![](assets/quick-seg2.png)

Der Filter wird oben angezeigt. Die Seitenleiste mit blauen Streifen ist im Gegensatz zur blauen Seitenleiste für Filter auf Komponentenebene in der Filterbibliothek auf der linken Seite sichtbar.

![](assets/quick-seg3.png)

## Schnellfilter bearbeiten

1. Bewegen Sie den Mauszeiger über den Schnellfilter und wählen Sie das Stiftsymbol aus.
1. Bearbeiten Sie die Filterdefinition oder den Filternamen.

## Schnellfilter speichern

Sie können Schnellfilter entweder im [!UICONTROL Schnellfilteraufbau] oder im [!UICONTROL Filtergenerator] speichern.

>[!IMPORTANT]
>Nachdem Sie den Filter gespeichert oder angewendet haben, können Sie ihn nicht mehr im Schnellfilteraufbau, sondern nur im regulären Filtergenerator bearbeiten.

### Speichern im Schnellfilter-Builder

1. Sobald Sie den Schnellfilter angewendet haben, halten Sie den Mauszeiger darüber und wählen Sie das Infosymbol (&quot;i&quot;) aus.
1. Klicken Sie auf **[!UICONTROL Verfügbar machen für alle Projekte und fügen Sie Ihrer Komponentenliste]** hinzu.
1. (Optional) Benennen Sie den Filter um.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

Beachten Sie, dass sich die Seitenleiste des Filters von gestreiftem Blau in Blau ändert. Er wird jetzt in der Komponentenliste in der linken Leiste angezeigt.

### Im Filter Builder speichern

1. Bewegen Sie den Mauszeiger über den Schnellfilter und wählen Sie das Infosymbol (&quot;i&quot;) aus.
1. Wählen Sie **[!UICONTROL Filter speichern]**
1. Belassen Sie den Namen unverändert oder benennen Sie den Filter um.

   Gehen Sie zurück zu Workspace und sehen Sie, wie der Filter jetzt über eine blaue Seitenleiste verfügt. Dies bedeutet, dass sie nicht mehr im Schnellfilteraufbau bearbeitet/geöffnet werden kann. Und durch Speichern wird sie Teil der Komponentenliste.

   ![](assets/quick-seg4.png)

Nachdem Sie den Filter angewendet haben, können Sie ihn Ihrer Liste der Filterkomponenten hinzufügen und für alle Ihre Projekte verfügbar machen.

1. Bewegen Sie den Mauszeiger über den gespeicherten Filter und wählen Sie das Stiftsymbol aus.

1. Beachten Sie dieses Dialogfeld oben im Filtergenerator:

   ![](assets/project-only.png)

1. Aktivieren Sie das Kontrollkästchen neben **[!UICONTROL Alle Projekte verfügbar machen und zur Komponentenliste hinzufügen.]**
1. Klicken Sie auf **[!UICONTROL Speichern]**.
1. Der Filter wird jetzt in der Liste der Filterkomponenten für alle Ihre Projekte angezeigt.
1. Sie können auch [den Filter](/help/components/filters/manage-filters.md) für andere Personen in Ihrer Organisation freigeben.

## Was sind reine Projektfilter?

Nur-Projekt-Filter sind entweder Schnellfilter oder Ad-hoc-Workspace-Projektfilter. Beim Bearbeiten/Öffnen in [!UICONTROL Filter Builder] wird das Feld &quot;Nur Projekt&quot;angezeigt. Wenn Sie einen Schnellfilter im Builder anwenden, aber das Kontrollkästchen &quot;Verfügbar machen&quot;nicht aktivieren, ist dieser Filter weiterhin nur ein Projekt, kann jedoch nicht mehr im [!UICONTROL Schnellfilteraufbau] geöffnet werden. Wenn Sie das Kontrollkästchen aktivieren und auf **[!UICONTROL SAVE]** klicken, handelt es sich jetzt um einen Filter für die Komponentenliste.
