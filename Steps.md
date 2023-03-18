# About Discord.JS 🌈

> Discord.js is a powerful JavaScript library that allows you to interact with the Discord API to create your own Discord bots. With Discord.js, you can create a bot that can respond to messages, join voice channels, and more. You can also use Discord.js to create custom commands, manage roles, and even create your own mini-games. With Discord.js, you can create a powerful and interactive bot that can help make your Discord server more engaging and fun.

# Creating a bot using Discord.JS
• Loging in to discord and create a server If you don’t have any yet. Be aware that you have to own the server or know someone with the rights to add the bot account in a later step. You create a new server by clicking the “+” icon in the left side menu.

• We will need to create a bot! So, Go to the **`Bot`** section in the left side menu, and click **` Add Bot`** on the right of the screen.

• Creating a bot token. Click on the Button **`Reset token`** button to create a new bot token. This token is secret and should not be shared with others. Save it in a text file for later use (`token is only shown once! Don't forget to save it in somewhere you feel secured. Thank me later.`).

• Setting up permission for your bot. Go to the OAuth2 ‣ URL Generator section of the settings menu. Set the scope to **`Bot`** and set the permissions to **`Read messages/View channels`** and **`Send messages.`** This will enable the bot to read and write messages in the server chat. You can also set permission to **`Administrator`** So, you don't have to set anything (`Faster Way`) [**NOT SUGGESTED**]

• Copy the invite URL and paste it into the browser. Scroll further down and find the **`Generated URL.`** It will look something like this:
```https://discord.com/api/oauth2/authorize?client_id={YOUR_CLIENT_ID}&permissions=3072&scope=bot```
Paste this URL into your browser’s search bar. Select the server you want to authorize the bot for and click **`Next`**. Accept the necessary permissions and finish by clicking **`Authorize.`**

• Welcome your newly created bot on the server! Close the tab and go back to your server. You will find your bot among the server members if everything went well.

• Bring the AI Bot to Life. Now that the bot is visible in our server, let’s make it do something with code.

• Initialize a new project. Create a new folder and name it something like **`Alpha`** in your preferred location on the computer. Now, open the VSCode application and the newly created folder under File > Open Folder. Now, in the menu bar under Terminal > New Terminal open a new terminal. A new terminal should pop up from the bottom. In the terminal, initialize a new Node.js application with the command: ```npm init -y``` Then press enter. In the file explorer on the left, you will see that executing the command created a new `package.json` file.

• Create a new file containing the bot code. Edit the `package.json` file to execute the script in this bot code file on start. Click on the **`New File`** icon to create a new Node script. Then name the file index.js and write  `console.log("Hi! I'm alpha. Don't forget to give me a star!");` code in the file. Don’t forget to save.

• Then go to the package.json file and edit it like this: 
```json
{
  "name": "alpha",
  "version": "1.0.0",
  "description": "Discord Basic Steps",
  "main": "index.js",
  "scripts": {
    "start": "node index.js"
  },
  "keywords": [],
  "author": "Alpha5959",
  "license": "ISC",
}
```
Now, you can execute the command: `npm start` In the terminal, it should print **`Hi! I'm alpha. Don't forget to give me a star!`**

• Install the Discord.js dependencies. Now that we can make the **`index.js`** script run, let’s install the Discord.js library to interact with Discord. In the terminal, run: `npm install discord.js`. This will install the Discord.js library to interact easily with the Discord API. If you only get warnings, there should not be a problem. If there are errors, however, please search for solutions online.

• Write the code that brings your AI bot to life. Open the **`index.js`** file. There, write the following code: 
```js
const { Client, Partials, Collection, GatewayIntentBits } = require('discord.js');
const config = require('./config/config');
const colors = require("colors");

// Creating a new client:
const client = new Client({
  intents: [
    GatewayIntentBits.Guilds,
    GatewayIntentBits.GuildMessages,
    GatewayIntentBits.GuildPresences,
    GatewayIntentBits.GuildMessageReactions,
    GatewayIntentBits.DirectMessages,
    GatewayIntentBits.MessageContent
  ],
  partials: [
    Partials.Channel,
    Partials.Message,
    Partials.User,
    Partials.GuildMember,
    Partials.Reaction
  ]
});
//Hosting the bot
require('http').createServer((req, res) => res.end('Ready.')).listen(3000);

client.on('message', message => {
    if (message.content === 'ping') {
        message.reply('pong');
      }
});

client.login(Token); //The token
```
Replace the **`Token`** with the token you saved for later use in Step 5 of this tutorial and put it between quotation marks. Then save the file. This token should not be shared with anyone, so don’t push the code for this tutorial directly to GitHub. There is an option to use the **`dotenv`** package in combination with a **`.gitignore`** file to store your token securely, but for this tutorial, I wanted to focus on simplicity rather than IT security.

• It is (a)live! Run the following command in the terminal and look at your Discord server. The bot should now appear online. `npm start` Troubleshooting: If you get an error like **`Error: Cannot find module ‘node:events,’`** make sure you have a Node.js version above version `16.6.0` installed. You can check your current Node version with the command: `node -v` If your version is lower than version `16.6.0`, head to the Node.js website and install a more recent version. You can always close a command that is stuck in the terminal using: `[Ctrl + C] (on Windows) or [Cmd + C] on MacOS`

• Try to rerun the `npm start` command and check your Discord server again. You should now see that your AI bot is online! Feel happy because your AI bot is now online :D

• Test your bot by sending it a message in the server.

# Hosting your bot

> There are lot of bot hosting. I suggest using paid hosting for your own security but, there is a ton of free hosting you can use. One of them is **Replit**! One of the biggest free hosting on the platform. You can visit it by clicking [here](https://replit.com/) Consider creating a account in it.

# CopyRights

© [Alpha5959](https://github.com/Alpha5959/)
© [Reliable Inc.](https://dsc.gg/reliable-support)
© Rlyxren Development
© [Better Programming](https://betterprogramming.pub/)
© [Discord.js Guide](https://discordjs.guide/)
© [Node.Js](https://nodejs.org/)
