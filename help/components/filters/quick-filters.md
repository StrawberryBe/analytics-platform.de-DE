---
description: Verwenden von Schnellfiltern in Analysis Workspace für Customer Journey Analytics
title: Schnellfilter
feature: CJA Workspace Basics
role: User, Admin
exl-id: 549e5db5-fcdf-43c5-bc43-590144aee309
source-git-commit: cea2faeaf9c2779ab808506025780fd3659a94b1
workflow-type: ht
source-wordcount: '950'
ht-degree: 100%

---

# Schnellfilter

Sie können innerhalb eines Projekts Schnellfilter erstellen, um die Komplexität des vollständigen [Filtergenerators](/help/components/filters/create-filters.md) zu umgehen. Schnellfilter

* Nur anwendbar auf Projekte, in denen sie erstellt wurden (Sie können dies ändern).
* Lassen bis zu 3 Regeln zu
* Können keine verschachtelten Container oder sequenziellen Regeln aufnehmen

Einen Vergleich der Möglichkeiten von Schnellfiltern mit vollständigen Komponentenlistenfiltern finden Sie [hier](/help/components/filters/filters-overview.md).

>[!IMPORTANT]
> Schnellfilter werden derzeit nur eingeschränkt getestet und sind noch nicht allgemein verfügbar.

## Voraussetzungen

