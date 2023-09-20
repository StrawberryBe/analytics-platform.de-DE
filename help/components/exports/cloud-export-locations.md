---
description: Konfigurieren des Cloud-Exportspeicherorts, an den Customer Journey Analytics-Daten gesendet werden können
keywords: Analysis Workspace
title: Konfigurieren von Cloud-Exportspeicherorten
feature: Components
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 6%

---

# Konfigurieren von Cloud-Exportspeicherorten

{{select-package}}

Bevor Sie Customer Journey Analytics-Daten an ein Cloud-Ziel exportieren können, siehe [Customer Journey Analytics-Daten in die Cloud exportieren](/help/analysis-workspace/export/export-cloud.md)müssen Sie den Ort hinzufügen und konfigurieren, an den die Daten gesendet werden sollen.

Dieser Prozess besteht aus dem Hinzufügen und Konfigurieren des Kontos (z. B. Amazon S3, Google Cloud Platform usw.), wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md)und dann den Speicherort innerhalb dieses Kontos (z. B. einen Ordner innerhalb des Kontos) hinzufügen und konfigurieren, wie in diesem Artikel beschrieben.

Informationen zum Verwalten vorhandener Standorte, einschließlich Anzeigen, Bearbeiten und Löschen von Standorten, finden Sie unter [Verwalten von Cloud-Exportspeicherorten und -konten](/help/components/exports/manage-export-locations.md).

So konfigurieren Sie einen Cloud-Exportspeicherort:

1. Sie müssen ein Konto hinzufügen, bevor Sie einen Ort hinzufügen können. Fügen Sie, falls noch nicht geschehen, ein Konto wie unter [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md).
1. Wählen Sie unter Customer Journey Analytics die Option [!UICONTROL **Komponenten**] > [!UICONTROL **Exporte**].
1. Im [!UICONTROL Exporte] Seite, wählen Sie die [!UICONTROL **Standorte**] Registerkarte.
1. Auswählen [!UICONTROL **Ort hinzufügen**].

   ![Schaltfläche &quot;Ort hinzufügen&quot;](assets/location-add.png)

   Das Dialogfeld Standort wird angezeigt.

1. Geben Sie die folgenden Informationen an: |Feld | Funktion | |—|—| | [!UICONTROL **Name**] | Der Name des Standorts.  | | [!UICONTROL **Beschreibung**] | Geben Sie eine kurze Beschreibung des Kontos ein, um es von anderen Konten desselben Kontotyps zu unterscheiden. | | [!UICONTROL **Standortkonto**] | Wählen Sie das Standortkonto aus, das Sie in [Konfigurieren von Cloud-Exportkonten](/help/components/exports/cloud-export-accounts.md). |

1. Im [!UICONTROL **Standorteigenschaften**] Informationen zum Kontotyp Ihres Standortkontos angeben.

   Erweitern Sie für Konfigurationsanweisungen den folgenden Abschnitt, der dem Kontotyp entspricht, den Sie in der [!UICONTROL **Standortkonten**] -Feld.

   +++Amazon S3 Role ARN

   Geben Sie die folgenden Informationen an, um einen Amazon S3 Role ARN-Speicherort zu konfigurieren:

   <!-- still need to update; can't create S3 role ARN account -->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Behälter**] | Der Behälter in Ihrem Amazon S3-Konto, an den Adobe Analytics-Daten gesendet werden sollen. Stellen Sie sicher, dass die von Adobe bereitgestellte Benutzer-ARN Zugriff auf das Hochladen von Dateien in diesen Bucket hat. |
   | [!UICONTROL **Präfix**] | Der Ordner im Behälter, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie dann einen umgekehrten Schrägstrich nach dem Namen hinzu, um den Ordner zu erstellen. Beispiel: folder_name/ |

   {style="table-layout:auto"}

+++

   +++Google Cloud Platform

   Geben Sie die folgenden Informationen an, um einen Google Cloud Platform-Speicherort zu konfigurieren:

   <!-- still need to update; can't create GCP account -->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Behälter**] | Der Bucket in Ihrem GCP-Konto, an den Customer Journey Analytics-Daten gesendet werden sollen. Stellen Sie sicher, dass Sie dem von Adobe bereitgestellten Prinzipal die Berechtigung zum Hochladen von Dateien in diesen Bucket erteilt haben. (Der Prinzipal wird bereitgestellt, wenn [Konfigurieren des Google Cloud Platform-Kontos](/help/components/exports/cloud-export-accounts.md). Informationen zum Gewähren von Berechtigungen finden Sie unter [Einen Prinzipal zu einer Richtlinie auf Behälterebene hinzufügen](https://cloud.google.com/storage/docs/access-control/using-iam-permissions#bucket-add) in der Dokumentation zu Google Cloud. |
   | [!UICONTROL **Präfix**] | Der Ordner im Behälter, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie dann einen umgekehrten Schrägstrich nach dem Namen hinzu, um den Ordner zu erstellen. Beispiel: folder_name/ |

   {style="table-layout:auto"}

