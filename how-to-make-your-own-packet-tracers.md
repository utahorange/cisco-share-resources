# creating your own packet tracers :)
Why suffer through pain when you can make others suffer through it too?

This doc is meant to be more of a review than a guide, so check out these two videos first, starting with Omar’s video. The YouTube video you can skip a lot and watch at 2X speed without missing anything.

## video resources
https://drive.google.com/file/d/1OiS3uE4T5VKMRLs6x0WaGy-_Bat5JT71/view?usp=sharing

^only accessible to cisco instructors

https://www.youtube.com/watch?v=XsKo3_BBCaA

## What you need
1. netacad account
2. cisco packet tracer
3. [an html editor](https://html-online.com/editor/)

## So how?
1. Create instructions and answer network
<img src="https://user-images.githubusercontent.com/86171033/147703679-91b5cae0-4d8f-4c0e-bdf0-7e08c45dfae9.jpg" width="400">

If the cli tab is missing for your routers, switches, go to *Preferences -> Show/Hide* and uncheck a few options.

**DO NOT** ```DO WR```

2. Extensions -> Activity Wizard and add a password
3. Begin checking off all the items you want scored
   - can show completion percentage
4. Copy initial network from answer network
5. Clear what you want to clear and/or lock specific items
   - on switch (privileged exec mode)
   ```
   erase startup-config
   del vlan.dat
   reload
   ```
   - on router
   ```
   erase startup-config
   reload
   ```
   - on pc/server, click on dhcp and back to static in *IP Configuration*
   
   
6. Copy-and-paste html of instructions into packet tracer
7. save-as and troubleshoot/try it out!
