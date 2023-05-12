---
title: SQL Connector
description: Erfahren Sie, wie Sie mit Query Service, Power BI und/oder Tableau auf Datenansichten mit SQL Connector zugreifen können.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
badgeCJASQLConnector: label="New Feature" type="Positive"
source-git-commit: 5b84c2c908f947b1abed621f68aa1a324faeecde
workflow-type: tm+mt
source-wordcount: '2890'
ht-degree: 6%

---

# SQL Connector

{{release-limited-testing}}

Die [!DNL Customer Journey Analytics (CJA) SQL Connector] ermöglicht SQL-Zugriff auf [Datenansichten](./data-views.md) die Sie in CJA definiert haben. Ihre Dateningenieure und Analytiker sind möglicherweise besser mit Power BI, Tableau oder anderen Business Intelligence- und Visualisierungs-Tools (auch BI-Tools genannt) vertraut. Sie können jetzt Berichte und Dashboards basierend auf denselben Datenansichten erstellen, die CJA-Benutzer bei der Erstellung ihrer Analysis Workspace-Projekte verwenden.

Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=de) ist die SQL-Schnittstelle zu Daten, die im Data Lake der Experience Platform verfügbar sind. Mit dem [!DNL CJA SQL Connector] aktiviert ist, wird die Funktionalität von [!DNL Query Service] wird erweitert, um Ihre CJA-Datenansichten als Tabellen oder Ansichten in einer [!DNL Query Service] Sitzung. Daher nutzen Business-Intelligence-Tools [!DNL Query Service] da ihre PostgresSQL-Schnittstelle nahtlos von dieser erweiterten Funktion profitiert.

Die wichtigsten Vorteile sind:

- Es ist nicht erforderlich, eine äquivalente Darstellung von CJA-Datenansichten im BI-Tool selbst zu erstellen. <br/>Siehe [Datenansicht](data-views.md) für weitere Informationen zur Funktionalität von Datenansichten, um zu verstehen, was neu erstellt werden muss.<br/>

- Größere Konsistenz bei der Berichterstellung und Analyse zwischen BI-Tools und CJA.

- Kombinieren Sie CJA-Daten mit anderen Datenquellen, die bereits in BI-Tools verfügbar sind.

## Voraussetzungen 

Um diese Funktion verwenden zu können, müssen Sie

- Aktivieren Sie die [!UICONTROL CJA SQL Connector] in Ihrer Experience Platform.

- Konfigurieren Sie die Funktionalität für die relevanten Produktprofile, Benutzergruppen und/oder einzelnen Benutzer.<br/>
Benutzer müssen Zugriff auf:
   - Experience Platform Query Service,
   - CJA Workspace-Projekte und
   - CJA-Datenansichten, die sie verwenden möchten.

- Verwenden Sie das Ablaufdatum für nicht ablaufende Anmeldeinformationen, um BI-Tools mit dem CJA SQL Connector zu verbinden. Thr [Handbuch zu Anmeldeinformationen](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) enthält weitere Informationen zum Festlegen ablaufender oder nicht ablaufender Anmeldeinformationen.

Siehe [Zugriffssteuerung](../admin/cja-access-control.md) im Abschnitt CJA-Administration weitere Informationen.


## Nutzung

So verwenden Sie die [!DNL CJA SQL Connector] -Funktion verwenden, können Sie SQL entweder direkt verwenden oder das Drag-and-Drop-Erlebnis verwenden, das im jeweiligen BI-Tool verfügbar ist.

### SQL

Sie können die Funktion direkt in SQL-Anweisungen verwenden, indem Sie entweder den Abfrage-Editor oder einen standardmäßigen PostgresSQL-Befehlszeilenschnittstelle (CLI)-Client verwenden.

+++ Abfrage-Editor

In der Experience Platform-Benutzeroberfläche:

1. Auswählen **[!UICONTROL ** Abfragen **]** von **[!UICONTROL ** DATENVERWALTUNG **]** in der linken Leiste.

