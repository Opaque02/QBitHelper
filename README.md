# QBitHelper - made by Opaquer

Hey guys, and welcome to my Plex/discord episode notifier bot!

So, first thing's first: I'm not a programmer at all. There may be bugs, and I haven't actually tried this on anything other than my Windows PC. I'm more than happy for people to work on it and make better versions as needed. Also, I've never done this before, so I don't know if there's a better way to do this. I'm going to walk through the steps of making the bot, installing all the necessary things, and finally the code to run. I know it's a lot, and I'm sorry, but if there's a better way to do it, I'd love to hear it!

Step 1: you'll want to make a discord bot and a server on discord. There's plenty of guides out there - since I was also trying to make one, I used [this](https://www.freecodecamp.org/news/create-a-discord-bot-with-python/) one. Just go until you add the bot to your server. For permissions, I added a bunch of ones you probably won't need for testing purposes, but I think [this](https://i.imgur.com/xUfYkWo.png) is the minimum you'll need (if not, feel free to update me). Basically, it needs to be able to send/read messages and delete messages. At some point you'll get a long token for your bot - keep it for step 3

Step 2: Install Python. Google this one, there's lots of guides out there. Once you've installed it, you'll need to install discord.py and plexapi. For windows, you go to cmd and do this:

    py -3 -m pip install -U discord.py
    py -3 -m pip install -U requests
    py -3 -m pip install -U qbittorrent-api

Check your operating system on how to install it. Next go to your discord server and make a new channel. The way this works is by tracking the channel for the specific commands, and replying to that channel. I called mine download tracker

NOTE: This bot DOES delete messages, so PLEASE make a new channel for the download tracker channel. While it will work on any channel, it will try to delete every message you have if it can. You've been warned.

Step 3: The fun stuff. Download the QBit.py file. In the middle-ish, there'll be a section for your details. The botChannel is the channel the bot is going to listen/message - what we called our download tracker channel. Copy the ID of that channel (Google how to do that if you haven't got your account set up with the advanced features) and paste it in after the = sign. Do not use any quotes of any type, as this needs to be an integer.

Next is the TV and movie category. I use Sonarr and Radarr, and by default they call themselves tv-sonarr and radarr in QBit - change it to whatever you have it named to. Next is the login details for your QBit web UI version. If this is running on the same computer as your QBit is, then hopefully localhost is all you need, but change it if you need to. Next you'll need your discord token for the bot. That was from step 1.

With a bit of luck, if you save it and run it, it'll say that it's connected to the discord bot, and that it's ready to go! When that's done, go to your download tracker discord channel and type $status. This may take a sec, but it'll delete everything in the channel that's not pinned, then update the channel with what's currently downloading. 

NOTE: I set up the bot command to be $, but you can change it to whatever you want :)

Also, the reason I have it delete everything that's not pinned is so that I can have instructions on my channel with how to use the bot, and because it's pinned and everything gets deleted, this will always stay at the top. 

By default, typing $status will show everything currently downloading, but you can go a bit fancy too. There's technically 2 commands it takes - $status {media category} {download type}. The media category is either movies or tv, depending if you want to just see what movies/TV shows are downloading. The download type is either downloading (default), completed (to just see the completed stuff), or all, to see everything. For example:

Typing $status movies will show all currently downloading movies, whereas $status tv will show all currently downloading TV shows

Typing $status movies completed will show all movies that have completed downloading

Typing $status all will show everything - all movies/tv shows currently downloading AND currently completed!

And with that, you should be good to go! Sorry again this was long winded! I hope you enjoy it, and that it works nicely for you! As I said, I'm not a programmer in any fashion, so there may be bugs that I may not be able to fix, but I'm also super happy for whoever to work on it as you see fit! If you make any cool updates, let me know!
