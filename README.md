SI4713 Configuration Program by ON7LDS
======================================

Find the last version on https://github.com/on7lds/

This program lets you configure a SI4713 FM transmitter chip connected via I²C to your Raspberry Pi

## Wiring
I used the Adafruit Stereo FM Transmitter with RDS/RBDS Breakout (https://www.adafruit.com/product/1958)
wired as follows :
| Pi   | Breakout  |
| ---- | --------- |
|3V3   |     VIN   |
|GND   |     GND   |
|SCL   |     SCL   |
|SDA   |     SDA   |
|GPIO5 |     RST   |

And wire LIN and RIN to some audio (I used the RPi 3.5mm audio out).

## I²C
Activate I²C on your Pi  
This can be a guide : https://learn.adafruit.com/adafruits-raspberry-pi-lesson-4-gpio-setup/configuring-i2c

## WiringPi
Install the wiringPi libraries & headers :


```sh
 $ sudo apt-get install wiringpi
```

## Compile
Then compile the program :

```sh
 $ gcc SI4713config.c -lwiringPi -o  SI4713config
```

## Use
Start transmitting on 91.25Mhz with max. power, no RDS
```sh
 $ ./SI4713config -f 9125 -p 115
```

Use interactive mode :
```sh
 $ ./SI4713config -i
```


Have fun !

