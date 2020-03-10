---
title: Kombinierte Datensätze
description: Erfahren Sie, wie CJA durch Kombinieren von Datensätzen eine Verbindung herstellt.
translation-type: tm+mt
source-git-commit: f9cdcb8a6efe688d553929c3081f3239e0691cd9

---


# Kombinierte Datensätze

Wenn Sie eine Verbindung herstellen, kombiniert CJA alle Schema und Datensätze in einem Datensatz. Dieser &quot;kombinierte Datensatz&quot;wird von CJA zum Berichte verwendet. Wenn Sie mehrere Schema oder Datensätze in eine Verbindung einschließen:

* Schema werden kombiniert. Duplikat-Schema-Felder werden zusammengeführt.
* Die Spalte &quot;Personen-ID&quot;jedes Datensatzes wird unabhängig von ihrem Namen in eine Spalte zusammengefasst. Diese Spalte bildet die Grundlage für die Identifizierung individueller Besucher in CJA.
* Zeilen werden basierend auf dem Zeitstempel verarbeitet.

## Beispiel

Siehe folgendes Beispiel. Sie haben zwei Datensätze, von denen jedes unterschiedliche Felder mit unterschiedlichen Daten enthält.

> [!NOTE] Adobe Experience Platform speichert Zeitstempel normalerweise in Unix-Millisekunden. Für die Lesbarkeit in diesem Beispiel werden Datum und Uhrzeit verwendet.

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

Wenn Sie eine Verbindung mit diesen beiden Datensätzen erstellen, wird die folgende Tabelle zum Berichte verwendet.

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

Dieser kombinierte Datensatz wird in Berichte verwendet. Es spielt keine Rolle, aus welchem Datensatz eine Zeile stammt. CJA behandelt alle Daten so, als wären sie im selben Datensatz. Wenn in beiden Datensätzen eine übereinstimmende Personen-ID angezeigt wird, gilt der gleiche eindeutige Besucher. Wenn in beiden Datensätzen mit einem Zeitstempel innerhalb von 30 Minuten eine übereinstimmende Personen-ID angezeigt wird, werden sie als Teil derselben Sitzung betrachtet.

Dieses Konzept gilt auch für die Zuordnung. Es spielt keine Rolle, aus welchem Datensatz eine Zeile stammt. Die Zuordnung funktioniert genau so, als kämen alle Ereignis aus einem einzigen Datensatz. Verwendung der oben stehenden Tabellen als Beispiel:

Wenn Ihre Verbindung nur die erste Tabelle und nicht die zweite enthält, zeigt das Ziehen eines Berichts mit der `string_color` Dimension und `metric_a` Metrik unter Verwendung der Last Touch-Zuordnung Folgendes an:

| string_color | metric_a |
| --- | --- |
| Blau | 5 |
| „Nicht angegeben“ | 6 |
| Rot | 2 |

Wenn Sie jedoch beide Tabellen in Ihrer Verbindung eingeschlossen haben, ändert sich die Zuordnung, da sie in beiden Datensätzen enthalten `user_847` ist. Eine Zeile aus den zweiten Datensatzattributen `metric_a` in &quot;Gelb&quot;, in der sie zuvor nicht angegeben wurden:

| string_color | metric_a |
| --- | --- |
| Gelb | 6 |
| Rot | 2 |
| Blau | 3 |
