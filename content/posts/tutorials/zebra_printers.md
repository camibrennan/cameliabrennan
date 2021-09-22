---
title: "Zebra Printers" 
date: 2021-09-20
draft: false
description: A tutorial about trying not to cry when your Zebra printer breaks. 
---

Zebra printers seem to either work really well or are broke at the most devastating time possible. 

I recently set up a Zebra printer using a Mac in order to bulk print postage for webstore orders using ShipStation. Prior to doing this, I had always relied on the assistance of an IT department &mdash; so I assure you, you can do this yourself, and everything you read about them not working on Mac's is not true! Label printers can take a little time to set up initially, but can really improve your fulfillment work flow. If you're able to bulk print postage labels, you can significantly expedite the packing and posting step for large mailings. 

**Example:** An album pre-order or promotional mailing where recipients all receive the same item. 

**Here are some miscellaneous tips I learned from recently setting up a Zebra printer (G-Series) to use with a Mac desktop.**

## Calibration

If you just purchased new printer labels or they start printing unevenly or weird, you can [calibrate the machine](https://www.zebra.com/us/en/support-downloads/knowledge-articles/g-series-gk-models-calibrating-the-printer.html) by holding down the button on the front of the Zebra printer. This works well for standard labels. I was at first skeptical that holding down a button until it blinked back at me a certain amount of times could resolve a problem, but it works!

Hold down the feed button until it flashes twice and then release. Other models may be different, but the Zebra support site will show what all the different flashes do in more detail. [Here is an example for the G-Series.](https://supportcommunity.zebra.com/s/article/G-Series-Feed-Button-Modes?language=en_US)


## Zebra Printer Driver Settings
If calibrating the machine doesn’t resolve your problem you’ll likely want to poke around in the driver settings. I found this to be the most intimidating, but it's only a little tricky once you get the hang of it. 

**You can’t adjust the Zebra printer settings in the normal printer settings**, but you can do using your Terminal application! If it's your first time using this application &mdash; you can use command space, then type "terminal" on a Mac.

Once your Terminal is open, **paste:** 

```sh
cupsctl WebInterface=yes
```

**Hit enter!**

You can now view our Zebra printer settings here under "Administration" by going here in your browser: **http://localhost:631/printers/**

[Here](https://www.zebra.com/us/en/support-downloads/knowledge-articles/ait/Install-CUPS-driver-for-Zebra-Printer-in-Mac-OS.html) is a good resource for more details on how to do this if you get stuck. 

**If prompted, your user name and password are whatever your username and password is for your computer.**

Try adjusting the **Media Tracking** , **Media Size** and **Media Type** setting under the Administration tab.

The label manufacturer should provide information regarding what settings to use and hopefully the size of the labels is clear, but if not give them a quick measure. From my experience, **"Web Sensing"** were most common as they're easiest to peel off but have a slight gap between each label. If there is no gap and the labels all run together, select **"Continuous"**. 

If this is still not working out [check here](https://support.zebra.com/cpws/docs/cups/cups_driver1_4_configure.pdf
) for some more information about how to configure your Zebra printer settings using CUPS. 

Godspeed. You can do it! 

