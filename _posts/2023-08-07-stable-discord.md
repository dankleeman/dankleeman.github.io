
---
title: "Stable Discord"
category: "Hobby Projects"
---

Repository: [https://github.com/dankleeman/stable-discord](https://github.com/dankleeman/stable-discord)
# Background
Earlier this year I got really into the whirlwind of generative AI as stable diffusion made it a lot more accessible for consumer hardware. I had initially started out with Midjourney but between the cost of that service and the occasional service outage I wanted something that ran on hardware I controlled. Further, not all of my friends wanted to pay for Midjourney but I really enjoyed the collaborative aspect of the service. When Midjourney was making that one of their big selling points I was initially skeptical of how important it would be, but after just one evening of bouncing ideas off of my friends I was sold.

To solve this problem I started working on "Stable Discord" which is an implementation of stable diffusion that uses a Discord bot as a frontend.  I've been playtesting this tool with my friends and just finally put the finishing touches on it enough to justify a release v1.0. 

# Project Overview
For more of the specifics, I'll let the README.md and repository speak for itself because I strove for as much of a self-contained approach here as possible. If a user wants to make changes to the code I tried to make that simple but avoidable as possible. For any user who wants to just get started right away, they should have to change nothing but the config.toml constants. This includes a variety of behavior changes from the diffusion model using GPU or xformers to cosmetic things like emojis to use when responding to a user or setting the wake word.

# Example Usage


# What's Next?
Stable Discord currently includes an "ignore-users" feature intended to prevent select users from giving commands to the bot. I had two uses in mind for this. Firstly, it is a rudimentary sort of spam defense which may be easier than putting every user on the allowed list. Secondly, and most helpfully, it allows two users to run Stable Discord in the same Discord channel and prevent the bots from hitting a sort of infinite loop a la [Talking Carl](https://www.youtube.com/watch?v=t-7mQhSZRgM). 

Only disallowing bots from each other, however still means that every command from a human gets processed by each bot causing duplicate output. Another option would be for every bot to have a unique wake word which still adds a layer of friction and manual intervention that I would like to avoid.

I would like to use this project as a leaping-off point to a similar idea that allows multiple users to contribute computing power as a pool to power a single bot. In this configuration users with slower machines can still help but aren't limited to the speed of their machine if other users' machines are free. I'm still sketching this out, but I think it could be viable to have the Discord bot controlled by a a light-weight process acting as a command and control server to which the GPU clients connect and offer up their time. The C&C server could maintain a queue of requests and a queue of clients and just match tasks to machines and return results.

I'll follow up if that's something I get working in a reasonably useable way.
