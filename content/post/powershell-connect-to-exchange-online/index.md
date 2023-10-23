---
title: Verbindung zu Exchange Online mit Powershell
date: 2023-23-10 00:00:00+0000
description: Verbindung zu Exchange Online mit Powershell
image: cover.jpg
tags: 
    - Exchange
    - M365
categories:
    - Exchange
    - M365
---

<!--more-->

In diesem Artikel wird kurz beschrieben, wie eine Verbindung zu Exchange Online bei M365 über Powershell hergestellt werden kann.

Zunächst öffnen wir Powershell als Administrator.

Nun installieren wir das Exchange Online Management Module.

Um das Modul für alle Benutzer auf dem Computer zu installieren, geben wir folgenden Befehl ein:
`Install-Module -Name ExchangeOnlineManagement`

Um das Modul nur für den aktuellen Benutzer zu installieren, geben wir folgenden Befehl ein:
`Install-Module -Name ExchangeOnlineManagement -Scope CurrentUser`

Abfragen bezüglich der NuGet-Anbieter und nicht vertrauenswürdigen Repositories akzeptieren wir mit "J".

![So sollte die Ausgabe aussehen](Connect_Exchange_Online_1.jpg)

Gelegentlich sollte in regelmäßigen Zeitabständen das Exchange Online Management Module aktualisiert werden.
Dies kann mit folgendem Befehl durchgeführt werden:

Um das Modul für alle Benutzer auf dem Computer zu aktualisieren, geben wir folgenden Befehl ein:
`Update-Module -Name ExchangeOnlineManagement`

Um das Modul nur für den aktuellen Benutzer zu aktualisieren, geben wir folgenden Befehl ein:
`Update-Module -Name ExchangeOnlineManagement -Scope CurrentUser`


Nun müssen wir das Exchange Online Management Modul laden, bzw. importieren.
Dies tun wir mit folgendem Befehl:
`Import-Module ExchangeOnlineManagement`

Sollte bei euch folgende Fehlermeldung erscheinen, dann müsst ihr zuerst die Execution Policy auf dem Computer anpassen.
![Fehlermeldung bezüglich Scripts](Connect_Exchange_Online_2.jpg)

Dies klappt mit folgendem Befehl:
`Set-ExecutionPolicy Unrestricted`

![Anpassung Execution Policy](Connect_Exchange_Online_3.jpg)

Anschließend klappt der obere "Import-Module ExchangeOnlineManagement" Befehl.


Wenn das Modul importiert wurde, können wir uns mit folgendem Befehl nun mit Exchange Online verbinden:
`Connect-ExchangeOnline -UserPrincipalName E-Mail-Adresse-@-Des-Globalen-Administrators`

![Verbindung zu Exchange Online herstellen](Connect_Exchange_Online_4.jpg)

Nach der Absetzung des Befehls öffnet sich ein Loginfenster. Hier müssen wir das Kennwort für den M365-Administrator eingeben.

![Loginfenster M365](Connect_Exchange_Online_5.jpg)


Nach der Passworteingabe sind wir erfolgreich verbunden.

![So sollte Powershell nach erfolgreichem Login bei M365 aussehen](Connect_Exchange_Online_6.jpg)

Nun testen wir noch schnell, ob wir erfolgreich verbunden sind und Exchange Online Befehle auch funktionieren.
Testweise geben wir folgenden Befehl ein um uns alle Postfächer anzeigen zu lassen:
`Get-Mailbox`

![Erfolgreiche Abfrage](Connect_Exchange_Online_7.jpg)

Das wars dann auch mit dem Artikel.