# Raspberry-ili9225spi
ILI9225 SPI TFT Library for RaspberryPi/OrangePi.  

This library can show a chart to ILI9225 SPI TFT.   

----

Wirering   

|TFT||Rpi/Opi|
|:-:|:-:|:-:|
|CS|--|Pin#24(SPI CE0)|
|RST|--|Pin#5(*)|
|DC|--|Pin#3(*)|
|SDA|--|Pin#19(SPI MOSI)|
|CLK|--|Pin#23(SPI SCLK)|
|GND|--|GND|
|5V|--|5V|

(*) 
This is default.   
If you want to use other pin, You have to change this.   

```
#define D_C  2  // GPIO2(Pin#3)
#define RST  3  // GPIO3(Pin#5)
```

----

build with bcm2835 library (very fast)   

```
wget http://www.airspayce.com/mikem/bcm2835/bcm2835-1.56.tar.gz
tar zxvf bcm2835-1.56.tar.gz
cd bcm2835-1.56
./configure
make
sudo make check
sudo make install
cd $HOME
```

_\* This tool require 1.56 or later._   
_\* Because this tool uses bcm2835_spi_write._   


```
git clone https://github.com/nopnop2002/Raspberry-ili9225spi
cd Raspberry-ili9225spi
cc -o demo demo.c fontx.c ili9225.c -lbcm2835 -lm -lpthread
sudo ./demo

ColorBarTest elapsed time[ms]=61
ArrowTest elapsed time[ms]=71
LineTest elapsed time[ms]=133
CircleTest elapsed time[ms]=127
RoundRectTest elapsed time[ms]=123
DirectionTest elapsed time[ms]=70
HorizontalTest elapsed time[ms]=101
VerticalTest elapsed time[ms]=99
FillRectTest elapsed time[ms]=129
ColorTest elapsed time[ms]=122
```

----

build with wiringPi library (very slow)   

```
git clone https://github.com/nopnop2002/Raspberry-ili9225spi
cd Raspberry-ili9225spi
cc -o demo demo.c fontx.c ili9225.c -lwiringPi -lm -lpthread -DWPI
sudo ./demo

ColorBarTest elapsed time[ms]=140
ArrowTest elapsed time[ms]=536
LineTest elapsed time[ms]=3157
CircleTest elapsed time[ms]=2764
RoundRectTest elapsed time[ms]=2746
DirectionTest elapsed time[ms]=480
HorizontalTest elapsed time[ms]=1399
VerticalTest elapsed time[ms]=1314
FillRectTest elapsed time[ms]=776
ColorTest elapsed time[ms]=278
```

---

![ili9225-11](https://user-images.githubusercontent.com/6020549/58362412-bfa46f00-7ed1-11e9-9c74-dd56ea798c2c.JPG)
![ili9225-12](https://user-images.githubusercontent.com/6020549/58362413-bfa46f00-7ed1-11e9-93c5-7a6c78b6b2a5.JPG)
![ili9225-13](https://user-images.githubusercontent.com/6020549/58362414-bfa46f00-7ed1-11e9-80a4-e3c8e6f0f901.JPG)
![ili9225-14](https://user-images.githubusercontent.com/6020549/58362415-c03d0580-7ed1-11e9-8506-bc6b8e9b9afd.JPG)
![ili9225-15](https://user-images.githubusercontent.com/6020549/58362416-c03d0580-7ed1-11e9-9f2a-b40fd4ee5776.JPG)
![ili9225-16](https://user-images.githubusercontent.com/6020549/58362417-c03d0580-7ed1-11e9-899d-a61d415d4947.JPG)
![ili9225-17](https://user-images.githubusercontent.com/6020549/58362418-c03d0580-7ed1-11e9-8a0d-fc3342925b06.JPG)
![ili9225-18](https://user-images.githubusercontent.com/6020549/58362419-c0d59c00-7ed1-11e9-8fec-2d5b673a877a.JPG)
![ili9225-19](https://user-images.githubusercontent.com/6020549/58362420-c0d59c00-7ed1-11e9-9b8b-cf3657149c2f.JPG)
![ili9225-20](https://user-images.githubusercontent.com/6020549/58362421-c16e3280-7ed1-11e9-8033-eea28354c9a5.JPG)
![ili9225-21](https://user-images.githubusercontent.com/6020549/58362674-a3ee9800-7ed4-11e9-9a87-2774e6b6dcc8.JPG)

