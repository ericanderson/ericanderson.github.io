---
layout: post
title: your pet project doesn't stand a fighting chance
categories: []
tags:
- Code
- OSS
- Success
- Thoughts
- Tips
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  _wpas_done_all: '1'
---

Developers! Developers! Developers!

![Photo of Steve Ballmer from Wired Photostream on flickr](/assets/your-pet-project-doesnt-stand-a-fighting-chance/balmer.jpg)

Your project is probably doomed to fail, which is sad because I bet its really cool and/or helpful. Sadly though, it doesn't matter how incredible you are pumping out the codez; there is **far** more to a successful project than that. Below are some problems you are likely seeing and how you can improve your projects success. Note: these suggestions are just as valuable in open source as they are in your workplace.

## Problem 1: No one is downloading / using your project

Assuming you actually built something useful, the reason that no one is using your stuff is not that its too complex or that you're users are too dumb to get it (although simplifying always helps). It's because you're not doing a good job at convincing them that Pet Project v1.0 will help them.

Think about the last time you heard about a new library or tool and hit the google, only to find no documentation (maybe some rdoc/javadoc if you are lucky, not that they commented on the methods/classes), no screenshots, no screencast, no examples, and hardly even a readme. At this point, you probably just moved on, realizing you didn't care that much.

If you are making any kind of user interface, take screenshots. They don't take that long.

If you're tool/library is sufficiently complex, make a screencast. It won't take that long. (Without any evidence of course, I think its this fact alone that made things like rails, heroku, and node so popular. Look at that cool video that built something real and deployed it in less than 5 minutes!)

Go back in time (if you're old enough) to look at PHP conquering the web at a time when every cgi script was written in perl. It wasn't just that PHP was easier to read/write nor that all the functions were documented online. It was that there were hundreds of tutorials that could concisely show you the php patterns for talking to mysql or reading a file. So write some tutorials. Write a README too. Done right, a README works as a pretty nice tutorial.

People, especially in this highly connected world are lazy. They are bombarded with information 24/7. They don't have time to figure out your project just to evaluate it. They want to know NOW! They'll put the time in once you've shown them its worth it. **You have to "market" your project to compel people to try it.**

## Problem 2: Your users don't stick around

Users won't typically stick around just because you made something. You can't be a complete dickhead and respond harshly to their emails/bugs. You can't ignore them. You can't just put the documentation out there and call it a day. You can't say, "its open source, submit a patch." Most people don't contribute code back. I don't know why, but even when its clearly spelled out as an option, they just don't do it. What people do do (hehe) is ask for help or submit bugs. (They also complain, but whether its twitter or the lunch room, if you are paying attention, you can get the feedback).

So, the question remains, how do you handle this FREE feedback? Do you help the users? Do you write up a FAQ? Do you fix the bugs they report? Do you help them work around their issues (even if it means debugging THEIR code)? Do you plan their improvements and communicate their timeline? Update your wiki?

Its not even enough to do these things every now and then. You have to do them now. **If they have to work around your project too much, without your help, they will have no reason to stick with you.**

Everyone has an agenda, list of goals, schedules, and goals. If you help someone get to their goals quickly, they will appreciate your help and will probably help someone else with similar issues that they had. This is important for your project, as not only do you keep your users, the users actually start promoting your project in various ways.

Which brings us to...

## Problem 3: You don't foster a community

Its great that you tackled problems 1 and 2 before they even became problems. Pat yourself on the back but don't start resting yet. If you hadn't noticed, all of the above takes a lot of time and effort. Luckily, now that you have the users, you don't need to go at it alone, but you do need to encourage a community so that your users help you.

Of course they'll tell their friends and boss about how great you tool/framework is. But if you have a forum for help, they'll probably start helping other users. If you have a mailing list, they will answer questions before you have to. They'll sit on your irc channel helping people. They'll help you test out new versions. They'll be a sounding board for future features. And eventually, they'll start contributing code.

But you have to foster this. You need to create the mailing lists or forums. You need to link to helpful blog posts from your README. You need to make it clear where to go for support. You need to make it clear how others can help. And if you want help developing, you better write docs on compiling/building/running tests.

You may not always have time to work on your project and as amazing as it feels to be critical to its success, **the best thing you can do is make the project resilient to your absence.**

## Bottom line

All projects have Product Manager(s), Project Manager(s), Community Managers, Support and Documentation teams, Designers, Developers, and QA. One day, when your project is a wild success, various people will fill these roles (even in open source), but for now, as the sole developer of Pet Project, **its up to you**.
