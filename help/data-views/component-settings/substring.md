---
title: Einstellungen der Teilstring-Komponenten
description: Verwenden Sie eine Teilmenge einer Zeichenfolge als Dimensionselemente.
solution: Customer Journey Analytics
feature: Data Views
exl-id: a763027e-68f7-4f0a-8082-85db5283c8e3
source-git-commit: e1d8cffac907e1043d18b1939585108ce95a0fda
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 7%

---

# [!UICONTROL Substring] Komponenteneinstellungen

[!UICONTROL Substring] Komponenteneinstellungen ermöglichen es Ihnen, mehrere Methoden zur Manipulation von Zeichenfolgen durchzuführen, um die gewünschten Dimensionselemente in Berichten abzurufen.

[!UICONTROL Substring] ist nur für Dimensionen verfügbar und rückwirkend für die Daten, auf die sie angewendet wird. Es handelt sich um eine sofortige Datenumwandlung, die vor der Anwendung von Filtern oder anderen Analysevorgängen erfolgt.

![Teilzeichenfolgen-Einstellungen](../assets/substring-settings.png)

## Von links/rechts

Nehmen Sie einen Teil einer Zeichenfolge basierend auf ihrer Position am Anfang oder Ende einer Zeichenfolge. **[!UICONTROL Von links]** und **[!UICONTROL Von rechts]** -Methoden bieten zwei Dropdown-Listen: **[!UICONTROL Von]** (wo die Ausgabe beginnt) und **[!UICONTROL nach]** (wo die Ausgabe endet).

* **[!UICONTROL String Start]**: Der Anfang der Zeichenfolge.
* **[!UICONTROL String End]**: Das Ende der Zeichenfolge.
* **[!UICONTROL Position]**: Eine statische Anzahl von Zeichen von links oder rechts, je nach Methode.
* **[!UICONTROL Zeichenfolge]**: Ordnen Sie ein Zeichen oder eine Folge von Zeichen zu, um den Anfang oder das Ende einer Zeichenfolge anzugeben. In diesem Dropdown-Menü werden auch zusätzliche Optionen angezeigt:
   * **[!UICONTROL Übereinstimmung]**: Die zuzuordnende Zeichenfolge. Wenn die Eingabe nicht mit diesem Feld übereinstimmt, [Keine Wertoptionen](no-value-options.md) gelten.
   * **[!UICONTROL Index]**: Die **[!UICONTROL Übereinstimmung]** -Kriterien in einer Zeichenfolge mehrmals vorkommen. Diese Ganzzahl bestimmt, welche Übereinstimmung die Ausgabe starten oder beenden soll, je nach Methode. Beispiel: ein Index von `1` stellt die erste Übereinstimmung dar. Wenn der Index höher ist als die Anzahl der verfügbaren Übereinstimmungen, [Keine Wertoptionen](no-value-options.md) gelten.
   * **[!UICONTROL Zeichenfolge einschließen]**: Ein Kontrollkästchen mit **[!UICONTROL Übereinstimmung]** Zeichenfolge in der Ausgabe, falls aktiviert.
* **[!UICONTROL Länge]**: Eine Ganzzahl, die die Zeichenzahl angibt, die nach der Startposition der Ausgabe eingefügt werden soll. Nur verfügbar unter **[!UICONTROL nach]** Dropdown-Liste.

## Trennzeichen

Verwenden Sie diese Methode für Felder, die ein Trennzeichen verwenden, um mehrere Zeichenfolgenwerte zu trennen. Sie können entweder ein einzelnes Element extrahieren, das als Ausgabe verwendet werden soll, oder die Zeichenfolge in ein Objekt-Array-Schemaelement konvertieren.

* **[!UICONTROL Kriterium]**: Wie Sie die durch Trennzeichen getrennte Werteliste behandeln möchten.
   * **[!UICONTROL Von links]**: Beginnen Sie am Anfang der durch Trennzeichen getrennten Liste und zählen Sie nach vorne.
   * **[!UICONTROL Von rechts]**: Beginnen Sie am Ende der durch Trennzeichen getrennten Liste und zählen Sie rückwärts.
   * **[!UICONTROL In Array konvertieren]**: Behandeln Sie diese Dimension so, als wäre sie ein Objekt-Array-Schemaelement.
* **[!UICONTROL Trennzeichen]**: Das Trennzeichen, das vom Feld verwendet wird.
* **[!UICONTROL Index]**: Nur vorhanden, wenn das Kriterium von links/rechts ist. Die Elementnummer, als ob sie sich in einem Array befände. Wenn die Zeichenfolgeneingabe beispielsweise `"Fox,Turtle,Rabbit,Wolf"` mit einem Index von 3 ist die Ausgabe `"Rabbit"`. Wenn der Index höher ist als die Anzahl der durch Trennzeichen getrennten Elemente, [Keine Wertoptionen](no-value-options.md) gelten.

## URL-Analyse

Zur Verwendung mit Feldern, die URLs enthalten. Verwenden der Beispiel-URL `https://example.com/store/index.html?cid=campaign#cart`, sind die folgenden Optionen verfügbar:

* **[!UICONTROL Protokoll abrufen]**: Rufen Sie das Protokoll der URL ab. Zum Beispiel `"https://"`.
* **[!UICONTROL Hosting abrufen]**: Rufen Sie den Host der URL ab. Zum Beispiel `"example.com"`.
* **[!UICONTROL Pfad abrufen]**: Rufen Sie den Pfad der URL ab. Zum Beispiel `"store/index.html"`.
* **[!UICONTROL Abfragezeichenfolgenwert abrufen]**: Rufen Sie den Wert aus einer einzelnen Abfragezeichenfolge ab. Platzieren Sie den gewünschten Abfragezeichenfolgenparameter im **[!UICONTROL Abfrageschlüssel]** -Feld. Wenn die obige URL mit der `"cid"` Abfrageschlüssel, die Ausgabe ist `"campaign"`.
* **[!UICONTROL Hashwert abrufen]**: Rufen Sie den Hash-Wert der URL ab. Zum Beispiel `"cart"`.

