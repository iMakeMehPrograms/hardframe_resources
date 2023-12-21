# Retroframe: Your perfect bitmap font! #
## What is Retroframe? ##
Retroframe is an unlicensed bitmap font for use in any software. This here .md file is so you can create an implementation to use it (or just to see what it is about).

## Why would you use Retroframe? ##
Put simply: Because bitmap fonts are easy to implement and use! (Especially with software like OpenGL!)

## How can I implement a reader for Retroframe? ##
If you are using the hardframe framework, there should be an implementation for you (depending on when you read this). If not, then here are some things to know:
- There is one pixel of padding on each letter making them 10x10 with full padding and 8x8 without. I would recommend having a dynamic padding system where you can remove or keep top, bottom, left, and right but it is up to preference.
- The empty space is transparent pixels
- The control characters (0-31 and 127) should not be rendered. (Unless you want to) They are for debugging or extra information.
- The font is white and red (red for control characters only), so you can tint it any color you want. (I would recommend having a x0.5 underlay with an offset for softer shadows)
- And most importantly: The ```retroframe_standard``` files only cover characters 0-127 (aka 1-128) of the ASCII standard. This is also the same as UTF-8. These characters are organized in ascending order, left to right and up to down.
- The ```retroframe_special``` file does not follow any worldwide standard. It is there for text-based shenanigans in hardframe. The standard for it will be covered later in this file. It has some overlap with the extended ASCII set but it is mostly different.
- ```retroframe_extended``` will cover the next 128 characters of _ASCII_. NOT UTF8. UTF8 has difficult-to-implement control characters with flexible accenting that do not mix well with the limited amount of pixels present in the font; thus it only does ASCII. The extended ASCII standard also contains some accented characters so it should do most languages (with the latin alphabet).

## You mentioned ```retroframe_special```. What is the standard for it? ##
As follows:

### Pointers ###
- 0 (128): Text Cursor
- 1 (129): Dashed Cursor
- 2 (130): Pointer
- 3 (131): Hand Pointer

### Box Art ###
Single:
- 4 (132): Single L-R
- 5 (133): Single U-D
- 6 (134): Single L-U
- 7 (135): Single U-R
- 8 (136): Single R-D
- 9 (137): Single D-L
- 10 (138): Single L-U-R
- 11 (139): Single U-R-D
- 12 (140): Single R-D-L
- 13 (141): Single U-L-D
- 14 (142): Single Cross
- 15 (143): Single Box

Double:
- 16 (144): Double L-R
- 17 (145): Double U-D
- 18 (146): Double L-U
- 19 (147): Double U-R
- 20 (148): Double R-D
- 21 (149): Double D-L
- 22 (150): Double L-U-R
- 23 (151): Double U-R-D
- 24 (152): Double R-D-L
- 25 (153): Double U-L-D
- 26 (154): Double Cross
- 27 (155): Double Box

### Dither Blocks ###
- 28 (156): Filled Block
- 29 (157): Dither Pattern A
- 30 (157): Dither Pattern B
- 31 (158): Half Dither L
- 32 (159): Half Dither R
- 33 (160): Half Dither U
- 34 (161): Half Dither D

### Shapes ###
- 35 (162): Circle
- 36 (163): Diamond
- 37 (164): Triangle L
- 38 (165): Triangle R
- 39 (166): Triangle U
- 40 (167): Triangle D
- 41 (168): Oval L-R
- 42 (169): Oval U-D
- 43 (170): Heart

### Symbols & Objects ###
- 44 (171): Alarm
- 45 (172): Pine Tree
- 46 (173): Tree
- 47 (174): Pistol R
- 48 (175): Pistol L
