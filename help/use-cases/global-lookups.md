---
title: Globale Suchen zu Ihren Datensätzen hinzufügen
description: Verwenden Sie globale Suchen, um die Berichte mit nützlichen Dimensionen in Customer Journey Analytics zu ergänzen.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
translation-type: tm+mt
source-git-commit: 8224fd2fde787f0d3cf0cb983641efc588c316b0
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 100%

---

# Globale Suchen zu Ihren Datensätzen hinzufügen

Anhand von globalen Suchen kann Customer Journey Analytics Berichte zu bestimmten Dimensionen/Attributen erstellen, die nicht für sich genommen, aber bei der Verknüpfung mit anderen Daten nützlich sind. Dies können beispielsweise Attribute von Smartphones oder Tablets und Attribute von OS- und Browser-Dimensionen wie etwa die Versionsnummern von Browsern sein. Eine „Globale Suche“ ist einem Lookup-Datensatz (im herkömmlichen Adobe Analytics als Klassifizierungen bezeichnet) ähnlich. Globale Suchen sind jedoch auf alle Experience Cloud-Organisationen anwendbar. Globale Suchen werden automatisch auf alle Ereignis-Datensätze angewendet, die bestimmte XDM-Schema-Felder enthalten (die jeweiligen Felder finden Sie unten).
Für jeden Schema-Speicherort, den Adobe klassifiziert, gibt es einen globalen Lookup-Datensatz. Sie können globale Lookup-Datensätze mit Analytics Source Connector oder anderen benutzerdefinierten Datensätzen verwenden, die diese akzeptieren.

Im herkömmlichen Adobe Analytics werden diese Dimensionen eigenständig angezeigt. In Customer Journey Analytics hingegen müssen Sie diese Dimensionen beim Erstellen von Datenansichten aktiv einbeziehen. Wenn ein Benutzer im Workflow „Verbindungen“ einen Datensatz auswählt, der mit einem Schlüssel für globale Suchen gekennzeichnet ist, dann bezieht die Benutzeroberfläche der Datenansichten alle globalen Lookup-Dimensionen ein, die für Berichte verfügbar sind. Der Workflow „Datenansichten“ bezieht diese globalen Lookup-Dimensionen, die für die Datenansicht verfügbar sind, mit ein. Die Lookup-Dateien werden automatisch aktualisiert und stehen für alle Regionen und Accounts zur Verfügung. Sie werden in regionsspezifischen Organisationen gespeichert, die dem Kunden zugeordnet sind.

## Globale Suchen mit Adobe Data Connector-Datensätzen verwenden

Globale Lookup-Datensätze werden zum Zeitpunkt des Berichts automatisch angewendet. Wenn Sie [Analytics Data Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=de-DE#connectors) verwenden und eine Dimension einbringen, für die Adobe eine globale Suche bereitstellt, wird diese globale Suche automatisch angewendet. Wenn ein Ereignis-Datensatz [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=de-DE)-Felder enthält, können globale Suchen darauf angewendet werden.

## Verfügbare globale Suchfelder

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`,  `group_id`,  `id`
* `os_group`
   * `os_group`,  `id`
* `mobile_audio_support - multi`
* `mobile_color_depth`
* `mobile_cookie_support`
* `mobile_device_name`
* `mobile_device_number_transmit`
* `mobile_device_type`
* `mobile_drm - multi`
* `mobile_image_support - multi`
* `mobile_information_services`
* `mobile_java_vm - multi`
* `mobile_mail_decoration`
* `mobile_manufacturer`
* `mobile_max_bookmark_url_length`
* `mobile_max_browser_url_length`
* `mobile_max_mail_url_length`
* `mobile_net_protocols - multi`
* `mobile_os`
* `mobile_push_to_talk`
* `mobile_screen_height`
* `mobile_screen_size`
* `mobile_screen_width`
* `mobile_video_support - multi`

## Bericht zu globalen Lookup-Dimensionen

Um einen Bericht zu den globalen Lookup-Dimensionen zu erstellen, müssen Sie diese hinzufügen, wenn Sie eine Datenansicht in Customer Journey Analytics erstellen:

![](assets/global-lookup.png)

Anschließend werden die Lookup-Daten in Workspace angezeigt:

![](assets/gl-reporting.png)
