# IoT-Project-using-ESP32-NodeMCU-network-with-Blynk
In this IoT tutorial, I have shown how to make the IoT Project using ESP32 NodeMCU ESP8266 network with Blynk App. With this IoT based home automation project, you can control multiple NodeMCU and ESP32 from a single Blynk cloud account. If the internet is not available, then you can control the home appliances from manual switches. During the article, I have shown all the steps to make this smart home system.

## This complete Home Automation system has the following features:
1. Connect multiple ESP32 and NodeMCUs with the same Blynk account (FREE plan).
2. Control home appliances with WiFi(Blynk App).
3. Control home appliances with manual switches.
4. Monitor real-time feedback in the Blynk App.
5. Control home appliances manually without internet.
6.You can connect any number of microcontrollers in this IoT network as per the requirements.

For each room, you just need a relay module & a microcontroller like ESP32 or NodeMCU to make this smart home project.

So if you follow all the steps, you can easily make this IoT project just by using ESP32 or NodeMCU and relay module. Or you can also use a custom-designed PCB for this project.

Although the PCB is not mandatory, I have used PCB to make the circuit compact and give the project a professional look.

## Required components for the ESP32 control 4 Relays PCB
1. ESP32 DEVKIT V1
2. Relays 5v (SPDT) (4 no)
3. BC547 Transistors (4 no)
4. PC817 Optocuplors (4 no)
5. 510-ohm 0.25-watt Resistor (4 no) (R1 - R4)
6. 1k 0.25-watt Resistors (6 no) (R5 - R10)
7. 10k 0.25-watt Resistor (1 no) (R11)
8. LED 5-mm (6 no)1N4007 Diodes (4 no) (D1 - D4)
9. Push Buttons (4 no)
10. Terminal Connectors
11. Jumpper (2 no)

## Required components for the NodeMCU control 4 Relays PCB
1. NodeMCU ESP8266
2. Relays 5v (SPDT) (4 no)
3. BC547 Transistors (4 no)
4. PC817 Optocuplors (4 no)
5. 510-ohm 0.25-watt Resistor (4 no) (R1 - R4)
6. 1k 0.25-watt Resistors (5 no) (R5 - R9)
7. LED 5-mm (5 no)
8. 1N4007 Diodes (5 no) (D1 - D5)
9. Push Buttons (4 no)
10. Terminal Connectors
11. Jumpper (2 no)

## Multiple ESP32 NodeMCU ESP8266 Network
Now if you have multiple rooms, then you can use either ESP32 or NodeMCU for each room and then repeat the same circuit for each room.

If you use ESP32 then you can use either a 4-channel or 8-channel relay module, but for the NodeMCU you have to use the 4-channel relay module.

There is no limitation on the number of ESP32 or NodeMCUs that can be connected. All microcontrollers will connect to the Blynk server using the same Authenticate Token.

So we can control each NodeMCU or ESP32 independently from the Blynk IoT App.

## Circuit Diagram of the ESP32 Control Relays
The circuit is very simple, I have used the GPIO pins D23, D22, D21 & D19 to control the 4 relays.

And the GPIO pins D13, D12, D14 & D27 are connected with switches to control the 4 relays manually.

I have used the INPUT_PULLUP function in Arduino IDE instead of using the pull-up resistors.

I have used a 5V mobile charger to supply the smart relay module.

If you use the momentary pushbutton then just connect the pushbutton across the GPIO pins and GND instead of switches.

Please take proper safety precautions while working with high voltage.

## Circuit Diagram of the NodeMCU Control Relays
For the NodeMCU, I have used the GPIO pins D1, D2, D5 & D6 to control the 4 relays. And the GPIO pins SD3, D3, D7 & RX are connected with push buttons to control the 4 relays manually.

I have used the INPUT_PULLUP function in Arduino IDE instead of using the pull-up resistors.

I have used a 5V mobile charger to supply the smart relay module.

The D3 pin should not be connected with GND during the booting process of NodeMCU.

If you use latched switch then just connect the switches across the GPIO pins and GND instead of pushbuttons.

## Create New Template for ESP32 in Blynk Cloud
For this smart house project, I have used the Blynk IoT Cloud Free plan. Click on the following link to create a Blynk Cloud account.

https://blynk.cloud/dashboard/register

Steps to Create New Template in Blynk IoT

1. Click on New Template.
2. Enter a template name, select the hardware as ESP8266, and the connection type will be WiFi.
3. Then click on DONE.
You will get the BLYNK_TEMPLATE_ID and BLYNK_DEVICE_NAME after creating the temple.

**Although, I have selected ESP32 for creating the Template but you can also use this Template for ESP8266, as I will use Virtual Pins for the Datastreams.

