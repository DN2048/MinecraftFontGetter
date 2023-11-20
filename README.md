# mcjarfontgetter

Extracts the "Mojangles" font from a Minecraft .jar file.  
To use, open makefont.html in a browser (as long as it isn't Internet Explorer or Microsoft Edge) and choose the Minecraft .jar file in the file input.  

## How to get a Minecraft .jar file

First, go to your computer's Minecraft directory. The default Minecraft directory is:

Windows: `C:/Users/username_here/AppData/Roaming/.minecraft`  
macOS: `/Users/username_here/Library/Application Support/minecraft`  
Linux: `/home/username_here/.minecraft`  
replacing `username_here` with your username. May include hidden files.

Alternatively, go to the resource pack folder's parent directory. The resource pack folder is accessible from Minecraft's resource pack options.

Once you are in the Minecraft directory, navigate to `/versions/1.20.1/1.20.1.jar`  
replacing `1.20.1` with the Minecraft version you want to extract the font from.

This is the Minecraft .jar file.

If a valid .jar file is selected, you'll get an OTF file with the extracted glyphs to download.

## Notes

Left-aligned glyphs are the default in-game. The glyphs are stored in a table in a PNG file and each one uses 8x8 pixels.
Any right columns of empty pixels in this 8x8 grid after the last column with any filled pixel are considered not used. Meaning that the font is NOT monospaced. The game also does this and adds an extra column (character padding) and row (line padding) of empty pixels to all glyphs, making them 9x9 pixels in-game (plus the multipliers). This is why the glyph for " i " for example, only uses 1x8 pixels in-game (2x9 with the padding. The line padding can be bigger like on Signs).

Using the center-alinged, all glyphs will be centered in a 8x8 grid making the font monospaced. This doesn't happen in-game.

## Libraries used

Uses code from [opentype.js](https://github.com/opentypejs/opentype.js), [jszip](https://github.com/Stuk/jszip), and [UPNG.js](https://github.com/photopea/UPNG.js).
