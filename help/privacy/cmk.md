---
title: Vom Kunden verwaltete Schlüssel
description: Erfahren Sie, wie Sie kundenverwaltete Schlüssel für CJA einrichten.
source-git-commit: 903c1423c91b220524174fa900a9ec13cd2051c6
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 83%

---

# Vom Kunden verwaltete Schlüssel

>[!NOTE]
>
>Diese Funktion wird im November 2022 verfügbar sein.

Customer Journey Analytics (CJA) bietet für Kunden von [Healthcare Shield](https://www.adobe.com/trust/compliance/hipaa-ready.html) und Privacy &amp; Security Shield die Option, einen Azure Customer Managed Key (CMK) zu nutzen, der auf Ihre CJA-Daten angewendet wird.  Beachten Sie, dass dieser Prozess vom [Einrichten von Adobe Experience Platform-CMK](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/customer-managed-keys.html?lang=de) getrennt ist.

>[!NOTE]
>
>Vom Kunden verwaltete Schlüssel sind derzeit nur für Unternehmen verfügbar, die das Add-on-Angebot für [Healthcare Shield oder Privacy &amp; Security Shield](https://experienceleague.adobe.com/docs/blueprints-learn/architecture/vertical-blueprints/healthcare-vertical.html%3Flang%3Den) gekauft haben.

## Einrichten von CMK für CJA

Führen Sie die folgenden Schritte aus, um CMK für CJA einzurichten:

1. Stellen Sie sicher, dass Sie berechtigt sind, Adobe CJA CMK auszuführen, indem Sie sich mit Ihrem Adobe-Konto-Team in Verbindung setzen.
1. Stellen Sie sicher, dass Sie in Azure ein Administrator mit einer privilegierten Rolle sind, z. B. „Anwendungsadministrator“, „Cloud-Anwendungsadministrator“ oder „globaler Administrator“. [Weitere Informationen von Microsoft](https://learn.microsoft.com/de-de/azure/active-directory/roles/permissions-reference)
1. Erstellen Sie einen neuen Azure-Schlüsseltresor, der nur mit CJA verwendet werden soll. [Weitere Informationen von Microsoft](https://learn.microsoft.com/de-de/azure/key-vault/general/)
1. Gewähren Sie dem Adobe Azure-Programm Zugriff auf den Schlüssel im Schlüsseltresor. Dies ist die Adobe-Anwendungs-ID: 251e3919-1940-4296-bb8b-6b9a5e8a4805. [Weitere Informationen von Microsoft](https://learn.microsoft.com/de-de/azure/storage/common/customer-managed-keys-configure-cross-tenant-existing-account?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&amp;tabs=powershell-preview%2Cazure-portal#the-customer-grants-the-service-providers-app-access-to-the-key-in-the-key-vault)
1. Erstellen Sie ein Adobe-Kundenunterstützungs-Ticket, um die CMK-Einrichtung anzufordern. Fügen Sie das Azure-URI in Ihr Ticket ein. Der URI befindet sich im **Schlüsselkennung** -Feld Ihres Azure-Schlüssels.

   ![](assets/key-identifier.png)

1. Die Kundenunterstützung von Adobe bestätigt den Abschluss der CMK-Anwendung in Ihren CJA-Daten.

Alle von Platform verwendeten Daten werden während der Übertragung und im Ruhezustand verschlüsselt, um Ihre Daten mit oder ohne CMK sicher zu halten. Informationen zur Adobe Experience Platform-Verschlüsselung: [Weitere Informationen](https://experienceleague.adobe.com/docs/experience-platform/landing/governance-privacy-security/encryption.html?lang=en).