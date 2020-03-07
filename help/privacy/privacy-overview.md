---
title: Überblick über die Privatsphäre in Customer Journey Analytics
description: Beschreibt, wie Datenschutzeinstellungen in Customer Journey Analytics funktionieren.
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b

---


# Überblick über die Privatsphäre in Customer Journey Analytics

Im Allgemeinen werden alle datenschutzrelevanten Einstellungen in Customer Journey Analytics von Adobe Experience Platform übernommen.

## GDPR

Customer Journey Analytics wird den Central Service (GDPR) nicht direkt abonnieren und stattdessen alle in Experience Platform vorgenommenen Änderungen übernehmen. Wir sind auf Platform Data Lake angewiesen, um GDPR-Löschungsanfragen zu erzwingen und uns zu benachrichtigen, wenn sie auf Pipeline abgeschlossen wurden. Wir hören auf Pipeline und synchronisieren alle Änderungen an betroffenen Stapeln in Customer Journey Analytics für Ereignisdatensätze. Profil- und Nachschlagedatasets, die von GDPR-Löschanforderungen betroffen sind, werden nach jeder Löschanforderung vollständig neu erfasst. Wir können garantieren, dass Löschungsanfragen innerhalb von 7 Tagen nach einem Löschereignis in Data Lake ausgeführt werden.

## CCPA

Der California Consumer Privacy Act (CCPA) erweitert die Datenschutzrechte und den Verbraucherschutz für Einwohner von Kalifornien, USA. Die neue Regelung tritt am 1. Januar 2020 in Kraft.
Der CCPA bietet neue Datenschutzrechte, mit denen Verbraucher beispielsweise ihre personenbezogenen Daten einsehen und löschen oder herausfinden können, ob (und an wen) ihre Daten verkauft oder weitergegeben wurden, und mit denen sie dem Verkauf ihrer personenbezogenen Daten widersprechen können.
Zur Vorbereitung auf den CCPA unterstützt der Datenschutzdienst Anfragen zur Abmeldung vom Verkauf personenbezogener Daten.
