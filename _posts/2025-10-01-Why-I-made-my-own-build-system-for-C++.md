---
layout: post
title: Why I'm busy making my own build system for C++
date: 2025-10-01
tags: [general]
---

## I used too much Rust

I am not a C++ developer by heart and if you look at the Twitter-sphere or Threads-sphere or whatever-sphere...C++ seems to be dunked on quitea lot from all sides. Some coming from the C-bros saying they want simplicity, some from the Rustaceans (dumb name...prove me wrong) advocating heavily for safety. Too be fair, this is anecdotal, in really all I couldn't care less about someone's opinions about programming languages.

I would say though that I did get the rust fever injected into my veins when I tried to build a software renderer in rust because, 1. Graphics programming isn't that widely supported in rust and would be a good testing ground to learn more about the language and 2. I am a masochist. Since I am a masochist, I decided, y'know, Rust isn't doing it for me, and I am not converted on C just yet... thus I decided on C++, which is just C with extra steps...right...right?

Say what you want about rust, but cargo is amazing, and coming from a world where I can just add a third-party package to my project super easily and build my project to having to manually do everything...was not great...

> This is triggering my PTSD of setting up emscripten for wasm a year ago

To be fair it has been streamlined a bit with the use of CMake and other build systems like ninja, throw a package manager in there like Conan and viola, you have a frankenstein rust project.

The only issue with this is that now I am dealing with multiple tools just to manage a project...again...not great, and so, the idea behind CPM (C++ Project Manager) was born, which aims to just consolidate all my tools under one umbrella. Why use conan/hunter/vcpkg along with CMake or ninja, can we just make it easier all under one tool.

This idea will be the main mission purpose for CPM:

> Make Using C++ Not Suck

Because at the end of the day... the language is going to evolve. Is it ever going to be as safe as Rust...probably not...is it ever going to be as simple as C (technically possible)...but no, no it won't and dispite the C++'s committee best efforts to chase everyone away, still most things are built with it and won't be replaced soon unless the business relying on it likes to burn money for months on end before seeing any ROI, it's probably going to stay here, so why not make the language and ecosystem as "fun" and as "streamlined" to use as possible.

This will be my contribution to the world, to make the world a better place for all, my magnum opus, my indulgence into the masochism which made me beat Elden Ring with nothing but fists.

I don't even know what I am talking about anymore...

Anyway...long live C++