2. Auswählen ![Abfrage erstellen](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL ** Abfrage erstellen **]**.

3. Um die Abfrage auszuführen, geben Sie Ihre SQL-Anweisung ein und wählen Sie die ![Play](assets/Smock_Play_18_N.svg) (oder drücken Sie UMSCHALT + EINGABETASTE).

+++


+++ PostgresSQL CLI

1. Suchen Sie in der Experience Platform-Benutzeroberfläche nach Ihren PostgresSQL-Anmeldeinformationen und kopieren Sie sie:

   1. Auswählen **[!UICONTROL ** Abfragen **]** von der linken Leiste (unter **[!UICONTROL ** DATENVERWALTUNG **]**).

   2. Auswählen **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste.

   3. Um die Verbindungszeichenfolge zu kopieren, verwenden Sie ![Kopieren](assets/Smock_Copy_18_N.svg) im **[!UICONTROL ** PSQL-Befehl **]** Abschnitt.

2. Öffnen Sie Ihre PostgresSQL-CLI.

3. Um sich anzumelden und mit der Ausführung Ihrer Abfragen zu beginnen, fügen Sie die Verbindungszeichenfolge in die PostgresSQL-CLI ein.

+++

Siehe [Anleitung zur Benutzeroberfläche des Abfrage-Editors](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) für weitere Informationen.


### BI-Tools

Derzeit wird der CJA SQL Connector für Power BI und Tableau unterstützt.

+++ Power BI

1. Suchen Sie in der Adobe Experience Platform-Benutzeroberfläche nach den Details Ihrer PostgresSQL-Anmeldedaten.

   1. Auswählen **[!UICONTROL ** Abfragen **]** von der linken Leiste (unter **[!UICONTROL ** DATENVERWALTUNG **]**).

   2. Auswählen **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste.

   3. Verwendung ![Kopieren](assets/Smock_Copy_18_N.svg) zum Kopieren der einzelnen Parameter der Postgres-Anmeldedaten ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername], und andere), wenn dies im Power BI erforderlich ist.

2. Im Power BI:

   1. Wählen Sie im Hauptfenster die Option **[!UICONTROL ** Daten abrufen **]** aus der oberen Symbolleiste.

   2. Auswählen **[!UICONTROL ** Mehr ...**]** in der linken Leiste.

   3. Im **Daten abrufen** Bildschirm, suchen Sie nach `PostgresSQL` und wählen Sie die **[!UICONTROL ** PostgresSQL-Datenbank **]** aus der Liste.

   4. Im **[!UICONTROL ** PostgressSQL-Datenbank **]** dialog:

      1. Einfügen **[!UICONTROL ** Host **]** Parameter aus Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in **[!UICONTROL ** Server **]** Textfeld.

      2. Einfügen **[!UICONTROL ** Datenbank **]** Parameter aus Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in **[!UICONTROL ** Datenbank **]** Textfeld.

         Hinzufügen `?FLATTEN` der **[!UICONTROL ** Datenbank **]** -Parameter, also liest er wie `prod:all?FLATTEN` zum Beispiel. Siehe [Reduzieren verschachtelter Datenstrukturen für die Verwendung mit BI-Tools von Drittanbietern](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) für weitere Informationen.

      3. Wenn Sie dazu aufgefordert werden **[!UICONTROL ** Data Connectivity **]** mode, select **[!UICONTROL ** DirectQuery **]** , um sicherzustellen, dass die Datenstrukturen ordnungsgemäß reduziert werden.

      4. Sie werden aufgefordert, **[!UICONTROL ** Benutzername **]** und **[!UICONTROL ** Passwort **]**. Äquivalente Parameter aus Experience Platform-Abfragen verwenden [!UICONTROL Anmeldeinformationen].
   5. Nach erfolgreicher Anmeldung werden die CJA-Datenansichtstabellen im Power BI **[!UICONTROL ** Navigator **]**. Datenansichtstabellen werden anhand von `dv_` in ihren Namen.


   6. Wählen Sie die zu verwendenden Datenansichtstabellen aus und wählen Sie **[!UICONTROL ** Laden **]**.

   Alle Dimensionen und Metriken, die mit einer oder mehreren ausgewählten Tabellen verknüpft sind, werden im rechten Bereich angezeigt und können in Ihren Visualisierungen verwendet werden.

   Siehe [Power BI zu Query Service verbinden](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) für weitere Informationen.

