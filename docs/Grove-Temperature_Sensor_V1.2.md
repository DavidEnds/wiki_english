---
title: Grove - Temperature Sensor V1.2
category: Sensor
bzurl: https://www.seeedstudio.com/Grove-Temperature-Sensor-p-774.html
oldwikiname: Grove - Temperature Sensor V1.2
prodimagename: Grove_Temperature_Sensor_View.jpg
surveyurl: https://www.surveymonkey.com/r/Grove-Temperature_Sensor_V1-2
sku: 101020015
tags: io_3v3, io_5v, plat_duino
---


<p style="text-align:center"><img src="https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/img/Grove_Temperature_Sensor_View.jpg" ></p>





The Grove - Temperature Sensor uses a [Thermistor](https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/res/NCP18WF104F03RC.pdf) to detect the ambient temperature. The resistance of a thermistor will increase when the ambient temperature decreases. It's this characteristic that we use to calculate the ambient temperature. The detectable range of this sensor is -40 - 125ºC, and the accuracy is ±1.5ºC

Note: This wiki works with Grove - Temperature sensor V1.1 as well, for V1.0 please refer to [Grove - Temperature Sensor](http://wiki.seeedstudio.com/Grove-Temperature_Sensor)



<p style="text-align:center"><a href="https://www.seeedstudio.com/Grove-Temperature-Sensor-p-774.html" target="_blank"><img src="https://raw.githubusercontent.com/SeeedDocument/Seeed-WiKi/master/docs/images/get_one_now_small.png" width="210" height="41"  border=0 /></a></p>



## Specifications
---
- Voltage: 3.3 ~ 5V
- Zero power resistance: 100 KΩ
- Resistance Tolerance: ±1%
- Operating temperature range: -40 ~ +125 ℃
- Nominal B-Constant： 4250 ~ 4299K

!!!Tip
    More details about Grove modules please refer to [Grove System](http://wiki.seeedstudio.com/Grove_System/)


## Platforms Supported
-------------------

| Arduino                                                                                             | Raspberry Pi                                                                                             | BeagleBone                                                                                      | Wio                                                                                               | LinkIt ONE                                                                                         |
|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/arduino_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/raspberry_pi_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/bbg_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/wio_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/linkit_logo_n.jpg) |

!!!Caution
    The platforms mentioned above as supported is/are an indication of the module's hardware or theoritical compatibility. We only provide software library or code examples for Arduino platform in most cases. It is not possible to provide software library / demo code for all possible MCU platforms. Hence, users have to write their own software library.


## Getting Started
---
After this section, you can make Grove - Temperature Sensor V1.1/1.2 run with only few steps.

!!!Note
    If this is the first time you work with Arduino, we firmly recommend you to see [Getting Started with Arduino](http://wiki.seeedstudio.com/Getting_Started_with_Arduino/) before the start.

### Play With Arduino

#### Hardware

- **Step 1.** Prepare the below stuffs:

| Seeeduino V4.2 | Base Shield|  Grove - Temperature Sensor |
|--------------|-------------|-----------------|
|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Light_Sensor/master/images/gs_1.jpg)|![enter image description here](https://raw.githubusercontent.com/SeeedDocument/Grove_Light_Sensor/master/images/gs_4.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/img/Grove_Temperature_Sensor_View_little.jpg)|
|[Get One Now](http://www.seeedstudio.com/Seeeduino-V4.2-p-2517.html)|[Get One Now](https://www.seeedstudio.com/Base-Shield-V2-p-1378.html)|[Get One Now](https://www.seeedstudio.com/Grove-Temperature-Sensor-p-774.html)|

- **Step 2.** Connect Grove - Temperature Sensor to port **A0** of Grove-Base Shield.

- **Step 3.** Plug Grove - Base Shield into Seeeduino.

- **Step 4.** Connect Seeeduino to PC via a USB cable.


![](https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/img/connect_Arduino.jpg)

!!!Note
	If we don't have Grove Base Shield, We also can directly connect Grove_Ultrasonic_Ranger to Seeeduino as below.

| Seeeduino       | Grove - Temperature Sensor |
|---------------|-------------------------|
| 5V           | Red                     |
| GND           | Black                   |
| Not Conencted | White                   |
| A0            | Yellow                  |



#### Software

- **Step 1.** Launch Arduino IDE and click **File>New** to open a new page. Copy the following code into the new page and upload. If you do not know how to upload the code, please check [How to upload code](http://wiki.seeedstudio.com/Upload_Code/).


```
// Demo code for Grove - Temperature Sensor V1.1/1.2
// Loovee @ 2015-8-26

#include <math.h>

const int B = 4275;               // B value of the thermistor
const int R0 = 100000;            // R0 = 100k
const int pinTempSensor = A0;     // Grove - Temperature Sensor connect to A0

void setup()
{
    Serial.begin(9600);
}

void loop()
{
    int a = analogRead(pinTempSensor);

    float R = 1023.0/a-1.0;
    R = R0*R;

    float temperature = 1.0/(log(R/R0)/B+1/298.15)-273.15; // convert to temperature via datasheet

    Serial.print("temperature = ");
    Serial.println(temperature);

    delay(100);
}
```

**Step 2.** Open the **Serial Monitor** of Arduino IDE by click **Tool-> Serial Monitor**. Or tap the ++ctrl+shift+m++ key at the same time. if every thing goes well, you will get the temperature.


The result should be like:

![](https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/img/Grove_Temperature_Sensor_result.jpg)



### Play With Raspberry Pi

#### Hardware

- **Step 1.** Prepare the below stuffs:

| Raspberry pi | GrovePi_Plus | Grove - Temperature Sensor |
|--------------|-------------|-----------------|
|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/rasp.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove_Ultrasonic_Ranger/raw/master/img/Grovepi%2B.jpg)|![enter image description here](https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/img/Grove_Temperature_Sensor_View_little.jpg)|
|[Get One Now](https://www.seeedstudio.com/Raspberry-Pi-3-Model-B-p-2625.html)|[Get One Now](https://www.seeedstudio.com/GrovePi%2B-p-2241.html)|[Get One Now](https://www.seeedstudio.com/Grove-Temperature-Sensor-p-774.html)|


- **Step 2.** Plug the GrovePi_Plus into Raspberry.

- **Step 3.** Connect Grove - Temperature Sensor ranger to **A0** port of GrovePi_Plus.

- **Step 4.** Connect the Raspberry to PC via USB cable.


![](https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/img/connect_pi.jpg)



#### Software

- **Step 1.** Follow [Setting Software](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/setting-software/) to configure the development environment.

- **Step 2.** Follow [Updating the Firmware](https://www.dexterindustries.com/GrovePi/get-started-with-the-grovepi/updating-firmware/) to update the newest firmware of GrovePi.

!!!Tip
    In this wiki we use the path **~/GrovePi/** instead of **/home/pi/Desktop/GrovePi**, you need to make sure Step 2 and Step 3 use the same path.

!!!Note
    We firmly suggest you to update the firmware, or for some sensors you may get errors.


- **Step 3.** Git clone the Github repository.

```
cd ~
git clone https://github.com/DexterInd/GrovePi.git

```

-	**Step 4.** Excute below commands to use the Grove - Temperature Sensor to meansure the temperature.

```
cd ~/GrovePi/Software/Python
sudo python grove_temperature_sensor.py
```

Here is the grove_temperature_sensor.py code.

```python
# NOTE:
# 	The sensor uses a thermistor to detect ambient temperature.
# 	The resistance of a thermistor will increase when the ambient temperature decreases.
#
# 	There are 3 revisions 1.0, 1.1 and 1.2, each using a different model thermistor.
# 	Each thermistor datasheet specifies a unique Nominal B-Constant which is used in the calculation forumla.
#
# 	The second argument in the grovepi.temp() method defines which board version you have connected.
# 	Defaults to '1.0'. eg.
# 		temp = grovepi.temp(sensor)        # B value = 3975
# 		temp = grovepi.temp(sensor,'1.1')  # B value = 4250
# 		temp = grovepi.temp(sensor,'1.2')  # B value = 4250

import time
import grovepi

# Connect the Grove Temperature Sensor to analog port A0
# SIG,NC,VCC,GND
sensor = 0

while True:
    try:
        temp = grovepi.temp(sensor,'1.2')
        print("temp =", temp)
        time.sleep(.5)

    except KeyboardInterrupt:
        break
    except IOError:
        print ("Error")

```

The result should be like:

```python

pi@raspberrypi:~/GrovePi/Software/Python $ sudo python grove_temperature_sensor.py

('temp =', 25.28652137917777)
('temp =', 25.28652137917777)
('temp =', 25.28652137917777)
('temp =', 25.28652137917777)
('temp =', 25.368489566400115)
('temp =', 25.61468397498203)
('temp =', 27.43501590142614)
('temp =', 27.85285590636829)
('temp =', 27.18509952680688)
('temp =', 26.852756540240193)

```



## Reference
---
If you want to know how the algorithm of temperature coming, please refer to the below image:

![](https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/img/Grove_Temperature_Sensor_Basic_Characteristics.jpg)


## Resources
---

- **[Zip]** [Grove - Temperature Sensor v1.1 Eagle File](https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/res/Grove_-_Temperature_sensor_v1.1.zip)
- **[PDF]** [Grove - Temperature Sensor v1.1.PDF](https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/res/Grove_-_Temperature_sensor_v1.1.pdf)
- **[PDF]** [Temperature Sensor datasheet](https://github.com/SeeedDocument/Grove-Temperature_Sensor_V1.2/raw/master/res/NCP18WF104F03RC.pdf)

## Tech Support
Please do not hesitate to contact [techsupport@seeed.cc](techsupport@seeed.cc) if you have any technical issue. Or submit the issue into our [forum](http://seeedstudio.com/forum/).
