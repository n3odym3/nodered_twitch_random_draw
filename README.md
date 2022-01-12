# Node-RED Twitch random draw
Node-RED Bot to randomly select active viewers from one or more Twitch channels

- My [Twitch channel](https://www.twitch.tv/ioodyme)
- My [Youtube channel](https://www.youtube.com/neodymetv)

## Prerequisites

- [Node-RED server](https://nodered.org/)
- [TMI Token](https://twitchapps.com/tmi/)

## Dependencies 

- [node-red-contrib-twitch-chat](https://flows.nodered.org/node/node-red-contrib-twitch-chat)

## Description

<img src="https://github.com/n3odym3/nodered_twitch_random_draw/blob/main/pictures/main.PNG" >

1. Add a viewer to the draw with the **!join** command in the Twitch chat (the viewer will only be counted once even if he/she has typed **!join** several times).
2. Admin commands
3. Usernames to exclude from the draw 
4. Help (Print instructions and command names in Twitch chat)
5. Reset the winner list (The winner list allows a viewer to win only once if there are several draws)
6. Start the draw (start to record the !join commands)
7. Stop the draw
8. Get the list of "active" viewers 
9. Select the Draw type (Normal: a viewer can win once. Mega: a viewer can win several times)
10. Check if the selected viewer is an "active" viewer (only a viewer currently connected in the chat can win. If a viewer type the !join command and then leave the chat, he will not be able to win)
11. Win message that will be displayed on the Twitch chat

## Instruction

### Bot setup

<img src="https://github.com/n3odym3/nodered_twitch_random_draw/blob/main/pictures/BotSetup1.PNG" width="40%">

1. Channel where the bot will be active
2. Bot config

<img src="https://github.com/n3odym3/nodered_twitch_random_draw/blob/main/pictures/BotSetup2.PNG" width="30%">

1. Bot Username (the bot can be the username of the broadcaster or another account. If this is the case, it is strongly recommended to **/mod** the bot)
2. TMI TOKEN (NOT the account password !!!!)
3. Channel where the bot will be active

### Banlist

<img src="https://github.com/n3odym3/nodered_twitch_random_draw/blob/main/pictures/BanList.PNG" width="50%">

Add the username to exclude from the Draw if required.

### Commands

If you change the commands name in the switch node...

<img src="https://github.com/n3odym3/nodered_twitch_random_draw/blob/main/pictures/CMD.PNG" width="40%">

Don't forget to also edit the command name in the **draw type** node (N°9 on the main picture)

<img src="https://github.com/n3odym3/nodered_twitch_random_draw/blob/main/pictures/CMD2.PNG" width="40%">

### How to use 

- Start the Node-RED server
- When a broadcaster in the bot's username list types the !start command, the bot starts recording !join commands on the broadcaster's channel
- Viewers can type !join to join the draw
- When the !stop command is typed by the broadcaster, the draw is stopped and the list of "active viewers" is retrieved by the robot.
- The !draw or !megadraw command allows to select a random viewer
