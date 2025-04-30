---
title: "Not Just for Hackers: How I Repurposed a Pentest Tool for a Blackout"
seoTitle: "Not Just for Hackers: How I Repurposed a Pentest Tool for a Blackout"
seoDescription: "Learn how a pentest tool can become a lifeline in a blackout, offering communication possibilities even offline."
datePublished: Wed Apr 30 2025 07:34:23 GMT+0000 (Coordinated Universal Time)
cuid: cma3meki9001l0aled7dje6rz
slug: not-just-for-hackers-how-i-repurposed-a-pentest-tool-for-a-blackout
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1745996799156/295d743a-97d2-4785-91e6-7cc1f6847901.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1745998363381/9b2e4836-2481-418c-a8de-b22af2d660e0.png
tags: php, community, self-hosted, offline, spain, blackout, wifipineapple, hak5

---

### The Network Is Down — Now What?

When the lights went out across Spain and Portugal in April 2025, it wasn’t just a power cut. It was a silence.

Elevators jammed mid-floor. Metro tunnels went black. Airports turned into echo chambers of confusion. For 8+ hours, even as power slowly flickered back into buildings, something more vital was still missing:

**Information.**

Phones had charge, but no signal. Laptops had Wi-Fi toggled on, but nowhere to connect. And in that vacuum, whispers started doing what they always do in a crisis — spreading fast, mutating faster.

No one knew what had happened. No one knew when help was coming.

And that’s exactly the moment a tiny, often-overlooked device can make a world of difference.

---

### What if there was a way to stay informed digitally— together — even offline?

The [Wi-Fi Pineapple Nano](https://hak5.org/products/wi-fi-pineapple), a cheap pocket router best known to cybersecurity tinkerers, wasn’t built for disaster relief. But it happens to be perfect for it. With a bit of preparation, this little box becomes an emergency communications node — quietly powerful in the most human way:

When people say “Where can I find water?” serve a map and list of nearby resources — no Internet needed. “I need to let my neighbor know I’m okay.” Host a local chat, instantly accessible to anyone nearby. “Did you hear a hospital was out of X?” Provide a single, verified source of local updates to stop rumors cold. “I have one phone with Internet left…” Share it via the Nano, fairly and securely, across the neighborhood.

The Nano can broadcasts an open Wi-Fi network — something like **“EmergencyNet”** — and any phone that connects instantly gets a pop-up page. No app. No login. Just local, living information.

### This isn’t about tech. It’s about trust.

When disaster strikes, misinformation spreads faster than help.  
It’s not malicious — it’s human. In the absence of news, people fill the gap with whatever they can find. An overheard conversation, a

But that’s exactly why a **shared, live, low-tech bulletin board** can matter more than extra food or candles. It becomes an anchor.

With a static site and a couple of JSON files, your Nano can carry:

* **Updates from neighbors** — who’s safe, who needs medicine, where traffic is backed up.
    
* **Shared files** — like emergency contacts, translated guides, or relief info in multiple languages.
    
* **Voice bulletin streams** — with a mic and a radio dongle, the Nano can broadcast looped updates over low-bandwidth audio.
    

And all of this works from a power bank — no grid, no cell towers, no problem.

### It doesn’t take much

A USB power bank is enough to keep the Nano running for up to **16 hours**, realistically. Two batteries, swapped morning and evening, can keep a whole street connected through the chaos.

With a second Wi-Fi dongle, it can also act as a **gateway** — tapping into any working hotspot and safely sharing the connection with everyone nearby. If someone has signal, **everyone gets it.**

Or set it higher — on a tree, balcony, or roof — and it becomes a **range extender**, passing messages from block to block. With a few of them daisy-chained together, even a full district can stay looped in.

### A few files, a little prep — real resilience

Set up your Nano now, before the next blackout:

* Preload a small HTML portal with chat and bulletin board.
    
* Point captive portal domains to the Nano’s IP so phones auto-open it.
    
* Drop in maps, contact lists, APKs, even a copy of the Red Cross first-aid handbook.
    
* Add a hand written label: *“Emergency Wi-Fi — join ‘EmergencyNet’”*
    

That’s it. No database. No server. No DNS. Just one open SSID and a page everyone sees the moment they connect.

### Because when everything else fails… clarity still matters

In a blackout, power is the first thing to go.  
But **certainty** — or the lack of it — is what really shapes the days that follow.

A €100 box can’t replace the Internet. But it can help **replace uncertainty with intel.** It can bring **structure to the mess.**  
And most of all, it can remind us that even when the grid collapses, **we don’t have to go dark.**