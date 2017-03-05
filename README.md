[![Latest Stable Version](https://poser.pugx.org/unreal4u/telegram-api/v/stable)](https://packagist.org/packages/unreal4u/telegram-api)
[![Build Status](https://travis-ci.org/unreal4u/telegram-api.svg)](https://travis-ci.org/unreal4u/telegram-api)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/unreal4u/telegram-api/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/unreal4u/telegram-api/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/unreal4u/telegram-api/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/unreal4u/telegram-api/?branch=master)
[![License](https://poser.pugx.org/unreal4u/telegram-api/license)](https://packagist.org/packages/unreal4u/telegram-api)

# Telegram API

This is a complete PHP7 bot API implementation for Telegram implementing the totality of [Bot API v2.3.1](https://core.telegram.org/bots/api-changelog#december-4-2016)

## Known bugs / Open issues

None at the moment. If you find any, feel free to [submit a PR](https://github.com/unreal4u/telegram-api/pulls) or
[create an issue](https://github.com/unreal4u/telegram-api/issues)!

### About this class

* Enables you to anything supported by the Telegram Bot API: messages, stickers, location, inline bots and any other supported method via PHP to a Telegram user (either direct conversation, channel, group or supergroup).
* Respects and implements the default types and methods made by Telegram itself. Have any doubts about any method? [Just check the original documentation](https://core.telegram.org/bots/api), this implementation will not differ too much.
* Doesn't need any dependency, except for Guzzle, which you can inject if you already use it elsewhere.
* **Full** inline bots support!

## Installation

The preferred method is composer, so add the following to your composer.json:

```json
{
  "require": {
    "unreal4u/telegram-api": "~2.3"
  }
}
```

### Upgrading v1.x to v2

Please check [the following Wiki page](https://github.com/unreal4u/telegram-api/wiki/Upgrading-from-v1-to-v2) if you 
have to upgrade from v1 to v2.

## General usage

### Basic usage example:

```php
use \unreal4u\TelegramAPI\TgLog;
use \unreal4u\TelegramAPI\Telegram\Methods\SendMessage;

$sendMessage = new SendMessage();
$sendMessage->chat_id = A_USER_CHAT_ID;
$sendMessage->text = 'Hello world!';

$tgLog = new TgLog(BOT_TOKEN);
$message = $tgLog->performApiRequest($sendMessage);
```

With the `SendMessage()` object, you can create a message to be sent through the TgLog object.  
All other functionality is based upon this behaviour, so every other method is very similar: you instantiate an object, 
pass that object to TelegramLog->performApiRequest() and you'll get the native Telegram response back as an object. 
Different methods return different object types. 

Please refer to the [examples directory](https://github.com/unreal4u/telegram-api/tree/master/examples) to view examples 
of some of the implemented methods, including inline bots. 

For examples of actual code that works in a production environment, please refer to my other repo: https://github.com/unreal4u/telegram-bots

### Getting updates via Webhook

Please check [the following wiki section](https://github.com/unreal4u/telegram-api/wiki/Getting-updates-via-Webhook) for
more information on this.

### Inline bots

Please checkout the [special wiki page](https://github.com/unreal4u/telegram-api/wiki/Inline-Bots) about inline bots.

### Extra requirements

If you want to use this package, you'll need a bot API key. Check 
[the following documentation](https://github.com/unreal4u/telegram-api/wiki/Creating-a-bot) for more instructions 
on that.

### Getting everything started up

The most difficult thing to do when performing an action with the Telegram API is to get the chat_id, which is the 
actual conversation window the bot talks to. You can execute the GetUpdates() method in order to get this chatId. Note
that there are some caveats on this, so you may be better out with the SetWebhook() method instead. 

## Development

### Semver

I will try my best to respect [Semantic Versioning](http://semver.org).  
That being said, the first stable release is v1.0.0, from there on no mayor BC changes will occur unless we update
the major.

### Want to colaborate?

Colaborations are **very** welcome! [Check this Wiki page out](https://github.com/unreal4u/telegram-api/wiki/Want-to-colaborate%3F) 
for more information that will make the development easier!

### Contact the author

I actually don't use Telegram. Nah, kidding, you can contact me at [t.me/unreal4u](https://telegram.me/unreal4u).
Another great way to help is to simply [create an issue](https://github.com/unreal4u/telegram-api/issues) or a
[pull request](https://github.com/unreal4u/telegram-api/pulls)!

### Bugs related with security

Please handle these responsibly! If you happen to find one, please
[contact the author privately](https://telegram.me/unreal4u).

### Special thanks to

- **Intensify** for reporting [this fatal error](https://github.com/unreal4u/telegram-api/issues/15).
