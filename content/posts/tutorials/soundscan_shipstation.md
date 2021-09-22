---
title: "How to Compile SoundScan Data Using ShipStation"
date: 2021-03-13
draft: false
description: A tutorial about compiling SoundScan Data using Shipstation
---

**UPDATE:** I'm currently working on a tool that does this automatically, but in the meantime ... 

### Add UPCs into ShipStation: 

The first step is to make sure all the UPCs for your releases are in ShipStation. It should pull these in with your product information automatically depending on what webstore you’re using, but if you don’t see them just go to **Products > All Products >** and you can add the UPC to each item. 

ShipStation does not seem to import this information automatically from Bandcamp, the last I checked — but Bandcamp reports sales to SoundScan. So, **you won’t need to report Bandcamp sales to SoundScan**, unless you’ve left the UPCs out on your Bandcamp listings or would prefer report them yourself. 

You should be able to bulk import UPCs if you export the existing products, add the UPC and then import back in again.

If you update these manually make sure to click “apply changes to open orders” next to the save changes button, so it’ll update your report for orders places before you updated the UPC. **Example:** Pre-orders you have not yet reported and want to make sure are included on first week sales.  

![UPC](/images/soundscan_1.png)

### Prepare a Report to Export: 

**Go to**: Orders > Advanced Search > Order Status: select “Awaiting Shipment” & “Shipped”  
“Order Date” select week you wish to report 

 +More Criteria … add Criteria : Country is Equal to United States

Hit Search! 

Once you’re viewing the orders you want to report — you’ll want to export this into a .csv. 

Click on the “Other Actions” drop down > Export Order Line Items “create a new format”, the select the fields you want to export 



![Export](/images/soundscan_2.png#center)


Now select the fields you want — date, store name, order date UPC etc. You won’t actually need more than the UPC and Zip Code and QTY but I include the name and full address and item names just so its easier to look at and make sure the information I’m looking at looks legit. 

![example](/images/soundscan_3.png)

You can name this and save so you can use it again! Hit Export! & download 

### Importing the ShipStation .csv file into Google Docs: 

I don’t have excel on my computer so I think it is easiest to just keep this in your downloads folder and then import from there into a google doc because lets face it, Numbers fucking sucks. 

I would suggest creating a blank sheet in google docs:
**File > Import > Upload > select a file from your device > find your ShipStation export .csv file > “open” > Import File & click “replace spreadsheet”**

Import Data! 

![example](/images/soundscan_4.png)


### Combining the UPC & Zip Codes:

Ok so now you’re almost done — all thats left is making the 9 digit zip code 5 digits & making a column with a formula to combine everything. 

Lets start with the zip code! Make a new column next to the zip codes, I usually just call it “short zip” but it does not matter.

A formula to take just the first 5 digits of the zip code if the zip code is in column J, row 2 is **=left(J2,5)** 

Then, you can just click the cell you want and google docs will automatically plug it in, or you can manually just type it in: 

![=left(J2,5)](/images/sounscan_5.png)

Once you have this in there are several options to copy this all the way down to apply to all the Zip Codes. Google docs usually pops up a suggestion to auto fill and you can just hit the green check and it will copy the formula all the way down adjusted for each cell:

![Auto Fill](/images/soundscan_6.png)

Sick! I’m assuming everyone also has to put some letters and numbers ahead of and after the UPC & Zip Code like so: 

Example: 
**M30 + 12 digit UPC + 5 Digit Zip Code + S**

If you have a 13 digit UPC you will omit the 0 after "M3". 

You’ll want to make a new column where your finalized list for SoundScan will live, and use the concatenate function to combine all this stuff together easily. This will look something like this: 

**=CONCATENATE("M30" & D2 & K2 & “S")**

Put “ ” around the letters, and plug in the cell where the UPC & Zip Code are (for me the UPC lived in D2 & the 5 Digit Zip Code in K2). Pull this all the way down using auto fill and you’re all done! 

If you need to then place this list in a different document, make sure to paste using **Edit > Paste Special > Paste Values Only**.

Hopefully this is helpful to someone other than me! This is the extent of my knowledge as we then send just the completed list to our distributor. If you are working independently w/ SoundScan I’m not quite sure how that work flow works.

Please feel free to [email](mailto:cameliabrennan@gmail.com) me if you have experience with what happens if you don’t have a distributor who helps, and I’ll add those instructions in to make this more helpful for those next steps. Otherwise I'll add them as soon as I find out!