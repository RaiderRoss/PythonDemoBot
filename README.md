# PythonDemoBot | How to create a Python Discord Bot with py-cord 
# This guide uses Maven and IntelliJ.
<h2>Summary</h2>

1. [Installation](#installation)

2. [Configuration](#configuration)

3. [Library set up](#library-set-up)

4. [Example Bot](#example-bot)

5. [Final](#final)


# Installation

» Download an IDE of your choice, preferably PyCharm you can download it [here](https://www.jetbrains.com/de-de/pycharm/download/).

» Finish installing the programme to your pc and open it when you are done.

# Configuration

» Make sure you have python set up on your device. If you don't, download it [here](https://www.python.org/downloads/).

» Create a new project, set your base interpreter, if its not set, this should be the path to the .exe file of your installed python.

» You can set a few more settings if you want like the location of your project

» When you are done click create. 

# Library set up

» Go to the file in the left up corner and search for ```Python Interpreter```

» Add a dependency by clicking the + and searching for ```py-cord```

» Click "Install Package"

» Wait for the package to be installed and close the two popup windows.

# Example Bot

» Clear the main file you should see now. This will be used to register the bot.


» Now add this code to the class.
```python
import discord

# This sets the intents to the default intents of discord.
intents = discord.Intents.default()

# This allows the bot to view the content of messages
intents.message_content = True

# Creates the bot with the intents
client = discord.Bot(intents=intents)

# This sets the variable TOKEN with your token
TOKEN = 'TOKEN'


```

» Next we will create the events.
```python
import discord
# This sets the intents to the default intents of discord.
intents = discord.Intents.default()

# This allows the bot to view the content of messages
intents.message_content = True

# Creates the bot with the intents
client = discord.Bot(intents=intents)

# This sets the variable TOKEN with your token
TOKEN = TOKEN'

# This calls the event listener of py-cord to listen to the on_ready event and when its executed to run the code
@client.event
async def on_ready():
    # This will be printed when the Bot has successfully connected to Discord
    print(f'{client.user} has connected to Discord!')

# This calls the event listener of py-cord to listen to the on_message event and when its executed to run the code
@client.event
async def on_message(message):
 # This is checking if the message equals  "ping"
    if message.content == 'ping':
   
        # This gets the channel from discord and puts it into a variable
        channel = message.channel
       
        # This is responding "pong" to the message
        await channel.send('pong!')
       

# This calls the slash command manager of py-cord to create a new command with the name ping and description "Ping!"
# and when the command is executed to run the code
@client.slash_command(name='ping', description='Ping!')

# This is responding "Pong!" to the command
async def ping(ctx):
    await ctx.respond("Pong!")

# This will start the Bot
client.run(TOKEN)

```
# Final

» Upload the main.py file to the Karlo-Hosting Panel
