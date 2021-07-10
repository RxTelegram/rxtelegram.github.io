---
layout: default
title: Handling Updates
parent: Concepts
nav_order: 3
---

# Basics

RxTelegram uses a reactive approach to allow the user to get access to Updates. The updates are providet asynchron and event-based by using the observer pattern together with the iterator pattern. RxTelegram provides Observables for each of the eleven different types of updates, which Telegram offers, with their api.

As soon as you subscribe to one of the Oberservables RxTelegram starts fetching Updates of this Type from the Telegram Api. So if you don't subscribe to any Updates RxTelegram will not ask the Telegram Api for any Updates.

# .Net standard 2.1

If you are using .net core 3.0 or any other [.net standard 2.1](https://docs.microsoft.com/en-us/dotnet/standard/net-standard) compatible version of .net you will be able to use asyncronous enumeratables. 