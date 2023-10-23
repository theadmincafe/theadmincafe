---
title: Verbindung zu Exchange Online mit Powershell
date: 2023-23-10
description: Verbindung zu Exchange Online mit Powershell
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