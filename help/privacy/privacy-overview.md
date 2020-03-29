---
title: Überblick über die Datenschutzfunktion in Customer Journey Analytics
description: Beschreibt, wie Datenschutzeinstellungen in Customer Journey Analytics funktionieren.
translation-type: ht
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# Überblick über die Datenschutzfunktion in Customer Journey Analytics

Im Allgemeinen werden alle datenschutzrelevanten Einstellungen in Customer Journey Analytics von Adobe Experience Platform übernommen.

## DSGVO

Customer Journey Analytics wird nicht in den zentralen Dienst der Datenschutz-Grundverordnung (DSGVO) eingebunden, sondern übernimmt stattdessen alle in Experience Platform vorgenommenen Änderungen. Wir sind darauf angewiesen, dass Platform Data Lake die DSGVO-Löschanfragen durchführt und uns benachrichtigt, wenn diese in der Pipeline abgeschlossen sind. Wir überwachen die Pipeline und synchronisieren alle Änderungen, die an betroffenen Batches in Customer Journey Analytics für Ereignis-Datensätze vorgenommen wurden. Profil- und Nachschlagedatensätze, die von DSGVO-Löschanfragen betroffen sind, werden nach jeder Löschanfrage vollständig neu erfasst. Wir garantieren, dass Löschanfragen innerhalb von sieben Tagen ab dem Löschvorgang in Data Lake ausgeführt werden.

## CCPA

Der California Consumer Privacy Act (CCPA) erweitert die Datenschutzrechte und den Verbraucherschutz für Einwohner von Kalifornien, USA. Die neue Regelung tritt am 1. Januar 2020 in Kraft.
Der CCPA bietet neue Datenschutzrechte, mit denen Verbraucher beispielsweise ihre personenbezogenen Daten einsehen und löschen oder herausfinden können, ob (und an wen) ihre Daten verkauft oder weitergegeben wurden. Zusätzlich können sie dem Verkauf ihrer personenbezogenen Daten widersprechen.
Zur Vorbereitung auf den CCPA unterstützt der Datenschutzdienst Anfragen zur Abmeldung vom Verkauf personenbezogener Daten.
