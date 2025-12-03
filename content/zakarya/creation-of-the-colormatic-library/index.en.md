+++
title = "Creation of the Colormatic Library"
date = 2025-05-17
draft = false
+++

This is the story of how I made the Colormatic Library, a place where we can centralize all of our publications. I'll cover some technical details, history, and decisions that were made along the way.

<!--more-->

### Introduction

I started development around May 8, 2025. Before that I was working on a project that I called the "Colormatic Media Manager" that could create, organize and update resources that would be available on the Colormatic Website. I was writing it in Go, and I also used that project as an opportunity to develop the software design & development workflow for Colormatic Studios.

Recently, I realized that I was basically just reinventing a CMS *(++c++ontent ++m++anagement ++s++ystem)* but worse. The system was planned to be a command-line program that you fed content into and it would publish that on the Colormatic Website, available through a Colormatic media viewer (based on the current video player) that never left the ideation phase. It would also have been able to display documents and wouldn't suck as much.

### Technical considerations

After realizing this, I decided that I needed to set up a CMS as another Colormatic service. For the longest time, we've just been rocking the power trio of Nginx, Gitea, and Keycloak. These guys were set up so well that their deployment is almost bulletproof. I've experimented with adding more services like Grafana or a Matrix provider, but they just didn't work out (I'm still thinking about adding that Matrix provider in the future). I knew/know that if this new CMS is going to hold up to its older siblings, it's going to need to be very robust, reliable, and maintainable without needing much maintenance.

So then I needed to find a CMS software that could hold its weight. Unfortunately, PHP is a very popular language to use for making systems like this (e.g. WordPress, etc.), so that ruled out most CMS software by default. There were also a couple that were based on Node.js (e.g. Ghost, etc.), but I want to avoid running JavaScript server-side. This is for various reasons, including its lack of multithreading (I know that v8 has some multithreaded processes, that's not what I'm talking about). I briefly looked back at Mezzanine (which I was originally planning to use for the Colormatic Website but decided to do something else), but the community is kind of dead. Then I checked out the other option written in Python: [Django CMS](https://www.django-cms.org/en/). As the name suggests, it's a CMS built around the [Django framework](https://www.djangoproject.com/). I saw this as a great option mainly because Django is described as "The web framework for perfectionists with deadlines". This appeals to me because I'm a perfectionist *without* deadlines.

*Note: multithreading allows a program to do multiple tasks at the same time, which can improve performance.*

I did some research and decided on the implementation details. I learned that Django CMS comes with a lot less batteries included than Keycloak or Gitea, so I had to build my own system to integrate it with Colormatic ID. Luckily, Mozilla has already made a plugin for Django that does [OpenID Connect integration](https://github.com/mozilla/mozilla-django-oidc). By the way, authentication on the Colormatic Library is (as of writing) currently only intended for staff so don't ask me why there isn't a login page.

*Note: OpenID Connect is a standard for users to use the same account information to log in to multiple websites and applications. We use it for Colormatic ID.*

### My plans for the near future regarding content in the library

I've got a couple of ideas for more blog posts, like a "State of Translation" series that would cover my efforts to make everything we publish available in as many languages as possible. I'm also planning to make all of my videos available here as well.

I believe that the Colormatic Library will be a crucial component of Colormatic's future. Having all of our content available in one place will allow people to get a really good idea of what we do. As of writing, there are still so many things that I need to add in order to make it a robust system that is accessible and easily usable to as many people as possible. There are also a lot of bells and whistles that I've seen on other blogs that I've looked at when doing research for designing this blog that I would like to steal.

### What I learned

I think it's also important to cover what I learned from this adventure. Before going into this, I obviously had no experience with CMS's. I've since learned what blogs usually look like, how Django generally works, how to set up a Python Docker container, and much more. This has been a great learning experience and has been more software development than system administration compared to setting up Colormatic Git and Colormatic ID.

So what do you think of the Colormatic Library? You can share your feedback with me via email at [zakarya@colormatic.org](mailto:zakarya@colormatic.org).
