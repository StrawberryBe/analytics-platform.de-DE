---
title: Verwenden von Bindungsdimensionen und Metriken in CJA
description: Ordnen Sie den Objekt-Arrays Dimensionen für die komplexe Persistenzanalyse zu.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
source-git-commit: 38c10e395b816d812d30f0698dc821ee0ea5c9b1
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 2%

---

# Verwenden von Bindungsdimensionen und Metriken in CJA

Customer Journey Analytics bietet mehrere Möglichkeiten, Dimensionswerte über den Treffer hinaus beizubehalten, für den sie festgelegt wurden. Eine der Persistenzmethoden, die Adobe anbietet, wird als Bindung bezeichnet. In früheren Versionen von Adobe Analytics wurde dieses Konzept als Merchandising bezeichnet.

Sie können Bindungsdimensionen mit Ereignisdaten der obersten Ebene verwenden. Dieses Konzept empfiehlt sich jedoch am besten bei der Arbeit mit [Objekte-Arrays](object-arrays.md). Sie können eine Dimension einem Teil eines Objekt-Arrays zuordnen, ohne sie auf alle Attribute in einem bestimmten Ereignis anzuwenden. Sie können beispielsweise einen Suchbegriff einem Produkt in Ihrem Warenkorb-Objekt-Array zuordnen, ohne diesen Suchbegriff an das gesamte Ereignis zu binden.

## Beispiel 1: Bindungsdimensionen verwenden, um zusätzliche Produktattribute einem Kauf zuzuordnen

Sie können Dimensionselemente innerhalb eines Objekt-Arrays an eine andere Dimension binden. Wenn das gebundene Dimensionselement angezeigt wird, ruft CJA die gebundene Dimension zurück und fügt sie im Ereignis für Sie ein. Betrachten Sie die folgende Journey:

1. Ein Besucher sieht sich eine Produktseite auf einer Waschmaschine an.

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "color": "white",
               "type": "front loader",
           },
       ],
       "timestamp": 1534219229
   }
   ```

1. Der Besucher sieht sich dann eine Produktseite auf einem Trockner an.

   ```json
   {
       "PersonID": "1",
       "product_views": 1,
       "product": [
           {
               "name": "Dryer 2000",
               "color": "neon orange",
           },
       ],
       "timestamp": 1534219502
   }
   ```

1. Letztlich tätigen sie einen Kauf. Die Farbe der einzelnen Produkte war nicht im Kaufereignis enthalten.

   ```json
   {
       "PersonID": "1",
       "orders": 1,
       "product": [
           {
               "name": "Washing Machine 2000",
               "price": 1600,
           },
           {
               "name": "Dryer 2000",
               "price": 499
           }
       ],
       "timestamp": 1534219768
   }
   ```

Wenn Sie den Umsatz nach Farbe ohne Bindungsdimension betrachten möchten, wird die Dimension `product.color` Beibehaltung und fehlerhafte Zuordnung der Farbe des Trockners:

| product.color | Umsatz |
| --- | --- |
| Neonorange | 2099 |

Sie können den Data View Manager aufrufen und die Produktfarbe an den Produktnamen binden:

![Binding-Dimension](assets/binding-dimension.png)

Wenn Sie dieses Persistenzmodell festlegen, nimmt Adobe den Produktnamen bei jedem Festlegen der Produktfarbe zur Kenntnis. Wenn bei einem nachfolgenden Ereignis für diesen Besucher derselbe Produktname erkannt wird, wird auch die Produktfarbe übernommen. Dieselben Daten, wenn Sie die Produktfarbe an den Produktnamen binden, sehen in etwa wie folgt aus:

| product.color | Umsatz |
| --- | --- |
| weiß | 1600 |
| Neonorange | 499 |

## Beispiel 2: Bindungsmetriken verwenden, um Suchbegriffe mit einem Produktkauf zu verknüpfen

Eine der gängigsten Merchandising-Methoden in Adobe Analytics besteht darin, einen Suchbegriff an ein Produkt zu binden, sodass jeder Suchbegriff für das entsprechende Produkt angerechnet wird. Betrachten Sie die folgende Journey:

1. Ein Besucher gelangt zu Ihrer Site und sucht nach &quot;Boxhandschuhen&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "boxing gloves",
       "product": [
           {
               "name": "Beginner gloves",
               "color": "Red",
               "price": "25.69"
           },
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Professional gloves",
               "color": "Blue",
               "price": "224.99"
           }
       ]
   }
   ```

1. Sie finden ein Paar Handschuhe, die sie mögen, und fügen es zu ihrem Warenkorb hinzu.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           }
       ]
   }
   ```

1. Der Besucher sucht dann nach &quot;Tennisschläger&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "tennis racket",
       "product": [
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Women's open racket",
               "price": "49.99"
           },
           {
               "name": "Extreme racket",
               "price": "134.99"
           }
       ]
   }
   ```

