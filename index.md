<div align="center">
    <img src="docs/images/logo/yambot.png?raw=true" alt="Yambot Logo" width="150">
    <h1>Yambot</h1>
</div>

<div align="center">
    <p>A batteries-included video player and media center that lives on Discord's Go Live streaming service.</p>
    <p>This copy of Yambot is currently on <b>version 2.1</b>.</p>
</div>

## Features
- A cross-platform video player based on a libmpv backend
- Control video player playback through intuitive Discord commands
- Queue videos from Youtube, Soundcloud, Vimeo, etc.
- Create video collections for local media using the provided CLI tools
- One-click/one-line launch to start up all of Yambot

## Installation

### Preparing Dependencies
1. Install the latest Python 3 (3.9 as of this release) using your operating system's preferred method.
2. Install mpv and libmpv according to your operating system's preferred method.
    * If you are using Windows, you can download the latest git release of libmpv from [Sourceforge (link)](https://sourceforge.net/projects/mpv-player-windows/) for your architecture. You will need to extract the 7z archive to a known location and add that known location to your Windows PATH.
3. (optional) Create and activate a Python virtual environment for Yambot to separate Yambot's Python environment from your system's Python environment.
4. Install the Python packages listed in requirements.txt (`pip3 install -r requirements.txt`).
    * If you are using Windows, you can skip installing the GTK dependencies **PyGObject** and **pycairo**, but you are restricted to the Qt-based frontend and must install **PyQt5** and **PyQt5-sip**.

### Setting up Discord
1. Ensure you have the Discord desktop client installed signed into the user you want to share the video player with.
2. Create a Discord bot token for the video player controller by going to the [Discord Developers page](https://discord.com/developers), creating a new application, and going to the Bot section. Note down the bot token.
3. Add the Discord video player controller bot to your server by using the link `https://discord.com/api/oauth2/authorize?client_id=<client_id>&permissions=401993552&scope=bot`, replacing `<client_id>` with the Client ID in the General Information section of your application.

### Downloading & Unpacking
1. Download and extract the provided release of Yambot to a known location.
2. Create a copy of `sample.env` and name it `.env`.
3. Fill in the appropriate values for `.env` according to your setup.
    * `DISCORD_BOT_TOKEN` is the bot token for the video player controller. Fill in this field with the bot token noted earlier.
    * `DB_PATH` is the location that Yambot will use to create and access the database. Relative and absolute paths OK.
    * `MEDIA_PATH` is the path where Yambot will use to search and add your local video collections. Relative and absolute paths OK.
4. Initialize the database by running `scripts/create_db.py`.
5. With this, Yambot is configured enough to run remote videos, but does not have local videos.

### Adding a Video Collection
1. Launch `scripts/add_collection.py`. You will be placed in a menu.
2. Type in `a` to add a collection. Follow the prompts to fill in the appropriate metadata and location of the media.
3. Add videos to the collections and confirm the order when prompted.

## Running Yambot
Once you've followed the above steps to setup Yambot, running it is simple.

0. (optional) Activate your virtual environment for Yambot if you created one.
1. Launch `bot.py` through the command line (`python3 bot.py`) or by double-clicking the file.
2. Open up your Discord client and share the `Yambot [MPV]` screen.


## Release Cycles
Below is a list of the releases you can expect for each major version. As an early self-hosting supporter of Yambot, you are entitled to the **minor, release, and lts** versions.

- **Release x.0 (next):** Fresh unstable-"stable" release with several new major features for the release cycle. Targeted to be stable enough for our development server and serves as a beta/release candidate for the cycle. _(2 weeks on Friday)_
- **Release x.1 (minor):** A more stabilized release of the x.0 release designed to be shipped out to Yambot self-hosters. May extend to releases from **x.1** to **x.3** if necessary. _(1 week)_
- **Release x.5 (release):** Minor improvements that cropped up with the version are implemented + feedback patch released after feedback received from self-hosters. Also culls deprecated features if possible. May be skipped and rolled into release **x.8**. _(1-2 weeks on Friday)_
- **Release x.8 (server):** Service stability patch. Preparing to roll the release out publicly, updating the website, and adding more infrastructure. Designed to be rolled out onto the kmoverse cluster only. _(1-2 weeks)_
- **Release x.9 (lts):** Golden master release for servers after public feedback is implemented in the form of minor bug fixes/QoL adjustments/additional tooling. _(1-2 weeks)_

## Support
As an early-bird supporter, over the 2.x release cycle you are entitled to support over Discord and email. Please send an email to yambot@kmo.berkeley.edu for a private invite to the Yambot support channels on the kmoverse Discord, or use this email address for any support issues.
