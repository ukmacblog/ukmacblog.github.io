---
date: "2020-12-08T00:00:00Z"
title: Daily Post - 08/12/2020
categories:
  - Microsoft
---
## Email Pains

Today has been a painful day trying to resolve an issue with Mail rules in Exchange Online. Yesterday I switched on a Malware Policy to block certain files types after reading [this article.](https://regarding365.com/a-little-bit-more-security-fb6825ef8435?source=rss----604cd9a532f6---4) All seemed fine but then first thing this morning I received a number of calls from users unable to email Helpdesk calls to our Helpdesk system ([Freshdesk](https://www.freshdesk.com)). It seems as though the change I made yesterday had triggered a mail rule setup to block users autoforwarding emails externally into action that must not have been working before.

To log calls with Freshdesk by email you send to a specific email address that is created when Freshdesk is configured. To make things easy for my organisations users I had setup a shared mailbox with the email address support@xxxx and instructed them to log calls by emailing this address. The shared mailbox was then set to autoforward to the Freshdesk email address. This autoforward was now broken and so users were unable to log calls or reply to existing ones.

Unfortunately trying to fix mail rules in Exchange is made more difficult due to the very long time it takes for changes made to become operational. According to [Lance Cal in this Microsoft Community thread](https://answers.microsoft.com/en-us/msoffice/forum/msoffice_o365admin-mso_exchon-mso_o365b/dlp-and-mail-transport-rules-in-eac/75486160-ee0e-4cc2-a9cb-a9311630cf83) changes can take up to 12 hours to become active. Thats a whole working day before I can see if the change I made to fix our issue works and during which time our IT Helpdesk that relies on email autoforward rules to operate remains unusable.

## Update

It seems that Exchange mail rules is not what I should have been looking at after all. What I discovered was that the mail rule I thought was blocking the autoforward was not being triggered at all. I found this by running the mail rule report ( shown highlighted in red in diagram below )

![Mail rule report](/images/2020-12-08-daily-post/mail-rule-report.jpg "Mail rule report")

Once I could see that no emails were matching the rule I started looking for other places where autoforwarding might be blocked. I had suspected there was probably something in the 365 Security and Compliance site that was responsible and the obvious culprit was in the [Anti-Spam](https://protection.office.com/antispam) settings. What I found here was that the "Automatic forwarding" setting was set to "Automatic - System-controlled". Changing this to "On - Forwarding is enabled" immediately resolved the issue I was having but of course at the same time changed the default policy for all users to allow auto-forwarding externally.

![Outbound spam filter policy](/images/2020-12-08-daily-post/outboundspam.jpg "Outbound spam filter policy")

To fix this I needed to add a new Outbound policy that blocked all users from autoforwarding but excluded the Helpdesk shared mailbox. The rule below does this and the best part is changes are effective immediately so no waiting for 12 hours for mail rules to take effect.

![Additional outbound rule](/images/2020-12-08-daily-post/outboundrule.jpg "Additional outbound rule")

A long day but hopefully one where I learned something about the way that mail policies work.

