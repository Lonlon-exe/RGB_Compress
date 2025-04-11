# RGB_Compress

### A new way to compress/decompress RGB images

## No Loss Version 
Works by analyzing which colors are in an image. Using the data, a color table is created. The length of this table is a binary number (24 bits long to secure that every color could be transmitted (16,000,000 possible colors)).
After that, each color gets assigned a number in binary; the length of this number is determined by the number of colors (longest 24 bits if all 16,000,000 colors are in one image). At last the whole binary "number" will be converted to one Base32hex number and stored in a .pic file which can be interpreted as an ordanary .txt file.

## Alternate version
Uses an algorithm, which takes pixels with similar RGB values and connects them (image quality may be lost).

Example:
[20,40,50] and [22,38,51] will be combined to [21,39,50]