Wenn die Eingabe keine gültige URL ist oder die gewünschte URL-Komponente nicht vorhanden ist, [Keine Wertoptionen](no-value-options.md) gelten.

## Kürzen

Entfernen Sie Leerzeichen oder Sonderzeichen aus der Zeichenfolge.

* **[!UICONTROL Zuschneiden von Leerzeichen]**: Ein Kontrollkästchen, mit dem alle Leerzeichen am Anfang und am Ende der Zeichenfolge entfernt werden, falls aktiviert.
* **[!UICONTROL Sonderzeichen beschneiden]**: Ein Kontrollkästchen, das eine **[!UICONTROL Sonderzeichen]** Eingabefeld, falls aktiviert. Alle Zeichen in diesem Feld werden aus der Ausgabe entfernt. Multi-Byte-Zeichen werden nicht unterstützt.

## Regex

Wenden Sie reguläre Ausdrücke auf eine Dimension an, um den gewünschten Wert abzurufen.

* **[!UICONTROL Regex]**: Die Formel für reguläre Ausdrücke.
* **[!UICONTROL Ausgabeformat]**: Ein optionales Feld, mit dem Sie Text hinzufügen oder die Regex-Subgruppenausgabe neu anordnen können. Wenn dieses Feld leer ist, ist die Zeichenfolgenausgabe der ausgewertete Regex-Ausdruck.
* **[!UICONTROL Groß-/Kleinschreibung]**: Ein Kontrollkästchen, das erzwingt, dass beim regulären Ausdruck die Groß-/Kleinschreibung beachtet wird, falls aktiviert.

CJA verwendet eine Untergruppe der Perl-Regex-Syntax. Wenn die Eingabe nicht mit dem regulären Ausdruck und der **[!UICONTROL Ausgabeformat]** leer ist, [Keine Wertoptionen](no-value-options.md) gelten. Die folgenden Ausdrücke werden unterstützt:

| Ausdruck | Beschreibung |
| --- | --- |
| `a` | Ein einzelnes Zeichen `a`. |
| `a|b` | Ein einzelnes Zeichen `a` oder `b`. |
| `[abc]` | Ein einzelnes Zeichen `a`, `b`oder `c`. |
| `[^abc]` | Beliebiges einzelnes Zeichen, außer `a`, `b`oder `c`. |
| `[a-z]` | Jedes einzelne Zeichen im Bereich von `a`-`z`. |
| `[a-zA-Z0-9]` | Jedes einzelne Zeichen im Bereich von `a`-`z`, `A`-`Z`oder Ziffern `0`-`9`. |
| `^` | Entspricht dem Zeilenanfang. |
| `$` | Entspricht dem Ende der Zeile. |
| `\A` | Beginn der Zeichenfolge. |
| `\z` | Ende der Zeichenfolge. |
| `.` | Entspricht einem beliebigen Zeichen. |
| `\s` | Beliebiges Whitespace-Zeichen. |
| `\S` | Beliebiges Zeichen, außer Whitespace-Zeichen. |
| `\d` | Beliebige Ziffer. |
| `\D` | Beliebiges Zeichen, außer Ziffern. |
| `\w` | Alle Buchstaben, Zahlen oder Unterstriche. |
| `\W` | Beliebiges Zeichen, das nicht in Wörtern zulässig ist. |
| `\b` | Beliebige Wortgrenze. |
| `\B` | Jedes Zeichen, das keine Wortgrenze ist. |
| `\<` | Wortbeginn. |
| `\>` | Ende des Wortes. |
| `(...)` | Alles erfassen zwischen. |
| `(?:...)` | Erfassung ohne Kennzeichnung. Verhindert, dass auf die Übereinstimmung in der Ausgabezeichenfolge verwiesen wird. |
| `a?` | Null oder eins von `a`. |
| `a*` | Null oder mehr von `a`. |
| `a+` | Ein oder mehr von `a`. |
| `a{3}` | Genau 3 von `a`. |
| `a{3,}` | 3 oder mehr von `a`. |
| `a{3,6}` | Zwischen 3 und 6 von `a`. |

Output-Platzhalter werden ebenfalls unterstützt. Sie können diese Sequenzen im **[!UICONTROL Ausgabeformat]** beliebig oft und in beliebiger Reihenfolge, um die gewünschte Zeichenfolgenausgabe zu erreichen.

| Ausgabe-Platzhaltersequenz | Beschreibung |
| --- | --- |
| `$&` | Gibt aus, was dem gesamten Ausdruck entsprach. |
| `$n` | Gibt aus, was mit dem n-ten Unterausdruck übereinstimmt. Beispiel: `$1` gibt den ersten Unterausdruck aus. |
| ``$` `` | Gibt den Text zwischen dem Ende der letzten gefundenen Übereinstimmung (oder dem Anfang des Textes aus, wenn keine vorherige Übereinstimmung gefunden wurde) und dem Beginn der aktuellen Übereinstimmung aus. |
| `$+` | Gibt aus, was mit dem letzten markierten Unterausdruck im regulären Ausdruck übereinstimmt. |
| `$$` | Gibt das Zeichenfolgenzeichen aus `"$"`. |

Im Folgenden finden Sie ein Video zum Thema Binden von Dimensionen:

>[!VIDEO](https://video.tv.adobe.com/v/342694/?quality=12)
