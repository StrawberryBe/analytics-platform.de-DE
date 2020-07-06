---
title: Kombinierte Datensätze
description: Erfahren Sie, wie CJA durch Kombinieren von Datensätzen eine Verbindung herstellt.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 100%

---


# Kombinierte Datensätze

Wenn Sie eine Verbindung herstellen, kombiniert CJA alle Schemata und Datensätze zu einem Datensatz. Dieser „kombinierte Datensatz“ wird von CJA für die Berichterstellung verwendet. Wenn Sie mehrere Schemata oder Datensätze in eine Verbindung einschließen:

* Schemata werden kombiniert. Doppelte Schemafelder werden zusammengeführt.
* Die Spalte „Personen-ID“ jedes Datensatzes wird unabhängig von ihrem Namen in eine Spalte zusammengefasst. Diese Spalte bildet die Grundlage für die Identifizierung von Unique Visitors in CJA.
* Zeilen werden anhand des Zeitstempels verarbeitet.

## Beispiel

Siehe folgendes Beispiel. Sie haben zwei Datensätze mit jeweils unterschiedlichen Feldern, die unterschiedliche Daten enthalten.

>[!NOTE]
>
>Adobe Experience Platform speichert Zeitstempel normalerweise in Unix-Millisekunden. Zur besseren Lesbarkeit werden in diesem Beispiel Datum und Uhrzeit verwendet.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |
| `user_310` | `1 Jan 7:04 AM` |  |  | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  | `3` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` |  |  | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  | `Triangle` | `3.1` |

Wenn Sie eine Verbindung mit diesen beiden Datensätzen erstellen, wird die folgende Tabelle für die Berichterstellung verwendet.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |  |  |
| `user_310` | `1 Jan 7:04 AM` |  |  |  | `2` |  |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  |  | `3` |  |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` |  | `Circle` |  | `8.5` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` |  | `4` |  |
| `user_847` | `2 Jan 12:44 PM` |  |  |  | `2` |  |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` |  | `Square` |  | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  |  | `Triangle` |  | `3.1` |

Dieser „kombinierte Datensatz“ wird für die Berichterstellung verwendet. Es spielt keine Rolle, aus welchem Datensatz eine Zeile stammt. CJA behandelt alle Daten so, als ob sie sich im selben Datensatz befinden. Wenn in beiden Datensätzen eine übereinstimmende Personen-ID angezeigt wird, werden sie als derselbe Unique Visitor betrachtet. Wenn eine übereinstimmende Personen-ID mit einem Zeitstempel innerhalb von 30 Minuten in beiden Datasets erscheint, werden sie als Teil derselben Sitzung betrachtet.

Dieses Konzept gilt auch für die Attribution. Es spielt keine Rolle, aus welchem Datensatz eine Zeile stammt. Die Attribution funktioniert genau so, als ob alle Ereignisse aus einem einzigen Datensatz stammen. Anhand dem Beispiel der oben stehenden Tabellen:

Wenn Ihre Verbindung nur die erste Tabelle und nicht die zweite Tabelle enthält, wird beim Abrufen eines Berichts unter Verwendung der `string_color`-Dimension und der `metric_a`-Metrik und der Attribution „Letztkontakt“ Folgendes angezeigt:

| string_color | metric_a |
| --- | --- |
| Nicht angegeben | 6 |
| Blau | 3 |
| Rot | 2 |

Wenn Sie jedoch beide Tabellen in Ihrer Verbindung eingeschlossen haben, ändert sich die Attribution, da `user_847` in beiden Datensätzen enthalten ist. Eine Zeile aus den zweiten Datensatz weist `metric_a` „Gelb“ zu. Diese Zuordnung wurde im vorherigen Fall nicht angegeben:

| string_color | metric_a |
| --- | --- |
| Gelb | 6 |
| Blau | 3 |
| Rot | 2 |
