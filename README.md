# RGB_Compress

### A new way to compress/decompress RGB images

## No Loss Version 
Works by analyzing which colors are in an image. This creates a color spectrum. The length of the spectrum is given by a number that indicates the amount of colors (16,000,000 possible colors).
After that, each color gets assigned a number in binary; the length of this number is determined by the number of colors (longest 24 bits if all 16,000,000 colors are in one image). At last the whole binary "number" will be converted to one Base32hex following RFC 4648 number and stored in a .pic file which can be interpreted as an ordanary .txt file.

16.000.000 in Base32Hex: 1GQG0 (with UTF-8 4 byte)

![grafik](https://github.com/user-attachments/assets/1204dd5c-9c70-4555-827a-8c66d3771111)


## Alternate version
Uses an algorithm, which takes pixels with similar RGB values and connects them (image quality may be lost).

Example:
[20,40,50] and [22,38,51] will be combined to [21,39,50]
