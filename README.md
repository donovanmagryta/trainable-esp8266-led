# IoT Whiteboard
ESP8266 based LED strip display of Yes/No API data.

Example API queries:
Will it rain today? Have I reached my Kickstarter goals? Snow day? Good windspeed to fly drone? 

Change settings easily & remotely - by using web app.

Manage multiple devices

Optimized circuit efficiency by using 60 pure red, green, or blue WS2812B LEDs.

Cheap - core parts cost < $10 US Dollars

![](out.jpg)

# Tutorial:
## 1. Get Parts:
* Wemos D1 Mini - https://www.banggood.com/custlink/GvvK5E8B0P

* WS2812B Addressable LED Strip (You must cut down to 60 LEDs with scissors) - https://www.banggood.com/custlink/3GmmFR9ee8

* Soldering Iron & 60/40 Rosin Core Lead Solder: https://www.banggood.com/custlink/DmKDPhZ6e6

* 5V 2A+ Power Supply - **Must be at least 2 amps.** - I used a cut USB cable and a 2.1A USB Charger. https://www.banggood.com/custlink/mD3K5Y9egq 

* Hot Glue Gun with Sticks: https://www.banggood.com/custlink/KKvKHhSNEe

* Whiteboard or Acrylic Sheet and Dry Erase Marker: https://www.ebay.com/itm/16-24-35-47-Aluminum-Frame-Magnetic-Whiteboard-Dry-Erase-w-Board-Marker-Pen/311936582732?hash=item48a0de844c:m:m-E-ZRTFjVYbyOAs701hznw&frcectupt=true

## 2. Install the Web App
Sign up for a free PHP web hosting service such as https://www.000webhost.com/

![](signup.gif)

Create a new site there.

![](newsite1.gif)

and load the led.php file onto there in the file manager area.

![](siteupload.gif)

Modify the url in the led.php to match the url of your website.

![](editphp.gif)

## 3. Install the Drivers & Software
Unzip the files.

![](unzip1.gif)
![](unzip2.gif)

Install the CH340 drivers.

![](driver1.gif)
![](driver2.gif)

## 4. Install Firmware
Open up UPyCraft and select board-->esp8266, select active USB port, and click burn firmware. Set flash erase-->on, custom firmware-->select your **micropython.bin** file you downloaded earlier and hit "flash".

![](burn.gif)

## 5. Install the Scripts
In a text editor or in UPyCraft, open up **connectWiFi.py** and input your WiFi hotspot credentials and in **main.py** enter your web hosting URL for led.php and hit save. Download these files to the board's filesystem.

![](code.gif)

## 6. Solder up your device
Strip wire tips

![](wire1.jpg)
![](wire2.jpg)
![](wire3.jpg)

Then tin with solder then fuse together.

>D1 Mini ESP8266 5V---5V 2A Power---LED VCC

>D1 Mini ESP8266 GND---Ground 2A Power---LED Ground

>D1 Mini ESP8266 GPIO4(D2)---LED Strip Data In


**Green wire = data, Red wire = +5V, White wire = Ground**

![](solder1.jpg)
![](solder2.jpg)
![](solder3.jpg)

Wrap individual connections in electrical tape to insulate and prevent a short circuit.

![](tape.jpg)

**Most Addressable LED strips have two additional power wires for convenience**

## 7. Train the Device
Edit the settings at your web hosting URL where led.php is located to program the device.
JSON is a nested data structure. To access the information you want, you need to enter the correct indices. As a way to understand better, here is a representation of the weather api data "consolidated_weather"-->1-->"weather_state_abbr". The TV API: 0-->"show"-->"status". Notice how curly brackets start and terminate each section.


![](app1.gif)


## Further Resources

Here is a list of public APIs that you may be able to pull data from using this system:

https://github.com/toddmotto/public-apis

![](apilist.gif)

