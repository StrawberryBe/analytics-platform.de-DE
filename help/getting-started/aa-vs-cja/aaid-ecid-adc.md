---
title: AAID, ECID, AACUSTOMID und der Analytics Source Connector
description: Erfahren Sie, wie der Analytics Source Connector mit Adobe Analytics-Identitätsfeldern umgeht.
source-git-commit: 348f4e8596146f7ff4234535fa76a54f7be33171
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 9%

---


# AAID, ECID, AACUSTOMID und der Analytics Source Connector

Adobe Analytics-Daten enthalten mehrere Identitätsfelder. Drei wichtige Identitätsfelder werden von der [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=de): AAID, ECID, AACUSTOMID.

## AAID

Die Adobe Analytics ID (AAID) ist die primäre Gerätekennung in Adobe Analytics und ist garantiert für jedes Ereignis, das über den Analytics Source Connector weitergeleitet wird. AAID wird manchmal als &quot;Legacy Analytics ID&quot;bezeichnet oder `s\_vi cookie id`. Eine AAID wird jedoch auch dann erstellt, wenn die `s\_vi` -Cookie nicht vorhanden ist. AAID wird durch die `_post\_visid\_high/post\_visid\_low_` Spalten in [Adobe Analytics-Daten-Feeds](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de#columns%2C-descriptions%2C-and-data-types).

Im Analytics Source Connector wird AAID in `HEX(post_visid_high) + "-" + HEX(host_visid_low)`. Das Feld &quot;AAID&quot;für ein bestimmtes Ereignis enthält eine einzelne Identität, die einer von mehreren verschiedenen Typen sein kann, wie unter [Reihenfolge der Vorgänge für Analytics-IDs](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-order-of-operations.html?lang=en%5B%5D). (Innerhalb einer gesamten Report Suite kann AAID eine Mischung aus Ereignistypen enthalten. Der Typ für jeden Treffer wird im `_[post\_]visid\_type_` in den Analytics-Daten-Feeds.) Siehe auch: [Datenspaltenreferenz](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=de).

## ECID

ECID (Experience Cloud-ID), manchmal auch als MCID (Marketing Cloud-ID) bezeichnet, ist ein separates Gerätekennungsfeld, das in Adobe Analytics ausgefüllt wird, wenn Analytics mithilfe der [Experience Cloud Identity-Dienst](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=de). Die ECID wird durch die `_mcvisid_` in Adobe Analytics-Daten-Feeds.

Wenn eine ECID für ein Ereignis vorhanden ist, kann die AAID auf der ECID basieren, je nachdem, ob die Analytics-Variable [Übergangsphase](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/grace-period.html?lang=de) konfiguriert ist. Siehe auch: [Analytics- und Experience Cloud-ID-Anforderungen](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/legacy-analytics.html?lang=en).

## AACUSTOMID

AACUSTOMID ist ein separates Identifikationsfeld, das in Adobe Analytics basierend auf der Verwendung des `s.VisitorID` in der Analytics-Implementierung. AACUSTOMID wird durch die `_cust_visid_` in Adobe Analytics-Daten-Feeds. Wenn AACUSTOMID vorhanden ist, basiert AAID auf AACUSTOMID. (AACUSTOMID überträgt alle anderen Kennungen, wie durch die Reihenfolge der oben genannten Vorgänge definiert.)

## Behandlung dieser Identitäten durch den Analytics Source Connector

Der Analytics Source Connector übergibt diese Identitäten in XDM-Form an Adobe Experience Platform als:

* `endUserIDs.\_experience.aaid.id`
* `endUserIDs.\_experience.mcid.id`
* `endUserIDs.\_experience.aacustomid.id`

Diese Felder sind nicht als Identitäten markiert. Stattdessen werden dieselben Identitäten in die **_identityMap_** als Schlüssel-Wert-Paare wie folgt:

* `{ “key”: “AAID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **_\<true or false\>_**} ] }`
* `{ “key”: “ECID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **_\<true or false\>_** } ] }`
* `{ “key”: “AACUSTOMID”, “value”: [ { “id”: “_\<identity\>_”, “primary”: **false** } ] }`

Innerhalb von identityMap:

* Wenn ECID vorhanden ist, wird es als primäre Identität für das Ereignis markiert. Beachten Sie, dass in diesem Fall AAID gemäß der obigen Diskussion auf ECID basieren kann.
Andernfalls wird AAID als primäre Identität für das Ereignis markiert.
* AACUSTOMID wird nie als Primäre ID für das Ereignis markiert. Wenn jedoch AACUSTOMID vorhanden ist, basiert AAID gemäß der obigen Diskussion auf AACUSTOMID.

Für CJA ist die Definition der Primären ID nur dann wichtig, wenn der Endbenutzer die Primäre ID als Personen-ID verwendet. Dies ist jedoch nicht erforderlich. Der Benutzer kann eine andere Identitätsspalte als Personen-ID auswählen.

