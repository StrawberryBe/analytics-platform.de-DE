---
title: Vom Kunden verwaltete Schlüssel
description: Erfahren Sie, wie Sie kundenverwaltete Schlüssel für CJA einrichten.
hide: true
hidefromtoc: true
source-git-commit: ce386f30e344b3921689a8ecc0e6fba0a55137f9
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 0%

---

# Vom Kunden verwaltete Schlüssel

>[!NOTE]
>
>Diese Funktion wird im November 2022 verfügbar sein.

Customer Journey Analytics (CJA) bietet die Option für [Gesundheitsschild](https://www.adobe.com/trust/compliance/hipaa-ready.html) Kunden von Privacy &amp; Security Shield verwenden einen Azure Customer Managed Key (CMK), der auf Ihre CJA-Daten angewendet werden soll.  Beachten Sie, dass dieser Prozess getrennt von [Einrichten von Adobe Experience Platform CMK](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html).

>[!NOTE]
>
>Vom Kunden verwaltete Schlüssel sind derzeit nur für Unternehmen verfügbar, die die [Gesundheitsschild oder Datenschutz- und Sicherheitsschild](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) Add-On-Angebot.

Führen Sie die folgenden Schritte aus, um CMK für CJA einzurichten:

1. Stellen Sie sicher, dass Sie über die Berechtigung für CMK verfügen, indem Sie sich mit Ihrem Adobe Account-Team in Verbindung setzen.
1. Erstellen Sie ein neues Azure Key Vault, das nur mit CJA verwendet werden soll.
1. Verbinden Sie Ihren Azure Key Value mit der Azure CJA CMK App (Link zu folgen).
1. Erstellen Sie ein Adobe-Kundenunterstützungs-Ticket, in dem die Einrichtung des CMK angefordert wird. Schließen Sie den Azure-URI in Ihr Ticket ein.
1. Die Kundenunterstützung von Adobe bestätigt den Abschluss der CMK-Anwendung für Ihre CJA-Daten.
