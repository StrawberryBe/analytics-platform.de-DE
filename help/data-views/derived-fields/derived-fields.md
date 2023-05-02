---
title: Abgeleitete Felder
description: Ein abgeleitetes Feld gibt die Berichtszeitbearbeitung von Schemafeldern und/oder Standardkomponenten durch eine Reihe verfügbarer Funktionen und Funktionsvorlagen an.
solution: Customer Journey Analytics
feature: Data Views
hide: true
hidefromtoc: true
exl-id: 1ba38aa6-7db4-47f8-ad3b-c5678e5a5974
source-git-commit: 3aa2f57e7cd11b013369ad80d0181bccb48eebe1
workflow-type: tm+mt
source-wordcount: '3225'
ht-degree: 9%

---

# Abgeleitete Felder

{{release-limited-testing}}

Abgeleitete Felder sind ein wichtiger Aspekt der Echtzeitberichterstellungsfunktion in Customer Journey Analytics (CJA). Mit einem abgeleiteten (benutzerdefinierten) Feld können Sie mithilfe eines anpassbaren Regel-Builders (Regel-Builder) spontan (häufig komplexe) Datenmanipulationen definieren. Anschließend können Sie dieses abgeleitete Feld als Komponente (Metrik oder Dimension) in [Arbeitsbereich](../../analysis-workspace/home.md) oder weiter als Komponente in definieren [Datenansicht](../data-views.md).

Abgeleitete Felder können viel Zeit und Mühe sparen, verglichen mit der Transformation oder Manipulation Ihrer Daten an anderen Standorten außerhalb von CJA. z. B. [Datenvorbereitung](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=de), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=en)oder innerhalb Ihrer eigenen Extract Transform Load (ETL)-/Extract Load Transform (ELT)-Prozesse.

Abgeleitete Felder werden als benutzerdefinierte Felder in [Datenansichten](../data-views.md), basieren auf einem Satz von Funktionen, die als Regeln definiert und auf verfügbare Standard- und/oder Schemafelder angewendet werden.

Anwendungsbeispiele sind:

- Definieren Sie ein benutzerdefiniertes Feld für den Seitennamen, das falsche erfasste Seitennamenwerte korrigiert, um die Seitennamenwerte zu korrigieren.

- Definieren Sie ein benutzerdefiniertes Marketing-Kanal -Feld, das den korrekten Marketing-Kanal anhand einer oder mehrerer Bedingungen bestimmt (z. B. URL-Parameter, Seiten-URL, Seitenname).

## Benutzeroberfläche für benutzerdefinierte Felder

Wenn Sie ein benutzerdefiniertes Feld erstellen oder bearbeiten, verwenden Sie die Benutzeroberfläche für benutzerdefinierte Felder.

![Dialogfeld &quot;Benutzerdefiniertes Feld&quot;](assets/custom-field-dialog.png)


