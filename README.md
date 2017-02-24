# Discord.js Music Plugin

![alt text](https://nodei.co/npm/discord.js-music-v11.png?downloads=true&stars=true "discord.js-music-v11 stats")

This version is not yet stable, although has been mildly tested, it has not been that extensive.   
It's an update of the original by [ruiqimao](https://github.com/ruiqimao/discord.js-music) for [Discord.js](https://discord.js.org/)'s version v11.x, and adds a few extra sprinkles. It still requires tweaks and testing but yeah it's something.

The commands available are:
* `play (<url>|<search string>)`: Play a video/music. It can take a URL from various services (YouTube, Vimeo, YouKu, etc). You can also search using a string.
* `skip [number]`: Skip some number of songs. Will skip 1 song if a number is not specified.
* `queue`: Display the current queue.
* `pause`: Pause music playback. (requires music manager)
* `resume`: Resume music playback. (requires music manager)
* `volume`: Adjust the playback volume between 1 and 200 (requires music manager)
* `leave`: Clears the song queue and leaves the channel.
* `clearqueue`: Clears the song queue.

Permissions:
* If `anyoneCanSkip` is false then only admins and the user that requested the song can skip it.
* Only admins can change volume or resume/pause music.

Things added:
* Search is working again.
* Added the command 'volume'
* Added the command 'leave'
* Added the command 'clearqueue'

Things changed:
* Permissions

Bugs?
* Sometimes the bot stops playing the song before it's over. (not confirmed)

Installation:  
1.  
```bash
npm install discord.js-music-v11  
```  
That's it!


This is a music plugin for Discord.js. Using it is as easy as:
```javascript
const Client = require('discord.js').Client;
const music = require('./path/to/this/project');

const client = new Client();
music(client);

client.login("<Bot token>");
```

The module consists of a single function, which takes two arguments:
```javascript
/*
 * @param {Client} client - The discord.js client.
 * @param {object} options - (Optional) Options to configure the music bot. Acceptable options are:
 * 		prefix: The prefix to use for the commands (default '!').
 * 		global: Whether to use a global queue instead of a server-specific queue (default false).
 * 		maxQueueSize: The maximum queue size (default 20).
 * 		anyoneCanSkip: Allow anybody to skip the song.
 * 		clearInvoker: Clear the command message.
 * 		volume: The default volume of the player.
 */
music(client, options);
```