1. Sie finden einen Schläger, den sie mögen, und fügen ihn ihrem Warenkorb hinzu.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           }
       ]
   }
   ```

1. Der Besucher sucht ein drittes Mal nach &quot;Schuhen&quot;.

   ```json
   {
       "PersonID": "1",
       "page_name": "Search results",
       "search": "1",
       "search_term": "shoes",
       "product": [
           {
               "name": "Men's walking shoes",
               "color": "Grey",
               "price": "54.95"
           },
           {
               "name": "Tennis shoes",
               "color": "White",
               "price": "42.59"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. Sie finden ein Paar Schuhe, die sie mögen, und fügen es zu ihrem Warenkorb hinzu.

   ```json
   {
       "PersonID": "1",
       "page_name": "Shopping cart",
       "cart_add": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

1. Der Besucher durchläuft den Checkout-Prozess und kauft diese drei Artikel.

   ```json
   {
       "PersonID": "1",
       "page_name": "Thank you for your purchase",
       "purchase": "1",
       "product": [
           {
               "name": "Tier 3 gloves",
               "color": "Black",
               "price": "89.99"
           },
           {
               "name": "Shock absorb racket",
               "price": "34.99"
           },
           {
               "name": "Skate shoes",
               "color": "Black",
               "price": "79.99"
           }
       ]
   }
   ```

Wenn Sie ein herkömmliches Zuordnungsmodell mit Suchbegriff verwenden, weisen alle drei Produkte den Umsatz nur einem einzigen Suchbegriff zu. Wenn Sie beispielsweise die erste Zuordnung mit der Suchbegriffdimension verwendet haben:

| search_term | Umsatz |
| --- | --- |
| Boxhandschuhe | 204,97 $ |

Wenn Sie die letzte Zuordnung mit der Suchbegriffdimension verwendet haben, weisen alle drei Produkte weiterhin den Umsatz einem einzelnen Suchbegriff zu:

| search_term | Umsatz |
| --- | --- |
| Schuhe | 204,97 $ |

Während dieses Beispiel nur einen Besucher enthält, können viele Besucher, die nach verschiedenen Elementen suchen, Suchbegriffe verschiedenen Produkten zuordnen, was es schwierig macht festzustellen, welche die besten Suchergebnisse tatsächlich sind.

Bei einer Bindungsdimension nimmt Adobe das Dimensionselement zur Kenntnis, an das es gebunden ist. Wenn derselbe Bindungswert in einem nachfolgenden Ereignis angezeigt wird, überträgt er das Dimensionselement, damit Sie ihm die gewünschte Metrik zuordnen können. In diesem Beispiel können wir die Bindungsdimension für search_term auf den Produktnamen setzen. Wenn wir diese Dimension im Datenansichtsmanager festlegen, müssen wir auch eine Bindungsmetrik festlegen, da sich die Bindungsdimension in einem Objekt-Array befindet. Eine Bindungsmetrik dient als Trigger für eine Bindungsdimension, sodass sie sich nur an Ereignisse bindet, bei denen die Bindungsmetrik vorhanden ist. In dieser Beispielimplementierung enthält die Suchergebnisseite immer eine Suchbegriffdimension und eine Suchmetrik. Wir können Suchbegriffe an den Produktnamen binden, wann immer die Suchmetrik vorhanden ist.

![Bindungsmetrik](assets/binding-metric.png)

Wenn Sie die Suchbegriffdimension auf dieses Persistenzmodell festlegen, wird die folgende Logik ausgeführt:

* Wenn search_term in einem Ereignis enthalten ist, überprüfen Sie, ob der Produktname vorhanden ist.
* Wenn der Produktname nicht vorhanden ist, führen Sie nichts aus.
* Wenn der Produktname vorhanden ist, überprüfen Sie, ob die Suchmetrik vorhanden ist.
* Wenn die Suchmetrik nicht vorhanden ist, führen Sie keine Aktionen aus.
* Wenn die Suchmetrik vorhanden ist, binden Sie den Suchbegriff an alle Produktnamen. Es verhält sich so, als ob es auf derselben Ebene wie der Produktname für dieses Ereignis wäre. In diesem Beispiel wird sie als product.search_term behandelt.
* Wenn derselbe Produktname in einem nachfolgenden Ereignis angezeigt wird, ist auch der gebundene Suchbegriff dort vorhanden.

In Analysis Workspace würde der resultierende Bericht in etwa wie folgt aussehen:

| search_term | Umsatz |
| --- | --- |
| Boxhandschuhe | 89,99 $ |
| Tennisschläger | 34,99 $ |
| Schuhe | $ 79.99 |
