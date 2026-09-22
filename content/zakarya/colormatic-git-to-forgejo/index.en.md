+++
date = "2026-09-21"
draft = false
title = "Migrating Colormatic Git to Forgejo"
+++

On September 21st, 2026, we officially switched from Gitea to Forgejo on Colormatic Git. This blog covers why I made this decision, and how I used an AI agent to manually migrate the production data.

<!--more-->

I originally created Colormatic Git because I didn't want to rely on GitHub for hosting our code. Since then, GitHub has only gotten worse, and hosting code ourself gives us sovereignty and self-reliance that I want to be a common theme for Colormatic. I chose Gitea because at the time, it was the commonly accepted standard for self-hosting a GitHub-like Git system. However, Gitea was on a trend of decreasing community sentiment because of some decisions they had made, and some community members decided to fork the project into a new project called Forgejo. I had heard about Forgejo a couple months after creating Colormatic Git, but migrating wasn't an option because the two projects had already diverged too much.

Over time, I continued to hear more negative sentiment towards Gitea, and positive sentiment towards Forgejo. I even had a little incident with CVE-2026-59774. I really wanted to use Forgejo, but how was I going to switch to it if a migration isn't possible?

You know what, I'll just do it regardless of whether it's "possible". AI has gotten good enough that I can have it assist me in performing the migration, so a task that would require a prohibitive amount of dedication and time was much quicker with LLM assistance. I spent last week getting everything together, making sure I prepared everything that is needed for the migration, then I had the agent run for half of the day yesterday while I rested for the Sabbath. I thought it was pretty cool. Today at 10:00 PM PDT we performed the actual cutover, where I had to steer the LLM to make sure it was doing things correctly.

Although I am very critical of AI and especially the people creating it, this technology has proven to be revolutionary for programming and working with computers in general. I understand the people who are upset and think that it shouldn't be used at all, but I think it is a powerful tool that can be used for good, evil, and stupid alike.

I am exited for the future of Colormatic Git and the awesome things we will be able to build going forward. This experience has taught me that it's important to think about the tools we rely on, switch them out when we need to, and decide what is and isn't an acceptable use.