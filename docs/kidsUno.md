# KidsUno STEM Education Development Board

![](img/1.png)

## What is KidsUno?

KidsUno STEM education development board is an open source hardware used to popularize children's programming education. It can easily be used in various programming-related teaching and development scenarios, including intelligent control, robot control, scientific experiments, and wearable device development. It is a good helper for teachers in programming education, and a creative tool for makers and programming enthusiasts.

KidsUno uses an ATmega328P-based processor, which is fully compatible with the Arduino IDE development environment. He has 14 digital input/output pins (6 of which can be used as PWM output), 8 analog inputs (of which A4 and A5 are used as fixed I2C), two servo pin interfaces, a USB interface, and a DC power interface , a power switch and a reset button, and a 128*64 OLED screen on board. Just connect it to your computer with a USB cable, or power it with an external power source to get started.

## KidsUno Specifications

|  microcontroller  | ATmega328P                                                   |
| :---------------: | ------------------------------------------------------------ |
| Operating Voltage | 5V                                                           |
|   Input voltage   | USB power supply: 5V, DC power supply: 6-12V                 |
| electric current  | The maximum output of USB power supply is 400mA, and the maximum output of DC power supply is 1.6A |
|   Maximum power   | 8W                                                           |
| Digital I/O pins  | 14                                                           |
|      PWM I/O      | 6                                                            |
|    Analog I/O     | 8 (A4, A5 as fixed I2C)                                      |
|     I2C pins      | 7                                                            |
|    Servo pins     | 2（D12 D13）                                                 |
|      Onboard      | 0.96 inch OLED                                               |
|  I/O pin current  | 20mA                                                         |
|   flash memory    | 32KB(ATmega328P)0.5KB of which is used by the bootloader     |
|       SRAM        | 2KB(ATmega328P)                                              |
|      EEPROM       | 1KB(ATmega328P)                                              |
|    clock speed    | 16MHZ                                                        |
|      volume       | 87.5x60x20mm                                                 |
|      weight       | 50g                                                          |


## KidsUno pinout

![](img/2.png)

## What can KidsUno do?

KidsUno combines different types of sensors or modules to realize various applications such as STEM teaching, Internet of Things, intelligent control works, DIY creative works, etc.
1. Teaching application: It supports graphics and code programming, which can be used by students at different stages to learn programming;
2. Intelligent control application: It features ultra-high-performance main control, strong expansion ability, which is easy to realize various intelligent control works.
3. Application of DIY creative works: Combine input and output sensors and modules to quickly realize a variety of DIY creative works.

## How to use KidsUno?

### getting started with Arduino IDE

#### Download Arduino IDE

When you get KidsUno, you need to download Arduino IDE and driver firstly.
You could download Arduino IDE from the official website:
https://www.arduino.cc/, click the SOFTWARE on the browse bar to enter download page, as shown below:

![](img/3.png)

There are various versions of IDE for Arduino. Just download a version compatible with your system. Here we will show you how to download and install the windows version of Arduino IDE.

![](img/4.png)

You can choose between the Installer (.exe) and the Zip packages. We suggest you use the first one that installs directly everything you need to use the Arduino Software (IDE), including the drivers. With the Zip package you need to install the drivers manually. The Zip file is also useful if you want to create a portable installation.

![](img/5.png)

You just need to click JUST DOWNLOAD.

#### Installing the driver for Windows system

![](img/6.png)

Download CH340 driver：
<https://sparks.gogo.co.nz/ch340.htm>l
Next, let’s install Arduino driver. 
For different operating system, there may be slight difference in installation method. Below is an example in WIN 7.
When you connect Arduino Uno to your computer the first time, right click “Computer” —> “Properties”—> “Device manager”, you can see “USB2.0-Serial”. 

![](img/7.png)

Click “USB2.0-Serial”, select “Update Driver software”.

![](img/8.png)

In this page, click “Browse my computer for driver software”.

![](img/9.png)

Find the “usb_ch341_3.1.2009.06” file,Click “Next”.

![](img/10.png)

Installation completed; click “Close”. 

![](img/11.png)

After driver is installed, go to “Device manager” again. Right click “Computer” —>  “Properties”—> “Device manager”, you can see CH340 device as below figure shows, also the Com port info.

