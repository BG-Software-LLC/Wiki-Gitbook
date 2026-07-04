---
description: >-
  Here you can find all the information that is needed in order to configurate
  messages of the plugin.
---

# Messages

You can edit every message that you want that is inside the language files. Most of the messages are configured (about 99% of them), and you can edit them however you want. Some of them has built-in laceholders for displaying information about the action that was done.\
For example, the player that did the action, the target of the action, etc.

In addition to the built-in placeholders, all of the messages support placeholders from PlaceholderAPI and MVdWPlaceholderAPI, which you can find on the main page. Furthermore, you can make more complex messages. For example, clickable messages with hoverable text and such.

## Raw Messages

Raw messages are messages that only have a message without any extras - not clickable, not sent as an action bar or anything else. These messages are very simple to be editted. All you have to do is just edit the message as a string, and that's it!

```yaml
RAW_MESSAGE: 'I am a raw message without any extras! &aColors are also supported! &{HEX:4e87ee}Even hex colors in 1.16 are supported!'
NEW_LINE_MESSAGE: |
  &aThis is the first line.
  &6This is the second line.
  &cYou can add unlimited lines :D
```

## Complex Messages

Complex messages are messages that can have extra actions to them. Action bars, titles, hoverable text and such, are all in this category.

{% hint style="info" %}
You can combine different message types in a single message.
{% endhint %}

### Action Bars

You can send action bars, the messages above the hotbar, by using the following format:

```yaml
MESSAGE:
  action-bar:
    text: '&aThis will be sent as an action bar!'
```

{% embed url="https://static.bg-software.com/imgs/action-bar-example.mp4" %}

### Titles

You can send titles, the big message in the middle of the screen, by using the following format:

```yaml
MESSAGE:
  title:
    title: '&aThe bigger text'  # If you don't want that to be sent, set this section to ''.
    sub-title: '&6The smaller text'  # If you don't want that to be sent, set this section to ''.
    fade-in: 20  # Fade in duration (in ticks).
    duration: 60  # Message duration (in ticks).
    fade-out: 20  # Fade out duration (in ticks).
```

{% embed url="https://static.bg-software.com/imgs/title-example.mp4" %}

### Bossbars

You can send boss bars, similar to the dragon's bar with custom color and text, by using the following format:

```yaml
MESSAGE:
  bossbar:
    color: 'PINK'  # The color to be used for the bossbar.
    message: '&eThe message of bossbar'
    ticks: 100  # The duration of the bossbar (in ticks)
    overlay: 'PROGRESS'  # The style of the bossbar.
```

The valid colors are `PINK`, `BLUE`, `RED`, `GREEN`, `YELLOW`, `PURPLE` and `WHITE` - invalid colors will default to `PINK`.

The valid overlays are `PROGRESS`, `NOTCHED_6`, `NOTCHED_10`, `NOTCHED_12` and `NOTCHED_20`.

{% hint style="info" %}
The `overlay` option only takes effect on servers with MiniMessage support (see below) - on other servers, the bossbar will always be displayed with the solid style.
{% endhint %}

### Sounds

You can play a sound when sending a message by using the following format:

```yaml
MESSAGE:
  sound:
    type: 'ENTITY_EXPERIENCE_ORB_PICKUP'  # The sound to be played.
    volume: 1
    pitch: 1
```

### Interactable Messages

You can send interactable messages that can execute commands or have hoverable text, by using the following format:

```yaml
MESSAGE:
  a:   # Random, but unique key.
    text: '&aI am hoverable text.'
    tooltip: '&6Hidden message!'
  b:
    text: '&6 I can execute commands, and I will be after the first message.'
    command: '/gmc'
  c:
    text: '&eI will put a command in the chat input instead of running it.'
    suggest: '/island create '
```

Each part supports the following options: `text` - the text to display; `tooltip` - hoverable text that is shown when hovering over the part; `command` - a command that will be executed when clicking the part; `suggest` - a command that will be put in the player's chat input when clicking the part (cannot be combined with `command`).

{% embed url="https://static.bg-software.com/imgs/interactable-messages-example.mp4" %}

## Custom language file

Creating a new language file is very easy task to do. All you need to do is to copy the en-US.yml file, rename it with a valid language format, and that's it! You can find a list of available language formats [here](https://www.oracle.com/technetwork/java/javase/java8locales-2095355.html).\
After you have the new file, you can edit it with the same technics that are explained above. When a new version comes out with new messages, your custom file will be updated automatically with the new messages, but in English.

## MiniMessage Support

If your server software has support to MiniMessage (Paper and its forks, on 1.18 and above), you can use MiniMessage format in the language files and it will be automatically parsed correctly.

{% hint style="warning" %}
You cannot use legacy color codes and MiniMessage format in the same message!
{% endhint %}
