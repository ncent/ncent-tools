# wordCentBot

## Setup
Create a `secret.env` file that looks like this:
```bash
TOKEN=ISSUED_BOT_TOKEN
```

## Run
```
sh dockerExec.sh
```

## Stop
```
docker rm -f wordBotContainer
```

## Logs
```
docker logs wordBotContainer
```

## Details

This bot of course needs to be able to listen to messages. Again, this bot needs an admin to prompt it to do certain things, so edit wordCentBot.js to change ADMIN_USERNAME to your handle so that you can control the bot. Other people will not be able to mess with the bot.
The important commands are /newGame and /automaticHints. Run "node wordCentBot.js" to start the script. You can have it running indefinitely. To start a new game, send "@wordCentBot /newGame" to the chat where you want the game to take place. The bot will then send you a message asking you to input word/clue information. Once you do this, the bot will post a message to the group, saying that the game is starting. You can send commands directly to the bot now. Send /automaticHints to start the bot publishing hints. The bot will give hints at random intervals which you can modify by changing the function, randomTime. You can also tell the bot to give new hints even while automatic hints are going. Tell the bot to post the current leaderboard to the game chat by sending it "/giveLeaderboard".
Note, the referral chains and points are reset when you start a new game.
The script wordCentBot.js should be running as long as the game is happening, but it is constantly saving game data in a file so if it crashes, or you need to stop it to change something, you can just restart it with "node wordCentBot.js" and send the bot the command "/restartGame".
Note, you can only have one game with the same bot going at a time, so wait until a game has finished (all hints have been given) to start a new game.

Some guy from stanford wrote this stuff not the current repo manager
