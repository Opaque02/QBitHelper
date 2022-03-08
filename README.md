# QBitHelper - made by Opaquer
#       (slash command fork by giplgwm)

Hey guys, and welcome to my Plex/discord episode notifier bot!

So, first thing's first: I'm not a programmer at all. There may be bugs, and I haven't actually tried this on anything other than my Windows PC. I'm more than happy for people to work on it and make better versions as needed. Also, I've never done this before, so I don't know if there's a better way to do this. I'm going to walk through the steps of making the bot, installing all the necessary things, and finally the code to run. I know it's a lot, and I'm sorry, but if there's a better way to do it, I'd love to hear it!

Step 1: you'll want to make a discord bot and a server on discord. There's plenty of guides out there - since I was also trying to make one, I used [this](https://www.freecodecamp.org/news/create-a-discord-bot-with-python/) one. Just go until you add the bot to your server. For permissions, the only 2 you need are "applications.commands" and "bot".

Step 2: Install Python. Google this one, there's lots of guides out there. Once you've installed it, you'll need to install interactions and qbittorrent api. For windows, you go to cmd and do this:
    cd (directory you put the bot files in)
    py -3 -m pip install -U requirements.txt

    if that fails you can install them manually with these 2 commands instead:
    py -3 -m pip install -U discord-py-interactions
    py -3 -m pip install -U qbittorrent-api

Check your operating system on how to install it. Next go to your discord server and make a new channel. The way this works is by tracking the channel for the specific commands, and replying to that channel. I called mine download tracker

Step 3: The fun stuff. Download the QBit.py file. In the middle-ish, there'll be a section for your details. The botChannel is the channel the bot is going to listen/message - what we called our download tracker channel. Copy the ID of that channel (Google how to do that if you haven't got your account set up with the advanced features) and paste it in after the = sign. Do not use any quotes of any type, as this needs to be an integer.

Next is the TV and movie category. I use Sonarr and Radarr, and by default they call themselves tv-sonarr and radarr in QBit - change it to whatever you have it named to. Next is the login details for your QBit web UI version. If this is running on the same computer as your QBit is, then hopefully localhost is all you need, but change it if you need to. Next you'll need your discord token for the bot. That was from step 1.

With a bit of luck, if you save it and run it, it'll say that it's connected to the discord bot, and that it's ready to go! When that's done, go to your download tracker discord channel and type /status. This may take a sec, but it'll update the channel with what's currently downloading. 


By default, typing $status will show everything currently downloading, but you can go a bit fancy too. There's technically 2 optional parameters it takes - /status {media category} {download type}. The media category is either movies or tv, depending if you want to just see what movies/TV shows are downloading. The download type is either downloading (default), completed (to just see the completed stuff), or all, to see everything. For example:

Typing /status movies will show all currently downloading movies, whereas $status tv will show all currently downloading TV shows

Typing /status movies completed will show all movies that have completed downloading

Typing /status all will show everything - all movies/tv shows currently downloading AND currently completed!

By default, the output will have everything that's not completed in descending order, so the things closest to completion will be at the top, and as you scroll down, it'll get closer to 0%. After all that, if there's anything that's 100% done, it'll show up at the end of the list

And with that, you should be good to go! Sorry again this was long winded! I hope you enjoy it, and that it works nicely for you! As I said, I'm not a programmer in any fashion, so there may be bugs that I may not be able to fix, but I'm also super happy for whoever to work on it as you see fit! If you make any cool updates, let me know!
