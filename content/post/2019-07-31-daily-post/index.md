---
date: "2019-07-31T00:00:00Z"
title: Powershell connection from MFA Account
categories:
- Microsoft
tags:
- PowerApps
aliases:
    /2019/07/wednesday-31-july-2019/
---

This is a Microsoft guide I need to use fairly regularly ! Wish connection to Exchange Online and Sharepoint Online from Powershell was a little easier to configure.

Interestingly when I tried this today if I ran Connect-EXOPSSesion with parameter for my UPN it didn't seem to work. If instead just ran the command with no parameters the standard login dialog appeared fine and I could enter my email address and authenticate with my Authenticator app ! Odd one...

via 
[Connect to Exchange Online PowerShell using multi-factor authentication | Microsoft Docs](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)

## PowerApps

I definitely need to come back to this one ! One of the tips here is to enable permissions to Sharepoint lists for PowerApps. The bit I need for my current project is to enable row level permissions so that users can only see entries they created. Very useful tip..

via 
[3 tips you need to know when using PowerApps forms on SharePoint lists - European SharePoint, Office 365 & Azure Conference, 2019, Prague, Czech Republic](https://www.sharepointeurope.com/3-tips-need-know-using-powerapps-forms-sharepoint-lists/)

ARGHH !

So I have created an app that uses the AzureAD connector to find the logged in users account details (Office location) only to find that when deploying this app to actual users ( who aren't Azure AD admins ) it doesn't work ! The user needs admin rights to query AzureAD so the connector is effectively no good for what I want to use it for.. Ah well.. Back to the Drawing board ! See article below for more.

via 
[Solved: Issue with Azure AD Connector - Power Platform Community](https://powerusers.microsoft.com/t5/Connectors/Issue-with-Azure-AD-Connector/td-p/66322)
