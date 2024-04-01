# ESP32-Web-Server

Step -1: Gather the material from the IoT kit:
● 1 x ESP32
● 1 x USB Cable
● 1 x Breadboard
● 6 x Jumper wires
● 1 x Buzzer
● 1 x LED

Step -2: Let’s do connections:
● Supply negative(GND (-ve)) from the ESP 32 to the breadboard negative terminal.
● Insert buzzer and LED into the breadboard
● Connect the resistor’s one terminal with a longer leg of the LED and the other end of the resistor with ESP32 GPIO pin numbers D2
● Connect the second resistor’s one terminal with a longer leg of the buzzer. And the other end of the resistor with ESP32 GPIO pin numbers D15
● Connect the short leg of LED and Buzzer with GND(0V) supply.

Step-3 Let’s write a code:
The first and most important thing while creating a web server is to include web server libraries.
Using the WiFi library, the device will be able to answer an HTTP request with your WiFI credentials.
After opening a web browser and navigating to your WiFi IP address, the board will respond with HTML content along it will display the input values from the ESP32 board. include keyword is used to import libraries in embedded language as we used to import in python language
● WiFi library: WiFi library will be able to answer all HTTP request
● WiFiClient: WiFiClient client helps to connect to a specified internet IP address and port.
● WebServer library will help to create a web server
● ESPmDNS enabled DNS(Domain Name System) on ESP32

After uploading libraries the next step is to connect with ESP32 with the WiFi. For that, we need to use SSID(Wi-Fi credentials i.e WiFi name and WiFi Password)
● Constant char is a variable that is used to save WiFi credentials. Set the SSID and password

Note: Teacher/Student should use their actual WIFi Credentials.

● Load the HTML design string, This string will take the actual design of the HTML page so use all content of HTML in one string.
● Set webServer port number to 80
● void handleroot() function monitors the presence of a webpage request and delivers the requested webpage.
● In response to an accepted request, server. send will send a success message
● 200 means the request is ok, usually, this will be the standard practice for sending messages for successful web pages

In case the HTTP request fails, the handleNotFound() function comes into play.
● string message is a variable along with datatype string which will save the message “File Not Found”.
● /n represents new line
● 192,178.0.1 will be the local address to access the server.
● The server will try to make the success request using get() and post() method
● 404 means the requested page could not be found but may be available again in the future.

As we have set up a server, now the next thing is to define the GPIO pins
● define GPIO pin along with data type int for LED_1 D2
● define GPIO pin along with data type int for Buzzer D15

Initialize using void setup() function
● PinMode() configures the specified pin to behave either as an input or an output. As we want to act this LED & Buzzer pin as output we will use OUTPUT here.
● Serial. begin(115200) is used to measure the speed of data exchange. This tells the Arduino to get ready to exchange messages with the Serial Monitor at a data rate of 9600 bits per second. That's 9600 binary ones or zeros per second and is commonly called a baud rate.



To make your Buzzer and LED on
Step -1:Gather the material from the IoT kit:
● 1 x ESP32
● 1 x USB Cable
● 1 x Breadboard
● 4 x Jumper wires
● 1 x Potentiometer
● 1 x Rotary Potentiometer

Step -2: Let’s do connections:
● Supply positive (VCC (+ve)) from the ESP 32 to the breadboard positive terminal.
● Supply negative(GND (-ve)) from the ESP 32 to breadboard negative terminal
● Take the DHT11 sensor (female jumper wires are already connected with DHT11)
● Take three male jumper wires to insert into DHT11 female jumper wires.
● Connect VCC (+ve) of DHT11 with VCC (+ve) of the breadboard
● Connect GND(-ve) of DHT11 with GND(-ve) of the breadboard
● Connect data/output pin of DHT11 with D15 of the ESP32

Step-3 Let’s write a code:
Define Pins
● define DHTPIN 15
● define DHTPIN DHT11

Initialize the setup()
● Serial. begin(9600) is used for data exchange speed. This tells the Arduino to get ready to exchange messages with the Serial Monitor at a data rate of 9600 bits per second. That's 9600 binary ones or zeros per second and is commonly called a baud rate.
● Serial.printIn is used to print data. Print (“DHT11 sensor!”)
● dht.begin() is used to begin the process

To execute the main process write the void loop()
● server.on will on the room bell i.e Buzzer
● server.send send success message on web page
● As soon as request message got success, It will make the Buzzer High using digitalWrite() function
● Repeat the same process to make Buzzer LOW using digitalWrite()
● If there is any error then the handlenotfound() function will call.

Now, it's time to write the code for the LED
● server.begin() will start the server.
● Serial.println is used to print (“HTTP server started”)
● Make the LED_1 LOW/HIGH using digitalWrite() function

Call the main function
● Call the main function server.handleClient()

Output:
Compile and upload the program to ESP32 board using Arduino IDE
● Verify the program by clicking the tick option
● Upload the program by clicking the arrow option

Note: If the port is not selected, insert the USB cable in Computer’s port and select the port
● Go to Tools and select Serial Monitor
● Select baud rate at 115200 as shown in screenshot
● Reset the ESP32 by pressing the EN button. The ESP32 connects to Wi-Fi and displays its IP address on the Serial Monitor. Copy that IP address, open the browser, paste the ESP32 IP address
Copy the address and paste it on the browser
● Following window will open
● Control your LED & Buzzer On and Off using a web server.
