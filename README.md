# Taiko bot

## Running locally

1.  `pip3 install -r requirements.txt`
2.  set environment variables (see elsewhere in this document)
3.  `python3 taiko-bot.py`

## Running in Docker container

1.  `docker build . -t taikobot`
2.  `docker run -d -e "DISCORD_SERVER_ID=<YOUR_SERVER_ID>" -e "DISCORD_CHANNEL_ID=<YOUR_CHANNEL_ID>" -e "DISCORD_TOKEN=<YOUR_DISCORD_BOT_TOKEN>" taikobot`

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