Jeder kann ein Schnellsegment erstellen. Sie benötigen jedoch die Berechtigung Segmenterstellung in [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/summary-tables.html?lang=de#analytics-tools), um die Schnellsegmente speichern oder in Segment Builder öffnen zu können.

## Erstellen von Schnellfiltern

Klicken Sie in einer Freiformtabelle auf das „+“-Symbol für den Filter im Kopf des Bedienfelds:

![Segmentfilter](assets/quick-seg1.png)

| Einstellung | Beschreibung |
| --- | --- |
| Name | Der Standardname eines Filters ist eine Kombination der Regelnamen im Filter. Sie können für den Filter einen benutzerfreundlicheren Namen wählen. |
| Ein-/Ausschließen | Sie können Komponenten in Ihrer Filterdefinition entweder ein- oder ausschließen, aber nicht beides. |
| Treffer-/Besuchs-/Besucher-Container | Schnellfilter enthalten nur einen [Filter-Container](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=de#filter-containers), mit dem Sie eine Dimension/Metrik/einen Datumsbereich in den Filter einbeziehen (oder daraus ausschließen) können. [!UICONTROL Besucher] enthält übergreifende Daten, die für den Besucher über Besuche und Seitenansichten hinweg spezifisch sind. Mit einen Container [!UICONTROL Besuch] können Sie Regeln für die Aufschlüsselung der Besucherdaten auf der Grundlage der Besuche festlegen und mit einem Container [!UICONTROL Treffer] können Sie die Besucherinformationen auf der Grundlage der einzelnen Seitenaufrufe aufschlüsseln. Der Standard-Container ist [!UICONTROL Treffer]. |
| Komponenten (Dimension/Metrik/Datumsbereich) | Definieren Sie bis zu 3 Regeln, indem Sie Komponenten (Dimensionen, Metriken, Datumsbereiche oder Dimensionswerte) hinzufügen. Es gibt 3 Möglichkeiten, die richtige Komponente zu finden:<ul><li>Beginnen Sie mit der Eingabe. Der [!UICONTROL Schnellfilter-Generator] findet automatisch die entsprechende Komponente.</li><li>Verwenden Sie die Dropdown-Liste, um die Komponente zu finden.</li><li>Per Drag-and-Drop aus der der linken Leiste ziehen.</li></ul> |
| Operator | Dropdown-Menü verwenden, um Standardoperatoren und Operatoren des Typs [!UICONTROL Distinct Count] zu finden. Siehe [Filteroperatoren](operators.md). |
| Plus (+)-Zeichen | Eine weitere Regel hinzufügen |
| AND/OR-Kriterien | Sie können den Regeln „AND“- oder „OR“-Kriterien hinzufügen, aber „AND“- und „OR“-Werte können nicht in einer Filterdefinition gemischt werden. |
| Übernehmen | Diesen Filter auf das Bedienfeld an. Wenn der Filter keine Daten enthält, werden Sie gefragt, ob Sie fortfahren möchten. |
| Builder öffnen | Zeigt den Filtergenerator an. Nachdem Sie den Filter im Filter-Builder gespeichert oder angewendet haben, wird er nicht mehr als „Schnellfilter“ betrachtet. Er wird Teil der Komponentenlisten-Filterbibliothek. |
| Abbrechen | Brechen Sie diesen Schnellfilter ab – wenden Sie ihn nicht an. |
| Datumsbereich | Der Validator verwendet den Datumsbereich des Bedienfelds für die Datensuche. Jeder Datumsbereich, der in einem Schnellfilter angewendet wird, überschreibt jedoch den Datumsbereich des Bedienfelds oben im Bedienfeld. |
| Vorschau (oben rechts) | Hiermit können Sie sehen, ob Sie über einen gültigen Filter verfügen und wie breit der Filter ist. Stellt eine Aufschlüsselung des Datensatzes dar, die Sie erwarten können, wenn Sie diesen Filter anwenden. Sie erhalten möglicherweise einen Hinweis, der anzeigt, dass dieser Filter keine Daten enthält. In diesem Fall können Sie weiterarbeiten oder aber die Filterdefinition ändern. |

Im Folgenden finden Sie ein Beispiel für einen Filter, der Dimensionen und Metriken kombiniert:

![Beispiel für eine Filterdefinition](assets/quick-seg2.png)

Der Filter wird oben angezeigt. Beachten Sie die Seitenleiste mit blauen Streifen im Gegensatz zur blauen Seitenleiste für Filter auf Komponentenebene auf der linken Seite der Filterbibliothek.

![Filtern von Komponentenstandorten](assets/quick-seg3.png)

## Bearbeiten von Schnellfiltern

1. Bewegen Sie den Mauszeiger über den Schnellfilter und wählen Sie das Stiftsymbol aus.
1. Bearbeiten Sie die Filterdefinition oder den Filternamen.

## Speichern von Schnellfiltern

Sie können Schnellfilter entweder im [!UICONTROL Schnellfilter-Generator] oder im [!UICONTROL Filtergenerator] speichern.

>[!IMPORTANT]
>Nachdem Sie den Filter gespeichert oder angewendet haben, können Sie ihn nicht mehr im Schnellfilter-Generator, sondern nur noch im regulären Filtergenerator bearbeiten.

### Speichern im Schnellfilter-Generator

1. Wenn Sie den Schnellfilter angewendet haben, halten Sie den Mauszeiger darüber und wählen Sie das Infosymbol („i“) aus.
1. Klicken Sie auf **[!UICONTROL Für alle Projekte verfügbar machen und der Komponentenliste hinzufügen]**.
1. (Optional) Benennen Sie den Filter um.
1. Klicken Sie auf **[!UICONTROL Speichern]**.

Beachten Sie, wie sich die Seitenleiste des Filters von gestreiftem Blau zu einem helleren Blau ändert. Er wird jetzt in der Komponentenliste in der linken Leiste angezeigt.

### Im Filtergenerator speichern

1. Bewegen Sie den Mauszeiger über den Schnellfilter und wählen Sie das Infosymbol („i“) aus.
1. Wählen Sie **[!UICONTROL Filter speichern]**
1. Belassen Sie den Namen unverändert oder benennen Sie den Filter um.

   Gehen Sie zurück zum Arbeitsbereich. Wie Sie sehen, verfügt der Filter jetzt über eine Seitenleiste in einem helleren Blau. Dies bedeutet, dass er nicht mehr im Schnellfilter-Generator bearbeitet/geöffnet werden kann. Und durch Speichern wird er Teil der Komponentenliste.

   ![Komponentenlisten-Filter](assets/quick-seg4.png)

Nachdem Sie den Filter angewendet haben, können Sie ihn Ihrer Liste der Filterkomponenten hinzufügen und für alle Ihre Projekte verfügbar machen.

1. Bewegen Sie den Mauszeiger über den gespeicherten Filter und wählen Sie das Stiftsymbol aus.

1. Beachten Sie dieses Dialogfeld oben im Filtergenerator:

   ![Dialog „Filter“](assets/project-only.png)

1. Aktivieren Sie das Kontrollkästchen neben **[!UICONTROL Alle Projekte verfügbar machen und der Komponentenliste hinzufügen]**.
1. Klicken Sie auf **[!UICONTROL Speichern]**.
1. Der Filter wird jetzt in der Liste der Filterkomponenten für alle Ihre Projekte angezeigt.
1. Sie können auch den Filter auch für andere Personen in Ihrer Organisation [freigeben](/help/components/filters/manage-filters.md).

## Was sind reine Projektfilter?

Reine Projektfilter sind entweder Schnellfilter oder Ad-hoc-Arbeitsbereich-Projektfilter. Beim Bearbeiten/Öffnen im [!UICONTROL Filter-Builder] wird das Feld „Nur Projekt“ angezeigt.

Wenn Sie einen Schnellfilter im Generator anwenden, aber das Kontrollkästchen „Verfügbar machen“ nicht aktivieren, ist dieser Filter weiterhin ein reiner Projektfilter, kann jedoch nicht mehr im [!UICONTROL Schnellfilter-Builder] geöffnet werden. Wenn Sie das Kontrollkästchen aktivieren und auf **[!UICONTROL Speichern]** klicken, handelt es sich ab sofort um einen Filter für die Komponentenliste.
