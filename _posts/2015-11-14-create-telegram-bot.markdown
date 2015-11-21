---
layout: post
title:  "Create telegam bot app on Ruby on Rails hosted on Heroku. Part 1."
date:   2015-11-14 15:58:12 +0800
categories: heroku, telegram botapi, rails
---


1. Lets create new folder and init new git repo there. Later we going to link it with github. Very recommend CLI tools Hub where you can manage you github repos from your command line. Then add README.md and push it to master. Now we have our code keep in safe place. Below is the commands

mkdir quote_of_the_day
cd quote_of_the_day
git init
hub create
touch README.md
git add .
git commit -am "added readme"
git push origin master

2. Lets create new rails app which will be serving requests coming from telegram. Of course ruby should be already installed. I recommend to use rbenv. Then need to install rails gem.

rails new .

3. Lets create new app in heroku. Heroku allow you to create free apps which can run within one process. It's more than enought for first version before bring it to production. I highly recomment use CLI provided by Heroku where you can manage all your apps (they call it Heroku toolbelt).

heroku apps:create motivatedquoteoftheday

After you create the app heroku gives you link to git repo which will be the key to deploy apps into heroku. All you need to do is create another remote in your git repo the rest will be done by heroku once you push there your changes. Heroku can detect your app and build it and deploy just in few seconds.

git remote add heroku https://git.heroku.com/motivatedquoteoftheday.git
git push heroku master

And you will see how the magical deployment happening. It's just fantastic.

The only thing you need to keep in mind that free version of Heroku support only postgres SQL.

4. Now lets create new telegram bot.

First you need to talk to botFather. He will guite you on how you going to create it. Once we have new bot created we need to link it with our brand new app.

How to do it I will explain you in next part.