---
title: Verwenden von Objekt-Arrays
description: Hier wird erklärt, wie CJA-Berichte Datenhierarchien darstellen.
exl-id: 59318da7-5408-4a9d-82aa-8bcbec7f7364
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: ht
source-wordcount: '418'
ht-degree: 100%

---

# Verwenden von Objekt-Arrays

Manche Plattformschemas können Objekt-Arrays enthalten. Eines der häufigsten Beispiele ist ein Warenkorb, der mehrere Produkte enthält. Jedes Produkt hat einen Namen, eine Produktnummer, eine Kategorie, einen Preis, eine Menge und andere Dimensionen, die Sie verfolgen möchten. Alle diese Faktoren haben unterschiedliche Anforderungen, müssen jedoch alle in denselben Hit passen.

In früheren Versionen von Adobe Analytics wurde dies durch die `products`-Variable erreicht. Dabei handelte es sich um eine verkettete Zeichenfolge, in der die Bestandteile eines Produkts durch Semikolons (`;`) getrennt waren, während die Produkte durch Kommas (`,`) getrennte waren. Dies war die einzige Variable mit eingeschränkter Unterstützung von „Objekt-Arrays“. Variablen mit mehreren Werten, wie z. B. Listenvariablen, konnten das Äquivalent zu Arrays unterstützen, sie konnten aber keine „Objekt-Arrays“ unterstützen. CJA erweitert dieses Konzept durch die Unterstützung beliebig tiefer Hierarchien in einer Datenzeile. Diese Funktion war in keiner früheren Version von Adobe Analytics verfügbar.

## Beispiel für gleiche Hits

Der folgende Hit ist ein JSON-Objekt, das den Kauf eines Kunden einer Waschmaschine und eines Trockners darstellt.

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

Beim Erstellen einer Datenansicht sind die folgenden Dimensionen und Metriken verfügbar (je nach Schema):

* **Dimensionen:**
   * ID
   * Produkt: SKU
   * Produkt: Name
   * Produkt: Bestell-ID
   * Produkt: Garantie: Gültigkeit
   * Produkt: Garantie: Länge
   * Produkt: Garantie: Name
   * Produkt: Garantie: Typ
* **Metriken:**
   * Produkt: Bestellungen
   * Produkt: Einheiten
   * Produkt: Umsatz
   * Produkt: Garantie
   * Produkt: Garantie: Umsatz

### Beispiele für gleiche Hits (Berichtsverhalten)

Unter Verwendung des obigen Hits zeigen die folgenden Tabellen Arbeitsbereich-Berichte mit einigen Dimensions- und Metrikkombinationen.

| `product : name` | `product : orders` | `product : revenue` |
| --- | --- | --- |
| `LG Washing Machine 2000` | `1` | `1600` |
| `LG Dryer 2000` | `1` | `500` |
| `Total` | `1` | `2100` |

CJA untersucht basierend auf der Tabelle selektiv die Dimension und die Metriken des Objekts.

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

Wenn Sie nur über Garantieumsätze berichten möchten, sieht Ihr Projekt in etwa wie folgt aus:

| `product : warranty : coverage` | `product : warranty : revenue` |
| --- | --- |
| `full coverage` | `200` |
| `extended` | `50` |
| `Total` | `250` |

CJA zieht für die Erstellung des Berichts diese Teile des Hits heran:

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

Da der Trockner keine Garantie hat, ist er nicht in der Tabelle enthalten.

Da Sie jede Dimension mit einer beliebigen Metrik kombinieren können, zeigt die folgende Tabelle, wie Daten mit nicht spezifizierten Dimensionselementen aussehen würden:

| `product : warranty : name` | `product : orders` | `product : warranty : orders` |
| --- | --- | --- |
| `LG 2000 standard` | `1` | `1` |
| `Unspecified` | `2` | `1` |
| `Total` | `2` | `2` |

Eine Produktbestellung existiert ohne einen verknüpften Garantienamen. Daher wird das Dimensionselement „Nicht spezifiziert“ zugeschrieben. Dasselbe gilt auch für die Bestellung der Produktgarantie:

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

Achten Sie auf die Bestellungen, die keinen mit ihnen verbundenen Namen haben. Dies sind die Bestellungen, die dem Dimensionselement „Nicht spezifiziert“ zugeordnet werden.

### Kombinieren von Metriken

CJA kombiniert nativ keine ähnlich benannten Metriken, wenn sie sich auf unterschiedlichen Objektebenen befinden.

| `product : category` | `product : revenue` | `product : warranty : revenue` |
| --- | --- | --- |
| `Washing Machines` | `1600` | `250` |
| `Dryers` | `500` | `0` |
| `Total` | `2100` | `250` |

Sie können jedoch eine berechnete Metrik erstellen, die die gewünschten Metriken kombiniert:

Berechnete Metrik „Gesamtumsatz“: `[product : revenue] + [product : warranty : revenue]`

Durch Anwendung dieser berechneten Metrik werden die gewünschten Ergebnisse angezeigt:

| `product : warranty : name` | `Total revenue (calculated metric)` |
| --- | --- |
| `Washing Machines` | `1850` |
| `Dryers` | `500` |
| `Total` | `2350` |
