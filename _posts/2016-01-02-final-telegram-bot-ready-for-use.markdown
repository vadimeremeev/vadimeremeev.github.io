---
layout: post
title:  "Add external libraries with the quotes and jokes to extend Telegram Bot."
date:   2016-01-01 15:58:12 +0800
categories: regexp
---

In this post we will extent our telegram bot with external API to get quote of the day, jokes and even russian quotes. After that our app will be ready to go live. 

During my research I found few good free API where I can extract the quotes and send it to our users. Let me show it to you below: 

1. [www.icndb.com](http://www.icndb.com/ "www.icndb.com")

        Amazing database with Chuck Norris quotes. Their API allows to get random quote which is suiteable for me. 
2. [www.theysaidso.com](http://www.theysaidso.com, "www.theysaidso.com")

        This web-site provide paid and free API. For free version without registration we can only get quite of the day. Which is good for us. 
3. [www.forismatic.com](http://www.forismatic.com "forismatic.com")

        provide quotes on Russian language for russian users. 

Each library will be stored in separate file in /lib folder and will have it's personal initializer. 

To get access to the specific library quote we will add additional commands to our bot starting from /

By having that every day we can enjoy best quotes and jokes from all over the world!