# shellbot
Looks like bot for Telegram (actually is sort of wrapper only)

## Important notice
At the moment, this bot can contain absolutely any vulnerabilities, up to execution shell commands from messages.
Please **DO NOT leave it runned** on any machine with the data you critically need.

## Dependencies
This script uses **curl** for requests and **jq** for JSON parsing. Also script calls **sha256sum** for check if code was changed (yeah, he online-development-ready™), and if your OS X don't have it yet, please install.

## How to use
- Create bot via [@botfather](https://t.me/botfather) and copy his token
- Rename **shellbot.conf.template** to **shellbot.conf**
- Insert to **shellbot.conf** your `TOKEN`
- Add value to `HANDLER` (script or something other for create responses from users' requests, see below)
- Run in debug mode: 
```
export DEBUG=1
./shellbot
```
- Try to communicate with your bot via Telegram client
- If everything is ok, stop bot, ```unset DEBUG``` and start bot in convenient way for you (maybe via *screen* or *crontab*)

## What is HANDLER
Handler is a program which receive text from message as arguments and
return some result for sending to user.

For example, if *date* will be used as `HANDLER`:
```
User request: --date=@2147483647 +%Y%m%d
Bot response: 20380119
```

## License
[MIT](LICENSE)

