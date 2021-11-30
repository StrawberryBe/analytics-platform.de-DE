---
title: Globale Suchen zu Ihren Datensätzen hinzufügen
description: Verwenden Sie globale Suchen, um die Berichte mit nützlichen Dimensionen in Customer Journey Analytics zu ergänzen.
exl-id: ab91659b-a1e6-4f6b-8976-410cf894d1a0
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 100%

---

# Globale Suchen zu Ihren Datensätzen hinzufügen

Anhand von globalen Suchen kann Customer Journey Analytics Berichte zu bestimmten Dimensionen/Attributen erstellen, die nicht für sich genommen, aber bei der Verknüpfung mit anderen Daten nützlich sind. Dies können beispielsweise Attribute von Smartphones oder Tablets und Attribute von OS- und Browser-Dimensionen wie etwa die Versionsnummern von Browsern sein. Eine „globale Suche“ ist ähnlich wie ein Lookup-Datensatz. Globale Suchen sind auf alle Experience Cloud-Organisationen anwendbar. Sie werden automatisch auf alle Ereignis-Datensätze angewendet, die bestimmte XDM-Schema-Felder enthalten (die jeweiligen Felder finden Sie unten). Für jeden Schema-Speicherort, den Adobe klassifiziert, gibt es einen globalen Lookup-Datensatz.

Im herkömmlichen Adobe Analytics werden diese Dimensionen eigenständig angezeigt. In Customer Journey Analytics hingegen müssen Sie diese Dimensionen beim Erstellen von Datenansichten aktiv einbeziehen. Im Verbindungs-Workflow wählen Sie einen Datensatz aus, der als Datensatz mit einem Schlüssel für die globale Suche gekennzeichnet wird. In der Datenansichts-Benutzeroberfläche werden automatisch alle globalen Lookup-Dimensionen einbezogen, die für Berichte verfügbar sind. Die Lookup-Dateien werden automatisch aktualisiert und stehen für alle Regionen und Accounts zur Verfügung. Sie werden in regionsspezifischen Organisationen gespeichert, die dem Kunden zugeordnet sind.

## Globale Suchen mit Adobe Data Connector-Datensätzen verwenden

Globale Lookup-Datensätze werden zum Zeitpunkt des Berichts automatisch angewendet. Wenn Sie Analytics Data Connector verwenden und eine Dimension einbringen, für die Adobe eine globale Suche bereitstellt, wird diese globale Suche automatisch angewendet. Wenn ein Ereignis-Datensatz XDM-Felder enthält, können globale Suchen darauf angewendet werden.

## Verfügbare globale Suchfelder

* `browser`
   * `browser`, `group_id`, `id`
* `browser_group`
   * `browser_group`, `id`
* `os`
   * `os`, `group_id`, `id`
* `os_group`
   * `os_group`, `id`
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
