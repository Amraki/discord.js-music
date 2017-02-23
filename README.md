# Discord.js Music Plugin

This version is not yet stable, although has been mildly tested, it has not been that extensive. It's an update of the original by [ruiqimao](https://github.com/ruiqimao/discord.js-music) for [Discord.js](https://discord.js.org/)'s version v11.x, and adds a few extra sprinkles. It still requires tweaks and testing but yeah it's something.

The commands available are:
* `play <url>`: Play a video/music. It can take a URL from various services (YouTube, Vimeo, YouKu, etc). Search has been removed temporally until a workaround can be found.
* `skip [number]`: Skip some number of songs. Will skip 1 song if a number is not specified.
* `queue`: Display the current queue.
* `pause`: Pause music playback. (requires music manager)
* `resume`: Resume music playback. (requires music manager)
* `volume`: Adjust the playback volume between 1 and 200 (requires music manager)

Permissions:
* If `anyoneCanSkip` is false then only admins and the user that requested the song can skip it.
* Only admins can change volume or resume/pause music.

Things to do:
* Get search working again

Things left to test:
* Sharing queue across multiple servers 

Bugs?
* Sometimes the bot stops playing the song before it's over.

Installation:  
1. Download and extract anywhere  
2. Edit examples/musicBot to match your needed config  
3. In the root folder, run:
```bash
npm install
```


This is a music plugin for Discord.js. Using it is as easy as:
```javascript
const Client = require('discord.js').Client;
const music = require('./path/to/this/project');

const client = new Client();
music(client);

client.login('< bot token here >');
```

The module consists of a single function, which takes two arguments:
```javascript
/*
 * Takes a discord.js client and turns it into a music bot.
 * 'derekmartinez18' done most of the work, I just fixed a few things.
 * 
 * @param client The discord.js client.
 * @param options (Optional) Options to configure the music bot. Acceptable options are:
 *                prefix: The prefix to use for the commands (default '!').
 *                global: Whether to use a global queue instead of a server-specific queue (default false).
 *                maxQueueSize: The maximum queue size (default 20).
 *                anyoneCanSkip: Allow anybody to skip the song.
 *                clearInvoker: Clear the command message.
 *                volume: The default volume of the player.
 */
music(client, options);
```
