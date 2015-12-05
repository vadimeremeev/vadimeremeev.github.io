---
layout: post
title:  "Create Telegam Bot. Part 2."
date:   2015-11-21 15:58:12 +0800
categories: heroku, telegram botapi, rails
---

In this post we will create new Telegram bot and link it with our awesome heroku app.

1. Ask BotFather to create new bot. 

        https://core.telegram.org/bots

2. There are two possibility to catch the messages from the bot within your app. First is by incoming callback function. And second constantly asking bot if there are new messages and if there are catch it. We will go for first option which is more flexible for us. 

        https://core.telegram.org/bots/api#setwebhook

3. Before that lets create tune rails app a bit by adding postgres DB which will have all our quotes, models, controller and library to work with Telegram

4. First lets create an ability to receive incoming requests from our beautiful bot. For this we need to define new method in our controller and link it with the url path which better make very unpredictable. To make sure that no other applications can send there data. Lets call it incomingdatafromtelegram9573. Then we need to register our callback in our bot by sending post request with the authorisation token and the url itself. Before that let's deploy our code with ability to see the incoming requests in the logs.

5. Heroku provides perfect logging system which allows to see different kind of logs in the same place. Just type heroku logs -t. To enable rails logs be part of it we need to do install gem rails_12factor which allows output logs into stdout to catch it later by heroku logging system. Also we need to add follow line into out controller to allow incoming post requests: 
        
        skip_before_action :verify_authenticity_token 


6. Once we have everything completed lets commit changes and push to heroku and test that incoming data are coming in to our URL. To do that let's tail logs in heroku and send post url. We should be able to see that data are coming in. 

7. Then lets tell to our bot where to send incoming requests. To do that we need to send follow get request: 

        https://api.telegram.org/API_TOKEN/setWebhook&url=URL. 
    
    API Token need to request from BotFather by asking /token.

8. Then let's add bot in your Telegram and test out the message but tailing the logs in our beautiful heroku toolbelt. Now you should see incoming json coming from telegram.

Congratulations! Now we have bot and we have app which can receive messages  from the bot. In next chapter we will finish our beautiful bot by adding database tables with the best quotes to motivate everyone and ability to reply and even send quote of the day once a day to those who wants to subscribe. 
