# telegram-pic-collection
A bot that has the potential of collecting pictures into categories and send them in groups.

# How to configure
First, modify the values in config.json.
```json
{
    "TOKEN": "YOUR_BOT_TOKEN",
    "PROXY_URL": "YOUR_PROXY_ADDRESS but won't take effect without system-wide proxy settings, use proxychains for Linux",
    "UID": "YOUR_TELEGRAM_UID",
    "demo": false,
    "bot_mode": "fwd-pic-topic"
}
```
You should replace the first 3 items but leave the other two unchanged. 

# Run the bot
To run the bot, simply execute this line: 
```sh
python3 run.py
```
For Windows, you need to specify HTTP Proxy server in settings while `proxy_url` is filled the same with it.
For Linux, simply use `proxychains` which can be installed by `sudo apt install proxychains` on Ubuntu, and use this line to run:
```sh
proxychains python3 run.py
```

# Add channels to the bot
## Channel Roles
There are two roles for channels: `source` and `target`. By default, it is assumed that you are the administrator of the channel, so that you can add your bot to it. Your bot has to be a member of the channel and have admin permissions, which the bot would check when adding channels.
### Source
A source channel is where the bot collect pictures from. Each channel marked as `source` should have multiple attributes specified, such as `alias`, `role`, and `hashtags`, which will be present in channels.json after a channel is added.
### Target
A target channel is where the bot send the collected pictures to. You can have multiple target channels, while the content will be sent to them are totally the same.
## How to add a channel
If your Telegram Bot is up and running, and properly configured to communicate with telegram-pic-collection, find your bot and send `/start` to it.
The bot should reply you with the instructions. Make sure that your bot is added to the channels in advance, and finish every step.
If you have done adding channels, it is suggested that you restart the bot to MAKE SURE it would work properly.

# What To Do with this bot
If you see some neat images on Telegram, just forward them to the `source` channels. They will be saved into different `imgdir`s which you have configured. 
If you have also added `target` channels, you can use command: `/sendnow [CHANNEL_NAME or CHANNEL_ALIAS]` to send images in groups. By default, each group contains 9 images. 
