---
layout: default
title: Getting all updates
parent: Handling Updates
nav_order: 3
---

# Getting all updates

## Basics
.net unfortunately does not provide an implementation for the IObservable interface, so we recommend you to install the Nuget package [System.Reactive](https://www.nuget.org/packages/System.Reactive/6.0.1-preview.1). This will allow you to subscribe to any IObservable interface provided by our library as follows.

``` csharp
.Subscribe(next => { }, exception => { })
```

As of .netstandard 2.1 you can also build a loop like this:
``` csharp
await foreach (var message in Bot.Updates.MessageEnumerable())
{
    
}
```
# Types of updates


| .netstandard 2.0   | .netstandard 2.1                                   |
|:-:|:-:|
| Update             | Update/ UpdateEnumerable()                         |
| Message            | Message/ MessageEnumerable()                       |
| EditedMessage      | EditedMessage/ EditedMessageEnumerable()           |
| InlineQuery        | InlineQuery/ InlineQueryEnumerable()               |
| ChosenInlineResult | ChosenInlineResult/ ChosenInlineResultEnumerable() |
| CallbackQuery      | CallbackQuery/ CallbackQueryEnumerable()           |
| ChannelPost        | ChannelPost/ ChannelPostEnumerable()               |
| EditedChannelPost  | EditedChannelPost/ EditedChannelPostEnumerable()   |
| ShippingQuery      | ShippingQuery/ ShippingQueryEnumerable()           |
| PreCheckoutQuery   | PreCheckoutQuery/ PreCheckoutQueryEnumerable()     |
| Poll               | Poll/ PollEnumerable()                             |
| PollAnswer         | PollAnswer/ PollAnswerEnumerable()                 |