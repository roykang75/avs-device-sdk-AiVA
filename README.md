# Raspberry Pi Quick Start Guide with Script for Hally Audio Board

This is avs-device-sdk for Hally Audio Board.  
Hally Audio Board is made by WizIoT.  

Detail description is below:  
https://github.com/alexa/avs-device-sdk

## Required hardware

1. Raspberry Pi 3 (Recommended) or Pi 2 Model B (Supported)
2. Raspberry Pi (Raspbian Stretch - Raspberry Pi Software Guide(https://www.raspberrypi.org/learning/software-guide/))
3. After install Raspbian, turn on SSH
   > Raspbian Menu > Preference >  Raspberry Pi Configuration > Select Interfaces Tab > SSH is enable.
4. Raspbian ID and Password: pi / raspberry

## Register a product

Before we get started, you'll need to register a device and create a security profile at developer.amazon.com. [Click here](https://github.com/alexa/alexa-avs-sample-app/wiki/Create-Security-Profile) for step-by-step instructions.

IMPORTANT: The allowed origins under web settings should be http://localhost:3000 and https://localhost:3000. The return URLs under web settings should be http://localhost:3000/authresponse and https://localhost:3000/authresponse.

If you already have a registered product that you can use for testing, feel free to skip ahead

## Setup and run
1. Update the installed image
```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get dist-upgrade
$ sudo shutdown -r
```
2. Pull avs-sdk-setup source
```
git clone https://github.com/roykang75/avs-device-sdk-for-hally.git
```

3. Update config.txt with the Client ID, Client Secret, and Product ID for your registered product and save.
4. Run the setup script with your configuration as an argument:
```
sudo bash setup.sh config.txt
```
5. After the setup script has finished running, you'll need to generate an authorization token. Run this command, and open your browser and navigate to http://localhost:3000. Log in with your Amazon credentials and follow the instructions provided:
```
sudo bash startauth.sh
```
6. Last and most importantly, let's run the sample app:
```
sudo bash startsample.sh
```
7. You can also run integration and unit tests:
```
sudo bash test.sh
```