# README
***

## netwatcher
[id]: don@effinthing.com "Don Feliciano"
Author: [Don Feliciano][id] with contributions by Massimo Castelli <br />
Credits: Display Notification Center Alert taken from: [automatedworkflows.com](http://automatedworkflows.com)

### Overview
Using an OS X feature called launchd, we've managed to create a simple tool that automates location switching between work and home.

This script will execute any time there is a network change and can:

* Set default printer
* Set Messages status
* Start/Stop [Proxifier](http://www.proxifier.com)
* Start/Stop Cisco AnyConnect VPN
* Turn Wi-Fi on/off based on presence/state of wired Ethernet
* Turn Wi-Fi off to save resources when there is no network connection available

### Installation

1. Install [Github](http://mac.github.com)
2. Go to <https://github.com/dfelicia/netwatcher>
3. Click the Clone in Mac button:<br />![clone_netwatcher](http://effinthing.com/netwatcher/clone_netwatcher.png "Clone netwatcher")
4. Open a terminal and cd to the directory where you cloned the repository; for example `cd ~/github/local/netwatcher`
5. Execute: `./setup` with desired options. Pass `-h` for usage
6. Answer the queries

For example:
	
    ./setup -t 5 -p 5
    Do you want to watch for wired ethernet connections? (y/n) y
    Do you want to enable flight mode? (Turns off Wi-Fi if not connected) (y/n) n
    Do you want to change your status in Messages when your connection changes? (y/n) y
    
    Modify /Users/dfelicia/.netwatcherrc to change the status messages
    
    
    The following printers are installed:
    
    Brother_MFC_J480DW
    stamford2_3074_mfd_us_oracle_com
    stamford2prt_3074_c_us_oracle_com
    
    system default destination: stamford2_3074_mfd_us_oracle_com
    
    Enter the name of your work printer or "none" to disable this feature
    [ Enter = stamford2_3074_mfd_us_oracle_com ]:
    Is "stamford2_3074_mfd_us_oracle_com" correct? (y/n) y
    Enter the name of your home printer or "none" to disable this feature
    [ Enter = stamford2_3074_mfd_us_oracle_com ]: Brother_MFC_J480DW
    Is "Brother_MFC_J480DW" correct? (y/n) y
    Do you want to enable Notification Center alerts? (Requires OSX >= 10.8) (y/n) n
    Enter the IP address pattern of your workplace
    [ Enter = 10.[0-9][0-9][0-9] ]:
    Is "10.[0-9][0-9][0-9]" correct? (y/n) y
    Enter the domain suffix pattern of your workplace
    [ Enter = example.com ]: oracle.com
    Is "oracle.com" correct? (y/n) y
    Enter the SSID for your workplace
    [ Enter = clear-corporate ]:
    Is "clear-corporate" correct? (y/n) y
    Enter the SSID for your home
    [ Enter = wrt ]: You kids get off my LAN
    Is "You kids get off my LAN" correct? (y/n) y
    Enter the domain suffix pattern for your home
    [ Enter = local ]:
    Is "local" correct? (y/n) y
    Setting options to: -t5 -p5
    Installation complete
    Use "defaults read ~/Library/LaunchAgents/local.netwatcher.plist" to see default plist values
    Use "defaults write ~/Library/LaunchAgents/local.netwatcher.plist <key> <value>" to change plist values
    Do "sudo touch /var/run/resolv.conf" to test
	
### Removal
1. Open a terminal and cd to the directory where you cloned the repository; for example `cd ~/github/local/netwatcher`
2. Execute: `./setup –u`

###Customization
Edit `~/Library/Scripts/netwatcher` (please consider contributing your changes if they don’t suck :-P). Change preferences in `~/.netwatcherrc` or by running `./setup -r`

###Logging
The log is stored in `~/Library/Logs` and will auto-purge when >= 1MB. It is best viewed in Console.app:<br />

![Console.app](http://effinthing.com/netwatcher/console_app.png)

###Notification Center
Notifications are (optionally) sent when netwatcher takes action:<br />

![Notification center messages](http://effinthing.com/netwatcher/notifications.png)