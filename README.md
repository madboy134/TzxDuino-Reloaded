# TzxDuino-Reloaded 1.3.2

Based on the original design of Andrew Beer, Duncan Edwards.

This new version has been completely reworked with smd components. Also change the distribution and connection orientation. Now, you just plug the TzxDuino on the Spectrum jack and use a common Android power supply (microusb b) and that's it, start loading tzx files!. This design also allows to use every type of i2c LCD or OLED Screen, by soldering a 1x4 row pin and taking out the lcd to a better viewable area.

# Works with

- TZX, TAP (Spectrum)
- TSX, CAS (MSX)
- CDT (AMSTRAD)

# Note

This is a work in progress, several testing must be made but it should work as is. I take no responsibiltiy for any damage to any equipment that results from the use of this board. USE AT YOUR OWN RISK!

If you like the project, buy me a beer :) info@arananet.net

# Audio Amp

Since is not clear if there is necessary a output amp, I have added a little solder jumper to bypass or enable the D9 signal to the AMP LM386. By setting the jumper to 1-2, will set the D9 signal to the op amp onboard (if you solder the lm386 on the pcb). Else if you don't want to use the OP AMP, you can set the jumper to 2-3, this will connect the D9 signal directly to the 3.5mm jack. 

# Images

<img src="https://github.com/arananet/TzxDuino-Reloaded/blob/master/images/img1.png?raw=true" width="700">

<img src="https://github.com/arananet/TzxDuino-Reloaded/blob/master/images/img2.png?raw=true" width="700">

# Instructions
 
1. Download the official TzxDuino code from http://arduitapemarkii.blogspot.com.es/2017/06/tzxduino-17.html 
2. Set the display hardware address on the TZXDuino_V1.7b.ino depending on what kind of display have. If does not work, use a i2c scanner in order to get the exact hardware address from the display.
3. Use a serial TTL programmer and the Arduino IDE to upload the code into the ATMEGA.
4. Plug an MicroSD card with all the files and enjoy the power of the TzxDuino!
5. In case we use the hex file to clon and flash many TzxDuino devices we need to set the fuses with the avrdude. 

Fuses are lfuse = 0xff hfuse = 0xDA, efuse = 0x05, LB = 0x0F

# Acrylic case

I also made an acrylic case for this pcb. https://www.thingiverse.com/thing:2535743

# Updates

17/02/2018: Add a screen voltage selector, this is because some chinese oled screen came with the VCC and GND mixed. This can be change on the screen (there are two resistros to swap voltage) but it will more fast to select onboard with two new available solder jumpers.

Changed the USB connector to a most common used.

20/01/2018: Mayor update:

* Fix silkscreen components.
* Added a gain regulator (if the op amp is present) by @jgilcas.
* Added a on-off switch for the op amp proposed by @jgilcas.
* Added a 5x2 pcb connector for use with other devices, proposed by spark2k06.
* Bom updated.
* Acrylic case updated.

18/12/2017: Bom updated. (thanks to @jgilcas for the tips)

03/11/2017: Complete redesigned for use with arduino pro mini.

16/09/2017: Added a 2.5mm for use with remote signal (MSX) and a DTR signal. Components realocated.

06/09/2017: Added a SD card socket on the back. You must cut the jack 3.5mm pins that are too large.

06/09/2017: First initial release. 

# Bill of materials

| Part          | Value                   | Package                        |
| ------------- | ----------------------- | ------------------------------ | 
| C1            | 10uf/22uf               | C0805K                         |
| C2            | 0.22uF                  | C0805K                         |
| C3            | 10uf                    | C0805K                         |
| C4            | 220uf (ECA-0JM221)      | CPOL-EUE1.8-4 (only with amp)  |
| M2            | ARDUINO PRO MINI        | PCB                            |
| REG           | LM1117 3V3              | SOT233                         |
| IC1           | 4050D                   | SO16                           |
| IC4           | LM386M-1                | SO08 (only if amp required)    |
| ISP           | AVR_SPI_PRG_6PTH        | 2X3                            |
| TTL           | PINHD_1X04              | 1X04                           |
| J1            | D9 bypass-enable        | Solder jumper                  |
| JP1           | OLED SCREEN CONNECTOR   | 1X04_ROUND                     |
| K1            | MICROUSB B              | 629105136821                   |
| POWER         | SMD 0805 LED            | CHIP-LED0805                   |
| ACT           | SMD 0805 LED            | CHIP-LED0805                   |
| R1            | 1K TrimPotentiometer    | RTRIM3103   (only with amp)    |
| R2 (FOR LED)  | 330/560/1K              | R0805                          |
| R3 (FOR LED)  | 330/560/1K              | R0805                          |
| PLAY          | PUSH BUTTON             | B3F-31XX                       |
| DOWN          | PUSH BUTTON             | B3F-31XX                       |
| ROOT          | PUSH BUTTON             | B3F-31XX                       |
| S1            | PUSH BUTTON             | B3F-10XX                       |
| STOP          | PUSH BUTTON             | B3F-31XX                       |
| UP            | PUSH BUTTON             | B3F-31XX                       |
| SD1           | MicroSD socket          | TF-PULL                        |
| SD SOCKET     | SDCARD_SMT_4U06132      | SDCARD_SMT_4U06132             |
| X1            | STEREOJACK 3.5mm        | STX3100                        |
| X2            | STEREOJACK 2.5mm        | PJ-204B                        |
| X3            | 5X2 Pin row             | Standard 1" double pin row     |

This is the arduino used in all the versions of the TZXDUINO. Must have A4 and A5 at bottom of the A2 and A3. AliExpress Link. https://es.aliexpress.com/store/product/Free-Shipping-New-Atmega328-5v-Version-Pro-Mini-Module-16M-For-Arduino-Compatible/1962508_32605434250.html?spm=a219c.search0104.3.6.27c06b16t4pHKf&ws_ab_test=searchweb0_0,searchweb201602_4_10152_10065_5722813_10151_10344_10068_10342_5722613_10547_10343_5722913_10340_10341_10548_10698_10697_10696_10084_10083_5722713_10618_10307_10301_10303_5711213_10059_10184_10534_308_100031_10103_441_10624_10623_10622_10621_10620_5722513_5711313,searchweb201603_1,ppcSwitch_5&algo_expid=69227fd3-b92f-4d61-afc6-97915d0331e3-3&algo_pvid=69227fd3-b92f-4d61-afc6-97915d0331e3&transAbTest=ae803_1&priceBeautifyAB=0