+++

+++Tableau

1. Suchen Sie in der Experience Platform-Benutzeroberfläche nach den Details Ihrer PostgresSQL-Anmeldedaten.

   1. Auswählen **[!UICONTROL ** Abfragen **]** von der linken Leiste (unter **[!UICONTROL ** DATENVERWALTUNG **]**).

   2. Auswählen **[!UICONTROL ** Anmeldeinformationen **]** aus der oberen Leiste.

   3. Verwendung ![Kopieren](assets/Smock_Copy_18_N.svg) zum Kopieren der einzelnen Parameter der Postgres-Anmeldedaten ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Datenbank], [!UICONTROL Benutzername], und andere) bei Bedarf in Tableau.

2. In Tableau:

   1. Auswählen **[!UICONTROL ** Mehr **]** von **[!UICONTROL ** Auf einen Server **]** in der linken Leiste.

   2. Auswählen **[!UICONTROL ** PostgresSQL **]** aus der Liste.

   3. Im [!UICONTROL PostgresSQL] dialog:

      1. Einfügen **[!UICONTROL ** Host **]** Parameter aus Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in **[!UICONTROL ** Server **]** Textfeld.

      2. Einfügen **[!UICONTROL ** Port **]** Parameter aus Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in **[!UICONTROL ** Port **]** Textfeld.

      3. Einfügen **[!UICONTROL ** Datenbank **]** Parameter aus Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in **[!UICONTROL ** Datenbank **]** Textfeld.

         Hinzufügen `%3FFLATTEN` der **[!UICONTROL ** Datenbank **]** -Parameter, also liest er wie `prod:all%3FFLATTEN` zum Beispiel. Siehe [Reduzieren verschachtelter Datenstrukturen für die Verwendung mit BI-Tools von Drittanbietern](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) für weitere Informationen.

      4. Auswählen **[!UICONTROL ** Benutzername und Kennwort **]** von **[!UICONTROL ** Authentifizierung **]** Liste.

      5. Einfügen **[!UICONTROL ** Benutzername **]** Parameter aus Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in **[!UICONTROL ** Benutzername **]** Textfeld.

      6. Einfügen **[!UICONTROL ** Passwort **]** Parameter aus Experience Platform-Abfragen [!UICONTROL Anmeldeinformationen] in **[!UICONTROL ** Passwort **]** Textfeld.

      7. Auswählen **[!UICONTROL ** Anmelden **]**.
   4. CJA-Datenansichten werden als Tabellen im **[!UICONTROL ** Verzeichnis **]** Liste. Datenansichtstabellen erhalten das Präfix `dv_`.

   5. Ziehen Sie die Tabellen, die Sie verwenden möchten, auf die Arbeitsfläche.

   Sie können jetzt mit den Daten aus den Datenansichtstabellen arbeiten, um Ihre Berichte und Visualisierungen zu erstellen.

   Siehe [Verbinden von Tableau mit Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) für weitere Informationen.

+++

Siehe [Clients mit Query Service verbinden](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) für einen Überblick und weitere Informationen über die verschiedenen verfügbaren Tools.

## Funktionalität

Standardmäßig wird für Ihre Datenansichten ein tabellensicherer Name aus ihrem Anzeigenamen generiert. Beispielsweise die Datenansicht mit dem Namen [!UICONTROL Meine Webdaten] hat den Namen der Ansicht `dv_my_web_data`.

