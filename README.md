# 🎨 RGB_Compress

**A novel way to compress and decompress RGB (and RGBA) images.**

This project introduces a custom image compression format focused on color optimization and text-based storage. It supports both lossless and lossy modes, with easy Base32Hex output.

---

## 🔒 No-Loss Version (Lossless)

The lossless algorithm works by analyzing all **unique colors** in an image.

- A color palette (spectrum) is created.
- Each pixel is stored as a binary index pointing to its color in the palette.
- The number of unique colors determines the bit length:
  - Example:  
    - 100 unique colors → 16 bits per pixel
    - 1023 unique colors -> 16 bitsperpixe
    - 16,777,215 unique RGB colors → 40 bits per pixel (max)

The final binary data is encoded using **Base32Hex** ([RFC 4648](https://datatracker.ietf.org/doc/html/rfc4648))  
and stored in a `.pict` file — a readable UTF-8 `.txt`-compatible format.

> **Example:**  
> `16,777,215` in Base32Hex = `FVVVV` → stored as 5 bytes in UTF-8

---

## 🎨 Alternate Version (Lossy)

The lossy variant reduces file size by merging similar RGB values:

- Pixels with nearly identical color values are averaged.
- This lowers the number of unique colors, enabling higher compression.

> **Example:**  
> `[20, 40, 50]` and `[22, 38, 51]` → `[21, 39, 50]`

This method also works with **RGBA** images.

---

## 📁 Output Format

All compressed images are saved as `.pic` files.  
These are Base32Hex-encoded and human-readable in text editors.
