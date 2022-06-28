---
title: AAID, ECID, AACUSTOMID und der Analytics Source Connector
description: Erfahren Sie, wie der Analytics Source Connector mit Adobe Analytics-Identitätsfeldern umgeht.
exl-id: c983cf50-0b6c-4daf-86a8-bcd6c01628f7
source-git-commit: 20ebfb36e769f7d683ad44ec84b11aafb301a737
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 9%

---

# AAID, ECID, AACUSTOMID und der Analytics Source Connector

Adobe Analytics-Daten enthalten mehrere Identitätsfelder. Drei wichtige Identitätsfelder werden von der [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de): AAID, ECID, AACUSTOMID.

## AAID

Die Adobe Analytics ID (AAID) ist die primäre Gerätekennung in Adobe Analytics und ist garantiert für jedes Ereignis, das über den Analytics Source Connector weitergeleitet wird. AAID wird manchmal als &quot;Legacy Analytics ID&quot;bezeichnet oder `s_vi` Cookie-ID. Eine AAID wird jedoch auch dann erstellt, wenn die `s_vi` -Cookie nicht vorhanden ist. AAID wird durch die `post_visid_high/post_visid_low` Spalten in [Adobe Analytics-Daten-Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de#columns%2C-descriptions%2C-and-data-types).

Im Analytics Source Connector wird AAID in `HEX(post_visid_high) + "-" + HEX(post_visid_low)`. Das Feld &quot;AAID&quot;für ein bestimmtes Ereignis enthält eine einzelne Identität, die einer von mehreren verschiedenen Typen sein kann, wie unter [Reihenfolge der Vorgänge für Analytics-IDs](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (Innerhalb einer gesamten Report Suite kann AAID eine Mischung aus Ereignistypen enthalten. Der Typ für jeden Treffer wird im `post _visid_type` in den Analytics-Daten-Feeds.) Siehe auch: [Datenspaltenreferenz](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de).

## ECID

ECID (Experience Cloud-ID), manchmal auch als MCID (Marketing Cloud-ID) bezeichnet, ist ein separates Gerätekennungsfeld, das in Adobe Analytics ausgefüllt wird, wenn Analytics mithilfe der [Experience Cloud Identity-Dienst](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=de). Die ECID wird durch die `mcvisid` in Adobe Analytics-Daten-Feeds.

Wenn eine ECID für ein Ereignis vorhanden ist, kann die AAID auf der ECID basieren, je nachdem, ob die Analytics-Variable [Übergangsphase](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=de) konfiguriert ist. Siehe auch: [Analytics- und Experience Cloud-ID-Anforderungen](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).

## AACUSTOMID

AACUSTOMID ist ein separates Identifikationsfeld, das in Adobe Analytics basierend auf der Verwendung des `s.VisitorID` in der Analytics-Implementierung. AACUSTOMID wird durch die `cust_visid` in Adobe Analytics-Daten-Feeds. Wenn AACUSTOMID vorhanden ist, basiert AAID auf AACUSTOMID. (AACUSTOMID überträgt alle anderen Kennungen, wie durch die Reihenfolge der oben genannten Vorgänge definiert.)

## Behandlung dieser Identitäten durch den Analytics Source Connector

Der Analytics Source Connector übergibt diese Identitäten in XDM-Form an Adobe Experience Platform als:

* `endUserIDs._experience.aaid.id`
* `endUserIDs._experience.mcid.id`
* `endUserIDs._experience.aacustomid.id`

Diese Felder sind nicht als Identitäten markiert. Stattdessen werden dieselben Identitäten in die **_identityMap_** als Schlüssel-Wert-Paare wie folgt:

* `{ “key”: “AAID”, “value”: [ { “id”: “<identity>”, “primary”: <true or false> } ] }`
* `{ “key”: “ECID”, “value”: [ { “id”: “<identity>”, “primary”: <true or false> } ] }`
* `{ “key”: “AACUSTOMID”, “value”: [ { “id”: “<identity>”, “primary”: false } ] }`

Die Elemente in Klammern

Innerhalb von identityMap:

* Wenn ECID vorhanden ist, wird es als primäre Identität für das Ereignis markiert. Beachten Sie, dass in diesem Fall AAID gemäß der obigen Diskussion auf ECID basieren kann.
Andernfalls wird AAID als primäre Identität für das Ereignis markiert.
* AACUSTOMID wird nie als Primäre ID für das Ereignis markiert. Wenn jedoch AACUSTOMID vorhanden ist, basiert AAID gemäß der obigen Diskussion auf AACUSTOMID.

Für CJA ist die Definition der Primären ID nur dann wichtig, wenn der Endbenutzer die Primäre ID als Personen-ID verwendet. Dies ist jedoch nicht erforderlich. Der Benutzer kann eine andere Identitätsspalte als Personen-ID auswählen.
