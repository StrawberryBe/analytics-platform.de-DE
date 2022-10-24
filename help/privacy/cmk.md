---
title: Vom Kunden verwaltete Schlüssel
description: Erfahren Sie, wie Sie kundenverwaltete Schlüssel für CJA einrichten.
source-git-commit: 4894519f618b79a5ca29952df48291c44915adae
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# Vom Kunden verwaltete Schlüssel

>[!NOTE]
>
>Diese Funktion wird im November 2022 verfügbar sein.

Customer Journey Analytics (CJA) bietet Kunden von Health Care Shield und Privacy &amp; Security Shield die Möglichkeit, einen Azure Customer Managed Key (CMK) zu verwenden, der auf Ihre CJA-Daten angewendet werden kann.  Beachten Sie, dass dieser Vorgang von der Einrichtung des Adobe Experience Platform-CMK getrennt ist (Link zu folgen).

>[!NOTE]
>
>Vom Kunden verwaltete Schlüssel sind derzeit nur für Unternehmen verfügbar, die die [Gesundheitsschild oder Datenschutz- und Sicherheitsschild](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) Add-On-Angebot.

Führen Sie die folgenden Schritte aus, um CMK für CJA einzurichten:

1. Stellen Sie sicher, dass Sie über die Berechtigung für CMK verfügen, indem Sie sich mit Ihrem Adobe Account-Team in Verbindung setzen.
1. Erstellen Sie ein neues Azure Key Vault, das nur mit CJA verwendet werden soll.
1. Verbinden Sie Ihren Azure Key Value mit der Azure CJA CMK App (Link zu folgen).
1. Erstellen Sie ein Adobe-Kundenunterstützungs-Ticket, in dem die Einrichtung des CMK angefordert wird. Schließen Sie den Azure-URI in Ihr Ticket ein.
1. Die Kundenunterstützung von Adobe bestätigt den Abschluss der CMK-Anwendung für Ihre CJA-Daten.
