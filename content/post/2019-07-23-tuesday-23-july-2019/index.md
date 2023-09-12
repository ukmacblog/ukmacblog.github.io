---
date: "2019-07-23T00:00:00Z"
title: Daily Log - Tuesday 23 July 2019
description: Managing users use of Word.. Huge documents where tiny ones will do just fine...
categories:
- Microsoft
---
## Powershell

Following a recent re-brand of our charity the Marketing team distributed a number of new template documents to various teams throughout the organisation and it wasnt until after this had happened that I discovered the blank Word template they had issued was over 26MB !

Basically they had dropped a full page high resolution image onto the document to create the header and footer that resulted in a huge template. I immediately recreated ( my version was 80KB ! ) using compressed versions of the graphics cut out from their original and sent back to them, but of course the big template was already in the wild. I did manage to track down a few areas who had already created their own templates based on the huge original by running a quick Powershell script to filter out Word documents over 2MB. The script is reproduced below if you are interested

Get-ChildItem *.docx -File -Recurse -ErrorAction SilentlyContinue | Where-Object {$_.Length -gt 2MB} | Sort-Object length -Descending | Select-Object Name,Directory,@{n='GB';e={"{0:N2}" -F ($_.length/ 1MB)}} | Format-List Name,Directory,GB

## Intune

This is something I have been waiting for… Adm template deployment to Windows 10 PC’s by Intune. I will definitely been looking at this more closely tomorrow

[Microsoft Intune announces general availability of administrative templates - Microsoft Tech Community - 737412](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-announces-general-availability-of/ba-p/737412)

## Software

One of the little utilities that I use ALL the time on Windows is 
[Ditto](https://www.microsoft.com/en-gb/p/ditto-clipboard/9nblggh3zbjq?activetab=pivot:overviewtab) a nice small and unobtrusive download from the Windows Store that provides clipboard management and saves me loads of time. If you are a Mac user then check out my 
[previous post on Copied](http://ukmac.net/2016/04/copied-sync-clipboard-ios-os-x/).

If you work on a PC or a Mac you should look into clipboard managers, one of those tools that you come to rely on and miss when you are using a PC without one. 

Anyone with suggestions on how to manage clipboards across Windows AND Mac please let me know in comments…