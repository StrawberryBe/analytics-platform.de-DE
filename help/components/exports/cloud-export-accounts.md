---
description: Konfigurieren des Cloud-Exportkontos, an das Customer Journey Analytics-Daten gesendet werden können
keywords: Analysis Workspace
title: Konfigurieren von Cloud-Exportkonten
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 5%

---

# Konfigurieren von Cloud-Exportkonten

{{select-package}}

Bevor Sie Customer Journey Analytics-Daten an ein Cloud-Ziel exportieren können, siehe [Customer Journey Analytics-Daten in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md)müssen Sie den Ort hinzufügen und konfigurieren, an den die Daten gesendet werden sollen.

Dieser Prozess besteht aus dem Hinzufügen und Konfigurieren des Kontos (z. B. Amazon S3, Google Cloud Platform usw.), wie in diesem Artikel beschrieben, und anschließendem Hinzufügen und Konfigurieren des Speicherorts innerhalb dieses Kontos (z. B. eines Ordners innerhalb des Kontos), wie in [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

Informationen zum Verwalten vorhandener Konten, einschließlich Anzeigen, Bearbeiten und Löschen von Konten, finden Sie unter [Verwalten von Cloud-Exportspeicherorten und -konten](/help/components/exports/manage-export-locations.md).

Sie müssen Customer Journey Analytics mit den erforderlichen Informationen konfigurieren, um auf Ihr Cloud-Zielkonto zuzugreifen.

So konfigurieren Sie ein Cloud-Exportkonto:

1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].
1. Im [!UICONTROL Exporte] Seite, wählen Sie die [!UICONTROL **Standortkonten**] Registerkarte.
1. Auswählen [!UICONTROL **Konto hinzufügen**].

   ![Konto hinzufügen](assets/account-add.png)

   Das Dialogfeld Konto hinzufügen wird angezeigt.
1. Geben Sie die folgenden Informationen an: |Feld | Funktion | |—|—| | [!UICONTROL **Name des Standortkontos**] | Der Name des Standortkontos. Dieser Name wird beim Erstellen eines Standorts angezeigt | | [!UICONTROL **Beschreibung des Standortkontos**] | Geben Sie eine kurze Beschreibung des Kontos ein, um es von anderen Konten desselben Kontotyps zu unterscheiden. | | [!UICONTROL **Kontotyp**] | Wählen Sie den Typ des Cloud-Kontos aus, in das Sie exportieren. Verfügbare Kontotypen sind Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake und Adobe Experience Platform. |
1. Im [!UICONTROL **Kontoeigenschaften**] -Abschnitt Informationen zum ausgewählten Kontotyp angeben.

   Erweitern Sie für Konfigurationsanweisungen den folgenden Abschnitt, der dem [!UICONTROL **Kontotyp**] die Sie ausgewählt haben.

   +++Amazon S3 Role ARN

   Geben Sie die folgenden Informationen an, um ein Amazon S3 Role ARN-Konto zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Rollen-ARN**] | Sie müssen einen Role ARN (Amazon Resource Name) bereitstellen, den Adobe verwenden kann, um Zugriff auf das Amazon S3-Konto zu erhalten. Dazu erstellen Sie eine IAM-Berechtigungsrichtlinie für das Quellkonto, hängen die Richtlinie an einen Benutzer an und erstellen dann eine Rolle für das Zielkonto. Weitere Informationen finden Sie unter [Diese AWS-Dokumentation](https://aws.amazon.com/premiumsupport/knowledge-center/cross-account-access-iam/). |
   | [!UICONTROL **Benutzer-ARN**] | Die Benutzer-ARN (Amazon Resource Name) wird von Adobe bereitgestellt. Sie müssen diesen Benutzer an die von Ihnen erstellte Richtlinie anhängen. |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Geben Sie die folgenden Informationen an, um ein Google Cloud Platform-Konto zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Projekt-ID**] | Ihre Google Cloud-Projekt-ID, die Sie aus Ihrem Google Cloud-Konto kopieren. Siehe [Dokumentation zu Google Cloud zum Abrufen einer Projekt-ID](https://cloud.google.com/resource-manager/docs/creating-managing-projects#identifying_projects). |
   | [!UICONTROL **Prinzipal**] | Der Prinzipal wird von Adobe bereitgestellt. Klicken Sie auf [!UICONTROL **Kopieren**] Symbol neben [!UICONTROL **Principal**] zum Kopieren des Feldinhalts und dann sicherstellen, dass Sie dem Prinzipal die Berechtigung zum Hochladen von Dateien in diesen Bucket in Google Cloud Platform erteilen. <!-- add link to Google Cloud docs on how to do this --> |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Geben Sie die folgenden Informationen an, um ein Azure SAS-Konto zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Anwendungs-ID**] | Kopieren Sie diese ID aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen im **Übersicht** in Ihrer Anwendung. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft-Identitätsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Mandanten-ID**] | Kopieren Sie diese ID aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen im **Übersicht** in Ihrer Anwendung. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft-Identitätsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Key Vault-URI**] | <p>Der Pfad zum SAS-Token im Azure Key Vault.  Um Azure SAS zu konfigurieren, müssen Sie ein SAS-Token mithilfe des Azure Key Vault als Geheimnis speichern. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zum Einrichten und Abrufen eines Geheimnisses aus Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations).</p><p>Nachdem der Schlüssel-Vault-URI erstellt wurde, fügen Sie im Key Vault eine Zugriffsrichtlinie hinzu, um der von Ihnen erstellten Azure-Anwendung Berechtigungen zu erteilen. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zur Zuweisung einer Key Vault-Zugriffsrichtlinie](https://learn.microsoft.com/en-us/azure/key-vault/general/assign-access-policy?tabs=azure-portal).</p> |
   | [!UICONTROL **Key Vault-Geheimnisname**] | Der geheime Name, den Sie beim Hinzufügen des Geheimnisses zum Azure Key Vault erstellt haben. In Microsoft Azure befinden sich diese Informationen im von Ihnen erstellten Key Vault im **Key Vault** Einstellungsseiten. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zum Einrichten und Abrufen eines Geheimnisses aus Azure Key Vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal?source=recommendations). |
   | [!UICONTROL **Geheimnis des Standortkontos**] | Kopieren Sie das Geheimnis aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen im **Zertifikate &amp; Geheimnisse** in Ihrer Anwendung. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft-Identitätsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). <!-- need to grant permission to the bucket. Jun will send info on where that is documented) --> |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Geben Sie die folgenden Informationen an, um ein Azure RBAC-Konto zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Anwendungs-ID**] | Kopieren Sie diese ID aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen im **Übersicht** in Ihrer Anwendung. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft-Identitätsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Mandanten-ID**] | Kopieren Sie diese ID aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen im **Übersicht** in Ihrer Anwendung. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft-Identitätsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |
   | [!UICONTROL **Geheimnis des Standortkontos**] | Kopieren Sie das Geheimnis aus der von Ihnen erstellten Azure-Anwendung. In Microsoft Azure befinden sich diese Informationen im **Zertifikate &amp; Geheimnisse** in Ihrer Anwendung. Weitere Informationen finden Sie unter [Microsoft Azure-Dokumentation zur Registrierung einer Anwendung bei der Microsoft-Identitätsplattform](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app). |

   {style="table-layout:auto"}

