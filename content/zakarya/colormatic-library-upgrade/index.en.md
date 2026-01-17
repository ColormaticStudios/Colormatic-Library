+++
date = "2026-01-16"
draft = false
title = "The Upgraded Colormatic Library"
+++

After using Django CMS to run the Colormatic Library for a while, I ended up not being pleased with many core details, like storing pages in the database, synchronous database access, and the janky content system.

<!--more-->

I wanted a system that is would store pages as files rather than documents in a database, like a static site generator. I mostly chose a CMS because they have web interfaces to edit pages and that's super useful for user friendliness. Unfortunately though, I couldn't find any static site generators that have a web interface that also match the requirements of the Colormatic Stack (No PHP, C#, or Javascript server logic, cannot rely on an external service, etc).

I've heard of this program called Hugo that is a terminal-based static site generator that takes in rich text files and HTML templates and produces a full website. Unfortunately, there didn't seem to be a usable web interface for it, but other than that it matched my needs perfectly. I eventually decided to give up the web interface dream and migrate the library to Hugo.

Honestly, I don't regret my decision so far. Sure, it's a shame that I can't edit the content from my browser and that may cause some issues for staff in the future, but it has been a lot nicer to use and maintain than Django CMS.

Overall, it's in a better situation and we can think about building a web editor tool ourselves in the future. The Colormatic Library now runs as a static website, and you can [see the source code on Colormatic Git](https://git.colormatic.org/ColormaticStudios/Colormatic-Library).

NOTES:
I started this blog post soon after I finished redoing the UI for the library in Hugo on December 11th 2025, but only wrote the first paragraph. I eventually picked it back up on January 16th to write the rest.