Wenn Sie die Datenansichts-IDs als Tabellennamen verwenden möchten, können Sie die optionale `CJA_USE_IDS` bei der Verbindung auf Ihren Datenbanknamen festlegen. Beispiel: `prod:all?CJA_USE_IDS` zeigt Ihre Datenansichten mit Namen wie `dv_ABC123`.

### Data Governance

Die Data Governance-bezogenen Einstellungen in Customer Journey Analytics werden von Adobe Experience Platform übernommen. Die Integration zwischen CJA und Adobe Experience Platform Data Governance ermöglicht die Kennzeichnung sensibler CJA-Daten und die Durchsetzung von Datenschutzrichtlinien.

Datenschutzbeschriftungen und -richtlinien, die für von Experience Platform genutzte Datensätze erstellt wurden, können im CJA-Datenansichts-Workflow angezeigt werden. Daher zeigen mit CJA SQL Connector abgefragte Daten geeignete Warnungen oder Fehler, wenn sie nicht den definierten Datenschutzbezeichnungen und Richtlinien entsprechen.

### Datenansichten auflisten

In der standardmäßigen PostgreSQL-CLI können Sie Ihre Ansichten mithilfe von `\dv`

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres
```

### Verschachtelt oder reduziert

Standardmäßig verwendet das Schema Ihrer Datenansichten verschachtelte Strukturen wie die ursprünglichen XDM-Schemas. Die Integration unterstützt auch die `FLATTEN` -Option. Mit dieser Option können Sie erzwingen, dass das Schema für die Datenansichten (und jede andere Tabelle in der Sitzung) reduziert wird. Die Verkürzung ermöglicht eine einfachere Verwendung in BI-Tools, die keine strukturierten Schemas unterstützen. Siehe [Arbeiten mit verschachtelten Datenstrukturen in Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) für weitere Informationen.

### Unterstützte SQL

Siehe [SQL-Referenz für Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) für die vollständige Referenz darüber, welcher SQL-Typ unterstützt wird.

Eine Übersicht über Muster und Beispiele finden Sie in der Tabelle &quot;Muster&quot;unten.

+++Muster

| Muster | Beispiel |
|---|---|
| Schemaerkennung | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Rangansicht/Aufschlüsselung | <pre>SELECT dim1, SUM(metric1) AS m1<br/>VON dv1<br/>WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;<br/>GRUPPE NACH DIME1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>VON dv1<br/>WO \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39; UND<br/>  filterId = &#39;12345&#39;<br/>GRUPPE NACH DIME1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>VON dv1<br/>WO \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39; UND<br/>  AND (dim2 = &#39;A&#39; ODER dim3 IN (&#39;X&#39;, &#39;Y&#39;, &#39;Z&#39;)<br/>GRUPPE NACH DIME1</pre> |
| HAVING-Klausel | <pre>SELECT dim1, SUM(metric1) AS m1<br/>VON dv1<br/>WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;<br/>GRUPPE NACH DIME1<br/>HAVING m1 > 100 |
| Unterschiedlich, oben <br/>Dimensionswerte | <pre>WÄHLEN SIE &quot;dim1 DISTINCT&quot;VON &quot;dv1&quot;</pre><pre>SELECT dim1 AS dv1<br/>VON dv1<br/>WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;<br/>GRUPPE NACH DIME1</pre><pre>SELECT dim1 AS dv1<br/>VON dv1<br/>WOBEI \`timestamp\` >= &#39;2022-01-01&#39; UND \`timestamp\` &lt; &#39;2022-01-02&#39;<br/>GRUPPE NACH DIME1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Metriksummen | <pre>SUM(metric1) AS m1 AUSWÄHLEN<br/>VON dv1<br/>WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;</pre> |
| Mehrdimensionale Dimension<br/>Aufschlüsselungen<br/>und oberste Unterscheidungen | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>VON dv1<br/>WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;<br/>GRUPPE BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>VON dv1<br/>WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;<br/>GRUPPE NACH 1, 2<br/>BESTELLUNG DURCH 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>VON dv1</pre> |
| Unterauswahl:<br/>Zusätzliches Ergebnis<br/>Filter | <pre>SELECT dim1, m1<br/>VON (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  VON dv1<br/>  WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;</br>  GRUPPE NACH DIME1<br/>)<br/>WOBEI DIm1 in (&#39;A&#39;, &#39;B&#39;)</pre> |
| Unterauswahl:<br/>Verbinden mit<br/>Datensatz nicht in<br/>CJA | <pre>SELECT b.key, a.dim1, a.m1<br/>VON (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  VON dv1<br/>  WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;<br/>  GRUPPE NACH DIME1<br/>)<br/>LINKE JOIN-Suche b ON a.dim1 = b.key</pre> |
| Unterauswahl:<br/>Abfrage über<br/>data-views | <pre>SELECT key, SUM(m1) AS total<br/>VON (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  VON dv1<br/>  WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;<br/>  GRUPPE NACH DIME1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  VON dv2<br/>  WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;<br/>  GRUPPE NACH DIME2<br/>GRUPPE nach Schlüssel<br/>BESTELLUNG NACH GESAMT</pre> |
| Unterauswahl: <br/>Ebenenquelle, <br/>Filtern, <br/>und Aggregation | Ebenen mit Unterselekten:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>VON (<br/>  SELECT \_.dim1,\_.m1<br/>  VON (<br/>    SELECT \* FROM dv1<br/>    WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;<br/>  ) \_<br/>  WOBEI \_.dim1 in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>) Zeilen<br/>GRUPPE NACH 1<br/>BESTELLUNG NACH GESAMT</pre><br/>Ebenen, die CTE MIT verwenden:<br/><pre>MIT DEN Zeilen ALS (<br/>  MIT \_ AS (<br/>    SELECT * FROM data_ares<br/>    WO \`timestamp\` ZWISCHEN &#39;2021-01-01&#39; UND &#39;2021-02-01&#39; IST<br/>  )<br/>  SELECT _.item, _.unit FROM _<br/>  WOBEI _.item NICHT NULL IST<br/>)<br/>SELECT rows.item, SUM(rows.unit) AS-Einheiten<br/>AUS DEN Zeilen WHERE rows.item in (&#39;A&#39;, &#39;B&#39;, &#39;C&#39;)<br/>GROUP BY rows.item</pre> |
| Wählt aus, wo die<br/>Metriken kommen voran<br/> oder mit<br/>die Dimensionen | <pre>SUM(metric1) AS m1, dim1<br/>VON dv1<br/>WOBEI \`timestamp\` ZWISCHEN &#39;2022-01-01&#39; UND &#39;2022-01-02&#39;<br/>GRUPPE NACH 2</pre> |

{style="table-layout:auto"}

+++

### Dimensionen

Sie können eine der Dimensionen auswählen, die standardmäßig verfügbar oder in der Datenansicht definiert sind. Sie wählen eine Dimension anhand ihrer Kennung aus.

### Metriken

Folgende Metriken stehen zur Auswahl:

- einer der standardmäßig verfügbaren Metriken,

- in der Datenansicht definiert wurde,

- berechnete Metriken, die mit der Datenansicht kompatibel sind, auf die der Benutzer Zugriff hat.

Sie wählen eine Metrik anhand ihrer Kennung aus, die in eine `SUM(metric)` -Ausdruck genau wie bei anderen SQL-Quellen.

Sie können:

- `SELECT COUNT(*)` oder `COUNT(1)` , um die Metrik &quot;Vorkommen&quot;abzurufen.

- `SELECT COUNT(DISTINCT dimension)` oder `SELECT APPROX_COUNT_DISTINCT(dimension)` , um die ungefähren eindeutigen Werte einer Dimension zu zählen. Siehe Details unter [Zählung von Unterschieden](#counting-distincts).

- [Inline-Berechnungen](#inline-calculations) , um Metriken spontan zu kombinieren und/oder mathematisch zu gestalten.

#### Zählung von Unterschieden

Aufgrund der Art und Weise, wie CJA funktioniert, können Sie als einzige Dimension eine exakte eindeutige Anzahl erhalten, ist die `adobe_personid` Dimension. Die folgenden SQL-Anweisungen `SELECT COUNT(DISTINCT adobe_personid)` oder `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` gibt den Wert der Standard-Besuchermetrik zurück, die der Anzahl der unterschiedlichen Personen entspricht. Bei anderen Dimensionen wird eine ungefähre eindeutige Anzahl zurückgegeben.

#### Bedingte Metriken

Sie können eine `IF` oder `CASE` -Klausel `SUM` oder `COUNT` Funktionen zum Hinzufügen zusätzlicher Filter, die für eine ausgewählte Metrik spezifisch sind. Das Hinzufügen dieser Klauseln ähnelt dem Anwenden eines Filters auf eine Metrikspalte in einer Workspace-Berichtstabelle.

Beispiele:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Inline-Berechnungen

Sie können in Ihren `SELECT` anstatt die Mathematik in einer berechneten Metrik zu definieren. In der folgenden Tabelle ist aufgeführt, welche Arten von Ausdrücken unterstützt werden.

| Operator oder Funktion | Details |
|---|---|
| `+`, `-`, `*`, `/`, und `%` | Addieren, subtrahieren, multiplizieren, dividieren und modularen/Rest |
| `-X` oder `+X` | Ändern des Zeichens oder einer Metrik, bei der X der Metrikausdruck ist |
| `PI()` | Kennzahl |
| `POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`und `TANH` | Unäre mathematische Funktionen |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Binärmathematik-Funktionen |

{style="table-layout:auto"}

### Sonderspalten

**Zeitstempel**

Die `timestamp` spezielle Spalte wird verwendet, um die Datumsbereiche für die Abfrage bereitzustellen. Ein Datumsbereich kann mit einer `BETWEEN` Ausdruck oder ein Paar `timestamp` `>`, `>=`, `<`, `<=` checks `AND`las zusammen.
Die `timestamp` ist optional und wird kein vollständiger Bereich angegeben, werden die Standardwerte verwendet:

- Wenn nur ein Minimum angegeben wird (`timestamp > X` oder ` timestamp >= X`), liegt der Bereich von X bis jetzt.

- Wenn nur eine maximale Anzahl angegeben wird (`timestamp < X` oder `timestamp <= X`), liegt der Bereich zwischen X-30 Tagen und X.

- Wenn nichts angegeben wird, liegt der Bereich zwischen jetzt 30 Tagen und jetzt.

Der Zeitstempelbereich wird in RankedRequest in einen globalen Datumsbereich-Filter konvertiert.
Das Zeitstempelfeld kann auch in Datums-/Uhrzeitfunktionen verwendet werden, um den Zeitstempel des Ereignisses zu analysieren und zu kürzen.

**Datumsbereich**

Die `daterange` Sonderspalten funktionieren ähnlich  `timestamp`, die Filterung ist jedoch auf volle Tage beschränkt. Die `daterange` ist ebenfalls optional und hat denselben Standardbereich wie `timestamp`.
Die `daterange` kann auch in Datums-/Uhrzeitfunktionen verwendet werden, um das Ereignisdatum zu analysieren und abzuschneiden.

**filterId**

Die `filterId` Die spezielle Spalte ist optional und wird verwendet, um einen extern definierten Filter auf die Abfrage anzuwenden. Das Anwenden eines extern definierten Filters auf eine Abfrage ähnelt dem Ziehen eines Filters auf einen Bereich in Workspace. Mehrere Filter-IDs können von `AND`- und sie.

### WHERE Clause

Die WHERE-Klausel wird in drei Schritten behandelt:

1. Suchen Sie den Datumsbereich aus dem `timestamp` spezielles Feld.

2. Suchen nach extern definierten `filterId`s, die in die Filterung einbezogen werden sollen.

3. Wandeln Sie die verbleibenden Ausdrücke in Ad-hoc-Filter um.

Die Verarbeitung erfolgt durch Parsen der ersten Ebene von `AND`s im `WHERE` -Klausel. Jede oberste Ebene `AND`ed -Ausdruck muss mit einem der oben genannten übereinstimmen. Alles, was tiefer als die erste Ebene von ist `AND`s oder, wenn die `WHERE` clause uses `OR`s auf der obersten Ebene wird als Ad-hoc-Filter behandelt.

### BESTELLUNG NACH

Standardmäßig sortiert die Abfrage die Ergebnisse nach der ersten ausgewählten Metrik in absteigender Reihenfolge. Sie können die standardmäßige Sortierreihenfolge überschreiben, indem Sie `ORDER BY ... ASC` oder `ORDER BY ... DESC`. Wenn Sie `ORDER BY`angegeben `ORDER BY` für die erste ausgewählte Metrik.

Sie können die Reihenfolge auch ändern, indem Sie `-` (Minus) vor der Metrik. Beide Anweisungen führen zur selben Reihenfolge:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### Allgemeine Funktionsunterstützung

| Funktion | Beispiel | Details |
|---|---|---|
| [CAST(column AS type)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) | ``CAST(`timestamp` AS STRING)`` oder <br/> `` `timestamp`::string `` | Die Typumwandlung wird derzeit nicht unterstützt, es wird jedoch kein Fehler ausgegeben. Die `CAST` -Funktion ignoriert wird. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Analysieren einer Zeitzeichenfolge als Zeitstempel zur Verwendung in einer `WHERE` -Klausel. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Analysieren einer Zeitzeichenfolge als Zeitstempel zur Verwendung in einer `WHERE` -Klausel, die optional ein Format für diese Zeitzeichenfolge bereitstellt. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Analysieren einer Datums-Zeichenfolge als Zeitstempel zur Verwendung in einer `WHERE` -Klausel. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Analysieren einer Datums-Zeichenfolge als Zeitstempel zur Verwendung in einer `WHERE` -Klausel, die optional ein Format für diese Datums-Zeichenfolge bereitstellt. |

{style="table-layout:auto"}

### Unterstützung von Dimension-Funktionen

Diese Funktionen können für Dimensionen im `SELECT`, `WHERE` -Klausel oder in bedingten Metriken.

**Zeichenfolgen-Funktionen**

| Funktion | Beispiel | Details |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. |

{style="table-layout:auto"}

**Funktionen für Datum/Uhrzeit**

| Funktion | Beispiel | Details |
|---|---|---|
| [YEAR(Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. |
| [MONTH(Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. |
| [DAY(Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. |
| [DAYOFWEEK(Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts , da Sie die Nummer und nicht den Anzeigenamen benötigen. |
| [DAYOFYEAR(Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. |
| [WEEK(Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. |
| [QUARTER(Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. |
| [HOUR(Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts , da Sie die Nummer und nicht den Anzeigenamen benötigen. |
| [MINUTE(Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. |
| [EXTRAKT(TEIL VON Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts für einige Teile dieser Funktion, da Sie die Nummer und nicht den Anzeigenamen benötigen.<br/>Folgende Komponenten werden unterstützt:<br>- Suchbegriffe: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Zeichenfolgen:  `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&quot;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`oder `'MINUTE'`. |
| [DATE_PART(Teil, Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld. Verwenden Sie die Element-ID anstelle des Werts für einige Teile dieser Funktion, da Sie die Nummer und nicht den Anzeigenamen benötigen.<br/>Unterstützte String-Teile sind: `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&quot;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`oder `'MINUTE'`. |
| [DATE_TRUNC(Granularität, Datum oder Datum/Uhrzeit)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Generieren Sie eine dynamische Dimensionsidentität für das übergebene Feld.<br/>Unterstützte Zeichenfolgengranularitäten sind: `'YEAR'`, &#39;`Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, &#39;`DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`&quot;, `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`oder `'MINUTE'`. |

{style="table-layout:auto"}

