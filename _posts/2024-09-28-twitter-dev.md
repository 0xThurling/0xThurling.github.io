---
title: How Tech Twitter unironically made me a better developer
date: 2024-08-10
category: Jekyll
layout: post
cover: ../assets/twitter-header.png
---

> Before we begin, some people might wonder why not Threads or BlueSky, well the reality most of the dev community on those platforms are small and filled with people that do mostly engagement bait - much more than Twitter at the moment, so the experience engaging with people are a bit dull at times.

## Why I joined Tech Twitter

Simple, to become a famous programmer...but in all honestly I'm way too stupid for that at the moment. The real reason is simply to grow my network in-case I get fired or something. I knew that, even though I don't really enjoy social media that much, it was needed to get opportunities I otherwise wouldn't have gotten, since I don't live in "the west", meaning US, EU, and other first world countries, my opportunities here are limited if you want to move outside of the financial space one day.

I saw this video of Jonathan blow saying if you want to grow as a developer, quit your job and go work at some place like SpaceX...well, we don't have a SpaceX, or really a diverse technology sector - so while this advice might work in the US, this doesn't work mostly anywhere else and other avenues need to be taken or made.

## See people develop cool stuff in real-time

The first person I followed on Twitter was an oke (the South-African bloke) named ThePrimagen, who lives on the Lord's time of Montana and uses the Lord's text editor of neovim. I followed the process where he built doom on the CLI and how he got twitch chat to effectively play the game. This was extremely niche, but at the same time, it made me think "This is kinda neat, I wanne do things like this". You can see more of how he did it here:

<iframe style="width: 100%; height: 500px" src="https://www.youtube.com/embed/3f9tbqSIm-E" title="1000 Players - One Game of Doom" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

This was only the beginning, soon I found a guy named Kache, this was a mistake since he never shuts up...however, through all his yapping he does say some interesting things, I started following him when he was still working on his own app called Dingboard, which is an AI powered quick image editor that quite satisfying to use. This also make me want to just build stuff for the sake of building stuff, not really for money, but just for fun.

There are countless examples of this exact scenario playing out on twitter and it made me just want to get better at my craft and just make cool shit. Even if it is only for myself, I don't really care.

## Get news at the speed of thought

I cannot tell you how invaluable this aspect of tech twitter has been, I get the news extremely quick, the crowdstrike issues...covered - this actually did impact quite a bunch of our clients, luckily not us. Exploits in the linux subsystem...covered. Dumb hot takes...also covered.

Being able to just go onto twitter and immediately get the latest tech news slathered in toxicity is something I won't exchange for anything. I was able to let my dev team know on quite a few occasions of the latest developments of technology including but not limited to Google Gemini's under 18 "unsafe" C++, as shown in the tweet below:

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Gemini won&#39;t return C++ coding help if you&#39;re under 18 because it &quot;wants to preserve your safety&quot;. <br><br>h/t: <a href="https://twitter.com/warptux?ref_src=twsrc%5Etfw">@warptux</a> <a href="https://t.co/G8tE9WKltu">pic.twitter.com/G8tE9WKltu</a></p>&mdash; Evis Drenova (@evisdrenova) <a href="https://twitter.com/evisdrenova/status/1765088705860219204?ref_src=twsrc%5Etfw">March 5, 2024</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Remember kids...use protection

## See cool new technologies that most devs don't talk about or acknowledge

When being on Tech Twitter, you see the interesting new technologies, like HTMX, the "cure" to bloated Frameworks/Libraries such as React, Angular, Vue, etc. HTMX doesn't solve all the worlds problems. it still requires you to do additional things in JavaScript if you need to, but the simplicity of knowing what is actually happening on the client side is a boon I would always take over the automagic of React. This is something the creator of HTMX calls Locality of Behaviour (LoB), which essentially boils down to this:

> The behaviour of a unit of code should be as obvious as possible by looking only at that unit of code

If you want to find out more about this have a look at his website here: [HTMX Locality of Behaviour](https://htmx.org/essays/locality-of-behaviour/){:target="\_blank"}

While you're there have a look at this as well: [HTMX sucks](https://htmx.org/essays/htmx-sucks/){:target="\_blank"}

Another thing that I noticed is that I got exposed to different programming languages, even though some of them are not v1.0 yet, the fundamental ideas are extremely interesting, such as Zig, or essentially how I see it as C v2.0, which is a systems programming language very similar to C, that has just enough extra safety precautions to not make it as easy to shoot yourself in the foot.

> BTW. Zig C/C++ interop is something to be admired. This allows you to use C libs as is.

While I myself moved away from Neovim to essentially Jetbrains-vim, which I will go about into how I set it up at a later date (I get all products on educational license so I am going to be using it). I used Neovim for about a year, it's vim's cooler, younger brother, which is quite nice to use and is a great experience if you want to learn how to work with your computer more in-depth. I am not going to bother going into too much detail with nvim, cause I am nidiot (hehe...kill me), however if you want to know more have a look at the father of neovim, have a look at Teej:

<iframe style="width: 100%; height: 500px" src="https://www.youtube.com/embed/m8C0Cq9Uv9o" title="The Only Video You Need to Get Started with Neovim" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Pitfalls of Tech Twitter

Though there are some cool things about being part of the online tech twitter community, there are some small caveats that come with this:

I cannot state this more lightly, some people are in fact just massive assholes, we are not going to name names, you just know 'em when you see 'em (or read 'em I guess). Those folks that will needlessly defend their position without knowing the full context or just attack you for saying something that isn't even controversial, like they're trying to prove a point, and boy...they will go down swinging.

<img src="https://c.tenor.com/O2PdIqI1eucAAAAC/tenor.gif" alt="community-tiny-git" width="900"/>

But beyond that, just remember that the Twitter-sphere as some folk call it, is a tiny, very very tiny...I like the word tiny. However, since the community on the platform isn't indicative of the broader development community and as such they talk about things most developers have no idea exist, for instance if you don't mention, the chances of all developers knowing something beyond the big 3 front-end frameworks/libraries i.e. Vue, React and Angular, you are fighting an uphill battle.

Me: "Heard of qwik?"
Them: "No..."
Me: "Astro?"
Them: "No..."
Me: "Svelte...?"
Them: "Yes"
Me: "Really?"
Them: "No..."
Me: "You're ngmi"
Them: "Get away from me..."

JavaScript runtimes? If it ain't node, don't even start...

While being at the cutting edge of technology, seeing things develop in real-time, this will probably have no bearing on the real world this instant, you are still going to write that crappy java spring-boot application or work with ASP webforms...I think I just vomited a little, and you know what, you're probably going to be fine (don't quote me on that).

But TL;DR; being connected to an online community that also shares a passion for what you do as a career (hopefully), is that you get to learn different peoples perspectives and why they chose to do what they do, even if does a slight tinge of passive-aggressive behaviour along with it. I would recommend anyone to join it, you'll have a lot more fun in the long run, but you will butt heads with a few as well along the way...but, such is life.
