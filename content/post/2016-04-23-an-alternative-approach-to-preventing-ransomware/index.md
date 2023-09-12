---
date: "2016-04-23T00:00:00Z"
title: An Alternative Approach to Preventing Ransomware ?
categories:
- Cyber Security
---

The rise in the prevelance of 
[Ransomware](https://en.wikipedia.org/wiki/Ransomware) hasn't really impacted on Mac Users as it has with the Windows community so far... 
Of course the Mac has benefited from a secure design and being a smaller (relatively) target over the years, but with the growth in use of OS X and the maturity of the tools used by unscrupulous elements this security by obscurity can no longer be guaranteed.

When the official downloadable version of the popular BitTorrent client, 
[Transmission](https://www.transmissionbt.com), was infected with a Ransomware client (
[KeRanger](https://en.wikipedia.org/wiki/KeRanger)) in March year it seemed that the reality had come home to roost. The fact is Ransomware poses one of the biggest risks to everyones personal data so it is exciting to hear of a company who are trying to tackle the issue with a form of early detection and blocking for this type of computer virus.

[Objective-see](https://objective-see.com/) is a company created by Patrick Wardle to publish security tools to protect Mac users and one of his products recently released, 
[RansomWhere?](https://objective-see.com/products/ransomwhere.html), aims to mitigate the impact of a Ransomware infection. It does this by monitoring for activity that looks like Ransomware, notably the rapid modification of multiple files. When it detects suspicious access it identifies and stops the process responsible and prompts the user to warn them that there is a potential ongoing infection. It then offers the option of killing the process or if the alert is a false positive triggered by some known bulk update process for example, to ignore it.

This approach is not infallible and of course there may still be a small number of files encrypted before it detects what is going on but if it prevents hundreds or thousands of documents from being irretrievably encrypted (without handing over cash to the Ransomware creators) it is certainly better than nothing, especially when you consider that this is not a pay monthly service or even a pay-for app but is in fact free to download. It should be noted that this is not a fully developed solution and is more of a working proof of concept so you may chose to wait for future more stable version arrives.

Patrick's site goes into quite a bit of detail which might put off less technical users and I wonder if this program works well whether it should be launched in a more user friendly package ? It's great to know the detail behind a solution such as this but most users are not that interested, they just need to know what it does and how to install. The low level information can be presented in technical specification page or a blog post. Speaking of which Patrick has a really interesting article on his site titled 
['Towards Generic Ransomware Detection?'](https://objective-see.com/blog/blog_0x0F.html) that is worth a read.

I have bookmarked 
[Objective-see](https://objective-see.com/) and will be watching this project with interest.