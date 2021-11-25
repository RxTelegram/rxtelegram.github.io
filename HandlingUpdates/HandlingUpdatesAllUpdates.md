---
layout: default
title: Getting all updates
parent: Handling Updates
nav_order: 3
---

# Getting all updates

## Basics
.net unfortunately does not provide an implementation for the IObservable interface, so we recommend you to install the Nuget package System.Reactive.Core. This will allow you to subscribe to any IObservable interface provided by our library as follows.

``` csharp
.Subscribe(next => { }, exception => { })
```

Ab .netstandard 2.1 kannst du auch eine Schleife wie folgt aufbauen:
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