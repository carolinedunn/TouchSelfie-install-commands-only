# TouchSelfie-install-commands-only
This repo is simply the commands needed to install TouchSelfie
Create your own photo booth or selfie station powered by a Raspberry Pi 3B and printer.

Features of this photo booth include:
 - Automatically upload photos to your Google Photos account
 - Users can immediately email the photos to themselves
 - 5 second countdown to each picture
 - Capability to backup all photos to a USB drive
 - Captures a list of all email addresses entered
 - Takes 4 photos in one frame
 - Create an Animation GIF
 - Print photos

Printer Links:
Canon SELPHY CP1300 - https://amzn.to/2DshBfg
Cartridges & 4X6 Paper - https://amzn.to/2ORzV3J
USB to Mini USB cable - https://amzn.to/2E1vjad

Project Materials:
Raspberry Pi 3B+ https://amzn.to/2MbzjVP (3B will also work https://amzn.to/2O8Pmoj )
5V / 2A Raspberry Pi Power Adapter https://amzn.to/2O6Oi43
8GB or larger microSD card https://amzn.to/2O5aj3i
7" Raspberry Pi touchscreen https://amzn.to/2O0vL9q
Raspberry Pi Module V2 camera https://amzn.to/2AAOqH3
Keyboard / Mouse combo https://amzn.to/2OB9Irj
1/4-20 hex nut https://amzn.to/2OBap3T
4 M2 screws and 6 M2 nuts
2 M3 10mm screws
2 M3 6mm screws
Small screwdriver
60" tripod https://amzn.to/2O8lNmO
or 50" tripod https://amzn.to/2MhWXju
Optional: Flash Drive
3D printed tripod mount https://www.thingiverse.com/thing:161...
3D printed camera mount https://www.thingiverse.com/thing:291...
If you do not have a 3D printer, click "Order This Printed" from the Thingiverse page

Original Photobooth Tutorial - https://youtu.be/aFwVVPyXen4

GitHub Repository: https://github.com/laurentalacoque/To... 

Raspian OS download link - https://www.raspberrypi.org/
Etcher - https://www.balena.io/etcher/

Additional note not included in the video:
You may want to print and post a disclaimer. I am not a lawyer and this is in no way intended to be considered legal advice, but here's a sample disclaimer - https://github.com/carolinedunn/Touch...

Shorthand notes with Install Commands:
Open a Terminal
Sudo raspi-config
Enable Camera

Reboot

Open a Terminal
sudo apt-get update
sudo apt-get install python-imaging (if that doesn't work try 'sudo apt-get install python-pil')
sudo apt-get install python-gdata
sudo apt-get install python-imaging-tk

sudo pip install --upgrade pip
sudo pip install --upgrade google-api-python-client
sudo pip install --upgrade oauth2client

# Install ImageMagick for the 'Animation' mode
sudo apt-get install imagemagick

# Install CUPS for the Printing function(optional)
sudo apt-get install cups
sudo apt-get install python-cups

sudo usermod -a -G lpadmin pi

Open a web browser
Go to - localhost:631
Add Printer - follow prompts

Open a Terminal 
git clone https://github.com/laurentalacoque/To...

mv TouchSelfie-extended TouchSelfie

cd TouchSelfie
chmod +x ./setup.sh
./setup.sh

Follow Prompts
Create a Project in console.developer.google.com
Create Credentials for Application Guide Other
Download .json
UPDATED: Rename download to google_client_id.json and move to 
/TouchSelfie/scripts

Click Connect for Client Store
Click Start
Authenticate and Allow
Copy Auth Code
Paste and Authenticate

Click Next
Check Log email addresses
Send Test email
Click Next

Select Album
Double Click
Click Next

Choose Directory 
/media/pi/4GB

Click Save

In Terminal:
chmod +x ./photobooth.sh
sudo ./photobooth.sh
