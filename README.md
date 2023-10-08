# Discord-ROIP
Script that monitors audio ports and relays audio between a radio transceiver and a discord voice channel

## Installation
This expects a fresh install of Ubuntu22.04. XUbuntu was used for testing. Install by typing the following commads. Discord will be installed via snap. 

```
sudo apt install git
git clone https://github.com/HansKillinger/Discord-ROIP
cd Discord-ROIP
sh install.sh
```

in your text editor, open 'config.py' and edit the sound card devices. These were listed at the end of the install script. They can be shown at any time by typing the following into a terminal. 
```
pactl list sources | grep -e "Name"
```

- RX_ADDRESS will be your audio mic port. This audio comes from the radio. 
- TX_ADDRESS will be an output 'monitor'. This will be the output from discord.
- RX_THRESHOLD is the level of RMS audio detected required to transmit from Radio to Discord
- TX_THRESHOLD is the level of RMS audio detected required to transmit from Discord to Radio
- DELAY is the time in milliseconds between polling the audio channels.

From your desktop menu, open your power management.  Disable lock screen on suspend, and disable any settings where power shuts off, or enables sleep or suspend. Turning the display off should be fine.

If you haven't already, create a new Discord account for your ROIP link. Make sure you have auto-login enabled in the Discord app with this account. Discord can be found in the desktop menu. Make the following changes in Discords settings under 'Voice & Video' tab.

- Set Microphone to audio device coming from Radio. Turn volume to max.
- Set output to audio device going to radio. Turn volume to max.
- Change Input Mode to Push to Talk
- Set the PTT key to 'SHIFT' key.
- Disable Echo Cancellation
- Set Noise Suppression to Standard or None

Next goto the 'Notifications' tab.

- Uncheck Enable Desktop Notifications
- Check Disable All Notification Sounds

