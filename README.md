# Setup

# Index
**Minecraft Internet Overview**
> * [Setting up a discord server (Required)](https://github.com/Capstone-Class-Minecraft-Internet/Setup#setting-up-a-discord-server)
> * [Setting up the minecraft Internet Automatically (Recommended)](https://github.com/Capstone-Class-Minecraft-Internet/Setup#setting-up-the-minecraft-internet-automatically)
### The setps below outline how to manually setup the minecraft internet, and are only intended to be used for educational and troubleshooting purposes.
> * [Setting up the minecraft Internet](https://github.com/Capstone-Class-Minecraft-Internet/Setup#setting-up-the-minecraft-internet)
> * [Setting up a compatible minecraft server](https://github.com/Capstone-Class-Minecraft-Internet/Setup#setting-up-a-compatible-minecraft-server)
> * [Setting up a discord to minecraft plugin](https://github.com/Capstone-Class-Minecraft-Internet/Setup#setting-up-a-discord-to-minecraft-plugin)
> * [Using the minecraft Internet](https://github.com/Capstone-Class-Minecraft-Internet/Setup#using-the-minecraft-internet)
> * [Using the minecraft website](https://github.com/Capstone-Class-Minecraft-Internet/Setup#using-the-minecraft-website)


# Setting up a discord server (Required)
A new or existing discord server can be used to run the minecraft-to-internet system. If you would like to use a new discord server, this [tutorial](https://discord.com/blog/starting-your-first-discord-server) can be used to set up the server basics. 

In addition to a discord server, two discord bots are required to allow minecraft to fully access the internet. The first discord bot is required to connect the minecraft server to discord, and the second bot is used to connect discord to the internet.

TODO: Add information about bot setup, and what information is required for bot setup.
_____
# Setting up the Minecraft internet automatically
The minecraft internet system can be setup in a few easy commands using docker to create a new world, and get your bots up and runnning!
1. [Install docker](https://docs.docker.com/get-docker/)
2. [Download](https://github.com/Capstone-Class-Minecraft-Internet/mc-docker) the premade Docker file
3. Extract the mc-docker files, and navigate to the exctracted directory through the terminal
    1. The docker user interface (docker desktop) can also be used to do this
4. Gather the following pieces of information: 
    #### Discord channel arguments
    1. clietID
    2. guildID
    3. token

    #### Channel Id arguments (You must use two different channels)
    1. Channel id #1 (known as botChannelID)
    2. Channel id #2 (known as botRelayChannelID)
    
    #### Firebase Credentials
    1. apiKey
    2. authDomain
    3. databaseURL
    4. projectID
    5. storageBucket
    6. messagingSenderId
    7. appId
5. Run the docker script with the following command, adding the data collected in the previous step where necessary:  ```UID=$(id -u) GID=$(id -g) clientID=$() guildID=$() token=$() botChannelId=$() botRelayChannelId=$() apiKey=$() authDomain=$() databaseURL=$() projectId=$() storageBucket=$() messagingSenderId=$() appId=$() docker-compose up -d```
6. Run the following docker command to accept the minecraft EULA, and officially start the minecraft server ```GET COMMAND FROM JD```
7. Congrats, you now have a working minecraft internet! Follow the guide [here](Put guide link here) to get started with sharing builds.
_____
# Setting up a compatible minecraft server
The minecraft internet system relies on papermc due to its support of bukkit plugins. This system could also work with spigot servers, but this walkthrough will focus on paperMC. 
1. [Install](https://papermc.io/downloads/paper) version 1.19 of the paperMC
2. [Setup and run](https://docs.papermc.io/paper/getting-started) the paperMC server
_____
# Setting up a discord to minecraft plugin
This section should work with any discord to minecraft link, but for the sake of this tutorial, we will use EssentialsX discord. This plugin has an easy setup process and provides a discord to minecraft command/chat relay, which is why we went with this choice
1. [Install](https://essentialsx.net/downloads.html) the essentialsX plugin.
2. [Install](https://essentialsx.net/downloads.html) the essentialsxDiscord extension plugin. 
3. [Follow](https://essentialsx.net/wiki/Discord-Tutorial.html) the essentialsXDiscord setup guide, using the bot created in the first step.
4. Configure the essentialsX discord plugin to use the proper discord channels. 
    1. Gather the following information
        1. guild (server) ID
        2. Channel ID #1 (Admin channel)
        3. Channel ID #2 (Relay channel)
    2. Open the config file created by the EssentialsXDiscord extension plugin, and set the required parameters to the information set above. 
        1. Set the guild parameter to the guild (server) ID
        2. Set the primary and staff parameters to Channel ID #1
        3. Set the channel parameter under console section to Channel ID #2
        4. Ensure command-relay and bot-command-relay are set to true
        5. Ensure show-webhook-messages and show-bot-messages parameters are set to false
     3. Test new bot configurations
         1. When users log into or out of the server, and when messages are sent in minecraft chat, they should appear in the admin channel
         2. A message sent in the relay channel should appear in minecraft chat, and commands typed into the relay channel should happen in game.
5. Restart the minecraft server to apply changes

_____
# Setting up the minecraft Internet
This section goes into how to install the second required discord bot.
1. [Download](https://github.com/Capstone-Class-Minecraft-Internet/discord-bot-no-admin-for-docker) the discord bot from github. 
2. Collect required discord information 
    1. Discord bot client ID
    2. discord guild(Server) ID
    3. Discord token
    4. Discord AdminChannelID
    5. Discord RelayChannelID
    6. Firebase apikey
    7. Firebase authDomain
    8. Firebase databaseURL
    9. Firebase projectID
    10. firebase StorageBucketID 
    11. firebase MessageSenderID
    12. Firebase appID
3. [Install](https://nodejs.org/en/download) Node.js and NPM.
4. Install discord.js using ```npm install discord.js```
5. Run the discord bot using ```node index.js ${botChannelId} ${botRelayChannelId} ${clientId} ${guildId} ${token} ${apiKey} ${authDomain} ${databaseURL} ${projectID} ${storageBucket} ${messagingSenderId} ${appId}```, Subbing in values with the values gathered in the previous step
6. Confirm functioning minecraft-to-discord system by typing !ping in minecraft. A ```Pong!``` response should be returned.
_____
# Using the minecraft Internet
The minecraft internet system provides an intuitive way to pull minecraft builds and other programs from the internet using *Mostly* vanilla minecraft.
### Basic Commands
- ```!get_computer``` - Sends a book to the user which contains clickable elements to create the computer that can instantly execute programs
- ```!get_build usernameArg buildIDArg``` - A command that takes a username and buildID arg. This command communicates with our firebase 'dns' system to retreive the build and send it to the user. This command does take some time to run, so it will send a notification to the user in game when the build or program is fully loaded. To run the fully loaded build or program, simply place a redstone block next to the orange command block from the minecraft computer build from the ```!get_computer``` command
- ```!ping``` - A sanity check to ensure that the bot is functional

_____
# Using the minecraft Build Uploader
Sign in or create an account at https://jiandong.wang/NBT2cmds/

Create a new username by choosing a username and pressing create. A username must be at least 7 characters long with no special characters. 

Press the choose file button and select your Mindcraft build NBT file. 

Your build path will be updated automatically under the builds available section.
![Image goes here](https://firebasestorage.googleapis.com/v0/b/first-project-df435.appspot.com/o/website.png?alt=media&token=8a0201c7-73e6-4acb-9903-c3e474967415)

# Who We Are
To learn more about this project and how we started, check out [Who We Are](https://capstone-class-minecraft-internet.github.io/Who-We-Are/).

# How This Works
To learn more about each component and the computer science behind this application, please visit [Educational Documentation](https://capstone-class-minecraft-internet.github.io/How-This-Works/).

