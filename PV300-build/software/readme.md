# Voron 2.4 Software

![Image of Voron 2.4](http://vorondesign.com/images/voron2.4.jpg)

Step 1: Insert SD card with "prepared firmware" into BTT Octopus
- Copy and paste the "agr-octopus-klipper.bin" from Agriolabs Github to an SD card.
- Rename file in SD card to "firmware.bin".
- Plug SD card into BTT Octopus.

Step 2: Install Octoprint onto Raspberry Pi 4
- Go to https://octoprint.org/ and download the latest version of OctoPi
- Go to https://www.balena.io/etcher/ and download the latest version of the program.
- Insert your SD card for the pi into your computer/laptop and open up BalenaEtcher.
- Click "Flash from file" and select the "octopi-buster-armhf.img" file.
- "Select target" will be the SD card you have inserted.
- Click "Flash!" and wait.
- After flashing the SDcard with the .img file, open up the SDCard and find "octopi-wpa-supplicant.txt".
- Open "octopi-wpa-supplicant.txt" with a text editor such as VScode/Brackets.
- Uncomment the lines prefixed with a single # of the configuration and enter your WIFI information below
   `## WPA/WPA2 secured`
   `#network={`
    #ssid="insert wifi user"
    #psk="insert password"
    #}`
- Example with WIFI info:
   `## WPA/WPA2 secured
    network={
    ssid="TELUS1234"
    psk="kappa123"
    }`
- Save file
- Insert card into Raspberry Pi 4 and power on.
- Find IP of pi in router menu(192.168.1.254 = Default Gateway) or https://octopi.local/.

Step 3: Configure Octoprint
- After finding the IP, enter the IP in the search bar on your browser.
- Set up octopi with the wizard:
    - Start: Click "Next"
    - Restore Backup?: Click "Next"
    - Access Control: Enter your username and password and click "Next"
    - Anonymous Usage Tracking: Click "Enable Anonymous Usage Tracking"
    - Online Connectivity Check: Click "Enable Connectivity Check"
    - Plugin Blacklist: Click "Enable Plugin Blacklist Processing"
    - Default Printer Profile, General: Enter Name for Printer and the Model. Ex. PV1 and Voron 2.4 300
    - Default Printer Profile, Print Volume: Enter Build Volume for the printer. Ex. Voron 2.4 300 = X 300, Y 300, Z 270 
- Go to https://www.putty.org/ to download and install PuTTY.
- Open up PuTTy and SSH with the IP.
- It will prompt you will a username and password to access the pi, Username: pi, Password: raspberry
- In the console, type "sudo raspi-config".
- It will prompt with entering the password again, enter the password.
- Use arrow keys and enter to navigate, Press enter on "1 System Options".
- Press enter on "S4 Hostname".
- Change the hostname to whatever you like and confirm.
- Press enter on "S3 Password".
- Change the password to whatever you like and confirm.
- Press enter on "Back"
- Press enter on "Finish" to complete.

Step 4: Install Klipper
- Open up PuTTY and enter the IP.
- Enter your username and the new password you created. Ex. Username: pi & Password:Kappa123
- Type "git clone https://github.com/KevinOConnor/klipper" and wait for it to install.
- After installing, type "./klipper/scripts/install-octopi.sh" to install the dependencies and wait for it to install.

Step 5: Configuring Octoprint to use Klipper
- Enter the IP in the browser. Ex. https://pv1
- In the navigation bar at the very top, click the 🔧 to open up the settings.
- In Serial Connection, type "/tmp/printer" in Additional serial ports.
- In Interval & Timeouts, change "Connection timeout" & "Communication timeout" to "600"s.
- In Behaviour, change the Error handling from "Disconnect from the printer" to "Cancel any ongoing prints but stay connected to the printer".
- Click "Save".
- Click "Close" to return to the homepage.
- In Connection (left-side sidebar), change Serial Port to "/tmp/printer" and click the two checkboxes "Save Connection Settings" & "Auto-connect on server startup".
- Click "Connect".
- In the terminal, type "status"

Step 6: Configuring Klipper
- Go to https://winscp.net/eng/download.php to download and install WinSCP.
- Open WinSCP and click "New Site"
- Enter IP and password for pi and click "Save".
- Name "Site Name" and click "Ok".
- Login into IP and enter the password.
- Copy and paste "agr-octopus-PV300-config.cfg" from Agriolabs GitHub into /home/pi.
- Rename file to "printer.cfg".


