# Setup

# Index
**Minecraft Internet Overview**
> * [Setting up a discord server (Required)](https://github.com/Capstone-Class-Minecraft-Internet/Setup#setting-up-a-discord-server)
> * [Setting up the minecraft Internet Automatically (Recommended)](https://github.com/Capstone-Class-Minecraft-Internet/Setup#setting-up-the-minecraft-internet-automatically)
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
_____
# Setting up a discord to minecraft plugin
_____
# Setting up the minecraft Internet
_____
# Using the minecraft Internet
_____
# Using the minecraft website
_____
Sign in or create an account at https://jiandong.wang/NBT2cmds/

Create a new username by choosing a username and pressing create. A username must be at least 7 characters long with no special characters. 

Press the choose file button and select your Mindcraft build NBT file. 

Your build path will be updated automatically under the builds available section.
![Image goes here](https://firebasestorage.googleapis.com/v0/b/first-project-df435.appspot.com/o/website.png?alt=media&token=8a0201c7-73e6-4acb-9903-c3e474967415)

# Who We Are
To learn more about this project and how we started, check out [Who We Are](https://capstone-class-minecraft-internet.github.io/Who-We-Are/).

# How This Works
To learn more about each component and the computer science behind this application, please visit [Educational Documentation](https://capstone-class-minecraft-internet.github.io/How-This-Works/).

