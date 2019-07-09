# Pi-OLED
Config for OLED display on pi 

Follow this tutorial to install the OLED display:
https://www.raspberrypi-spy.co.uk/2018/04/i2c-oled-display-module-with-raspberry-pi/

**Enable I2C Interface:**

The I2C interface is disabled by default so you need to enable it. You can do this within the raspi-config tool on the command line by running :

`sudo raspi-config`

The following libraries may already be installed but run these commands anyway to make sure :

```sudo apt install -y python3-dev
sudo apt install -y python-imaging python-smbus i2c-tools
sudo apt install -y python3-pil
sudo apt install -y python3-pip
sudo apt install -y python3-setuptools
sudo apt install -y python3-rpi.gpio
```
If you are using Python 2 then use these commands instead :

```sudo apt install -y python-dev
sudo apt install -y python-imaging python-smbus i2c-tools
sudo apt install -y python-pil
sudo apt install -y python-pip
sudo apt install -y python-setuptools
```


**Install OLED Python Library:**

In order to display text, shapes and images you can use the Adafruit Python library. It should work with all SSD1306 based displays including their own 128×32 and 128×64 devices.

To install the library we will clone the Adafruit git repository. Ensure git is installed by running :

`sudo apt install -y git`
Then clone the repository using the following command :

`git clone https://github.com/adafruit/Adafruit_Python_SSD1306.git`

Once that completes navigate to the library’s directory :

`cd Adafruit_Python_SSD1306`

and install the library for Python 3 :

`sudo python3 setup.py install`

Install the other library:

`git clone https://github.com/adafruit/Adafruit_Python_PureIO.git`

Once that completes navigate to the library’s directory :

`cd Adafruit_Python_PureIO`

Then to install the library

`sudo python3 setup.py install`

**Install the font and Stats:**

Then create a folder in `/home/pi/` and copy the content of OLED in it

Start the script by modifying `sudo nano /etc/rc.local` and adding this line before the `exit 0`


`sudo python3 /home/pi/OLED/statspihole.py &`