+++

   +++Azure SAS

   Geben Sie die folgenden Informationen an, um einen Azure SAS-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Container-Name**] | Der Container innerhalb des von Ihnen angegebenen Kontos, an den Customer Journey Analytics-Daten gesendet werden sollen. |
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie dann einen umgekehrten Schrägstrich nach dem Namen hinzu, um den Ordner zu erstellen. Zum Beispiel, `folder_name/` |

   {style="table-layout:auto"}

+++

   +++Azure RBAC

   Geben Sie die folgenden Informationen an, um einen Azure RBAC-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Container**] | Der Container innerhalb des von Ihnen angegebenen Kontos, an den Adobe Analytics-Daten gesendet werden sollen. Stellen Sie sicher, dass Sie Berechtigungen zum Hochladen von Dateien in die Azure-Anwendung erteilen, die Sie zuvor erstellt haben. |
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie dann einen umgekehrten Schrägstrich nach dem Namen hinzu, um den Ordner zu erstellen. Zum Beispiel, `folder_name/` |
   | [!UICONTROL **Konto**] | Das Azure-Speicherkonto. |

   {style="table-layout:auto"}

+++

   +++Snowflake

   Geben Sie die folgenden Informationen an, um einen Snowflake-Speicherort zu konfigurieren:

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **DB**] | Die Standarddatenbank, die verwendet werden soll, wenn eine Verbindung hergestellt wurde, oder eine leere Zeichenfolge. Die angegebene Datenbank sollte eine bestehende Datenbank sein, für die die angegebene Standardrolle über Berechtigungen verfügt. <p>Weitere Informationen finden Sie unter [Referenzseite für JDBC-Treiberverbindungsparameter in der Snowflake-Dokumentation](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Schema**] | Das Standardschema, das für die angegebene Datenbank verwendet werden soll, nachdem eine Verbindung hergestellt wurde, oder eine leere Zeichenfolge. Das angegebene Schema sollte ein vorhandenes Schema sein, für das die angegebene Standardrolle über Berechtigungen verfügt. <p>Weitere Informationen finden Sie unter [Referenzseite für JDBC-Treiberverbindungsparameter in der Snowflake-Dokumentation](https://docs.snowflake.com/en/developer-guide/jdbc/jdbc-parameters).</p> |
   | [!UICONTROL **Schrittname**] | Der Name des Speicherorts, an dem Datendateien unter Snowflake gespeichert werden. <p>Weitere Informationen finden Sie unter [Auswählen einer internen Phase für lokale Dateien in der Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |
   | [!UICONTROL **Schrittpfad**] | Der Pfad zum Speicherort, an dem Datendateien unter Snowflake gespeichert werden. <p>Weitere Informationen finden Sie unter [Auswählen einer internen Phase für lokale Dateien in der Snowflake-Dokumentation](https://docs.snowflake.com/en/user-guide/data-load-local-file-system-create-stage).</p> |

   {style="table-layout:auto"}

+++

   +++Adobe Experience Platform

   Geben Sie die folgenden Informationen an, um einen Adobe Experience Platform-Speicherort zu konfigurieren:

   <!-- still need to update; can't create AEP account -->

   | Feld | Funktion |
   |---------|----------|
   | [!UICONTROL **Kennung der IMS-Organisation**] | Die IMS-Organisations-ID wird von Adobe bereitgestellt. Klicken Sie auf das Symbol Kopieren neben dem [!UICONTROL **Kennung der IMS-Organisation**] zum Kopieren des Feldinhalts und zur anschließenden Verwendung der ID in Ihrem Adobe Experience Platform-Konto. |
   | [!UICONTROL **Präfix**] | Der Ordner im Container, in den Sie die Daten ablegen möchten. Geben Sie einen Ordnernamen an und fügen Sie dann einen umgekehrten Schrägstrich nach dem Namen hinzu, um den Ordner zu erstellen. Zum Beispiel, `folder_name/` |

+++

1. Wählen Sie [!UICONTROL **Speichern**] aus.

1. Sie können jetzt Daten aus Analysis Workspace in das Konto und den Speicherort exportieren, die Sie konfiguriert haben. Informationen zum Exportieren von Daten in die Cloud finden Sie unter [Exportieren von Projektdaten in die Cloud](/help/analysis-workspace/export/export-cloud.md).