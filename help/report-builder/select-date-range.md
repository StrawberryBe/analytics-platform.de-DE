---
title: Auswählen eines Datenbereichs in Report Builder in CJA
description: Beschreibt die Verwendung des Kalenders, rollierender Datumsangaben und benutzerdefinierter Ausdrücke in Report Builder für CJA
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
source-git-commit: b655813816b2a8e0d47b035eefa11926f106ee0e
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 2%

---


# Datumsbereich auswählen

Um den Datumsbereich eines vorhandenen Datenblocks zu ändern, wählen Sie Datenblock bearbeiten oder verwenden Sie das Bedienfeld SCHNELLE BEARBEITUNG .

Verwenden Sie die folgenden Optionen, um einen Datumsbereich für einen Datenblock zu ändern.

**Kalender**

Mit dem Kalender können Sie statische oder rollierende Datumswerte mit den folgenden Optionen erstellen:

- Datumsbereich-Feld
- Kalender
- Dropdown-Menü &quot;Voreinstellung&quot;
- Rollierender Datumsmodus
- Ausdrücke anpassen


**Aus Zelle**

Mit der Option Von Zelle können Sie auf Daten verweisen, die in Zellen eines Arbeitsblatts eingegeben wurden.

Sie können den aktuellen Tag für einen beliebigen Datumsbereich ausschließen.

![](./assets/image17.png)

## Verwenden des Kalenders

Wenn Sie **Kalender** verwenden, zeigt das Datumsbereichsfeld den aktuellen Datumsbereich für die Datenblock-Anforderung an. Sie können Datumsangaben direkt in das Datumsbereichsfeld eingeben oder eine Datumsbereichsauswahloption verwenden.

### Datumsbereich-Feld

So geben Sie Daten direkt in das Datumsbereichsfeld ein

1. Klicken Sie auf das Datumsbereichsfeld neben dem Kalendersymbol.

1. Geben Sie das Start- und Enddatum für Ihren Datumsbereich ein.

### Kalender

So wählen Sie Datumsangaben mithilfe des Kalenders aus

1. Klicken Sie auf das Kalendersymbol, um einen monatlichen Kalender anzuzeigen.

1. Klicken Sie auf ein Startdatum.

1. Klicken Sie auf ein Enddatum.

Um einen Datumsbereich rückwärts festzulegen, klicken Sie zuerst auf das Enddatum und dann auf das Startdatum.

![](./assets/image18.png)

### Dropdown-Menü &quot;Voreinstellung&quot;

Das voreingestellte Dropdown-Menü enthält einen Standardsatz vordefinierter Datumsbereiche und Datumsbereichskomponenten für eine von Ihnen gespeicherte Datenansicht oder eine für Sie freigegebene Datenansicht.

### Rollierende Datumswerte

Mit der Option Rollierende Datumswerte können Sie einen Datumsbereich mithilfe rollierender Datumswerte auswählen.

1. Wählen Sie **Rollierende Datumswerte verwenden** aus.

1. Wählen Sie einen rollierenden Ausdruck für Ihr Start- und Enddatum aus.

   ![](./assets/image19.png)

   **Start von**  - Ermöglicht die Auswahl des Anfangs eines Tages, einer Woche, eines Monats, eines Quartals oder eines Jahres.

   **Ende von**  - Ermöglicht die Auswahl des Endes eines Tages, einer Woche, eines Monats, eines Quartals oder eines Jahres.

   **Fester Tag**  - Ermöglicht die Festlegung eines Start- oder Enddatums, während das andere Datum rollierend ist.

1. Wählen Sie als rollierenden Zeitraum Tag, Woche, Monat, Quartal oder Jahr aus.

   ![](./assets/image20.png)

1. Fügen Sie Tage, Wochen, Monate, Quartale oder Jahre ab dem rollierenden Datum hinzu oder subtrahieren Sie diese.

   ![](./assets/image21.png)

1. Klicken Sie auf Weiter , um den Datenbereich zu definieren.

   Verwenden Sie die Datumsvorschau, um zu bestätigen, dass der resultierende Datumsbereich der gewünschte Bereich ist.

### Benutzerdefinierte Ausdrücke

Mit der Option für benutzerdefinierte Ausdrücke können Sie den Datumsbereich ändern, indem Sie einen benutzerdefinierten Ausdruck erstellen oder eine arithmetische Formel eingeben.

1. Wählen Sie **Rollierende Datumswerte verwenden** aus.

1. Wählen Sie **Benutzerdefinierten Ausdruck verwenden** aus.

   Wenn Sie die Option **Benutzerdefinierten Ausdruck verwenden** auswählen, sind die standardmäßigen Steuerelemente für rollierende Datumsbereiche deaktiviert.

   ![](./assets/custom_expression.png)

1. Geben Sie einen benutzerdefinierten Ausdruck ein.

   Eine Beispielliste von benutzerdefinierten Ausdrücken finden Sie unter **Datumsausdrücke**.

1. Verwenden Sie die Datumsvorschau, um zu überprüfen, ob der resultierende Datumsbereich der gewünschte Bereich ist.

#### Benutzerdefinierten Ausdruck erstellen

1. Geben Sie eine **Datumsreferenz** ein.

1. Fügen Sie **Datumsoperatoren** hinzu, um das Datum in die Vergangenheit oder Zukunft zu verschieben.

