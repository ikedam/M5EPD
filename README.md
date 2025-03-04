# M5Paper Library

## About this fork

This is a fork of [M5EPD](https://github.com/m5stack/M5EPD).
The purpose of this fork is to clear the license issue of M5EPD. See [m5stack/M5EPD#21](https://github.com/m5stack/M5EPD/issues/21) for more details about the license issue.

This repository does following modifications to the original M5EPD:

* Reimplement some features from scratch.
    * SHT3x (was under GNU GENERAL PUBLIC LICENSE Version 3)
    * Button (was under Creative Commons Attribution-ShareAlike 3.0 Unported License)
* Remove some features.
    * CommUtil (was under GNU Lesser General Public License v2.1)
    * M5Timer (was under GNU Lesser General Public License v2.1 or later)
* Update the [LICENSE](LICENSE) file to include all license notices for codes in this repository.
    * Please let me know appropriate format for such license notices!
    * Please let me know if this library contains codes with licenses not written here.
    * This repository contains following codes derived from other projects:
        * codes from FreeType, under FreeType license:
            * src/base
            * src/freetype
            * src/ft2build.h
            * src/sfnt
            * src/smooth
            * src/truetype
        * codes under MIT / BSD / FreeBSD license:
            * TFT_eSPI, Sprite, src/Fonts
                * Supposed to come from https://github.com/Bodmer/TFT_eSPI
        * 3-clause BSD license:
            * Tom Thumb 3x5 font
                * See https://github.com/adafruit/Adafruit-GFX-Library/pull/75 for details.
        * codes under MIT license:
            * M5EPD_Canvas
                * Supposed to come from https://github.com/espressif/WROVER_KIT_LCD
            * pngle from https://github.com/kikuchan/pngle
            * qrcode from https://github.com/ricmoo/QRCode
            * SHT3x, Button
                * Contributed in this repository.

![M5Paper_Pic_01](https://m5stack.oss-cn-shenzhen.aliyuncs.com/image/product_jpg/assets/img/product_pics/core/m5paper/m5paper_01.jpg)

## Description

**M5Paper** is M5Stacks latest core device with a touch enabled E-ink display. Powered by the ESP32-D0WDQ6-V3 this is our first device to integrate a super sized 540*960 @4.7" E-ink display，which supports 16 grayscale levels. The display is a GT911 capacitive touch screen，which supports two point touch and a variety of gesture controls . Compared to a regular LCD，E-ink displays are easier on the eyes, which makes them a great choice for reading or viewing for longer periods. Other benefits are the low power consumption and the ability to retain the image even if power to the display is terminated. Integrated in the CoreInk are an multi-function button for operation, SHT30 temperature and moisture sensor, physical buttons and an TF card port for data storage.

Additionally the FM24C02 internal eeprom chip(256KB-EEPROM)can be used to store vital data even when the device is off. A 1150mAh lipo battery keeps the device going for long periods and battery life can be further preserved by using the RTC(BM8563)to set the device into deep sleep and wake it up again when needed。Three HY2.0-4P expansion ports are included which allow for building complex projects using the existing sensors in the M5Stack ecosystem.

?>Warning: Do not expose to ultraviolet rays for a long time, otherwise it may cause irreversible damage to the ink screen.

## PinMap

**E-INK & TF Card**

Resolution：540*960
 
<table>
 <tr><td>ESP32 Chip</td><td>GPIO13</td><td>GPIO12</td><td>GPIO14</td><td>GPIO15</td><td>GPIO4</td></tr>
 <tr><td>IT8951</td><td>MISO</td><td>MOSI</td><td>SCK</td><td>CS</td><td>/</td></tr>
 <tr><td>TF Card</td><td>MISO</td><td>MOSI</td><td>SCK</td><td>/</td><td>CS</td></tr>
</table>


**Multi-function button**

<table>
 <tr><td>ESP32 Chip</td><td>GPIO37</td><td>GPIO38</td><td>GPIO39</td></tr>
 <tr><td>Multi-function button</td><td>Right</td><td>BTN/PWR</td><td>Left</td></tr>
</table>


**Internal I2C Connection**

<table>
 <tr><td>ESP32 Chip</td><td>GPIO21</td><td>GPIO22</td><td>GPIO36</td></tr>
 <tr><td>GT911</td><td>SDA</td><td>SCL</td><td>INT</td></tr>
 <tr><td>SHT30</td><td>SDA</td><td>SCL</td><td>/</td></tr>
 <tr><td>BM8563</td><td>SDA</td><td>SCL</td><td>/</td></tr>
 <tr><td>FM24C02</td><td>SDA</td><td>SCL</td><td>/</td></tr>
</table>

**USB Serial**

<table>
 <tr><td>ESP32 Chip</td><td>GPIO1</td><td>GPIO3</td></tr>
 <tr><td>CP2104</td><td>RXD</td><td>TXD</td></tr>
</table>

## M5Paper-HY2.0 4P Port

<table>
      <thead>
         <th>PORT</th>
         <th>PIN</th>
         <th>Protocol:</th>
      </thead>
      <tbody>
      <tr>
         <td>PORT.A</td>
         <td>G25,G32</td>
         <td>I2C</td>
      </tr>
      <tr>
         <td>PORT.B</td>
         <td>G26,G33</td>
         <td>DAC/ADC</td>
      </tr>
      <tr>
         <td>PORT.C</td>
         <td>G18,G19</td>
         <td>UART</td>
      </tr>
    </tbody>
</table>

## ESP32 ADC/DAC Mappable Pins

<table>
      <thead>
         <th>ADC1</th>
         <th>ADC2</th>
         <th>DAC1</th>
         <th>DAC2</th>
      </thead>
      <tbody>
      <tr>
         <td>8 Channel</td>
         <td>10 Channel</td>
         <td>2 Channel</td>
         <td>2 Channel</td>  
      </tr>
      <tr>
         <td>G32-39</td>
         <td>G0/2/4/12-15/25-27</td>
         <td>G25</td>
         <td>G26</td>
      </tr>
    </tbody>
</table>

For more info on specific pin functions refer to the official ESP32 Docs[ESP32 datasheet](https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/datasheet/core/esp32_datasheet_en.pdf)

## Related Link

- **Datasheet** 
   - [ESP32](https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/datasheet/core/esp32_datasheet_en.pdf)
   - [SHT30 Datasheet](https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/datasheet/unit/SHT3x_Datasheet_digital.pdf)
   - [BM8563](https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/datasheet/core/BM8563_V1.1_cn.pdf)
   - [SY7088](https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/datasheet/core/SY7088-Silergy.pdf)
   - [GT911-datasheet](https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/datasheet/core/m5paper/gt911_datasheet.pdf)

-  **API**

   - [Arduino API](https://docs.m5stack.com/#/en/arduino/arduino_home_page?id=m5paper_api)

## Schematic

   - [M5 PAPER Schematic](https://m5stack.oss-cn-shenzhen.aliyuncs.com/resource/docs/schematic/Core/m5paper/M5_PAPER_SCH.pdf)
