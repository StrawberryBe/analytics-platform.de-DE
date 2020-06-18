---
title: Objekte mit Arrays
description: Verstehen Sie, wie CJA Berichte zu Datenhierarchien erstellt.
translation-type: tm+mt
source-git-commit: 52fecf03cc503fa59101f6280c671e153e2129e9
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---


# Objekte mit Arrays

Bei einigen Plattformfeldern kann es sich um Objektarchiven handeln. Eines der häufigsten Beispiele wäre ein Einkaufswagen, der mehrere Produkte enthält. Jedes Produkt hat einen Namen, eine SKU, eine Kategorie, einen Preis, eine Menge und andere Dimensionen, die Sie verfolgen möchten. Alle diese Facetten haben unterschiedliche Anforderungen, müssen jedoch alle in denselben Treffer passen.

In früheren Versionen von Adobe Analytics wurde diese Leistung mit der `products` Variablen ausgeführt. Es handelte sich um eine verkettete Zeichenfolge, die durch Semikolons (`;`) getrennt war, um die Facetten eines Produkts zu trennen, während durch Kommas (`,`) getrennte Produkte definiert wurden. Es war die einzige Variable mit begrenzter Unterstützung von &quot;object arrays&quot;. Variablen mit mehreren Werten, wie z. B. Liste vars, könnten das Äquivalent zu Arrays unterstützen, &quot;object arrays&quot;konnten jedoch nicht unterstützt werden. CJA erweitert dieses Konzept durch die Unterstützung willkürlich tiefer Hierarchien in einer Datenzeile, eine Funktion, die in einer früheren Version von Adobe Analytics nicht verfügbar ist.

## Gleiches Trefferbeispiel

Der folgende Treffer ist ein JSON-Objekt, das einen Kauf eines Kunden aus einer Waschmaschine und Trockner darstellt.

```json
{
  "ID": "1", 
  "product": [
    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
  ], 
  "timestamp": 1534219229
}
```

Beim Erstellen einer Ansicht sind die folgenden Dimensionen und Metriken verfügbar (je nach Schema):

* **Dimensionen:**
   * ID
   * Produkt: SKU
   * Produkt: name
   * Produkt: order_id
   * Produkt: Garantie: Abdeckung
   * Produkt: Garantie: length
   * Produkt: Garantie: name
   * Produkt: Garantie: type
* **Metriken:**
   * Produkt: Aufträge
   * Produkt: Einheiten
   * Produkt: Umsatz
   * Produkt: Garantie
   * Produkt: Garantie: Umsatz

### Gleiche Trefferbeispiele (Verhalten von Berichten)

Die folgenden Tabellen zeigen Workspace-Berichte mit einigen Dimensions- und Metrikkombinationen.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA untersucht selektiv die Dimension und die Metriken des Objekts, basierend auf der Tabelle.

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
+      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
+      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
      "warranty": [
        {
          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
          "revenue": 200
        }, 
        {
          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
        }
      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
+      "name": "LG Dryer 2000", 
+      "orders": 1, 
+      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Wenn Sie nur über Garantieinnahmen berichten möchten, würde Ihr Projekt in etwa wie folgt aussehen:

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

CJA untersucht die folgenden Teile des Treffers, um den Bericht zu generieren:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
+          "coverage": "full coverage", 
          "length": "2 year", 
          "name": "LG 2000 standard", 
          "orders": 1, 
+          "revenue": 200
+        }, 
+        {
+          "coverage": "extended", 
          "length": "1 year", 
          "orders": 1, 
+          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
      "orders": 1, 
      "revenue": 500, 
      "units": 1
    }
+  ], 
+  "timestamp": 1534219229
+}
```

Da der Trockner keine Garantie enthielt, ist er nicht in der Tabelle enthalten.

Da Sie jede Dimension mit einer beliebigen Metrik kombinieren können, zeigt die folgende Tabelle, wie Daten mit nicht angegebenen Dimensionswerten aussehen würden:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Eine Produktbestellung existiert ohne einen Garantienamen, der mit ihr verknüpft ist. Daher wird der Dimensionswert auf &quot;Nicht angegeben&quot;gesetzt. Dasselbe gilt auch für die Bestellung der Produktgarantie:

```diff
{
  "ID": "1", 
+  "product": [
+    {
      "SKU": "1234", 
      "category": "Washing Machines", 
      "name": "LG Washing Machine 2000", 
+      "orders": 1, 
      "revenue": 1600, 
      "units": 1,
      "order_id":"abc123", 
+      "warranty": [
+        {
          "coverage": "full coverage", 
          "length": "2 year", 
+          "name": "LG 2000 standard", 
+          "orders": 1, 
          "revenue": 200
+        }, 
+        {
          "coverage": "extended", 
          "length": "1 year", 
+          "orders": 1, 
          "revenue": 50, 
          "type": "LG 2000 addon"
+        }
+      ]
+    }, 
+    {
      "SKU": "4567", 
      "category": "Dryers", 
      "name": "LG Dryer 2000", 
+      "orders": 1, 
      "revenue": 500, 
      "units": 1
+    }
+  ], 
+  "timestamp": 1534219229
+}
```

Notieren Sie die Bestellungen, die keinen Namen haben, der mit ihnen verbunden ist. Dies sind die Bestellungen, die dem Dimensionswert &quot;Nicht angegeben&quot;zugeordnet werden.

### Kombinieren von Metriken

CJA kombiniert keine ähnlich benannten Metriken nativ, wenn sie sich auf unterschiedlichen Objektebenen befinden.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

Sie können jedoch eine berechnete Metrik erstellen, die die gewünschten Metriken kombiniert:

Berechnete Metrik &quot;Gesamtumsatz&quot;: `[product : revenue] + [product : warranty : revenue]`

Die Anwendung dieser berechneten Metrik zeigt die gewünschten Ergebnisse an:

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |

## Persistenzbeispiele

