<h1 align="center">
  WHM (WebHookManager)
</h1>
<p align="center">
  <a href="https://nodei.co/npm/@devartsite/whm"><img src="https://nodei.co/npm-dl/@devartsite/whm.png?months=5&height=2" alt="npm"></a>
  <a href="https://nodei.co/npm/@devartsite/whm"><img src="https://nodei.co/npm/@devartsite/whm.svg" alt="npm"></a>
</p>
<p align="center">  
  <a href="https://www.npmjs.com/package/@devartsite/whm"><img src="https://img.shields.io/npm/v/@devartsite/whm.svg" alt="npm version"></a>
  <img alt="GitHub package.json version" src="https://img.shields.io/github/package-json/v/devartsite/whm">
  <img src="https://img.shields.io/badge/code_style-standard-brightgreen.svg" alt="Standard - JavaScript Style Guide">
  <img alt="GitHub top language" src="https://img.shields.io/github/languages/top/devartsite/whm">
  <img alt="GitHub code size in bytes" src="https://img.shields.io/github/languages/code-size/devartsite/whm">
  <img alt="GitHub repo size" src="https://img.shields.io/github/repo-size/devartsite/whm">
  <img alt="Libraries.io dependency status for latest release, scoped npm package" src="https://img.shields.io/librariesio/release/npm/@devartsite/whm">
  <img alt="npm" src="https://img.shields.io/npm/dw/@devartsite/whm">
  <img alt="GitHub commit activity" src="https://img.shields.io/github/commit-activity/m/devartsite/whm?style=plastic">
  <img alt="npm collaborators" src="https://img.shields.io/npm/collaborators/@devartsite/whm">
  <img alt="NPM" src="https://img.shields.io/npm/l/@devartsite/whm">
</p>
<p align="center">
  <a href="https://discord.gg/3hGMPw"><img src="https://img.shields.io/discord/592890801575690259" alt="discord"></a>
  <img alt="GitHub issues" src="https://img.shields.io/github/issues/devartsite/whm">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/devartsite?style=plastic">
  <img alt="GitHub followers" src="https://img.shields.io/github/followers/devartsite?style=plastic">
  <img alt="GitHub stars" src="https://img.shields.io/github/stars/devartsite/whm?style=plastic">
  <img alt="GitHub watchers" src="https://img.shields.io/github/watchers/devartsite/whm?style=plastic">
  <img alt="GitHub forks" src="https://img.shields.io/github/forks/devartsite/whm?style=plastic">
</p>
<p align="center">
Webhookmanager is a manager of webhook in cli<br>
Easy to use, it will allow you to send notifications on Discord or your phone with Macrodroid
<p>

Features
-----
 * Add a webhook (Discord, Macrodroid)
 * Delete a webhook
 * View infos of webhook by name
 * View list of webhooks
 * Execute webook with message

Installation
-----
To install whm :
``` sh
npm install -g @devartsite/whm
```
And run this command to see help :
``` sh
whm -h
```

Usage
-----
  * To add a webhook (-d for discord or -m for macrodroid):
    ``` sh
    whm add <name> <url> <option>
    ```
  * To delete a webhook:
    ``` sh
    whm del <name>
    ```
  * To get info of webhook by name:
    ``` sh
    whm info <name>
    ```
  * To list your webhooks:
    ``` sh
    whm list
    ```
  * To execute a webhook:
    ``` sh
    whm exec <name> <message>
    ```
    Options (-d --date to attach a new date to the message, -w --who to find out who did what):
    * date option:
      ``` sh
      whm exec mywebhook "my message at {{date}} with date on middle" -d
      ```
      ``` sh
      whm exec mywebhook "my message with date on end of message, at " -d
      ```
    * who option:
      ``` sh
      whm exec mywebhook "my message by {{who}} with who on middle" -w
      ```
      ``` sh
      whm exec mywebhook "my message with who on end of message, at " -w
      ```

Pratical usage
--------------
If you need to receive a notification on a webook when someone connects to your server in ssh, you can use the example below.

  * Example 1 ([Discord webook](https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks))

    First you do add your webhook
    ``` sh
    whm add mywebhook https://discordapp.com/api/webhooks/<channelid>/<webhookid> -d
    ```
    Now in the user file ".bashrc" add this line:
    ``` bash
    whm exec mywebhook "Connection shell to example by {{who}} at {{date}}" -w -d
    ```
    Now when someone connects to shell example you receive this notification on your server Discord

  * Example 2 ([Macrodroid webook](https://macrodroid.com/)) 

    WARNING!! You have to add your macrodroid url in tiny url else if you don't so that, your webhook will not work
    ________
  
    First you do add your webhook
    ``` sh
    whm add mywebhook https://tinyurl.com/<id>/<secret> -m
    ```
    Now in the user file ".bashrc" add this line:
    ``` bash
    whm exec mywebhook "Connection shell to example by {{who}} at {{date}}" -w -d
    ```
    Now when someone connects to shell example you receive this notification on your Device where you have previously configured this webhook in Macrodroid

Todo list
---------
  * API to use this module easily by importing it into a project
  * Possibility to send custom data

  Maybe more ...
