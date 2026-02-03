# DAPS
DAPS is a shell written in pure Python. No other language except from JSON for the configuration file is used.
# Installation
Go to Releases and get the newest version of DAPS.
This is a .zip for Releases and a single file for pre-releases. (Pre-releases can some times be .zips too! Make sure you're downloading the correct version!)
I'd recommend a stable version, aka as a "Release"
Once downloaded, extract to a folder of your choice.
Open the `installer` foler and run install.sh.
After that, just run `daps`!
# Usage
Here comes the fun part!
Basic shell commands work, like `cd` or `ls`.
Built-in commands are `clear`, `clearhist`, `update` and `exit`
### clear
The `clear` command will clear everything on screen.
See Configuration below for options.
### clearhist
Clears history.
The shell cannot record history if you have rn this command until the shell is restarted.
This is a feature to prevent bugs, and cannot be turned off.
### exit
Exits the shell.
What else would it do?
### update
This command will update DAPS by cloning DAPS into a temp folder, coping that version of DAPS into /usr/bin.
# Configuration of the shell
The shell will create a file named config.json in the ~/.config/daps/ directory where ~ is your cuurent user's home folder.
By defualt, the file will only contain: 
```json
{}
```
To start editing, drop the last } to the bottom like this:
```json
{

}
```
Then, you can add the following options.
### "greeter"
"greeter" is a config option runs it's value at every shell start.
Like so:
```json
{
"greeter": "fastfetch"
}
```
This will run `fastfetch` at shell start.

### "aliases"
"aliases" is a config list for shell aliases.
Like so:
```json
{
"aliases": {
"ll": "ls -l"
}
}
```
#### PLEASE NOTE! At the moment, built-in shell commands, can not be used in aliases. Built-in commands are listed above.
### "cleargreet"
"cleargreet" specifies if the greeter program should be ran on `clear`.
Like so:
```json
{
"cleargreet": "yes"
}
```
### What a full config would look like:
```json
{
"aliases": {
"ll": "ls -l"
}
"greeter": "fastfetch"
"cleargreet": "yes"
}
```
## More things are to come!
## DAPS is protected by the GNU license, meaning any contributions or deriatives of the program MUST be fully open source.
### © Nytrix Labs 2026
