# Telegram Bot for Controlling Various Things Remotely

With this bot, you can systemctl start/stop services

and list/add/remove/delete torrents through your Transmission daemon.

## 0. Prepare

Install Go and generate your Telegram bot's API token.

## 1. Install

```bash
$ go get -u github.com/meinside/telegram-bot-remotecontrol
$ cd $GOPOATH/src/github.com/meinside/telegram-bot-remotecontrol
$ cp config.json.sample config.json
$ vi config.json
```

and edit values to yours:

```json
{
	"api_token": "0123456789:abcdefghijklmnopqrstuvwyz-x-0a1b2c3d4e",
	"available_ids": [
		"telegram_id_1",
		"telegram_id_2",
		"telegram_id_3"
	]
}
```

## 2. Build and run

```bash
$ go build -o telegrambot main.go
```

and run it:

```bash
$ ./telegrambot
```

## 3. Run as a service

### a. systemd

```bash
$ sudo cp systemd/telegrambot.service /lib/systemd/system/
$ sudo vi /lib/systemd/system/telegrambot.service
```

and edit **User**, **Group**, **WorkingDirectory** and **ExecStart** values.

It will launch automatically on boot with:

```bash
$ sudo systemctl enable telegrambot.service
```

and will start with:

```bash
$ sudo systemctl start telegrambot.service
```

## 998. Trouble shooting

TODO

## 999. License

MIT

