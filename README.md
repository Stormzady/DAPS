# DAPS
DAPS is a shell written in pure Python. No other language except from JSON for the configuration file is used.
# Installation
Go to Releases and get the newest version of DAPS.
This may be a pre-release or a release.
Then, copy the daps file to /usr/bin either using `sudo cp daps /usr/bin` in the place you saved daps to or copy it with a file manager.
# Usage
Here comes the fun part!
Basic shell commands work, like `cd` or `ls`.
Built-in commands are `clear`, `clearhist` and `exit`
### clear
The `clear` command will clear everything on screen.
See Configuration below for options.
### clearhist 
Clears history.
The shell cannot record hidtory if you have rn this command until the shell is restarted.
This is a feature to prevent bugs, and cannot be turned off.
### exit
Exits the shell.
What else would it do?
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
```
{
"greeter": "fastfetch"
}
```
This will run `fastfetch` at shell start.

### "aliases"
"aliases" is a config list for shell aliases.
Like so:
```
{
"aliases": {
"ll": "ls -l"
}
}
```
# Have a nice time!
