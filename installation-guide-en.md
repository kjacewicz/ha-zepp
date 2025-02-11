# How to Install HA on Your Zepp Watch to Control Your Devices
### Table of Contents
- Compatible Models
- App Features
- Installing the App
- Preparation
- Installation via Installer
- Installation via Terminal
- App Configuration
- Credits & Acknowledgments

# Compatible Models
Thanks to our community members, we have tested and adapted the app for the following models:
- Amazfit GTS 3
- Amazfit GTR 3
- Amazfit GTR 3 Pro
- Amazfit GTS 4 Mini
- Amazfit GTS 4
- Amazfit GTR 4
- Amazfit Cheetah Pro
- Amazfit Active
- Amazfit Active Edge
- Amazfit Balance
- Amazfit T-REX 2
- Amazfit Bip 5 Unity
- Amazfit Band 7
- Xiaomi Band 7 (requires an additional step, see [this guide](http://web.archive.org/web/20241103093642/https://aguacatec.es/instalar-ha-en-la-xiaomi-band-7/))
We are currently working on making the app compatible with more Zepp devices. If you have one that’s not on the list, join our [Telegram community](https://t.me/aguacatec_es) to test it out! Also, if you're considering purchasing a new watch, check [Amazfit Global Retail Store](https://s.click.aliexpress.com/e/_DdSQKvj) on AliExpress for pricing.

# App Features
Once you install **HA** on your **Zepp** watch, you’ll be able to:
- Display your entities in **three categories** (devices, scripts, and sensors)
- **Control your devices** (turn lights and plugs on/off, adjust brightness and effects if supported, and control media entities)
- **Launch scripts and automations**
- **View sensor information**

# Installing the App
If you’re ready, follow these steps to **install HA on your Zepp watch!**
## Preparation
1. If you haven’t already, download and install the Zepp app (formerly Amazfit) on your mobile device. Once installed, create an account and log in.
Open the Zepp app on your phone.
2. Navigate to Profile > Settings > About and tap the Zepp logo multiple times until you see the message:
"**Developer mode activated**."
3. Now, we need to **build and install the Home Assistant app** (it might sound complicated, but I’ll guide you step by step).
## Set Up the Development Environment
Before installing the app, you need to prepare your development environment as described by [Zepp’s platform](https://docs.zepp.com/docs/1.0/guides/tools/cli/) (or watch this [**tutorial video**](https://www.youtube.com/watch?v=inFi-dEFnR0)).
* Install Node.js - Visit [Node.js](https://nodejs.org/) and download the version labeled “**Recommended For Most Users**”.
Run the installer and follow the instructions.
* Install Git. Download the latest version from [Git's official site](https://git-scm.com/). Run the installer and follow the setup process.
* Create a Developer Account - Go to the [Zepp Developer Console](https://console.zepp.com/) and create an account (do not use your Google account).
This is required to install the HA app on your Zepp watch.

Almost there! Now, you have two installation options:
Easy Method – Use the [installer created by Barny](/HA-ZeppOS-instaleitor.zip).
Manual Method – Install it yourself via the terminal.

# Installation via Installer
1. Download the [installation file](/HA-ZeppOS-instaleitor.zip), unzip it, and run it.
2. Select your language using the keyboard (press 1 for Spanish, 2 for English), then press Enter.
3. Press 4 and Enter to install Zeus CLI (the software for creating Zepp apps).
Once installed, close the window manually.
4. Press 5 and Enter to check the installed version.
If it returns a version number, the installation was successful.
5. Press 6 and Enter to install or update the Home Assistant app.
6. Press 7 and Enter, then select your device from the list. If necessary, use the arrow keys to scroll down. A QR code will be generated.
   Install via Zepp App.
7. Open the Zepp app on your mobile device. Navigate to Profile > Your Watch > Developer Mode.
   Tap the “+” icon in the top right corner, then tap “Scan”.
   Scan the QR code displayed in the terminal and wait for the "Installing" message to complete.
   Now, navigate through your Zepp watch menu, and you’ll find the Home Assistant option available!

## Installation via Terminal
If you encounter any issues with the installer or prefer a manual installation, follow these steps:
Open the Terminal:
* On Windows, type "cmd" in the search bar and open the Command Prompt.
Install Zeus CLI:
* Run the command:
```
npm i @zeppos/zeus-cli -g
```
Verify the Installation:
Run the command:
```
zeus -v
```
If it returns a version number, the installation was successful.
💡 Note: If you get an error "npm ERR! code EBUSY", run:
```
npm install -g npm@latest
```
Then, try installing Zeus CLI again.

5. Now we are going to install our version of the Home Assistant application. To do this, run the following commands from your terminal (each line is a command):
```
git clone https://github.com/TitoTB/ha-zepp  
cd ha-zepp  
zeus preview  
```
6. When you run this last command, the Zepp developer console will open in your browser, where you will have to log in with the account you created previously.
7. Once this is done, go back to the console and select your Zepp watch from the available options (if necessary, use the arrow keys to scroll down the list). This will generate a QR code on the screen, which we will use to install the application.
8. Open the Zepp app on your mobile device and go to Profile > Your watch > Developer Mode, tap the “+” icon in the top right corner and then “Scan.” Now scan the QR code generated on the console and wait for the “Installing” screen to finish. Now if you browse your Zepp watch, you will see that you already have the “Home Assistant” option in your menu.

# App Configuration
Now, we just need to connect the app to your HA instance.
Open Zepp app → Profile > Your Watch > Developer Mode > Mini Program > Home Assistant (Settings).
Enter the following details:
Local HA instance address: http://homeassistant.local:8123/  

External HA instance address: (Your external access domain, e.g., https://yourdomain.com/)
Long access token: Generate this in Home Assistant:
Open the HA mobile app → Menu → Tap your username → Scroll down → Create Token.
Name it (e.g., “XiaomiBand7”) and copy the token.
Paste it into the Zepp app.

In the “Entities” section you can use the search engine to select the entities you want to control (you can search by name, domain or leave it empty to get the entire list). Then click on the “Search” button and activate the entities you want. You can also use the “Top” button to sort the selected entities.

# Credits & Acknowledgments
This app is built upon the work of ga2mer and shorty88, who introduced entity grouping by categories.
From the Aguacatec community (Barny & Tito), we have refined the interface and expanded compatibility to more Zepp OS watches.
Need help? Join our community!
If you found this useful, share it! 🚀

Translated from: http://web.archive.org/web/20241103093642/https://aguacatec.es/instalar-ha-en-tu-reloj-zepp/
