---
title: Customer Journey Analytics und Data Governance
description: Beschreibt, wie Data Governance in Customer Journey Analytics funktioniert.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 2f74c10f821aed421e31ee8e14b854f2a73c11f1
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 75%

---

# Customer Journey Analytics und Data Governance

Im Allgemeinen werden alle Data Governance-bezogenen Einstellungen in Customer Journey Analytics von Adobe Experience Platform übernommen.

## Data Governance

CJA unterstützt die in Adobe Experience Platform eingerichteten Data Governance-Beschriftungen und -Richtlinien. Weitere Informationen finden Sie unter [CJA-Unterstützung für Adobe Experience Platform Data Governance](/help/data-views/data-governance.md).

## DSGVO

Customer Journey Analytics wird nicht in den zentralen Service der Datenschutz-Grundverordnung (DSGVO) eingebunden, sondern übernimmt stattdessen alle in Experience Platform vorgenommenen Änderungen. Wir sind darauf angewiesen, dass Platform Data Lake die DSGVO-Löschanfragen durchführt und uns benachrichtigt, wenn diese in der Pipeline abgeschlossen sind. Wir überwachen die Pipeline und synchronisieren alle Änderungen, die an betroffenen Batches in Customer Journey Analytics für Ereignis-Datensätze vorgenommen wurden. Profil- und Nachschlagedatensätze, die von DSGVO-Löschanfragen betroffen sind, werden nach jeder Löschanfrage vollständig neu erfasst. Wir garantieren, dass Löschanfragen innerhalb von sieben Tagen ab dem Löschvorgang in Data Lake ausgeführt werden.

## CCPA

Der California Consumer Privacy Act (CCPA) erweitert die Datenschutzrechte und den Verbraucherschutz für Einwohner von Kalifornien, USA. Die neue Regelung tritt am 1. Januar 2020 in Kraft.
Der CCPA bietet neue Datenschutzrechte, mit denen Verbraucher beispielsweise ihre personenbezogenen Daten einsehen und löschen oder herausfinden können, ob (und an wen) ihre Daten verkauft oder weitergegeben wurden. Zusätzlich können sie dem Verkauf ihrer personenbezogenen Daten widersprechen.
Zur Vorbereitung auf den CCPA unterstützt der Datenschutzdienst Anfragen zur Abmeldung vom Verkauf personenbezogener Daten.
