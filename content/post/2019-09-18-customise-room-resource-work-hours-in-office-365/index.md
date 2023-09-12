---
date: "2019-09-18T00:00:00Z"
title: Customise Room Resource work hours in Office 365 
categories:
- Microsoft
aliases:
    /2019/09/customise-room-resource-work-hours-in-office-365/
---
I have recently started setting up Room Resources in our Office 365 tenant and quickly discovered that that rooms are only available Monday to Friday 08:00 to 17:00 by default.

Fortunately there is a Powershell command to modify this to suit your room requirements.

First connect to Exchange PowershellSet-MailboxCalendarConfiguration -Identity <SMTPRoomResource> -WorkingHoursStartTime 00:00:00 -WorkingHoursEndTime 23:59:59

This is for an individual room resource. Alternatively if all your rooms have the same availability schedule you can change all at once with the command below

```Powershell
Get-MailBox | where {$_.ResourceType -eq "Room"} | Set-MailboxCalendarConfiguration -WorkingHoursStartTime 00:00:00 -WorkingHoursEndTime 23:59:59
```
