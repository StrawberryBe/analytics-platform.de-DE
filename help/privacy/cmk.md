---
title: Vom Kunden verwaltete Schlüssel
description: Erfahren Sie, wie Sie kundenverwaltete Schlüssel für CJA einrichten.
hide: true
hidefromtoc: true
source-git-commit: 08a322e159725c565dafdc5ef28758cc97fb9ae4
workflow-type: tm+mt
source-wordcount: '322'
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

## Einrichten von CMK für CJA

Führen Sie die folgenden Schritte aus, um CMK für CJA einzurichten:

1. Stellen Sie sicher, dass Sie berechtigt sind, Adobe CJA CMK durchzuführen, indem Sie sich mit Ihrem Adobe Account-Team in Verbindung setzen.
1. Stellen Sie sicher, dass Sie in Azure ein Administrator mit einer privilegierten Rolle sind, z. B. &quot;Anwendungsadministrator&quot;, &quot;Cloud Application Administrator&quot;oder &quot;Global Administrator&quot;. [Weitere Informationen zu Microsoft](https://learn.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)
1. Erstellen Sie ein neues Azure Key Vault, das nur mit CJA verwendet werden soll. [Weitere Informationen zu Microsoft](https://learn.microsoft.com/en-us/azure/key-vault/general/)
1. Gewähren Sie der Adobe Azure App Zugriff auf den Schlüssel im Schlüsselvault. Dies ist die Adobe Application ID: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Weitere Informationen zu Microsoft](https://learn.microsoft.com/en-us/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Erstellen Sie ein Adobe-Kundenunterstützungs-Ticket, in dem die Einrichtung des CMK angefordert wird. Schließen Sie den Azure-URI in Ihr Ticket ein. Der URI befindet sich im **Schlüsselkennung** -Feld Ihres Azure-Schlüssels.

   ![](assets/key-identifier.png)

1. Die Kundenunterstützung von Adobe bestätigt den Abschluss der CMK-Anwendung in Ihren CJA-Daten.

Alle von Platform verwendeten Daten werden während der Übertragung und im Ruhezustand verschlüsselt, um Ihre Daten mit oder ohne CMK sicher zu halten. Informationen zur Adobe Experience Platform-Verschlüsselung: [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=en).