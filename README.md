# EnBeat_NEW
Live editing algorithmic music generator with a collection of many formulas from around the internet.

> [!IMPORTANT]
> ## Before you create an issue
> Do not create issues suggesting new sound modes or new functions.
> Even if these were the original purpose of the player,
> it is now intended to be a more advanced bytebeat player compared to Dollchan.
>
> I share the sentiment that you can create the functions in the bytebeat code itself,
> and make converters from your preferred mode to Floatbeat/Funcbeat,
> rather than try to get players to make their own built-in functions.
>
> Any issues I see that just serve to add new modes/functions will be closed as not planned.
> This is what I've already done and is what I will continue to do in the future.

**Access player at https://chasyxx.github.io/EnBeat_NEW/**<br>
**Dollchan discission threads https://dollchan.net/btb**

![UI buttons and a visualiser showing sierpinski triangles](https://user-images.githubusercontent.com/105890603/229014766-38a7c067-55d3-4120-9ed8-2a8aeb4c1f20.png)

## List of features compared to dollchan
* Spectrogram (Plots pitches of the sound output in real time)
* Mic input (Useful for creating DSP filters or modems instead of songs)
* Customizable sample rate for ultrasonic sound cards and/or higher-quality string simulation
* Big codes still update the link (dollchan has problems with this and has closed the issue regarding it)
* Ability to save codes locally as supercookies
* Link size shown in size indicator (Also KiB and KB are shown seperately)

## Compilation

1. Install Node.js
2. Run with npm:
```
git clone https://github.com/SthephanShinkufag/bytebeat-composer.git
cd bytebeat-composer
npm install
npm start
```
3. Compiled scripts will be created in the `/build` directory.<br>
4. Access to the site is provided through the `index.html` in the root directory.

## Collection of songs

Songs lists are stored in GZIP-compressed JSON `/data/library/*.gz` files.
Codes larger than 1KB are stored in `/data/songs/*/*.js` files.

To maintain your own library of songs:

1. Create a MySQL database on your server.
2. Set up PHP with the MySQLi extension on your server.
3. Copy `settings.default.php` to `settings.php` in the root directory.
4. Configure `settings.php` with your database settings.
5. `chmod` write permissions to the `/data` directory.
6. Go to your Bytebeat Player page > "Settings" section > "Manage library" link.
7. Log in using the admin password you set in `BYTEBEAT_ADMINPASS` in `settings.php`.
8. The management panel is now available.

The following management functions are provided:
- "Migrate to database" button &ndash; Sets up a empty database with codes from the `all.gz` file and the `songs/` directory. **This clears the old contents of the database.**
- "Make library files" button &ndash; Generates `/data` library files from your database.
- "Add a song" button &ndash; Opens a form to add a new song.