##Create Datastreams in Blynk Cloud
After that, you have to create Datastreams. Here I will control 8 relays, so I have created 8 Datastreams to control 8 relays.
You have to create the Datastreams according to the number of relays you want to control.
Steps to Create Datastreams:
1. Go to the Datastreams tab.
2. Click on New Datastream and select Virtual Pin.
3. Enter a name, select the virtual pin V1, and the datatype will be Integer. MIN value is "0" & MAX value is "1".
4. Then click on Create.
5. For the Feedback create the last Datastram with virtual pin V5, and datatype will be String.
Then click on Create.
6.In a similar way, create the next datastreams with virtual pin V2, V3, V4, V5, V6, V7, and V8.

## Set Up Blynk Cloud Web Dashboard
Steps to configure the Web Dashboard to control 8 relays from Blynk Cloud Dashboard
1. Go to the Web dashboard tab.
2. Drag and drop Switch widgets according to the number of relays.
3. Go to the settings of each widget, and select a Datastream.
4.Click on Save.

Then again click on "Save" to save the Template.

## Add Device Using Template in Blynk IoT##
Steps to add a device in Blynk IoT cloud:
1. First, go to Device, then click on "New Device".
2. Click on "From template".
3. Select the Template, and give the device name.
4. Click on Create.
Then in the device info tab, you will get the Blynk Auth Token, Template ID, and Device Name. All these details will be required in the code.

## PCBs Used for This IoT Project
To make the circuit compact and give a professional look, I have designed PCBs for the ESP32 and NodeMCU control relays circuit.

You can download the PCB Gerber file of this Lora project from the following link:

Download PCB Gerber File: https://github.com/techstudycell/IoT-Project-using-ESP32-NodeMCU-network-with-Blynk/tree/main/PCB_Gerber

## Order the PCB from JLCPCB
After downloading the Garber file you can easily order the PCB.
1. Visit https://jlcpcb.com/RAB and Sign in / Sign up.
2. Click on the QUOTE NOW button.
3. Click on the "Add your Gerber file" button. Then browse and select the Gerber file you have downloaded.
4. Set the required parameter like Quantity, PCB masking color, etc.
5. After selecting all the Parameters for PCB click on SAVE TO CART button.
6. Type the Shipping Address.
7. Select the Shipping Method suitable for you.
8. Submit the order and proceed with the payment.
9. You can also track your order from the JLCPCB

My PCBs took 2 days to get manufactured and arrived within a week using the DHL delivery option.
PCBs were well packed and the quality was really good at this affordable price.

## Solder All the Components on PCB
After that, I have soldered all the components as per the circuit diagram.

Then connect the ESP32 or NodeMCU with the PCB.

## Codes for This IoT Project Using ESP32 and ESP8266

Download the source codes: https://github.com/techstudycell/IoT-Project-using-ESP32-NodeMCU-network-with-Blynk/tree/main/Code

In the Tutorial video, I have explained all the steps to program the NodeMCU and ESP32 using Arduino IDE.

Before uploading the code you have to install the following boards in Arduino IDE
1. ESP8266 Board
2. ESP32 Board

Then install the following libraries
1.  Blynk Library
2. AceButton Library

I have mentioned all the download links in the code.
1. In the code, enter the Blynk Auth Token, Template ID, and Device Name
2. Then enter the WiFi Name and Password.

For each NodeMCU or ESP32, you have to change the virtual pins in the code. For the ESP32, virtual pins will be V1, V2, V3, V4. And for the NodeMCU, virtual pins will be V5, V6, V7, V8.

To program NodeMCU select the “NodeMCU 1.0 ESP-12E” board and proper PORT. Then click on the upload button.

To program ESP32, select the “DOIT ESP32 DEVKIT V1” board and proper PORT. Then click on the upload button.

And while programming, please don't connect both microcontrollers with the laptop at the same time.

## Set Up Blynk IoT App Mobile Dashboard
Install the Blynk IoT app from Google Play Store or App Store. Then log in and Tap on Developer Mode. Select the template that you have already made Then go to the Widget box (on the right) to add widgets.

Steps to set up Blynk IoT app Mobile Dashboard: 
1. Add 8 Button widgets from Widget Box.
2. Go to Button widget settings.
3. Enter the name, select Datastream, Mode will be SWITCH.
4. After configuring all the widgets tap on exit.
If the NodeMCU or ESP32 is connected with WiFi the BLUE LED (Built-in) will turn ON.

Please watch the complete tutorial video for more details.

## Control the Appliances With Blynk IoT
If the NodeMCU or ESP32 is connected with WiFi, then you can control the home appliances from Blynk IoT App.

You also use multiple smartphones to control the appliances with Blynk IoT App. For that, you have to log in same Blynk account from all the smartphones. In this way, all smartphones will be sink to the Blynk server.

You can control, monitor the real-time status of the relays from anywhere in the world with the Blynk IoT App.

## Controlling Relays Without WiFi
If the WiFi is not available, you can control the relays from the switches or pushbuttons.

The NodeMCU or ESP32 will check for the WiFi after every 2 seconds. When the WiFi is available, the ESP32 or NodeMCU will automatically connect with the WiFi.

I hope you have liked this home automation project. I have shared all the required information for this project.

I will really appreciate it if you share your valuable feedback. Also if you have any queries please write in the comment section.

Thank you & Happy Learning.
