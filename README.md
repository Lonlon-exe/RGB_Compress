# RGB_Compress
A new way to compress/decompress RGB images
Works by analyzing which colors are in an image. Using the data, a color table is created. The length of this table is a binary number (24 bits long to secure that every color could be transmitted (16,000,000 possible colors)).
After that, each color gets assigned a number in binary; the length of this number is determined by the number of colors (longest 24 bits if all 16,000,000 colors are in one image).

Alternate version
Uses an algorithm, which takes pixels with similar RGB values and connects them (image quality may be lost).
