# Taiko bot

A simple Discord bot for displaying Neotokyo server information on user request.

## Running locally

1.  `pip3 install -r requirements.txt`
2.  set environment variables (see elsewhere in this document)
3.  `python3 taiko-bot.py`

## Running in Docker container

1.  `docker build . -t taikobot`
2.  `docker run -d -e "DISCORD_SERVER_ID=<YOUR_SERVER_ID>" -e "DISCORD_CHANNEL_ID=<YOUR_CHANNEL_ID>" -e "DISCORD_TOKEN=<YOUR_DISCORD_BOT_TOKEN>" taikobot`

## Running with Dokku

On the server:

1. `dokku apps:create taiko-bot`
2. `dokku config:set taiko-bot DISCORD_TOKEN=<YOUR_DISCORD_BOT_TOKEN>`
3. `dokku config:set taiko-bot DISCORD_SERVER_ID=<YOUR_SERVER_ID>`
4. `dokku config:set taiko-bot DISCORD_CHANNEL_ID=<YOUR_CHANNEL_ID>`

In this repository:

1. `git remote add dokku dokku@dokku.me:taiko-bot` (replace `dokku.me` with your own dokku host name. You only have to do this once)
2. `git push dokku`

## Supported environment variables

| Name                   | Default            | Description                                                                 |
| ---------------------- | ------------------ | --------------------------------------------------------------------------- |
| DISCORD_TOKEN          |                    | The Discord bot token to use. MUST be set.                                  |
| SOURCE_CHECK_INTERVAL  | 300                | The source server query interval in seconds                                 |
| DISCORD_SERVER_ID      | 124171198245502976 | The discord server to use                                                   |
| DISCORD_CHANNEL_ID     | 174364630175449089 | The discord channel to use                                                  |
| PLAYER_COUNT_THRESHOLD | 2                  | The player count threshold, if greater than forces msg about active servers |

## Dependencies

- [discord.py](https://github.com/Rapptz/discord.py)
- [python-valve](https://github.com/serverstf/python-valve)
