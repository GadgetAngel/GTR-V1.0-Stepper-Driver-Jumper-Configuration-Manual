# GTR-V1.0-Stepper-Driver-Jumper-Configuration-Manual

:exclamation: This project provides and Interactive PDF (documentation) on how to configure stepper motor 
driver boards and how to use them with the GTR V1.0 (3D printer controller) board.  This manual also 
shows the user how to connect additional equipment to the GTR V1.0 Board: Raspberry Pi, BLTouch, 
BTT Smart Filament Sensor, 
PT100 sensor via Analog ADC I/O Input (PT100 Amplifier), 
PT100 sensor via Software SPI (Adafruit MAX31865 Amplifier), 
PT100 sensor via Hardware SPI (Adafruit MAX31865 Amplifier),
K-Type Thermocouple via Analog ADC I/O Input (Adafruit AD8495 Amplifier), 
K-Type Thermocouple via Software SPI (Adafruit MAX31855 Amplifier),
K-Type Thermocouple via Hardware SPI (Adafruit MAX31855 Amplifier) and
Link to TWhite101 Instructable on how to add an EEPROM :exclamation:
```
I use Git for Windows with VScode to manage this repository.  I also use Git LFS extensions
for .pdf and .png files.

Install Git with LFS extensions: https://git-lfs.github.com/

To Download the whole repository do the following: select the "Clone or download button" and 
click on "paste to clipboard" button so you can place the URL for the GitHub repository 
to the clipboard. Now Open Git Bash.  Change the current working directory to the location 
where you want the cloned directory.
Type git clone, and then paste the URL you copied earlier.
$ git clone https://github.com/GadgetAngel/GTR-V1.0-Stepper-Driver-Jumper-Configuration-Manual.git
Press Enter to create your local clone.
Now open Window explorer to the location of local clone.
```
## The Whole Repository in .zip file is located on Google Drive at: 
https://drive.google.com/file/d/1JAKp56H0si4NkxV2h0dzVdrsr1X1zslA/view?usp=sharing 

## Table of Contents:

```
Stepper Driver Jumper Configurations for GTR V1.0 Board
By       @GadgetAngel

ABOUT.............................................................................................................I
Preface...........................................................................................................1
  What is a Stepper motor?........................................................................................2
  Stall Detection and Sensor-less Homing..........................................................................3
    Requirements Needed to Make Sensor-less Homing Work...........................................................3
  Introduction to LEGENDS and Common Terminology in this Manual...................................................4
POLOLU A4988......................................................................................................6
  Driver Chip Chart for POLOLU A4988..............................................................................6
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set...............7
    Special Consideration of “D” Jumper (RST&SLP) for GTR V1.0 Board..............................................8
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have RST&SLP Set..10
  The (latest release of) Marlin Setup for POLOLU A4988 Drivers..................................................15
BIQU A4988.......................................................................................................17
  Driver Chip Chart for BIQU A4988...............................................................................17
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set..............18
    Special Consideration of “D” Jumper (RST&SLP) for GTR V1.0 Board.............................................19
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have
    RST&SLP Set..................................................................................................21
  The (latest release of) Marlin Setup for BIQU A4988 Drivers....................................................26
DRV8825..........................................................................................................28
  Driver Chip Chart for DRV8825..................................................................................28
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set..............29
    Special Consideration of “D” Jumper (RST&SLP) for GTR V1.0 Board.............................................30
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have
    RST&SLP Set..................................................................................................32
  The (latest release of) Marlin Setup for DRV8825 Drivers.......................................................38
BIQU LV8729......................................................................................................41
  Driver Chip Chart for BIQU LV8729..............................................................................41
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set.......42
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have
    RST&SLP Set..................................................................................................44
  The (latest release of) Marlin Setup for BIQU LV8729 Drivers...................................................50
FYSETC LV8729....................................................................................................54
  Driver Chip Chart for FYSETC LV8729............................................................................54
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set.......55
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have
    RST&SLP Set..................................................................................................57
  The (latest release of) Marlin Setup for FYSETC LV8729 Drivers.................................................63
LERDGE LV8729....................................................................................................67
  Driver Chip Chart for LERDGE LV8729............................................................................67
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set.......68
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have
    RST&SLP Set..................................................................................................70
  The (latest release of) Marlin Setup for LERDGE LV8729 Drivers.................................................76
MKS LV8729.......................................................................................................80
  Driver Chip Chart for MKS LV8729...............................................................................80
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set.......81
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have 
    RST&SLP Set..................................................................................................83
  The (latest release of) Marlin Setup for MKS LV8729 Drivers....................................................89
FYSETC S6128 V1.1................................................................................................93
  Driver Chip Chart for FYSETC S6128 V1.1........................................................................93
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set..............94
    Special Consideration of “D” Jumper (RST&SLP) for GTR V1.0 Board.............................................95
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have RST&SLP Set..97
  The (latest release of) Marlin Setup for FYSETC S6128 V1.1 Drivers............................................103
FYSETC ST820....................................................................................................107
  Driver Chip Chart for FYSETC ST820............................................................................107
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.............108
    Special Consideration of “D” Jumper (RST&SLP) for GTR V1.0 Board............................................109
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have
    RST&SLP Set.................................................................................................111
  The (latest release of) Marlin Setup for FYSETC ST820 Drivers.................................................117
BIQU ST820......................................................................................................122
  Driver Chip Chart for BIQU ST820..............................................................................122
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.............123
    Special Consideration of “D” Jumper (RST&SLP) for GTR V1.0 Board............................................124
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have
    RST&SLP Set.................................................................................................126
  The (latest release of) Marlin Setup for BIQU ST820 Drivers...................................................132
POLOLU ST820 (STSPIN820)........................................................................................137
  Driver Chip Chart for POLOLU ST820 (STSPIN820)................................................................137
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set.............138
    Special Consideration of “D” Jumper (RST&SLP) for GTR V1.0 Board............................................139
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have
    RST&SLP Set.................................................................................................141
  The (latest release of) Marlin Setup for POLOLU ST820 (STSPIN820) Drivers.....................................147
POLOLU MP6500...................................................................................................152
  Driver Chip Chart for POLOLU MP6500...........................................................................152
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set......153
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have 
    RST&SLP Set.................................................................................................155
  The (latest release of) Marlin Setup for POLOLU MP6500 Drivers................................................159
POLOLU TB67S249FTG..............................................................................................163
  Driver Chip Chart for POLOLU TB67S249FTG......................................................................163
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set......164
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have 
    RST&SLP Set.................................................................................................166
  The (latest release of) Marlin Setup for POLOLU TB67S249FTG Drivers...........................................172
BIQU S109.......................................................................................................176
  Driver Chip Chart for BIQU S109...............................................................................176
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set......177
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have
    RST&SLP Set.................................................................................................179
  The (latest release of) Marlin Setup for BIQU S109 Drivers....................................................185
FYSETC S109.....................................................................................................189
  Driver Chip Chart for FYSETC S109.............................................................................189
  GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set......190
  GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have 
    RST&SLP Set.................................................................................................192
  The (latest release of) Marlin Setup for FYSETC S109 Drivers..................................................198
BIQU TMC2100 Stand-alone Mode...................................................................................202
  Driver Chip Chart for BIQU TMC2100 in Stand-alone Mode........................................................202
  GTR V1.0 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 1...................................203
  GTR V1.0 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 2...................................204
  GTR V1.0 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers...........................206
  The (latest release of) Marlin Setup for BIQU TMC2100 Drivers in Stand-alone Mode.............................211
MKS TMC2100 Stand-alone Mode....................................................................................215
  Driver Chip Chart for MKS TMC2100 in Stand-alone Mode.........................................................215
  GTR V1.0 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 1...................................216
  GTR V1.0 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 2...................................217
  GTR V1.0 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers...........................219
  The (latest release of) Marlin Setup for MKS TMC2100 Drivers in Stand-alone Mode..............................224
BIQU TMC2130 (SA) Stand-alone Mode..............................................................................228
  Driver Chip Chart for BIQU TMC2130 (SA) in Stand-alone Mode...................................................228
  GTR V1.0 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 1...................................229
  GTR V1.0 LEGEND of Driver Chip Chart for Tri State Stepper Drivers - PART 2...................................230
  GTR V1.0 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers...........................232
BIQU TMC2130 SPI Mode...........................................................................................241
  Driver Chip Chart for BIQU TMC2130 in SPI Mode................................................................241
  GTR V1.0 LEGEND of Driver Socket Representation for Stepper Motor Drivers in SPI Mode.........................244
  Information on Sensor-less Homing for GTR V1.0................................................................247
  The (latest release of) Marlin Setup for BIQU TMC2130 Drivers in SPI Mode.....................................252
BIQU TMC2208 V3.0 (SA) Stand-alone Mode for StealthChop.........................................................266
  Driver Chip Chart for BIQU TMC2208 V3.0 (SA) in Stand-alone Mode (StealthChop)................................266
  GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (StealthChop)...267
  GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone
    Mode (StealthChop)..........................................................................................269
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 (SA) Drivers in Stand-alone Mode for StealthChop...273
BIQU TMC2208 V3.0 (OTP) Stand-alone Mode for SpreadCycle........................................................277
  Driver Chip Chart for BIQU TMC2208 V3.0 (OTP) in Stand-alone Mode (SpreadCycle)...............................277
  GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (SpreadCycle)...278
  GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone
    Mode (SpreadCycle)..........................................................................................280
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 (OTP) Drivers in Stand-alone Mode for SpreadCycle..284
BIQU TMC2208 V3.0 UART Mode.....................................................................................288
  Driver Chip Chart for BIQU TMC2208 V3.0 in UART Mode..........................................................288
  GTR V1.0 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode........................291
  The (latest release of) Marlin Setup for BIQU TMC2208 V3.0 Drivers in UART Mode...............................297
FYSETC TMC2208 V1.2 (SA) Stand-alone Mode for StealthChop.......................................................306
  Driver Chip Chart for FYSETC TMC2208 V1.2 (SA) in Stand-alone Mode (StealthChop)..............................306
  GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (StealthChop)...307
  GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone 
    Mode (StealthChop)..........................................................................................309
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 (SA) Drivers in Stand-alone Mode for StealthChop.313
FYSETC TMC2208 V1.2 (OTP) Stand-alone Mode for SpreadCycle......................................................317
  Driver Chip Chart for FYSETC TMC2208 V1.2 (OTP) in Stand-alone Mode (SpreadCycle).............................317
  GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (SpreadCycle)...318
  GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone 
    Mode (SpreadCycle)..........................................................................................320
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 (OTP) Drivers in Stand-alone Mode 
    for SpreadCycle.............................................................................................324
FYSETC TMC2208 V1.2 UART Mode...................................................................................328
  Driver Chip Chart for FYSETC TMC2208 V1.2 in UART Mode........................................................328
  GTR V1.0 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode........................331
  The (latest release of) Marlin Setup for FYSETC TMC2208 V1.2 Drivers in UART Mode.............................337
BIQU TMC2225 V1.0 (SA) Stand-alone Mode for StealthChop.........................................................346
  Driver Chip Chart for BIQU TMC2225 V1.0 (SA) in Stand-alone Mode (StealthChop)................................346
  GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (StealthChop)...347
  GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in 
    Stand-alone Mode (StealthChop)..............................................................................349
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 (SA) Drivers in Stand-alone Mode for StealthChop...353
BIQU TMC2225 V1.0 (OTP) Stand-alone Mode for SpreadCycle........................................................357
  Driver Chip Chart for BIQU TMC2225 V1.0 (OTP) in Stand-alone Mode (SpreadCycle)...............................357
  GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (SpreadCycle)...358
  GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone 
    Mode (SpreadCycle)..........................................................................................360
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 (OTP) Drivers in Stand-alone Mode for SpreadCycle..364
BIQU TMC2225 V1.0 UART Mode.....................................................................................368
  Driver Chip Chart for BIQU TMC2225 V1.0 in UART Mode..........................................................368
  GTR V1.0 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode........................371
  The (latest release of) Marlin Setup for BIQU TMC2225 V1.0 Drivers in UART Mode...............................377
BIQU TMC2209 V1.2 (SA) Stand-alone Mode for StealthChop.........................................................386
  Driver Chip Chart for BIQU TMC2209 V1.2 (SA) in Stand-alone Mode (StealthChop)................................386
  GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (StealthChop)...387
  GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone 
    Mode (StealthChop)..........................................................................................389
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 (SA) Drivers in Stand-alone Mode for StealthChop...393
BIQU TMC2209 V1.2 (OTP) Stand-alone Mode for SpreadCycle........................................................397
  Driver Chip Chart for BIQU TMC2209 V1.2 (OTP) in Stand-alone Mode (SpreadCycle)...............................397
  GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (SpreadCycle)...398
  GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone 
    Mode (SpreadCycle)..........................................................................................400
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 (OTP) Drivers in Stand-alone Mode for SpreadCycle..404
BIQU TMC2209 V1.2 UART Mode.....................................................................................408
  Driver Chip Chart for BIQU TMC2209 V1.2 in UART Mode..........................................................408
  GTR V1.0 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode........................411
  Information on Sensor-less Homing for GTR V1.0................................................................415
  The (latest release of) Marlin Setup for BIQU TMC2209 V1.2 Drivers in UART Mode...............................420
BIQU TMC2226 V1.0 (SA) Stand-alone Mode for StealthChop.........................................................434
  Driver Chip Chart for BIQU TMC2226 V1.0 (SA) in Stand-alone Mode (StealthChop)................................434
  GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (StealthChop)...435
  GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone 
    Mode (StealthChop)..........................................................................................437
  The (latest release of) Marlin Setup for BIQU TMC2226 V1.0 (SA) Drivers in Stand-alone Mode for StealthChop...441
BIQU TMC2226 V1.0 (OTP) Stand-alone Mode for SpreadCycle........................................................445
  Driver Chip Chart for BIQU TMC2226 V1.0 (OTP) in Stand-alone Mode (SpreadCycle)...............................445
  GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (SpreadCycle)...446
  GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone
    Mode (SpreadCycle)..........................................................................................448
  The (latest release of) Marlin Setup for BIQU TMC2226 V1.0 (OTP) Drivers in Stand-alone Mode for SpreadCycle..452
BIQU TMC2226 V1.0 UART Mode.....................................................................................456
  Driver Chip Chart for BIQU TMC2226 V1.0 in UART Mode..........................................................456
  GTR V1.0 LEGEND of Driver Socket Representation for Stepper Motor Drivers in UART Mode........................459
  Information on Sensor-less Homing for GTR V1.0................................................................463
  The (latest release of) Marlin Setup for BIQU TMC2226 V1.0 Drivers in UART Mode...............................468
BIQU TMC5160 V1.2 SPI Mode......................................................................................482
  Driver Chip Chart for BIQU TMC5160 V1.2 in SPI Mode...........................................................482
  GTR V1.0 LEGEND of Driver Socket Representation for Stepper Motor Drivers in SPI Mode.........................485
  Information on Sensor-less Homing for GTR V1.0................................................................488
  The (latest release of) Marlin Setup for BIQU TMC5160 V1.2 Drivers in SPI Mode................................493
BIQU TMC5161 V1.0 SPI Mode......................................................................................507
  Driver Chip Chart for BIQU TMC5161 V1.0 in SPI Mode...........................................................507
  GTR V1.0 LEGEND of Driver Socket Representation for Stepper Motor Drivers in SPI Mode.........................510
  Information on Sensor-less Homing for GTR V1.0................................................................513
  The (latest release of) Marlin Setup for BIQU TMC5161 V1.0 Drivers in SPI Mode................................518
APPENDIX A......................................................................................................532
  How to adjust the Vref on a Stepper Motor Driver board using the Potentiometer................................532
    How to Tune Stepper Motor Drivers?..........................................................................532
APPENDIX B......................................................................................................534
  For the TMC drivers what’s the difference between stand-alone mode and (“UART” or “SPI “) modes?..............534
  How to Calculate Vref for Non-TMC Stepper Motor Divers........................................................534
  How to Calculate Vref for TMC Stepper Motor Drivers...........................................................535
    Driving Current Calculation Formulas for TMC Stepper Motor Drivers¹.........................................536
      #1 TMC2100 with Rs = 0.110Ω (110mΩ).......................................................................536
      #2 TMC2130 with Rs = 0.110Ω (110mΩ) for Stand-alone Mode and SPI Mode.....................................536
      #3 TMC2208 with Rs = 0.110Ω (110mΩ) for Stand-alone Mode..................................................537
      #4 TMC2208 with Rs = 0.110Ω (110mΩ) for UART Mode.........................................................537
      #5 TMC2209 with Rs =0.110Ω (110mΩ) for Stand-alone Mode...................................................538
      #6 TMC2209 with Rs = 0.110Ω (110mΩ) for UART Mode.........................................................538
      #7 TMC2225 with Rs = 0.150Ω (150mΩ) for Stand-alone Mode..................................................539
      #8 TMC2225 with Rs = 0.150Ω (150mΩ) for UART Mode.........................................................539
      #9 TMC2226 with Rs = 0.150Ω (150mΩ) for Stand-alone Mode..................................................540
      #10 TMC2226 with Rs = 0.150Ω (150mΩ) for UART Mode........................................................540
      #11 TMC5160 with Rs = 0.075Ω (75mΩ) for SPI Mode..........................................................541
      #12 TMC5161 with Rs = 0.062Ω (62mΩ) for SPI Mode..........................................................541
APPENDIX C......................................................................................................542
  The (Latest Release of) Marlin Setup That Is Common to ALL Stepper Motor Drivers..............................542
    Link to BIGTREETECH GTR-V1.0 Operating Instruction..........................................................542
    Link to BIGTREETECH GTR-V1.0 Github Page....................................................................542
    Link to Pronterface Software................................................................................543
    Link to How to Calibrate your 3D Printer....................................................................543
    GTR V1.0 Color PIN Diagram..................................................................................560
    GTR V1.0 Color Wiring Diagram...............................................................................561
    GTR V1.0 Color PIN 1 Diagram................................................................................563
    GTR V1.0 Color Schematic Diagram............................................................................564
    GTR V1.0 Uncolored Schematic Diagram........................................................................565
APPENDIX D......................................................................................................566
  Legends for GTR V1.0 Stepper Driver Jumper Configurations.....................................................566
  GTR V1.0 LEGEND COMMON to ALL Driver Socket Representation....................................................567
  GTR V1.0 LEGENDS for Driver Socket Representations and LEGENDS for Driver Chip Charts.........................571
    GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Have
      RST&SLP Set...............................................................................................571
    GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Have RST&SLP PINS Set...........574
      Special Consideration of “D” Jumper (RST&SLP) for GTR V1.0 Board..........................................575
    GTR V1.0 LEGEND of Driver Socket Representation for Binary State Stepper Motor Drivers Which Do Not Have 
      RST&SLP Set...............................................................................................576
    GTR V1.0 LEGEND of Driver Chip Chart for Binary State Stepper Drivers Which Do Not Have RST&SLP PINS Set....579
    GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone 
      Mode (StealthChop)........................................................................................580
    GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (StealthChop).582
    GTR V1.0 LEGEND of Driver Socket Representation for TMC Binary State Stepper Motor Drivers in Stand-alone 
      Mode (SpreadCycle)........................................................................................583
    GTR V1.0 LEGEND of Driver Chip Chart for TMC Binary State Stepper Drivers in Stand-alone Mode (SpreadCycle).585
    GTR V1.0 LEGEND of Driver Socket Representation for Tri State Stepper Motor Drivers.........................586
    GTR V1.0 LEGEND of Driver Chip Chart for Tri State Stepper Drivers..........................................588
    GTR V1.0 LEGEND of Driver Socket Representation for SPI Capable Stepper Motor Drivers.......................589
    GTR V1.0 LEGEND of Driver Socket Representation for UART Capable Stepper Motor Drivers......................596
    GTR V1.0 LEGEND of Driver Socket Representation for Sensor-less Homing Capable Stepper Motor Drivers........605
  GTR V1.0 Examples of Stepper Driver Jumper Configurations.....................................................611
    GTR V1.0 Examples of Stepper Driver Jumper Configurations for Binary State Drivers without RST&SLP Set......611
    GTR V1.0 Examples of Stepper Driver Jumper Configurations for Binary State Drivers with RST&SLP Set.........615
    GTR V1.0 Examples of Stepper Driver Jumper Configurations for Tri State Drivers.............................619
    GTR V1.0 Examples of Stepper Driver Jumper Configurations for TMC2209 with Sensor-less Homing...............626
    GTR V1.0 Examples of Stepper Driver Jumper Configurations for TMC2209 without Sensor-less Homing............627
    GTR V1.0 Examples of Stepper Driver Jumper Configurations for TMC2130 with Sensor-less Homing...............628
    GTR V1.0 Examples of Stepper Driver Jumper Configurations for TMC2130 without Sensor-less Homing............629
APPENDIX E......................................................................................................630
  Location Of “firmware.bin” File from the Marlin Compilation for GTR V1.0 Board................................630
APPENDIX F......................................................................................................633
  Links to Reference Material...................................................................................633
    Marlin Firmware Documentation...............................................................................633
    Information on Stepper Motor Drivers and Micro-stepping.....................................................633
    POLOLU A4988 and BIQU A4988.................................................................................634
    DRV8825.....................................................................................................634
    BIQU LV8729, FYSETC LV8729, LERDGE LV8729, and MKS LV879....................................................635
    BIQU LV8729.................................................................................................635
    FYSETC LV8729...............................................................................................636
    LERDGE LV8729...............................................................................................636
    MKS LV8729..................................................................................................637
    FYSETC S6128 V1.1...........................................................................................637
    FYSETC ST820................................................................................................638
    BIQU ST820..................................................................................................638
    POLOLU ST820 (STSPIN820)....................................................................................639
    POLOLU MP6500...............................................................................................639
    POLOLU TB67S249FTG..........................................................................................640
    BIQU S109 and FYSETC S109...................................................................................640
    BIQU S109...................................................................................................641
    FYSETC S109.................................................................................................641
    Marlin Firmware Documentation Specific to TMC Drivers.......................................................642
    Information Common to All TMC Drivers.......................................................................642
    BIQU TMC2100 and MKS TMC2100................................................................................643
    BIQU TMC2130................................................................................................644
    Information Common to BIQU TMC2208 V3.0 and FYSETC TMC2208 V1.2.............................................644
    Information Common to BIQU TMC2208 V3.0 and FYSETC TMC2208 V1.2 (Continued).................................645
    BIQU TMC2208 V3.0...........................................................................................645
    FYSETC TMC2208 V1.2.........................................................................................645
    Information Common to TMC2208 and BIQU TMC2225..............................................................646
    BIQU TMC2225 V1.0...........................................................................................646
    BIQU TMC2209 V1.2...........................................................................................647
    BIQU TMC5160 V1.2...........................................................................................647
    BIQU TMC5161 V1.0...........................................................................................648
    Links on SKR V1.4 TURBO Board...............................................................................648
    Links on SKR PRO V1.1 Board.................................................................................649
    Links on SKR PRO V1.2 Board.................................................................................650
    Links on SKR V1.3 Board.....................................................................................651
    Links on SKR V1.4 Board.....................................................................................652
    Links on GTR V1.0 Board.....................................................................................653
    Links on M5 V1.0 Add-on-board for GTR V1.0 Board............................................................654
    Miscellaneous Information...................................................................................655
    Miscellaneous Information (continued).......................................................................656
    Facebook Groups.............................................................................................661
APPENDIX G......................................................................................................662
  BIGTREETECH Reference Material for GTR V1.0 Board.............................................................662
    GTR V1.0 Original PIN Diagram...............................................................................662
    GTR V1.0 Original PIN Diagram - Corrected...................................................................663
    GTR V1.0 Original Wiring Diagram 1..........................................................................664
    GTR V1.0 Original PIN 1 Diagram.............................................................................665
    GTR V1.0 Original Schematic Diagram.........................................................................666
APPENDIX H......................................................................................................667
  BIGTREETECH’s Smart Filament Sensor (SFS) Guide for GTR V1.0 Board............................................667
  Information About BIGTREETECH’s SFS...........................................................................669
  SFS Wired to Extend-Interface-1 Connector.....................................................................671
    Marlin 2.0.x Setup for SFS Connected to Extend-Interface-1 Connector........................................672
  SFS Wired to E2 Limit Switch..................................................................................675
    Marlin 2.0.x Setup for SFS Connected to E2 Connector........................................................676
APPENDIX I......................................................................................................686
  “Connecting up Raspberry Pi via TFT Connector” Guide for GTR V1.0 Board.......................................686
  Connecting GTR V1.0 to Raspberry Pi to Eliminate USB Cable Via TFT Connector..................................687
    TFT Connector Wiring Diagram for Connecting GTR V1.0 to Raspberry Pi to Eliminate USB Cable.................690
  Marlin 2.0.x Setup for Connecting up Raspberry Pi.............................................................693
APPENDIX J......................................................................................................696
  “Connecting up Raspberry Pi via Raspberry Pi Header” Guide for GTR V1.0 Board.................................696
  Connecting GTR V1.0 to Raspberry Pi to Eliminate USB Cable Via Raspberry Pi Connector.........................697
    Pi Connector Wiring Diagram for Connecting GTR V1.0 to Raspberry Pi to Eliminate USB Cable..................700
  Marlin 2.0.x Setup for Connecting up Raspberry Pi.............................................................703
APPENDIX K......................................................................................................706
  “Connecting up Raspberry Pi via WIFI Header” Guide for GTR V1.0 Board.........................................706
  Connecting GTR V1.0 to Raspberry Pi to Eliminate USB Cable Via WIFI Header....................................707
    WIFI Header Wiring Diagram for Connecting GTR V1.0 to Raspberry Pi to Eliminate USB Cable...................710
  Marlin 2.0.x Setup for Connecting up Raspberry Pi.............................................................713
APPENDIX L......................................................................................................716
  BLTouch Guide for GTR V1.0 Board..............................................................................716
  Connecting GTR V1.0 with BLTouch..............................................................................717
    Wiring Diagram for Connecting GTR V1.0 with BLTouch.........................................................720
  Marlin 2.0.x Firmware Setup for Connecting a BLTouch to GTR V1.0 Board........................................721
    Explanation when to use Marlin variable Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN..................................726
    Understanding Marlin Firmware’s NOZZLE_TO_PROBE_OFFSET Setting..............................................730
APPENDIX M......................................................................................................745
  PT100 Sensor Connection Guide to the GTR V1.0 Board via Analog ADC I/O Input..................................745
  Hyperlink Map for this PT100 Sensor Connection Guide via Analog ADC I/O Input.................................746
  Connecting  GTR V1.0 with  PT100 Sensor.......................................................................747
  E3D PT100 Amplifier Board Specifications......................................................................747
    E3D’s PT100 Amplifier Board -- Schematic Diagram............................................................748
    Hyperlink to Texas Instruments’ INA826  Amplifier Data Sheet................................................748
  Analog Procedure..............................................................................................751
    Connecting GTR V1.0 Board with PT100 Amplifier Board and PT100 Sensor.......................................751
      Locations of 3.3VDC Referenced to Analog Ground for the GTR V1.0 Board’s Thermistor Ports.................762
      Hardware Hack Instructions for the GTR V1.0 Board’s T0 (E0) Thermistor Port...............................764
      Hardware Hack Instructions for the GTR V1.0 Board’s T1 (E1) Thermistor Port...............................766
      Hardware Hack Instructions for the GTR V1.0 Board’s T2 (E2) Thermistor Port...............................768
    Instructions for Supplying Power to the PT100 Amplifier Board...............................................771
      Method #1 (5 VDC Digital PWR) for Powering the PT100 Amplifier Board for Techniques #1,  
        Technique #2, and Technique #8..........................................................................772
      Method #1 (3.3 VDC Digital PWR) for Powering the PT100 Amplifier Board for Techniques #3,
        and Technique #4........................................................................................773
      Method #1 (5 VDC Digital PWR) for Powering the PT100 Amplifier Board for Techniques #9,  
        Technique #10, and Technique #11........................................................................774
      Method #1 (3.3 VDC Digital PWR) for Powering the PT100 Amplifier Board for Techniques #5,  
        Technique #6, and Technique #7..........................................................................775
      Method #2 (3.3 VDC ref GNDAO, Analog PWR) for Powering PT100 Amplifier Board for Technique #5, 
        Technique #6, and Technique #7..........................................................................776
    Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR).............................................777
    Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR).............................................778
    Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR)...........................................779
    Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR)R).........................................780
    Wiring Diagram for Technique #5 & Method #1 (3.3 VDC Digital PWR)...........................................781
    Wiring Diagram for Technique #5 & Method #2 (3.3 VDC ref GNDAO, Analog PWR).................................782
    Wiring Diagram for Technique #6 & Method #1 (3.3 VDC Digital PWR)...........................................783
    Wiring Diagram for Technique #6 & Method #2 (3.3 VDC ref GNDAO, Analog PWR).................................784
    Wiring Diagram for Technique #7 & Method #1 (3.3 VDC Digital PWR)...........................................785
    Wiring Diagram for Technique #7 & Method #2 (3.3 VDC ref GNDAO, Analog PWR).................................786
    Wiring Diagram for Technique #8 & Method #1 (5 VDC Digital PWR).............................................787
    Wiring Diagram for Technique #9 & Method #1 (5 VDC Digital PWR).............................................788
    Wiring Diagram for Technique #10 & Method #1 (5 VDC Digital PWR)............................................789
    Wiring Diagram for Technique #11 & Method #1 (5 VDC Digital PWR)............................................790
      Marlin 2.0.x Firmware Setup for Connecting a PT100 Sensor to the GTR V1.0 Board...........................791
      Marlin 2.0.x Firmware Setup for Technique #1..............................................................792
      Marlin 2.0.x Firmware Setup for Technique #2..............................................................799
      Marlin 2.0.x Firmware Setup for Technique #3..............................................................806
      Marlin 2.0.x Firmware Setup for Technique #4..............................................................813
      Marlin 2.0.x Firmware Setup for Technique #5..............................................................820
      Marlin 2.0.x Firmware Setup for Technique #6..............................................................827
      Marlin 2.0.x Firmware Setup for Technique #7..............................................................834
      Marlin 2.0.x Firmware Setup for Technique #8..............................................................841
      Marlin 2.0.x Firmware Setup for Technique #9..............................................................853
      Marlin 2.0.x Firmware Setup for Technique #10.............................................................860
      Marlin 2.0.x Firmware Setup for Technique #11.............................................................867
APPENDIX N......................................................................................................874
  PT100 Sensor Connection Guide to the GTR V1.0 Board via Software SPI Protocol.................................874
  Hyperlink Map for this PT100 Sensor Connection Guide via Software SPI Protocol................................875
  Digital Procedure.............................................................................................876
    Connecting  GTR V1.0 with Adafruit MAX31865 Amplifier Board and PT100 Sensor................................876
    Adafruit MAX31865 Amplifier Board Specification.............................................................877
      Adafruit MAX31865 Amplifier Board -- Schematic Diagram....................................................878
      Hyperlink to MAXIM Integrated’s MAX31865 Data Sheet.......................................................878
    Connecting GTR V1.0 with Adafruit MAX31865 Amplifier Board via Software SPI.................................880
      Method #1 (5 VDC Digital PWR) for Powering the MAX31865 Amplifier Board for Technique #1 
        and Technique #2........................................................................................889
      Method #1 (3.3 VDC Digital PWR) for Powering the MAX31865 Amplifier Board for Technique #3 
        and Technique #4........................................................................................890
      Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR)...........................................891
      Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR)...........................................892
      Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR).........................................893
      Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR).........................................894
      Marlin 2.0.x Firmware Setup for Technique #1..............................................................896
      Marlin 2.0.x Firmware Setup for Technique #2..............................................................909
      Marlin 2.0.x Firmware Setup for Technique #3..............................................................922
      Marlin 2.0.x Firmware Setup for Technique #4..............................................................935
APPENDIX O......................................................................................................948
  PT100 Sensor Connection Guide to the GTR V1.0 Board via Hardware SPI Protocol.................................948
  Hyperlink Map for this PT100 Sensor Connection Guide via Hardware SPI Protocol................................949
  Digital Procedure.............................................................................................950
    Connecting  GTR V1.0 with Adafruit MAX31865 Amplifier Board and PT100 Sensor................................950
    Adafruit MAX31865 Amplifier Board Specification.............................................................951
      Adafruit MAX31865 Amplifier Board -- Schematic Diagram....................................................952
      Hyperlink to MAXIM Integrated’s MAX31865 Data Sheet.......................................................952
    Connecting  GTR V1.0 with Adafruit MAX31865 Amplifier Board via Hardware SPI................................954
      Method #1 (5 VDC Digital PWR) for Powering the MAX31865 Amplifier Board for Technique #1 
        and Technique #2........................................................................................964
      Method #1 (3.3 VDC Digital PWR) for Powering the MAX31865 Amplifier Board for Technique #3 
        and Technique #4........................................................................................965
      Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR)...........................................966
      Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR)...........................................967
      Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR).........................................968
      Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR).........................................969
      Marlin 2.0.x Firmware Setup for Technique #1..............................................................971
      Marlin 2.0.x Firmware Setup for Technique #2..............................................................984
      Marlin 2.0.x Firmware Setup for Technique #3..............................................................997
      Marlin 2.0.x Firmware Setup for Technique #4.............................................................1010
APPENDIX P.....................................................................................................1023
  1st & 2nd K-Type Thermocouple Sensor Connection Guide to the GTR V1.0 Board via Analog ADC I/O Input.........1023
  Hyperlink Map for this K-Type Thermocouple Sensor Connection Guide via Analog ADC I/O Input..................1024
  Connecting  GTR V1.0 with K-Type Thermocouple Sensor.........................................................1025
  Adafruit AD8495 Amplifier Board Specifications...............................................................1025
    Adafruit’s AD8495 Amplifier Board -- Schematic Diagram.....................................................1026
    Hyperlink to Analog Devices’ AD8495 Amplifier Data Sheet...................................................1026
    How To Prevent a Noisy K-Type Thermocouple.................................................................1027
  Connecting GTR V1.0 with One (1) or Two (2) K-Type Thermocouple Sensor.......................................1029
    Hook Up One (1) K-Type thermocouple to the GTR V1.0 board: #1, #2, and #3..................................1030
    Hook Up Two (2) K-Type thermocouple to the GTR V1.0 board: #4, and #5......................................1030
    Hook Up Two (2) K-Type thermocouple to the GTR V1.0 board: #5 (continued), and #6..........................1031
    Hook Up Two (2) K-Type thermocouple to the GTR V1.0 board: #6 (continued), #7, and #8......................1032
    Hook Up Two (2) K-Type thermocouple to the GTR V1.0 board: #8 (continued)..................................1033
  Analog Procedure.............................................................................................1036
    Connecting GTR V1.0 with K-Type Thermocouple Sensor and Adafruit’s AD8495 Amplifier Board..................1036
      Locations of 3.3VDC Referenced to Analog Ground for the GTR V1.0 Board’s Thermistor Ports................1047
      Hardware Hack Instructions for the GTR V1.0 Board’s T0 (E0) Thermistor Port..............................1049
      Hardware Hack Instructions for the GTR V1.0 Board’s T1 (E1) Thermistor Port..............................1051
      Hardware Hack Instructions for the GTR V1.0 Board’s T2 (E2) Thermistor Port..............................1053
    Instructions for Supplying Power to the AD8495 Amplifier Board.............................................1056
      Method #1 (5 VDC Digital PWR) for Powering the AD8495 Amplifier Board for Techniques #1,  
        Technique #2, and Technique #8.........................................................................1057
      Method #1 (3.3 VDC Digital PWR) for Powering the AD8495 Amplifier Board for Techniques #3,  
        and Technique #4.......................................................................................1058
      Method #1 (5 VDC Digital PWR) for Powering the AD8495 Amplifier Board for Techniques #9,  
        Technique #10, and Technique #11.......................................................................1059
      Method #1 (3.3 VDC Digital PWR) for Powering the AD8495 Amplifier Board for Techniques #5,  
        Technique #6, and Technique #7.........................................................................1060
      Method #2 (3.3 VDC ref GNDAO, Analog PWR) for Powering AD8495 Amplifier Board for Technique #5, 
        Technique #6, and Technique #7.........................................................................1061
    Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR)............................................1062
    Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR)............................................1063
    Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR)..........................................1064
    Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR)R)........................................1065
    Wiring Diagram for Technique #5 & Method #1 (3.3 VDC Digital PWR)..........................................1066
    Wiring Diagram for Technique #5 & Method #2 (3.3 VDC ref GNDAO, Analog PWR)................................1067
    Wiring Diagram for Technique #6 & Method #1 (3.3 VDC Digital PWR)..........................................1068
    Wiring Diagram for Technique #6 & Method #2 (3.3 VDC ref GNDAO, Analog PWR)................................1069
    Wiring Diagram for Technique #7 & Method #1 (3.3 VDC Digital PWR)..........................................1070
    Wiring Diagram for Technique #7 & Method #2 (3.3 VDC ref GNDAO, Analog PWR)................................1071
    Wiring Diagram for Technique #8 & Method #1 (3.3 VDC Digital PWR)..........................................1072
    Wiring Diagram for Technique #9 & Method #1 (5 VDC Digital PWR)............................................1073
    Wiring Diagram for Technique #10 & Method #1 (5 VDC Digital PWR)...........................................1074
    Wiring Diagram for Technique #11 & Method #1 (5 VDC Digital PWR)...........................................1075
    Marlin 2.0.x Firmware Setup for Connecting a K-Type Thermocouple Sensor to the GTR V1.0 Board..............1076
      Marlin 2.0.x Firmware Setup for Technique #1.............................................................1077
      Marlin 2.0.x Firmware Setup for Technique #2.............................................................1085
      Marlin 2.0.x Firmware Setup for Technique #3.............................................................1093
      Marlin 2.0.x Firmware Setup for Technique #4.............................................................1101
      Marlin 2.0.x Firmware Setup for Technique #5.............................................................1109
      Marlin 2.0.x Firmware Setup for Technique #6.............................................................1117
      Marlin 2.0.x Firmware Setup for Technique #7.............................................................1125
      Marlin 2.0.x Firmware Setup for Technique #8.............................................................1133
      Marlin 2.0.x Firmware Setup for Technique #9.............................................................1148
      Marlin 2.0.x Firmware Setup for Technique #10............................................................1156
      Marlin 2.0.x Firmware Setup for Technique #11............................................................1164
APPENDIX Q.....................................................................................................1172
  1st & 2nd K-Type Thermocouple Sensor Connection Guide to the GTR V1.0 Board via Software SPI Protocol........1172
  Hyperlink Map for this K-Type Thermocouple Sensor Connection Guide via Software SPI Protocol.................1173
  Digital Procedure............................................................................................1174
    Connecting GTR V1.0 with 1st & 2nd Adafruit MAX31855 Amplifier Board and K-Type Thermocouple Sensor........1174
    MAX31855 Amplifier Board Specification.....................................................................1175
      Adafruit’s MAX31855 Amplifier Board -- Schematic Diagram.................................................1176
      Hyperlink to MAXIM’s MAX31855 Data Sheet.................................................................1176
      How To Prevent a Noisy K-Type Thermocouple...............................................................1177
    Using the Embedded MAX31855 Amplifier and a 2nd MAX31855 Amplifier with 2nd Thermocouple Sensor............1179
      Marlin 2.0.x Firmware Setup for one K-Type Thermocouple connected to KTEM................................1180
    Connecting GTR V1.0 with 2nd Adafruit MAX31855 Amplifier Board via Software SPI............................1192
      Method #1 (5 VDC Digital PWR) for Powering the MAX31865 Amplifier Board for 
        Technique #1 and Technique #2..........................................................................1199
      Method #1 (3.3 VDC Digital PWR) for Powering the MAX31865 Amplifier Board for 
        Technique #3 and Technique #4..........................................................................1200
      Wiring Diagram for Technique #1 & Method #1 (5 VDC Digital PWR)..........................................1201
      Wiring Diagram for Technique #2 & Method #1 (5 VDC Digital PWR)..........................................1202
      Wiring Diagram for Technique #3 & Method #1 (3.3 VDC Digital PWR)........................................1203
      Wiring Diagram for Technique #4 & Method #1 (3.3 VDC Digital PWR)........................................1204
      Marlin 2.0.x Firmware Setup for Technique #1.............................................................1206
      Marlin 2.0.x Firmware Setup for Technique #2.............................................................1219
      Marlin 2.0.x Firmware Setup for Technique #3.............................................................1232
      Marlin 2.0.x Firmware Setup for Technique #4.............................................................1245
APPENDIX R.....................................................................................................1258
  2nd K-Type Thermocouple Sensor Connection Guide to the GTR V1.0 Board via Hardware SPI Protocol..............1258
  Hyperlink Map for this K-Type Thermocouple Sensor Connection Guide via Hardware SPI Protocol.................1259
  Digital Procedure............................................................................................1260
    Connecting GTR V1.0 with MAX31855 Amplifier Board and 2nd K-Type Thermocouple Sensor.......................1260
    MAX31855 Amplifier Board Specification.....................................................................1261
      Adafruit’s MAX31855 Amplifier Board -- Schematic Diagram.................................................1262
      Hyperlink to MAXIM’s MAX31855 Data Sheet.................................................................1262
      How To Prevent a Noisy K-Type Thermocouple...............................................................1263
    Connecting GTR V1.0 with 2nd Adafruit MAX31855 Amplifier Board via Software SPI ONLY.......................1265
APPENDIX S.....................................................................................................1266
  EEPROM Guide for GTR V1.0 Board..............................................................................1266
    Link to TWhite101 Instructable Guide called “BigTreeTech SKR Pro V1.1 or V1.2; Adding a EEPROM”............1267
    Link to TWhite101 Instructable Guide called “Correcting the Issue With On-board EEPROM 
      for the BTT GTR V1.0”....................................................................................1268
Index..........................................................................................................1269
```
---

## Web Sites to Help ReCalibrate or Calibrate Your 3D Printer

https://teachingtechyt.github.io/calibration.html?fbclid=IwAR2HwowLZs4jnP0RU1pVZ1TmMxYbvNhqFvoGKGzCXAyCB_HdcZDkemmTJhc#intro

https://3dpc.nl/

---