Sie können einen benutzerdefinierten Datumsausdruck eingeben, der mehrere Operatoren enthält, z. B. ```tm-11m-1d```.

#### Datumsangaben

In der folgenden Tabelle sind Beispiele für Datumsreferenzen aufgeführt.

| Datumsreferenz | Typ | Beschreibung |
|----------------|--------------|----------------------------|
| 01.01.10 | Statisches Datum | Im ISO-Datumsformat eingegeben |
| td | Rollierendes Datum | Beginn des aktuellen Tages |
| tw | Rollierendes Datum | Beginn der aktuellen Woche |
| tm | Rollierendes Datum | Beginn des aktuellen Monats |
| tq | Rollierendes Datum | Beginn des aktuellen Quartals |
| ty | Rollierendes Datum | Beginn des laufenden Jahres |

#### Datumsoperatoren

In der folgenden Tabelle sind Beispiele für den Datumsoperator aufgeführt.

| Datumsoperatoren | Einheit | Beschreibung |
|----------------|---------|--------------------|
| +6d | Tag | Hinzufügen von 6 Tagen zur Datumsreferenz |
| +1w | Woche | Eine ganze Woche zur Datumsreferenz hinzufügen |
| -2 m | Monat | 2 vollständige Monate bis zur Datumsreferenz abziehen |
| -4q | Quartal | 4 Quartale zur Datumsreferenz abziehen |
| -1y | Jahr | 1 Jahr bis Datumsreferenz abziehen |

#### Datumsausdrücke

In der folgenden Tabelle sind Beispiele für Datumsausdrücke aufgeführt.

| Datumsausdruck | Bedeutung |
|-----------------|--------------------------------------|
| td-1w | Erster Tag der letzten Woche |
| tm-1d | Letzter Tag des vorherigen Monats |
| td-52w | Am selben Tag, vor 52 Wochen |
| tm-11m-1d | Letzter Tag des gleichen Monats im letzten Jahr |
| &quot;2020-09-06&quot; | 9. Sept. 2020 |

## Datumsbereich aus Zelle

Der Datumsbereich kann in Zellen eines Arbeitsblatts angegeben werden. Verwenden Sie die Option **Datumsbereich von Zelle** , um das Start- und Enddatum des Datenblocks aus ausgewählten Zellen auszuwählen. Wenn Sie die Option **Von Zelle** auswählen, zeigt das Bedienfeld die Felder **Von** und **Bis** an, in die Sie einen Zellenspeicherort eingeben können.

![](./assets/image23.png)

## Heute ausschließen

Wählen Sie die Option **Heute ausschließen** aus, um den aktuellen Tag aus einem ausgewählten Datumsbereich auszuschließen. Wenn Sie sich dafür entscheiden, heute einzubeziehen, werden möglicherweise unvollständige Daten für heute abgerufen.

Wenn diese Option aktiviert ist, schließt die Option **Heute ausschließen** den aktuellen Tag aus allen Datumsbereichsmodi aus, einschließlich Kalender, rollierenden Datumsangaben oder benutzerdefinierten Ausdrücken.

## Gültige Datumsbereiche

In der folgenden Liste werden die gültigen Datumsbereichsformate beschrieben.

- Das Start- und das Enddatum müssen im folgenden Format angegeben werden: YYYY-MM-DD

- Das Startdatum muss vor dem Enddatum liegen oder damit übereinstimmen. Beide Daten können auf die Zukunft eingestellt werden.

- Bei Verwendung rollierender Datumswerte muss das Startdatum heute oder in der Vergangenheit liegen. Sie muss in der Vergangenheit liegen, wenn die Option **Heute ausschließen** aktiviert ist.

- Sie können einen statischen Datumsbereich für die Zukunft erstellen. Beispielsweise müssen Sie möglicherweise ein künftiges Datum für den Start einer Marketing-Kampagne in der nächsten Woche festlegen. Mit dieser Option wird eine Arbeitsmappen-Überwachung für eine Kampagne im Voraus erstellt.

## Datumsbereich ändern

Sie können den Datumsbereich eines vorhandenen Datenblocks bearbeiten, indem Sie im Bedienfeld BEFEHLE die Option Datenblock bearbeiten auswählen oder indem Sie im Bedienfeld SCHNELLE BEARBEITUNG den Link Datumsbereich auswählen.

**Datenblock bearbeiten**  - Ermöglicht die Bearbeitung mehrerer Datenblock-Parameter (einschließlich Datumsbereich) für einen einzelnen Datenblock.

**Schnellbearbeitung: Datumsbereich**  - Ermöglicht die Bearbeitung des Datumsbereichs eines oder mehrerer Datenblöcke.

So bearbeiten Sie den Datumsbereich im Bedienfeld &quot;SCHNELLE BEARBEITUNG&quot;

1. Wählen Sie Zellen in einem oder mehreren Datenblöcken in einem Arbeitsblatt aus.

1. Klicken Sie auf den Link **Datumsbereich** im Bedienfeld SCHNELLANBEARBEITUNG .

1. Wählen Sie den Datumsbereich mit einer der Datumsauswahloptionen aus.

1. Klicken Sie auf **Übernehmen**.


Report Builder wendet den neuen Datumsbereich auf alle Datenblöcke in der Auswahl an.
