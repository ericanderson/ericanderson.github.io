---
layout: post
title: Using Pretty URLs with Spring and Annotations
categories: []
tags:
- Java
- Spring Framework
status: publish
type: post
published: true
meta:
  aktt_notify_twitter: 'yes'
  _aktt_hash_meta: ''
  _edit_last: '1'
  _wp_old_slug: ''
---
<strong>Update June 15th, 2010</strong>: This page is no longer relevant. Spring 3 provides a much cleaner annotation driven method for nice URLs. This page is likely only relevant to you if you are using legacy Spring 2 or 2.5.

I’m currently working on a Java Web App with Spring. If you aren’t familiar with the <a href="http://springframework.org">Spring Framework</a>, especially with the annotation support, then you’ve never had the pleasure of developing a web app in Java (but you may have experienced the pain). In another post, I will explain why this is so amazing, but for now lets just assume you know.

If you notice on blogs or other sites they have something called “pretty urls”. Essentially if you had a blog, this lets you have <code>/post/welcome-to-my-site/</code> instead of <code>/post/?id=33</code>. Using the Spring Framework and the hot new annotation support in 2.5.1, you can easily achieve that.

Specify your url on your method like so:

{% gist 805060 %}

Now all we need to do is pull out the part of the URL that has whats in the star. I’ve created the following class to assist in this manner:

{% gist 805063 %}

So equipped with this class, you only have to do the following:

{% gist 805067 %}

Note: This will also (sort of) work if you have a url like: <code>"/post/*/*/"</code> (the array will have a length of 2). However, if you get <code>"/post/welcome/"</code> as the URL from the user, <code>breakUri()</code> will return null, in which case you might want to check for <code>"/post/*/"</code>.

Now, this code isn’t very complex but it does allow you to deal with pretty urls without the hassle of building the regex yourself (something you may sometimes have to do!)

Finally, I’ve put <a href="http://jira.springframework.org/browse/SPR-4451">a request</a> into the fine folks that develop the Spring Framework to include this type of functionality out of the box so your method could be something like:

{% gist 805070 %}

Please go <a href="http://jira.springframework.org/browse/SPR-4451">vote for that feature</a> at Spring’s issue tracking database.