|  | Name | Beschreibung |
|---------|----------|--------|
| 1 | **Selektor** | Sie verwenden den Auswahlbereich, um Ihre ![Funktion](assets/Smock_Function_18_N.svg) Funktion,![Symbol für Funktionsvorlage](assets/Smock_FileTemplate_18_N.svg) Funktionsvorlage,![Symbol für Schemafeld](assets/Smock_Folder_18_N.svg) Schemafeld oder![Standardfeldsymbol](assets/Smock_DragHandle_18_N.svg)Standardfeld auf zum Regel-Builder. <br/>Verwenden Sie das Dropdown-Menü, um zwischen [!UICONTROL Funktionen], [!UICONTROL Funktionsvorlagen], [!UICONTROL Schemafelder]und [!UICONTROL Standardfelder].<br/>Sie können mithilfe der Variablen ![Suchsymbol](assets/Smock_Search_18_N.svg) Suchfeld. <br/>Sie können die ausgewählte Objektliste filtern, indem Sie ![Filtersymbol](assets/Smock_Filter_18_N.svg) Filter und Filter im [!UICONTROL Filtern von Feldern nach] angezeigt. Sie können Filter einfach mit ![Symbol &quot;Schließen&quot;](assets/CrossSize75.svg) für jeden Filter. |
| 2 | **Regel-Builder** | Sie erstellen Ihr benutzerdefiniertes Feld sequenziell mithilfe einer oder mehrerer Regeln. Eine Regel ist eine spezifische Implementierung einer Funktion und ist daher immer nur einer Funktion zugeordnet. Sie erstellen eine Regel, indem Sie eine Funktion per Drag-and-Drop in den Rule Builder ziehen. Der Funktionstyp bestimmt die Schnittstelle der Regel.<br/>Siehe [Regelschnittstelle](#rule-interface) für weitere Informationen. <br/>Sie können eine Funktion am Anfang, Ende oder zwischen Regeln einfügen, die bereits im Regel-Builder verfügbar sind. Die letzte Regel im Rule Builder bestimmt die endgültige Ausgabe des benutzerdefinierten Felds. |
| 3 | **[!UICONTROL ** Feldeinstellungen **]** | Sie können Ihr benutzerdefiniertes Feld benennen und beschreiben und den Feldtyp überprüfen. |
| 4 | **[!UICONTROL ** Endausgabe **]** | In diesem Bereich wird eine direkt aktualisierte Vorschau der Ausgabewerte angezeigt, die auf den Daten der letzten 30 Tage und den Änderungen basiert, die Sie am benutzerdefinierten Feld im Regel-Builder vornehmen. |

{style="table-layout:auto"}

Wenn Sie zum ersten Mal auf die Benutzeroberfläche für benutzerdefinierte Felder zugreifen, wird die [!UICONTROL Mit einer Feldvorlage beginnen] angezeigt.

![Dialogfeld für benutzerdefinierte Feldvorlagen](assets/field-template-dialog.png)

1. Wählen Sie die Vorlage aus, die den Typ des zu erstellenden Felds am besten beschreibt.
2. Wählen Sie die **[!UICONTROL ** Auswählen **]** zum Fortfahren.

Das Dialogfeld &quot;Benutzerdefiniertes Feld&quot;enthält Regeln (und Funktionen), die für den von Ihnen ausgewählten Feldtyp erforderlich oder nützlich sind. Siehe [Funktionsvorlagen](#function-templates) für weitere Informationen zu den verfügbaren Vorlagen.

## Regelschnittstelle

Wenn Sie eine Regel im Regel-Builder definieren, verwenden Sie die Regel-Oberfläche.

![Regelschnittstelle](assets/rule-interface.png)

|  | Name | Beschreibung |
|---------|----------|--------|
| A  | **Regelname** | Standardmäßig lautet der Regelname **Regel X** (X bezieht sich auf eine Sequenznummer). Um den Namen einer Regel zu bearbeiten, wählen Sie deren Namen aus und geben Sie den neuen Namen ein, z. B. `Query Parameter`. |
| B | **Name der Funktion** | Der ausgewählte Funktionsname für die Regel, z. B. [!DNL URL PARSE]. Wenn die Funktion der letzte in der Funktionssequenz ist und die endgültigen Ausgabewerte bestimmt, wird dem Funktionsnamen gefolgt von [!DNL FINAL OUTPUT]beispielsweise [!DNL URL PARSE - FINAL OUTPUT]. <br/>Um ein Popup mit weiteren Informationen zur Funktion anzuzeigen, wählen Sie ![Hilfesymbol](assets/Smock_HelpOutline_18_N.svg). |
| C  | **Regelbeschreibung** | Sie können optional einer Regel eine Beschreibung hinzufügen.<br/>Auswählen ![Weitere Symbole](assets/More.svg), wählen Sie **[!UICONTROL ** Beschreibung hinzufügen **]** , um eine Beschreibung hinzuzufügen, oder **[!UICONTROL ** Beschreibung bearbeiten **]** , um eine vorhandene Beschreibung zu bearbeiten.<br/>Geben Sie im Editor eine Beschreibung ein. Sie können die Symbolleiste verwenden, um den Text zu formatieren (mithilfe der Stilauswahl, fett, kursiv, unterstrichen, rechts, links, zentriert, Farbe, Nummernliste, Aufzählungsliste) und Links zu externen Informationen hinzuzufügen. <br/>Um die Bearbeitung der Beschreibung abzuschließen, klicken Sie außerhalb des Editors auf . |
| D | **Funktionsbereich** | Definiert die Logik der Funktion. Die Benutzeroberfläche hängt vom Funktionstyp ab. Siehe [Funktionsreferenz](#function-reference) Detaillierte Informationen zu den einzelnen unterstützten Funktionen. |

{style="table-layout:auto"}

## Benutzerdefiniertes Feld erstellen

1. Wählen Sie eine Datenansicht aus oder erstellen Sie eine Datenansicht. Siehe [Datenansichten](../data-views.md) für weitere Informationen.

2. Wählen Sie die **[!UICONTROL ** Komponenten **]** in der Datenansicht.

3. Auswählen **[!UICONTROL ** Benutzerdefiniertes Feld erstellen **]** über die linke Leiste.

4. Um Ihr benutzerdefiniertes Feld zu definieren, verwenden Sie die [!UICONTROL Benutzerdefiniertes Feld erstellen] -Schnittstelle. Siehe [Benutzeroberfläche für benutzerdefinierte Felder](#custom-field-interface).

   Um Ihr neues benutzerdefiniertes Feld zu speichern, wählen Sie **[!UICONTROL ** Speichern **]**.

5. Ihr neues benutzerdefiniertes Feld wird zum **[!UICONTROL ** Benutzerdefinierte Felder >**]** Container, als Teil von **[!UICONTROL ** Schemafelder **]** in der linken Leiste Ihrer Datenansicht.


## Benutzerdefiniertes Feld bearbeiten

1. Wählen Sie eine Datenansicht aus. Siehe [Datenansichten](../data-views.md) für weitere Informationen.

2. Wählen Sie die **[!UICONTROL ** Komponenten **]** in der Datenansicht.

3. Auswählen **[!UICONTROL ** Schemafelder **]** im [!UICONTROL Verbindung] auf der linken Seite.

4. Auswählen **[!UICONTROL ** Benutzerdefinierte Felder >**]** Container.

5. Bewegen Sie den Mauszeiger über das benutzerdefinierte Feld, das Sie bearbeiten möchten, und wählen Sie ![Symbol Bearbeiten](assets/Smock_Edit_18_N.svg).

6. Um Ihr benutzerdefiniertes Feld zu bearbeiten, verwenden Sie die [!UICONTROL Benutzerdefiniertes Feld bearbeiten] -Schnittstelle. Siehe [Benutzeroberfläche für benutzerdefinierte Felder](#custom-field-interface).

   - Auswählen **[!UICONTROL ** Speichern **]** , um Ihr aktualisiertes benutzerdefiniertes Feld zu speichern.

   - Auswählen **[!UICONTROL ** Abbrechen **]** , um alle Änderungen abzubrechen, die Sie am benutzerdefinierten Feld vorgenommen haben.

   - Auswählen **[!UICONTROL ** Speichern unter **]** , um das benutzerdefinierte Feld als neues benutzerdefiniertes Feld zu speichern. Das neue benutzerdefinierte Feld hat denselben Namen wie das ursprünglich bearbeitete benutzerdefinierte Feld mit `(copy)` hinzugefügt.

## Benutzerdefiniertes Feld löschen

1. Wählen Sie eine Datenansicht aus. Siehe [Datenansichten](../data-views.md) für weitere Informationen.

2. Wählen Sie die **[!UICONTROL ** Komponenten **]** in der Datenansicht.

3. Auswählen **[!UICONTROL ** Schemafelder **]** Registerkarte in [!UICONTROL Verbindung] -Bereich.

4. Auswählen **[!UICONTROL ** Benutzerdefinierte Felder >**]** Container.

5. Bewegen Sie den Mauszeiger über das benutzerdefinierte Feld, das Sie löschen möchten, und wählen Sie ![Symbol Bearbeiten](assets/Smock_Edit_18_N.svg).

6. In der Verwendung **[!UICONTROL ** Benutzerdefiniertes Feld bearbeiten **]** -Benutzeroberfläche verwenden, wählen Sie Löschen aus.

   A [!UICONTROL Komponente löschen] werden Sie aufgefordert, den Löschvorgang zu bestätigen. Betrachten Sie alle externen Verweise, die außerhalb der Datenansicht auf das benutzerdefinierte Feld vorhanden sein können.

   - Auswählen **[!UICONTROL ** Weiter **]** , um das benutzerdefinierte Feld zu löschen.


## Funktionsvorlagen

Um schnell ein benutzerdefiniertes Feld für bestimmte Anwendungsfälle zu erstellen, sind Funktionsvorlagen verfügbar. Auf diese Funktionsvorlagen kann über den Bereich Selektor in der Benutzeroberfläche Benutzerdefiniertes Feld zugegriffen werden oder sie werden bei der ersten Verwendung in der [!UICONTROL Mit einer Feldvorlage beginnen] Assistent.


### Marketing-Kanäle

Diese Vorlage ist so konfiguriert, dass die [URL-Analyse](#dnl-url-parse) und [Groß-/Kleinschreibung](#dnl-case-when) verwendet mehrere Male, um geeignete Werte aus einer URL zu erhalten. Anschließend wird auf diese Werte Logik angewendet, um die URL einem bestimmten Marketing-Kanal zuzuordnen.

+++ Details

Um die Vorlage zu verwenden, müssen Sie die richtigen Parameter für jede Funktion angeben, die als Teil der Regeln in der Vorlage aufgeführt wird. Siehe [Funktionsreferenz](#function-reference) für weitere Informationen.

![Regel-Builder für Marketing-Kanalvorlagen](assets/marketing-channel-template.png)

+++

<!--

+++ Data clean up template

>[!WARNING]
>
>Could not find any information on this template.
+++

-->

## Funktionsreferenz

Für jede unterstützte Funktion finden Sie im Folgenden Details zu:

- Spezifikationen:
   - Eingabedatentyp: Art der unterstützten Daten,
   - input: mögliche Eingabewerte,
   - enthaltene Operatoren: für diese Funktion unterstützte Operatoren (falls vorhanden),
   - limit: maximale Anzahl von Regeln mit dieser Funktion, die Sie in einem abgeleiteten Feld verwenden können,
   - Ausgabe.

- Anwendungsbeispiele, darunter:
   - Daten vor der Definition des benutzerdefinierten Felds
   - Definieren des benutzerdefinierten Felds
   - Daten nach der Definition des benutzerdefinierten Felds

- dependencies (optional)


<!-- Concatenate -->

### [!DNL Concatenate]

Kombiniert zwei oder mehr Felder, benutzerdefinierte Felder oder vom Benutzer eingegebene Werte in einem Feld mit definierten Trennzeichen.

+++ Details

## Spezifikationen {#concatenate-io}

| Eingabedatentyp | Eingabe | Eingeschlossene Operatoren | Limit | Ausgabe |
|---|---|---|:--:|---|
| <p>Zeichenfolge</p> | <ul><li>Zwei oder mehr Werte zu kombinieren<ul><li>Felder</li><li>Abgeleiteter Wert aus einer vorherigen Regel</li><li>Vom Benutzer eingegebener Wert</li></ul></li><li>Trennzeichen<ul><li>Eingabe oder Auswahl eines Trennzeichens für jeden Wert</li></ul></li> </ul> | <p>Nicht angegeben</p> | <p>2</p> | <p>Neues benutzerdefiniertes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall {#concatenate-uc}

Sie erfassen derzeit die Ursprungs- und Zielflughafencodes als separate Felder. Sie möchten die beiden Felder zu einer durch Bindestriche (-) getrennten Dimension zusammenfassen. So können Sie die Kombination aus Ursprung und Ziel analysieren, um die wichtigsten gebuchten Routen zu identifizieren.

Annahmen:

- Die Ursprungs- und Zielwerte werden in separaten Feldern in derselben Tabelle erfasst.
- Der Benutzer legt fest, das Trennzeichen &quot;-&quot;zwischen den Werten zu verwenden.

Stellen Sie sich die folgenden Buchungen vor:

- Der Kunde ABC123 bucht einen Flug zwischen Salt Lake City (SLC) und Orlando (MCO)
- Der Kunde ABC456 bucht einen Flug zwischen Salt Lake City (SLC) und Los Angeles (LAX)
- Der Kunde ABC789 bucht einen Flug zwischen Salt Lake City (SLC) und Seattle (SEA)
- Der Kunde ABC987 bucht einen Flug zwischen Salt Lake City (SLC) und San Jose (SJO)
- Der Kunde ABC654 bucht einen Flug zwischen Salt Lake City (SLC) und Orlando (MCO)

Der gewünschte Bericht sollte wie folgt aussehen:

| Ursprung/Ziel | Buchungen |
|----|---:|
| SLC-MCO | 2 |
| SLC-LAX | 1 |
| SLC-SEA | 1 |
| SLC-SJO | 1 |

{style="table-layout:auto"}


### Daten vor {#concatenate-uc-databefore}

| Herkunft | Ziel |
|----|---:|
| SLC | MCO |
| SLC | LAX |
| SLC | SEA |
| SLC | SJO |
| SLC | MCO |

{style="table-layout:auto"}

### Benutzerdefiniertes Feld {#concatenate-customfield}

Sie definieren eine neue **[!UICONTROL ** Origin - Ziel **]** benutzerdefiniertes Feld. Sie verwenden die **[!UICONTROL CONCATENATE]** -Funktion, um eine Regel zum Verketten der [!UICONTROL Original] und [!UICONTROL Ziel] -Felder, die `-` [!UICONTROL Trennzeichen].

![[!DNL Concatenate] Regel](assets/concatenate.png)

### Daten nach {#concatenate-dataafter}

| Origin - Ziel<br/>(benutzerdefiniertes Feld) |
|---|
| SLC-MCO |
| SLC-LAX |
| SLC-SEA |
| SLC-SJO |
| SLC-MCO |

{style="table-layout:auto"}

+++

<!-- CASE WHEN -->

### [!DNL Case When]

Wendet Bedingungen an, die auf definierten Kriterien aus einem oder mehreren Feldern basieren. Diese Kriterien werden dann verwendet, um die Werte in einem neuen benutzerdefinierten Feld basierend auf der Reihenfolge der Bedingungen zu definieren.

+++ Details

## Spezifikationen {#casewhen-io}

| Eingabedatentyp | Eingabe | Eingeschlossene Operatoren | Limit | Ausgabe |
|---|---|---|:---:|---|
| <ul><li>Zeichenfolge</li><li>Numerisch</li><li>Datum/Datum/Uhrzeit</li></ul> | <ul><li>Eingabefelder</li><li>Kriterien</li></ul> | <p><u>Zeichenfolgen</u></p><ul><li>Gleich</li><li>Gleich jedem Begriff</li><li>Enthält die Wortgruppe</li><li>Enthält einen der Begriffe</li><li>Enthält alle Begriffe</li><li>Beginnt mit</li><li>Beginnt mit einem beliebigen Begriff</li><li>Endet mit</li><li>Endet mit einem beliebigen Begriff</li><li>Ist nicht gleich</li><li>Ist gleich keinem Begriff</li><li>Enthält nicht die Wortgruppe</li><li>Enthält keine Begriffe</li><li>Enthält nicht alle Begriffe</li><li>Beginnt nicht mit</li><li>Beginnt nicht mit einem Begriff</li><li>Endet nicht mit</li><li>endet nicht mit einem Begriff</li><li>Ist eingestellt</li><li>Ist nicht eingestellt</li></ul><p><u>Numerisch</u></p><ul><li>Gleich</li><li>Ist nicht gleich</li><li>Größer als</li><li>Größer als oder gleich</li><li>Kleiner als</li><li>Kleiner als oder gleich</li><li>Ist eingestellt</li><li>Ist nicht eingestellt</li></ul><p><u>Daten </u></p><ul><li>Gleich</li><li>Ist nicht gleich</li><li>Ist später als</li><li>Ist später als oder gleich</li><li>Is before</li><li>Ist vor oder gleich</li><li>Ist eingestellt</li><li>Ist nicht eingestellt</li></ul> | <p>5</p> | <p>Neues benutzerdefiniertes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall 1 {#casewhen-uc1}

Sie möchten Regeln definieren, um verschiedene Marketing-Kanäle zu identifizieren, indem Sie eine kaskadierende Logik anwenden, um ein Marketing-Kanal-Feld auf den richtigen Wert festzulegen:

- Wenn der Referrer aus einer Suchmaschine stammt und die Seite einen Abfragezeichenfolgenwert hat, wobei `cid` contains `ps_`sollte der Marketing-Kanal als **Gebührenpflichtige Suche**.
- Wenn der Referrer aus einer Suchmaschine stammt und die Seite nicht über die Abfragezeichenfolge verfügt `cid`sollte der Marketing-Kanal als **Kostenlose Suche**.
- Wenn eine Seite einen Abfragezeichenfolgenwert hat, wobei `cid` contains `em_`sollte der Marketing-Kanal als **Email**.
- Wenn eine Seite einen Abfragezeichenfolgenwert hat, wobei `cid` contains `ds_`sollte der Marketing-Kanal als **Display Ad**.
- Wenn eine Seite einen Abfragezeichenfolgenwert hat, wobei `cid` contains `so_`sollte der Marketing-Kanal als **Paid Social**.
- Wenn der Referrer aus einer Referrer-Domäne von twitter.com, facebook.com, linkedin.com oder tiktok.com stammt, sollte der Marketing-Kanal als **Natürliche Social**.
- Wenn keine der oben genannten Regeln übereinstimmt, sollte der Marketing-Kanal als **Andere verweisende Stelle**.

Falls Ihre Site die folgenden Beispielereignisse erhält, die Referrer und Seiten-URL enthalten, sollten diese Ereignisse wie folgt identifiziert werden:

| Ereignis-   | Referrer | Seiten-URL | Marketing-Kanal |
|:--:|----|----|----|
| 1 | `https://facebook.com` | `https://site.com/home` | Natürliche Social |
| 2 | `https://abc.com` | `https://site.com/?cid=ds_12345678` | Anzeigen |
| 3 |  | `https://site.com/?cid=em_12345678` | E-Mail |
| 4 | `https://google.com` | `https://site.com/?cid=ps_abc098765` | Paid Search |
| 5 | `https://google.com` | `https://site.com/?cid=em_765544332` | E-Mail |
| 6 | `https://google.com` |  | Kostenlose Suche  |

{style="table-layout:auto"}

### Daten vor {#casewhen-uc1-databefore}

| Referrer | Seiten-URL |
|----|----|
| `https://facebook.com` | `https://site.com/home` |
| `https://abc.com` | `https://site.com/?cid=ds_12345678` |
|  | `https://site.com/?cid=em_12345678` |
| `https://google.com` | `https://site.com/?cid=ps_abc098765` |
| `https://google.com` | `https://site.com/?cid=em_765544332` |
| `https://google.com` |

{style="table-layout:auto"}

### Benutzerdefiniertes Feld {#casewhen-uc1-customfield}

Sie definieren eine neue `Marketing Channel` benutzerdefiniertes Feld. Sie verwenden die **[!UICONTROL WENN]** Funktionen zum Definieren von Regeln, die Werte für die basierend auf vorhandenen Werten für `Page URL` und `Referring URL` -Feld.

Beachten Sie die Verwendung der Funktion . **[!UICONTROL ** URL PARSE **]** zum Definieren von Regeln zum Abrufen der Werte für `Page Url` und `Referring Url` vor **[!UICONTROL ** WENN **]** -Regeln angewendet werden.

![[!DNL Case when] Regel 1](assets/case-when-1.png)

### Daten nach {#casewhen-uc1-dataafter}

| Marketing-Kanal |
|----|
| Natürliche Social |
| Anzeigen |
| E-Mail |
| Paid Search |
| E-Mail |
| Kostenlose Suche  |

{style="table-layout:auto"}


## Anwendungsfall 2 {#casewhen-uc2}

Sie haben mehrere verschiedene Varianten der Suche in Ihrer Dimension &quot;Produktsuchmethoden&quot;erfasst. Um die Gesamtleistung der Suche im Vergleich zum Durchsuchen zu verstehen, müssen Sie viel Zeit damit verbringen, die Ergebnisse manuell zu kombinieren.

Ihre Site erfasst die folgenden Werte für Ihre Dimension &quot;Produktsuchmethoden&quot;. Letztlich weisen alle diese Werte auf eine Suche hin.

| Erfasster Wert | Tatsächlicher Wert |
|---|---|
| search p13n_no | Suche |
| search p13n_yes | Suche |
| search refine p13n_no | Suche |
| search refine p13n_yes | Suche |
| Suchumleitung p13n_yes | Suche |
| search-redirect | Suche |

{style="table-layout:auto"}


### Daten vor {#casewhen-uc2-databefore}

| Methoden zur Produktsuche |
|----|
| search p13_no |
| search p13_yes |
| Browsen |
| search refine p13_no |
| search refine p13_yes |
| Browsen |
| Suchumleitung p13_yes |
| search-redirect |
| Browsen |

{style="table-layout:auto"}

### Benutzerdefiniertes Feld {#casewhen-uc2-customfield}

Sie definieren eine `Product Finding Methods (new)` benutzerdefiniertes Feld. Sie erstellen Folgendes **[!UICONTROL ** WENN **]** Regeln in Rule Builder. Diese Regeln gelten für die Logik für alle möglichen Varianten der alten **[!UICONTROL ** Methoden zur Produktsuche **]** Feldwerte für `search` und `browse` mithilfe der **[!UICONTROL Enthält die Wortgruppe]** Kriterium.

![[!DNL Case When] Regel 2](assets/case-when-2.png)

### Daten nach {#casewhen-uc2-dataafter}

| Methoden zur Produktsuche (neu) |
|----|
| Suche |
| Suche |
| Browsen |
| Suche |
| Suche |
| Browsen |
| Suche |
| Suche |
| Browsen |

{style="table-layout:auto"}


## Anwendungsfall 3 {#casewhen-uc3}

Als Reiseunternehmen möchten Sie die Reisedauer für gebuchte Reisen buchen, damit Sie über die gesammelten Reisen berichten können.

Annahmen:

- Die Organisation erfasst die Reisedauer in ein numerisches Feld.
- Sie möchten 1-3 Tage Dauer in einen Eimer mit der Bezeichnung &quot;Kurzreise&quot; einpacken.
- Sie möchten 4 bis 7 Tage lang in einen Eimer mit der Bezeichnung &quot;Mittelreise&quot; einpacken.
- Sie möchten 8-Tage-Dauern in einen Eimer mit der Bezeichnung &quot;Langreise&quot; einpacken.
- 132 Reisen wurden für eine Dauer von 1 Tag gebucht
- 110 Ausflüge wurden für eine Dauer von 2 Tagen gebucht
- 105 Ausflüge wurden für eine Dauer von 3 Tagen gebucht
- 99 Reisen wurden für eine Dauer von 4 Tagen gebucht
- 92 Reisen wurden für eine Dauer von 5 Tagen gebucht
- 85 Ausflüge wurden für eine Dauer von 6 Tagen gebucht
- 82 Reisen wurden für eine Dauer von 7 Tagen gebucht
- 78 Reisen wurden für eine Dauer von 8 Tagen gebucht
- 50 Reisen wurden für eine Dauer von 9 Tagen gebucht
- 44 Reisen wurden für eine Dauer von 10 Tagen gebucht
- 38 Ausflüge wurden für eine Dauer von 11 Tagen gebucht
- 31 Reisen wurden für eine Dauer von 12 Tagen gebucht

Ihr gewünschter Bericht sollte wie folgt aussehen:

| Art der Reisedauer | Buchungen |
|----|---:|
| Mittelreise | 358 |
| Kurzreise | 347 |
| Langreise | 241 |

{style="table-layout:auto"}

### Daten vor {#casewhen-uc3-databefore}

| Reisedauer |
|---:|
| 1 |
| 12 |
| 3 |
| 6 |
| 4 |
| 8 |
| 6 |
| 2 |
| 1 |
| 2 |
| 21 |
| 8 |

### Benutzerdefiniertes Feld {#casewhen-uc3-customfield}

Sie definieren eine `Trip Duration (bucketed)` benutzerdefiniertes Feld. Sie erstellen Folgendes **[!UICONTROL ** WENN **]** Regel im Regel-Builder. Diese Regel wendet eine Logik an, um die alte **[!UICONTROL ** Reisedauer **]** -Feldwerte in drei Werte: `short trip`, `medium  trip`und `long trip`.

![[!DNL Case When] Regel 3](assets/case-when-3.png)


### Daten nach {#casewhen-uc3-dataafter}

| Reisedauer (zusammengefasst) |
|---|
| Kurzreise |
| Langreise |
| Kurzreise |
| Mittelreise |
| Mittelreise |
| Langreise |
| Mittelreise |
| Kurzreise |
| Kurzreise |
| Kurzreise |
| Langreise |
| Langreise |


## Abhängigkeiten

Die folgenden Abhängigkeiten gelten beim Auswählen und Festlegen von Werten.


|  | Datensatzabhängigkeiten |
|:---:|----|
| <span style='color: red'>A </span> | Werte _select_ innerhalb desselben [!UICONTROL Wenn], [!UICONTROL Else If] struct (using [!UICONTROL und] oder [!UICONTROL Oder]), muss aus demselben Datensatz stammen. |
| <span style='color: red'>B</span> | Alle Werte, die Sie _set_ innerhalb von -Konstrukten und über die Regel hinweg müssen aus demselben Datensatz stammen. |
| <span style='color: blue'>C </span> | Die Werte, die Sie _select_ quer [!UICONTROL Wenn], [!UICONTROL Else If] -Konstrukte in der Regelaufgabe _not_ müssen aus demselben Datensatz stammen. |

{style="table-layout:auto"}

![Groß-/Kleinschreibung bei Datensatzabhängigkeiten](assets/case-when-datasets.png)


|  | Typabhängigkeiten |
|:---:|----|
| <span style='color: red'>D</span> | Die Werttypen, die Sie _set_ -Regel muss identisch sein. |
| <span style='color: blue'>E</span> | Die Werttypen, die Sie _select_ innerhalb eines Konstrukts oder über Konstrukte hinweg in einer Regel kann von beliebigem Typ sein (Zeichenfolge, numerisch, Datum). |

{style="table-layout:auto"}

![Groß-/Kleinschreibung bei Typabhängigkeiten](assets/case-when-types.png)

+++


<!-- FIND AND REPLACE -->

### [!DNL Find and Replace]

Sucht alle Werte in einem ausgewählten Feld und ersetzt diese Werte durch einen anderen Wert in einem neuen benutzerdefinierten Feld.

+++ Details

## Spezifikationen {#findreplace-io}

| Eingabedatentyp | Eingabe | Eingeschlossene Operatoren | Limit | Ausgabe |
|---|---|---|:---:|---|
| <p>Zeichenfolge</p> | <ul><li><span>Feldkriterien für den Zeitpunkt der Ersetzung</span></li><li><span>Feldwert &quot;Ersetzen durch&quot;</span><ul><li><span>Benutzereingabe</span></li><li><span>Separates Feld</span></li></ul></li></ul> | <p><u>Zeichenfolgen</u></p><ul><li>Alle suchen und Alle ersetzen</li></ul> | <p>1</p> | <p>Neues benutzerdefiniertes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall {#findreplace-uc}

Sie haben einige falsch formatierte Werte für Ihren externen Marketingkanalbericht erhalten, z. B. `email%20 marketing` anstelle von `email marketing`. Diese fehlerhaften Werte brechen Ihre Berichterstellung auf und erschweren die Performance von E-Mails. Sie möchten `email%20marketing` mit `email marketing`.

**Originalbericht**

| Externe Marketingkanäle | Sitzungen |
|---|--:|
| E-Mail-Marketing | 500 |
| email %20marketing | 24 |

{style="table-layout:auto"}

**Bevorzugter Bericht**

| Externe Marketingkanäle | Sitzungen |
|---|--:|
| E-Mail-Marketing | 524 |


### Daten vor {#findreplace-uc-databefore}

| Externes Marketing |
|----|
| E-Mail-Marketing |
| email%20marketing |
| E-Mail-Marketing |
| E-Mail-Marketing |
| email%20marketing |

{style="table-layout:auto"}

### Benutzerdefiniertes Feld {#findreplace-uc-customfield}

Sie definieren eine `Email Marketing (updated)` benutzerdefiniertes Feld. Sie verwenden die **[!UICONTROL SUCHEN UND ERSETZEN]** -Funktion zum Definieren einer Regel zum Suchen und Ersetzen aller Vorkommen von `email%20marketing` mit `email marketing`.

![[!DNL Find and Replace] Regel](assets/find-and-replace.png)

### Daten nach {#findreplace-uc-dataafter}

| Externes Marketing<br/>(benutzerdefiniertes Feld) |
|----|
| E-Mail-Marketing |
| E-Mail-Marketing |
| E-Mail-Marketing |
| E-Mail-Marketing |
| E-Mail-Marketing |

{style="table-layout:auto"}

+++


<!-- LOOKUP -->

### [!DNL Lookup]

Definiert einen Satz von Lookup-Werten, die durch entsprechende Werte ersetzt werden.

+++ Details


## Spezifikationen {#lookup-io}

| Eingabedatentyp | Eingabe | Eingeschlossene Operatoren | Limit | Ausgabe |
|---|---|---|:---:|---|
| <ul><li>Zeichenfolge</li><li>Numerisch</li><li>Datum</li></ul> | <ul><li>Sing-Feld</li><li>Suchdatei<ul><li>Schlüsselspalte</li><li>Neue Feldspalte</li></ul></li></ul> | <p>Nicht angegeben</p> | <p>5</p> | <p>Neues benutzerdefiniertes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall 1 {#lookup-uc1}

Sie verfügen über eine CSV-Datei, die eine Schlüsselspalte für `hotelID` und eine oder mehrere zusätzliche Spalten, die mit dem `hotelID`: `city`, `rooms`, `hotel name`.
Sie erfassen die Hotel-ID in einer Dimension, möchten jedoch eine aus der `hotelID` in der CSV-Datei.

**Struktur und Inhalt von CSV-Dateien**

| hotelID | city | Zimmer | Hotelname |
|---|---|---:|---|
| SLC123 | Salt Lake City | 40 | SLC-Innenstadt |
| LAX342 | Los Angels | 60 | LA Airport |
| SFO456 | San Francisco | 75 | Market Street |

{style="table-layout:auto"}

**Aktueller Bericht**

| Hotel-ID | Produktansichten |
|---|---:|
| SLC123 | 200 |
| LX342 | 198 |
| SFO456 | 190 |

{style="table-layout:auto"}


**Gewünschter Bericht**

| Hotelname | Produktansichten |
|----|----:|
| SLC-Innenstadt | 200 |
| LA Airport | 198 |
| Market Street | 190 |

{style="table-layout:auto"}

### Daten vor {#lookup-uc1-databefore}

| Hotel-ID |
|----|
| SLC123 |
| LAX342 |
| SFO456 |

{style="table-layout:auto"}


### Benutzerdefiniertes Feld {#lookup-uc1-customfield}

Sie definieren eine `Hotel Name` benutzerdefiniertes Feld. Sie verwenden die **[!UICONTROL ** SUCHEN **]** -Funktion, um eine Regel zu definieren, mit der Sie die Werte der **[!UICONTROL ** Hotel-ID **]** und durch neue Werte ersetzen.

![[!DNL Lookup] Regel 1](assets/lookup-1.png)

### Daten nach {#lookup-uc1-dataafter}

| Hotelname |
|----|
| SLC-Innenstadt |
| LA Airport |
| Market Street |

{style="table-layout:auto"}


## Anwendungsfall 2 {#lookup-uc2}

Sie haben URLs anstelle des benutzerfreundlichen Seitennamens für mehrere Seiten erfasst. Diese gemischte Sammlung von Werten unterbricht die Berichterstellung.

### Daten vor {#lookup-uc2-databefore}

| Seitenname |
|---|
| Startseite |
| Flugsuche |
| `http://www.adobetravel.ca/Hotel-Search` |
| `https://www.adobetravel.com/Package-Search` |
| Angebote und Angebote |
| `http://www.adobetravel.ca/user/reviews` |
| `https://www.adobetravel.com.br/Generate-Quote/preview` |

{style="table-layout:auto"}

### Benutzerdefiniertes Feld {#lookup-uc2-customfield}

Sie definieren eine `Page Name (updated)` benutzerdefiniertes Feld. Sie verwenden die **[!UICONTROL ** SUCHEN **]** -Funktion, um eine Regel zu definieren, mit der Sie Werte Ihrer vorhandenen **[!UICONTROL ** Seitenname **]** und ersetzen Sie sie durch die aktualisierten richtigen Werte.

![[!DNL Lookup] Regel 2](assets/lookup-2.png)

### Daten nach {#lookup-uc2-dataafter}

| Seitenname (aktualisiert) |
|---|
| Startseite |
| Flugsuche |
| Hotelsuche |
| Paketsuche |
| Angebote und Angebote |
| Überprüfungen |
| Anführungszeichen erstellen |

+++

<!-- URL PARSE -->

### [!DNL URL Parse]

Analysiert verschiedene Teile einer URL, einschließlich Protokoll-, Host-, Pfad- oder Abfrageparametern.

+++ Details

## Spezifikationen {#urlparse-io}

| Eingabedatentyp | Eingabe | Eingeschlossene Operatoren | Limit | Ausgabe |
|---|---|---|:---:|---|
| <ul><li>Zeichenfolge</li></ul> | <ul><li>Sing-Feld</li><li>Parsing-Option<ul><li>Protokoll abrufen</li><li>Host abrufen</li><li> Pfad abrufen</li><li>Wert der Abfrage abrufen<ul><li>Abfrageparameter</li></ul></li><li>Hash-Wert abrufen</li></ul></li></ul></li></ul> | <p>Nicht angegeben</p> | <p>5</p> | <p>Neues benutzerdefiniertes Feld</p> |

{style="table-layout:auto"}


## Anwendungsfall 1 {#urlparse-uc1}

Sie möchten die Referrer-Domäne aus der Referrer-URL nur als Teil des Regelsatzes eines Marketing-Kanals verwenden.

### Daten vor {#urlparse-uc1-databefore}

| Verweisende URL |
|----|
| `https://www.google.com/` |
| `https://duckduckgo.com/` |
| `https://t.co/` |
| `https://l.facebook.com/` |

{style="table-layout:auto"}

### Benutzerdefiniertes Feld {#urlparse-uc1-customfield}

Sie definieren eine  `Referring Domain` benutzerdefiniertes Feld. Sie verwenden die **[!UICONTROL ** URL PARSE **]** -Funktion, um eine Regel zum Abrufen des Hosts aus dem **Verweisende URL** und speichern Sie sie im neuen benutzerdefinierten Feld.

![[!DNL Url Parse] Regel 1](assets/url-parse-1.png)

### Daten nach {#urlparse-uc1-dataafter}

| Referrer Domain |
|----|
| www.google.com |
| duckduckgo.com |
| t.co |
| l.facebook.com |

{style="table-layout:auto"}


## Anwendungsfall 2 {#urlparse-uc2}

Sie möchten den Wert der `cid` -Parameter einer Abfragezeichenfolge in einer Seiten-URL als Teil der Ausgabe eines abgeleiteten Trackingcode-Berichts.

### Daten vor {#urlparse-uc2-databefore}

| Seiten-URL |
|----|
| `https://www.adobe.com/?cid=abc123` |
| `https://www.adobe.com/?em=email1234&cid=def123` |
| `https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123` |

{style="table-layout:auto"}

### Benutzerdefiniertes Feld {#urlparse-uc2-customfield}

Sie definieren eine `Query String CID` benutzerdefiniertes Feld. Sie verwenden die **[!UICONTROL ** URL PARSE **]** -Funktion, um eine Regel zum Abrufen des Werts des Abfragezeichenfolgenparameters in der Seiten-URL zu definieren, wobei `cid` als Abfrageparameter. Der Ausgabewert wird im neuen benutzerdefinierten Feld gespeichert.

![[!DNL Url Parse] Regel 2](assets/url-parse-2.png)

### Daten nach {#urlparse-uc2-dataafter}

| Abfragezeichenfolgen-CID |
|----|
| abc123 |
| def123 |
| xyz123 |

{style="table-layout:auto"}

+++
