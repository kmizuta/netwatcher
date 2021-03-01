# README
***

## netwatcher
[id]: don@effinthing.com "Don Feliciano"
Author: [Don Feliciano][id]<br />

### Overview
A simple script that automates location switching between work and home.

This script will execute any time there is a network change and can:

* Set default printer
* Set Adium status
* Start/Stop [Proxifier](http://www.proxifier.com)
* Start/Stop Cisco AnyConnect VPN
* Start/Stop Dropbox
* Start/Stop NextCloud
* Start/Stop Oracle Documents
* Turn Wi-Fi on/off based on presence/state of wired Ethernet

### Installation

1. Install [Github](http://mac.github.com)
2. Go to <https://github.com/dfelicia/netwatcher>
3. Click the Clone in Mac button
4. Open a terminal and cd to the directory where you cloned the repository; for example `cd ~/github/local/netwatcher`
5. Execute: `./setup` with desired options. Pass `-h` for usage
6. Answer the questions

For example:
	
    ./setup -t5 -p10
    Do you want to watch for wired ethernet connections? (y/n) y
    Do you want to change your status in Adium when your connection changes? (y/n) y
    Enter your Adium account username
    [ Enter = dfelicia ]: don@effinthing.com
    Is "don@effinthing.com" correct? (y/n) y

    Modify /Users/dfelicia/.netwatcher/config to change the status messages

    The following printers are installed:

    Laser_Printer
    stamfordmfd03
    ysoft-safeq-1

    system default destination: stamfordmfd03

    Enter the name of your work printer or "none" to disable this feature
    [ Enter = stamfordmfd03 ]:
    Is "stamfordmfd03" correct? (y/n) y
    Enter the name of your home printer or "none" to disable this feature
    [ Enter = stamfordmfd03 ]: Laser_Printer
    Is "Laser_Printer" correct? (y/n) y
    Do you want to enable Notification Center alerts? (y/n) y
    Enter the IP address pattern of your workplace
    [ Enter = 10.[0-9][0-9][0-9] ]:
    Is "10.[0-9][0-9][0-9]" correct? (y/n) y
    Enter the domain suffix pattern of your workplace
    [ Enter = example.com ]: example.com
    Is "example.com" correct? (y/n) y
    Enter the SSID for your workplace
    [ Enter = clear-corporate ]:
    Is "clear-corporate" correct? (y/n) y
    Enter the SSID for your home
    [ Enter = You kids get off my LAN ]:
    Is "You kids get off my LAN" correct? (y/n) y
    Enter the domain suffix pattern for your home
    [ Enter = local ]:
    Is "local" correct? (y/n) y
    Setting options to: -t5 -p10
    Installation complete
    Use "defaults read ~/Library/LaunchAgents/local.netwatcher.plist" to see default plist values
    Use "defaults write ~/Library/LaunchAgents/local.netwatcher.plist <key> <value>" to change plist values
    Do "sudo touch /var/run/resolv.conf" to test
	
### Removal
1. Open a terminal and cd to the directory where you cloned the repository; for example `cd ~/github/local/netwatcher`
2. Execute: `./setup –u`

### Customization
Edit `~/Library/Scripts/netwatcher` (please consider contributing your changes if they don’t suck :-P). Change preferences in `~/.netwatcher/config` or by running `./setup -r`

### Logging
The log is stored in `~/Library/Logs` and will auto-purge when >= 1MB. It is best viewed in Console.app

### Notification Center
If terminal-notifier is installed, Notification Center alerts are (optionally) sent when netwatcher takes action. You can install terminal-notifier via [Homebrew](https://formulae.brew.sh/formula/terminal-notifier) <br />