![](img/12.png)

#### Installing the driver for Windows MAC system

Download CH340 driver：
<https://sparks.gogo.co.nz/ch340.html>

1. Click V1.5 CH340 MaxOS Driver package

![](img/13.png)

![](img/14.png)

2. After the download, you will see below:

![](img/15.png)

3. click installation package and tap Continue.

![](img/16.png)

4. Click Install.

![](img/17.png)

5. Input your user password and click Install Software.

![](img/18.png)

6. Tap Continue Installation.

![](img/19.png)

7. Wait to install.

![](img/20.png)

8. Click Restart after the installation is finished.

![](img/21.png)

#### Arduino IDE Setting

Click![](img/22.png)icon，open Arduino IDE.

![](img/23.png)

To avoid the errors when uploading the program to the board, you need to select the correct Arduino board that matches the board connected to your computer.

Then come back to the Arduino software, you should click Tools→Board, select the board. (as shown below)

![](img/24.png)

Then select the correct COM port (you can see the corresponding COM port after the driver is successfully installed)

![](img/25.png)

Before uploading the program to the board, let’s demonstrate the function of each symbol in the Arduino IDE toolbar.

![](img/26.png)

1- Used to verify whether there is any compiling mistakes or not.
2- Used to upload the sketch to your Arduino board.
3- Used to send the serial data received from board to the serial plottle.
4- Used to send the serial data received from board to the serial monitor.

#### Start First Program

Open the file to select Example, choose BLINK from BASIC, as shown below:

![](img/27.png)

![](img/28.png)

Set board and COM port, the corresponding board and COM port are shown on the lower right of IDE.

![](img/29.png)

Click![](img/30.png)to start compiling the program, check errors.

![](img/31.png)

Click![](img/32.png)to upload the program, upload successfully.

![](img/33.png)

Upload the program successfully, the onboard LED lights on for 1s, lights off for 1s. Congratulation, you have finished the first program.

#### onboard OLED display

##### Installing an OLED Display Library

