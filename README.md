Overview and Warning: 
=====

This library was originally created to experiement with the FlexIO capabilities of the new Teensy 4 board and
will also support the Teensy 4.1


This program is free software: you can redistribute it and/or modify it 

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. 


Details on FlexIO
====================

See chapter 49 of the IMXRT1060RM manual which you can download from the PJRC website:
https://www.pjrc.com/teensy/datasheets.html

There are more discussions about FlexIO up on the PJRC forum, including:
https://forum.pjrc.com/threads/58228-T4-FlexIO-Looking-back-at-my-T4-beta-testing-library-FlexIO_t4


FlexIO pins on T4 and T4.1
==========================

The Teensy 4 (ARDUINO_TEENSY40) has the following Flex IO pins defined:
-------------

Note: I have these tables in Teensy pin number order,  It may also be interesting to also have
a version with FlexIO pin order, as at some point I will experiment with parallel pin IO..

FlexIO 1 - The three rows are: Teensy pin, Flex IO pin, and MUX setting for that pin:
```
    2,       3,    4,    5,  33,
    4,       5,    6,    8,  7, 
    0x14, 0x14, 0x14, 0x14, 0x14
```    

FlexIO 2 
```
    6,       7,    8,    9,  10,    11,   12,   13,   32, 
    10,     17,   16,   11,  0,      2,    1,    3,   12, 
    0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 
```

FlexIO 3 - Note Flex IO 3 does not have DMA support
```
    7,       8,   14,   15,   16,   17,   18,   19,   20,  21,    22,   23,   26,   27,   
    17,     16,    2,    3,    7,    6,    1,    0,   10,   11,    8,    9,   14,   15,    
    0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19,
```

The Teensy 4.1 (ARDUINO_TEENSY41) Will have additional IO pins.  
-------------
**FlexIO 1** - The three rows are: Teensy pin, Flex IO pin, and MUX setting for that pin:
```
    2,       3,    4,    5,  33,    49,   50,   52,   54
    4,       5,    6,    8,  7,     13,   14,   12,   15
    0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14
```    
Ranges: 4-8,12-15

**FlexIO 2** 
```
    6,       7,    8,    9,  10,    11,   12,   13,   32,   34,   35,   36,   37
    10,     17,   16,   11,  0,      2,    1,    3,   12,   29,   28,   18,   19
    0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14
```
So have bit ranges 0-3, 10-12, 16-19, 28-29

**FlexIO 3** - Note Flex IO 3 does not have DMA support
```
    7,       8,   14,   15,   16,   17,   18,   19,   20,  21,    22,   23,   26,   27,   34,   35,   36,   37,   38,   39,   40,   41
    17,     16,    2,    3,    7,    6,    1,    0,   10,   11,    8,    9,   14,   15,   29,   28,   18,   19,   12,   13,    4,    5 
    0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19 
```
Have ranges: 0-19, 28-29

The Teensy Sparkfun MicroMod (ARDUINO_TEENSY_MICROMOD) is sort of a cross between T4 and T4.1, but has additional pins on FlexIO 2  
-------------

**FlexIO 1** - The three rows are: Teensy pin, Flex IO pin, and MUX setting for that pin:
```
    2,       3,    4,    5,  33,  0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff,
    4,       5,    6,    8,  7,   0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff,
    0x14, 0x14, 0x14, 0x14, 0x14, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff, 0xff,
```    
Ranges: 4-8

**FlexIO 2** 
```
    6,       7,    8,    9,  10,    11,   12,   13,   32,   40,   41,   42,   43,   44,   45,
    10,     17,   16,   11,  0,      2,    1,    3,   12,    4,    5,    6,    7,    8,    9,
    0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14, 0x14,
```
So have bit ranges 0-12, 16-17

**FlexIO 3** - Note Flex IO 3 does not have DMA support
```
    7,       8,   14,   15,   16,   17,   18,   19,   20,  21,    22,   23,   26,   27, 0xff,   
    17,     16,    2,    3,    7,    6,    1,    0,   10,   11,    8,    9,   14,   15, 0xff,    
    0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0x19, 0xff,
```
Have ranges: 0-3,6-11,14-17

Library details
===============
<to be filled in>

Examples:
---------


Future Updates
==============


Again WIP
=====