+++

   +++Snowflake

   Geben Sie die folgenden Informationen an, um ein Snowflake-Konto zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Kontokennung**] | Identifiziert eindeutig ein Snowflake-Konto innerhalb Ihres Unternehmens sowie im gesamten globalen Netzwerk von Snowflake-unterstützten Cloud-Plattformen und Cloud-Regionen. <p>Weitere Informationen finden Sie unter [Seite &quot;Konto-IDs&quot;in der Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/admin-account-identifier).</p> |
   | [!UICONTROL **Benutzer**] | Gibt den Anmeldenamen des Benutzers für die Verbindung an. Dies ist ein Benutzer, der speziell zum Adobe verwendet wird. Sie können den Benutzer im Snowflake erstellen, nachdem Sie hier den Benutzernamen angegeben haben. <p>Weitere Informationen finden Sie unter [Referenzseite für JDBC-Treiberverbindungsparameter in der Snowflake-Dokumentation](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Rolle**] | Die standardmäßige Zugriffssteuerungsrolle, die in der vom Treiber initiierten Snowflake-Sitzung verwendet wird. Sie sollten eine spezifische Rolle für Adobe erstellen, die Lese- und Schreibzugriff hat.<p>Weitere Informationen finden Sie unter [Referenzseite für JDBC-Treiberverbindungsparameter in der Snowflake-Dokumentation](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Öffentlicher Schlüssel**] | Der öffentliche Schlüssel wird von Adobe bereitgestellt. Klicken Sie auf das Symbol Kopieren neben dem [!UICONTROL **Öffentlicher Schlüssel**] zum Kopieren des Feldinhalts und dann den öffentlichen Schlüssel in Ihrem Snowflake-Konto verwenden. Weitere Informationen finden Sie unter [Seite &quot;Schlüsselpaarauthentifizierung und Schlüsselpaar-Rotation&quot;in der Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/key-pair-auth). |

+++

   +++Adobe Experience Platform

   Alle Adobe Experience Platform-Kunden können Daten in die AEP-Einstiegszone exportieren.

   Geben Sie die folgenden Informationen an, um ein Adobe Experience Platform-Konto zu konfigurieren.

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Kennung der IMS-Organisation**] | Die IMS-Organisations-ID wird von Adobe bereitgestellt. Klicken Sie auf das Symbol Kopieren neben dem [!UICONTROL **Kennung der IMS-Organisation**] zum Kopieren des Feldinhalts und zur anschließenden Verwendung der ID in Ihrem Adobe Experience Platform-Konto. |

+++

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Fahren Sie mit [Konfigurieren von Cloud-Exportspeicherorten](/help/components/exports/cloud-export-locations.md).