An OLED LCD display is integrated on the KisUno development board, the SSD1306 controller in the OLED display has flexible but complex drivers. To use the SSD1306 controller, extensive knowledge of memory addressing is required. Fortunately, the [SSD1306 library](https://github.com/adafruit/Adafruit_SSD1306) can be used to hide the complexities of the SSD1306 controller, allowing us to control the display with simple commands.

To install the library, navigate to Sketch > Include Library > Manage Libraries… Wait for the Library Manager to download the library index and update the list of installed libraries.

![](img/34.png)

Filter your search by typing ‘adafruit ssd1306’. There should be a few entries. Look for SSD1306. Click on that entry and then choose Install.

![](img/35.png)

This SSD1306 library is a hardware-specific library for low-level functions. To display graphics primitives such as points, lines, circles, and rectangles, it must be paired with the [Adafruit GFX Library](https://github.com/adafruit/Adafruit-GFX-Library). Install this library as well.

![](img/36.png)

Internally, the SSD1306 library makes use of the [Adafruit Bus IO Library](https://github.com/adafruit/Adafruit_BusIO). So, look for Adafruit BusIO in the library manager and install it as well.

![](img/37.png)

##### OLED Basic Drawings

![](img/38.png)

Here’s a simple code that will do the following:

```c++
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128 // OLED display width, in pixels
#define SCREEN_HEIGHT 64 // OLED display height, in pixels

// Declaration for SSD1306 display connected using I2C
#define OLED_RESET     -1 // Reset pin # (or -1 if sharing Arduino reset pin)
#define SCREEN_ADDRESS 0x3C
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);


void setup()
{
  Serial.begin(9600);
  
  // initialize the OLED object
  if(!display.begin(SSD1306_SWITCHCAPVCC, SCREEN_ADDRESS)) {
    Serial.println(F("SSD1306 allocation failed"));
    for(;;); // Don't proceed, loop forever
  }

  // Uncomment this if you are using SPI
  //if(!display.begin(SSD1306_SWITCHCAPVCC)) {
  //  Serial.println(F("SSD1306 allocation failed"));
  //  for(;;); // Don't proceed, loop forever
  //}

  // Clear the buffer.
  display.clearDisplay();

  // Draw Rectangle
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.println("Rectangle");
  display.drawRect(0, 15, 60, 40, WHITE);
  display.display();
  delay(2000);
  display.clearDisplay();

  // Draw Filled Rectangle
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.println("Filled Rectangle");
  display.fillRect(0, 15, 60, 40, WHITE);
  display.display();
  delay(2000);
  display.clearDisplay();

  // Draw Round Rectangle
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.println("Round Rectangle");
  display.drawRoundRect(0, 15, 60, 40, 8, WHITE);
  display.display();
  delay(2000);
  display.clearDisplay();

  // Draw Filled Round Rectangle
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.println("Filled Round Rectangl");
  display.fillRoundRect(0, 15, 60, 40, 8, WHITE);
  display.display();
  delay(2000);
  display.clearDisplay();

  // Draw Circle
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.println("Circle");
  display.drawCircle(20, 35, 20, WHITE);
  display.display();
  delay(2000);
  display.clearDisplay();

  // Draw Filled Circle
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.println("Filled Circle");
  display.fillCircle(20, 35, 20, WHITE);
  display.display();
  delay(2000);
  display.clearDisplay();

  // Draw Triangle
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.println("Triangle");
  display.drawTriangle(30, 15, 0, 60, 60, 60, WHITE);
  display.display();
  delay(2000);
  display.clearDisplay();

  // Draw Filled Triangle
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.println("Filled Triangle");
  display.fillTriangle(30, 15, 0, 60, 60, 60, WHITE);
  display.display();
  delay(2000);
  display.clearDisplay();
}

void loop() {
}
```

##### OLED Displays Text

![](img/39.png)

```c++
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128 // OLED display width, in pixels
#define SCREEN_HEIGHT 64 // OLED display height, in pixels
// Declaration for SSD1306 display connected using I2C
#define OLED_RESET     -1 // Reset pin # (or -1 if sharing Arduino reset pin)
#define SCREEN_ADDRESS 0x3C
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);
void setup()
{
  Serial.begin(9600);
  
  // initialize the OLED object
  if(!display.begin(SSD1306_SWITCHCAPVCC, SCREEN_ADDRESS)) {
    Serial.println(F("SSD1306 allocation failed"));
    for(;;); // Don't proceed, loop forever
  }
  // Clear the buffer.
  display.clearDisplay();

  // Display Text
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,28);
  display.println("Hello world!");
  display.display();
  delay(2000);
  display.clearDisplay();

  // Display Inverted Text
  display.setTextColor(BLACK, WHITE); // 'inverted' text
  display.setCursor(0,28);
  display.println("Hello world!");
  display.display();
  delay(2000);
  display.clearDisplay();

  // Changing Font Size
  display.setTextColor(WHITE);
  display.setCursor(0,24);
  display.setTextSize(2);
  display.println("Hello!");
  display.display();
  delay(2000);
  display.clearDisplay();

  // Display Numbers
  display.setTextSize(1);
  display.setCursor(0,28);
  display.println(123456789);
  display.display();
  delay(2000);
  display.clearDisplay();

  // Specifying Base For Numbers
  display.setCursor(0,28);
  display.print("0x"); display.print(0xFF, HEX); 
  display.print("(HEX) = ");
  display.print(0xFF, DEC);
  display.println("(DEC)"); 
  display.display();
  delay(2000);
  display.clearDisplay();

  // Display ASCII Characters
  display.setCursor(0,24);
  display.setTextSize(2);
  display.write(3);
  display.display();
  delay(2000);
  display.clearDisplay();

  // Scroll full screen
  display.setCursor(0,0);
  display.setTextSize(1);
  display.println("Full");
  display.println("screen");
  display.println("scrolling!");
  display.display();
  display.startscrollright(0x00, 0x07);
  delay(2000);
  display.stopscroll();
  delay(1000);
  display.startscrollleft(0x00, 0x07);
  delay(2000);
  display.stopscroll();
  delay(1000);    
  display.startscrolldiagright(0x00, 0x07);
  delay(2000);
  display.startscrolldiagleft(0x00, 0x07);
  delay(2000);
  display.stopscroll();
  display.clearDisplay();

  // Scroll part of the screen
  display.setCursor(0,0);
  display.setTextSize(1);
  display.println("Scroll");
  display.println("some part");
  display.println("of the screen.");
  display.display();
  display.startscrollright(0x00, 0x00);
}
void loop() {
}
```


##### OLED Displays Bitmap

![](img/40.png)

```c++
#include <SPI.h>
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128 // OLED display width, in pixels
#define SCREEN_HEIGHT 64 // OLED display height, in pixels
// Declaration for SSD1306 display connected using I2C
#define OLED_RESET     -1 // Reset pin # (or -1 if sharing Arduino reset pin)
#define SCREEN_ADDRESS 0x3C
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);
// Declaration for SSD1306 display connected using software SPI://#define OLED_MOSI   9//#define OLED_CLK   10//#define OLED_DC    11//#define OLED_CS    12//#define OLED_RESET 13//Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, OLED_MOSI, OLED_CLK, OLED_DC, OLED_RESET, OLED_CS);
// Bitmap of MarilynMonroe Image
const unsigned char MarilynMonroe [] PROGMEM = {
  0xff, 0xff, 0xff, 0xff, 0xff, 0xf8, 0x1f, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xff, 0xc0, 0x1f, 0xff, 0xff, 0xf0, 0x41, 0xff, 0xff, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xff, 0x80, 0x7f, 0xff, 0xff, 0xf8, 0x03, 0xff, 0xff, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xff, 0xf9, 0xff, 0xff, 0xff, 0xe0, 0x07, 0xff, 0xff, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xff, 0x87, 0xff, 0xff, 0xff, 0xf8, 0x03, 0xff, 0xff, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xff, 0x07, 0xff, 0xff, 0xff, 0xf8, 0x01, 0xf1, 0xff, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xff, 0x9f, 0xff, 0xff, 0xff, 0xf8, 0x00, 0xf8, 0xff, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xff, 0xbf, 0xff, 0xff, 0xff, 0xfc, 0x02, 0x78, 0x7f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xff, 0xfc, 0x3f, 0xff, 0xff, 0xfe, 0x03, 0x7c, 0x1f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xff, 0xf0, 0x07, 0xff, 0xff, 0xfe, 0x01, 0xfe, 0x1f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xfd, 0xe0, 0x03, 0xff, 0xff, 0xfc, 0x00, 0xfe, 0x0f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xfe, 0x87, 0xe0, 0xff, 0xff, 0xfc, 0x00, 0x06, 0x07, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xfc, 0x1f, 0xf9, 0xff, 0xff, 0xfc, 0x00, 0x02, 0x07, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xf8, 0x1f, 0xff, 0xff, 0xff, 0xfc, 0x00, 0xc3, 0xc3, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xf0, 0x3f, 0xff, 0xff, 0xe0, 0x0c, 0x00, 0xe7, 0x81, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xf0, 0x0f, 0xff, 0xff, 0xe0, 0x02, 0x00, 0x02, 0x00, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xf0, 0x0f, 0xff, 0xff, 0xe0, 0x01, 0x00, 0x00, 0x00, 0x3f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0x80, 0x00, 0x3f, 0xff, 0xff, 0xe0, 0x00, 0x00, 0x1e, 0x3f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xfc, 0x00, 0x00, 0x0f, 0xff, 0x3f, 0xf8, 0x00, 0x18, 0x7f, 0x1f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xf8, 0x01, 0x80, 0x03, 0xfc, 0x3f, 0xfc, 0x00, 0x70, 0xfe, 0x1f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xf0, 0x43, 0xff, 0xff, 0xf8, 0x7f, 0xf8, 0x00, 0x00, 0x7e, 0x1f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xe0, 0x07, 0xff, 0xff, 0xf0, 0xff, 0xfc, 0x00, 0x00, 0x7c, 0x3f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xe0, 0x0f, 0xff, 0xff, 0xf1, 0xef, 0xf8, 0x00, 0x01, 0xfc, 0x3f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xe4, 0xff, 0xff, 0xff, 0xf3, 0x80, 0xa0, 0x00, 0x07, 0xfc, 0xaf, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xec, 0x5f, 0xff, 0xff, 0xe7, 0xf0, 0x00, 0x00, 0x03, 0xfe, 0xdf, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xee, 0x7f, 0xff, 0xff, 0xc7, 0xf8, 0x00, 0x00, 0x03, 0xff, 0xdf, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xfe, 0x7f, 0xff, 0xf7, 0xc7, 0xff, 0x06, 0x00, 0x03, 0xff, 0xbf, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xfe, 0x5f, 0xff, 0xc7, 0x07, 0xff, 0x80, 0x00, 0x07, 0xdb, 0xbf, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xee, 0xff, 0xff, 0x80, 0x03, 0xff, 0xc0, 0x00, 0x03, 0xc3, 0x0f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xfe, 0xff, 0xff, 0x98, 0x03, 0xff, 0xf8, 0x00, 0x07, 0xe0, 0x0f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xef, 0xff, 0xff, 0xf8, 0x01, 0xff, 0xfc, 0x01, 0x07, 0xfc, 0x1f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xcf, 0xef, 0xff, 0xff, 0xe1, 0xff, 0xfc, 0x01, 0x07, 0xf8, 0x1f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x9f, 0xff, 0xff, 0x7f, 0xf1, 0xff, 0xf8, 0x02, 0x07, 0x88, 0x3f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xcf, 0xef, 0xf8, 0x0f, 0xff, 0xff, 0xe0, 0x00, 0x07, 0x84, 0x3f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xe7, 0xef, 0xf0, 0x04, 0x7f, 0xff, 0xc0, 0x00, 0x07, 0x84, 0x7f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x3f, 0xff, 0xe0, 0x00, 0x1f, 0xff, 0x80, 0x00, 0x06, 0x04, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x3f, 0x7f, 0xe1, 0xf0, 0x07, 0xff, 0x80, 0x00, 0x07, 0x06, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0xff, 0xc3, 0xfe, 0x03, 0xff, 0x00, 0x00, 0x03, 0x80, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xf2, 0x3f, 0xc6, 0x7f, 0x81, 0xce, 0x00, 0x00, 0x01, 0xc1, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xe0, 0x3f, 0xc0, 0x07, 0xc1, 0xfe, 0x00, 0x00, 0x0d, 0xc0, 0x7f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xe0, 0x3f, 0xc0, 0x01, 0xe0, 0xfc, 0x00, 0x00, 0x0f, 0xc0, 0x7f, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xc0, 0x3f, 0xc0, 0x00, 0x50, 0xfc, 0x00, 0x00, 0x0e, 0xc0, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xc0, 0x3f, 0xc0, 0x00, 0x18, 0xf8, 0x00, 0x00, 0x0e, 0xc1, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xc0, 0x3f, 0xc0, 0x00, 0x00, 0xf8, 0x00, 0x00, 0x66, 0x81, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xc0, 0x1f, 0xc7, 0x80, 0x00, 0xf8, 0x00, 0x01, 0xe0, 0x00, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xc0, 0x1f, 0xc1, 0xe0, 0x01, 0xf8, 0x00, 0x03, 0xf0, 0x01, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x80, 0x1f, 0xc0, 0x3e, 0x03, 0xf0, 0x00, 0x00, 0xe0, 0x03, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x00, 0x1f, 0xe0, 0xe0, 0x03, 0xf2, 0x00, 0x00, 0xc0, 0x03, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x80, 0x1f, 0xf0, 0x00, 0x07, 0xe6, 0x00, 0x00, 0xc0, 0x03, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x80, 0x1f, 0xff, 0x00, 0x1f, 0xee, 0x00, 0x00, 0x80, 0x07, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xb8, 0x0f, 0xff, 0xf0, 0x3f, 0xdc, 0x00, 0x00, 0x00, 0x0f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xbc, 0x0f, 0xff, 0xff, 0xff, 0xdc, 0x00, 0x00, 0x00, 0x0f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x9e, 0x0f, 0xff, 0xff, 0xff, 0xf8, 0x00, 0x00, 0x00, 0x1f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x08, 0x0f, 0xff, 0xff, 0xff, 0x70, 0x00, 0x00, 0x00, 0x1f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x00, 0x0b, 0xff, 0xff, 0xfe, 0xe0, 0x00, 0x00, 0x00, 0x1f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x00, 0x0b, 0xff, 0xff, 0xf9, 0xc0, 0x00, 0x00, 0x00, 0x3f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x3c, 0x09, 0xff, 0xff, 0xf1, 0x80, 0x00, 0x00, 0x00, 0x7f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x1e, 0x08, 0x3f, 0xff, 0xc0, 0x00, 0x00, 0x00, 0x00, 0x7f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x1f, 0x08, 0x03, 0xff, 0x00, 0x00, 0x00, 0x00, 0x00, 0x7f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x00, 0x08, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x1f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0x80, 0x1c, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x1f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xce, 0x1c, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x1f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xfe, 0x1c, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x3f, 0xff, 0xff, 0xff, 
  0xff, 0xff, 0xff, 0xff, 0x7e, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x7f, 0xff, 0xff, 0xff
};
void setup()
{
  Serial.begin(9600);
  
  // initialize the OLED object
  if(!display.begin(SSD1306_SWITCHCAPVCC, SCREEN_ADDRESS)) {
    Serial.println(F("SSD1306 allocation failed"));
    for(;;); // Don't proceed, loop forever
  }

  // Uncomment this if you are using SPI
  //if(!display.begin(SSD1306_SWITCHCAPVCC)) {
  //  Serial.println(F("SSD1306 allocation failed"));
  //  for(;;); // Don't proceed, loop forever
  //}

  // Clear the buffer.
  display.clearDisplay();

  // Display bitmap
  display.drawBitmap(0, 0,  MarilynMonroe, 128, 64, WHITE);
  display.display();

  // Invert Display
  //display.invertDisplay(1);
}
void loop() {
}
```



### Getting started with kidsblock
#### Download kidblock

Download the KidsBlock software

Download Link:

Windows: <https://www.kidsblock.cn/Down/KidsBlock.exe>

MacOS: <https://www.kidsblock.cn/Down/KidsBlock-MACOS.dmg>


Note: We take the Windows system as an example. 

#### kidblock Setting

1. Double click“KidsBlock Setup.exe”![](img/41.png)
2. Tap“Anyone who uses this computer(all users)”，then click“Next”

![](img/42.png)

3. Click“Browse...”and choose the Disk where the software will be placed (here, we choose C Drive). Then click“Install”.

![](img/43.png)

![](img/44.png)

4. After a few seconds, the installation is complete.Click "Finish" to open the installed Kidsblock software.

![](img/45.png)

5. If the computer security alert window appears, click “Allow access”, then we can open the Kidsblock. 

![](img/46.png)

6.Click Check update under![](img/47.png)to update the software to the latest version

![](img/48.png)

#### Start First Program

After installing the Kidsblock software, let's start writing the first code. First, select the KidUno development board in the hardware selection.

![](img/49.png)

![](img/50.png)

Click Connect to connect the hardware, then return to the code editor.

![](img/51.png)

![](img/52.png)

Click Upload in the upper right corner to switch to upload mode.

![](img/53.png)

![](img/54.png)

![](img/55.png)

![](img/56.png)

#### OLED display

1. OLED Basic Drawings

OLED can be used to draw various basic geometric figures, such as lines, circles, rectangles, triangles and ellipses, etc. We can use Kidsblock graphical programming software to make OLED display different graphics.

![](img/57.png)

2. OLED Displays Text

OLED uses thin-film materials and tiny electronic components to produce high-resolution displays and can also be used to display text. OLEDs are more energy efficient than LCD displays, with faster response times, they can transmit more information and are available over a wider field of view. We can use the Kidsblock to make OLED display different text.

![](img/58.png)

3. OLED Displays Bitmap

OLED displays can display images, which are usually in white or black. To display an image, the color of the image must be determined first, then the pixel values in the image are converted to monochrome pixel values, and finally become a bitmap on the OLED monochrome display. In addition, the viewing angle of the OLED screen is also very large, the horizontal and vertical viewing angles both reach 180 degrees, and the screen content can be viewed from different angles. We can use the Kidsblock to make OLED display different images.

![](img/59.png)