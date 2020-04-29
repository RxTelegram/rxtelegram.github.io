---
layout: default
title: Quickstart Terminal
parent: Quickstart Overview
nav_order: 1
---

# Quickstart Guide (Terminal)

Hey 👋,
thanks for using [RxTelegram.Bot](https://github.com/RxTelegram/RxTelegram.Bot). This quickstart guide will give you an easy 3 Steps Solution how you can get started with RxTelegram.Bot using your Terminal. Quickstart guides are also Available for Visual Studio or Rider.

## 1. Bot Father

Before we can get started you need to create a Telegram Bot by visiting [@BotFather](https://t.me/BotFather) with any Telegram client and create a new bot. He will give you an access token which you need to authorize your bot at every request, but do not worry we will handle this for you.

## 2. Hello World - by copy and pasta

Just open up your Terminal in a new Folder and run the following commands.

1. Create a new dotnet project.

    ```bash
    dotnet new console
    ```

2. Add the RxTelegram.Bot nuget package

    ```bash
    dotnet add package RxTelegram.Bot
    ```

3. Open the ```Programm.cs``` file and paste the following content.

    > **Replace ACCESS_TOKEN_HERE with the access token Botfaher gave you.**

    ```csharp
    using System;
    using RxTelegram.Bot;

    namespace Awesome {
        class Program {
            public static void Main () {
                var botClient = new TelegramBot ("ACCESS_TOKEN_HERE");
                var me = botClient.GetMe().Result;
                Console.WriteLine (
                    $"Hello, World! I am user {me.Id} and my name is {me.FirstName}."
                );
            }
        }
    }
    ```

## 3. Run your programm

The last step is quid simple. Just Run it 😎

```bash
dotnet run
```

## Troubleshooting

### Invalid Bot Token

```text
Unhandled exception. RxTelegram.Bot.Exceptions.InvalidTokenException: The given bot token is not valid. See "https://core.telegram.org/bots/api#authorizing-your-bot" for further information. Token was: ACCESS_TOKEN_HERE
   at RxTelegram.Bot.BotInfo.ValidateToken(String token)
   at RxTelegram.Bot.BotInfo..ctor(String token)
   at RxTelegram.Bot.TelegramBot..ctor(String token)
   at Awesome.Program.Main() in C:\Users\nikwe\Downloads\asf\Program.cs:line 7
```

If you get an Exception like this it is most likely that you did not replaced the access token in the code sample or you copied the wrong one.
