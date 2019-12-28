# Sprites

When games load, the engine looks for a `sprite.png` to process. The `sprite.png` can be used to load sprite data into memory and is made available as an option for those using external image editors to work on their graphics. The PNG file is cut up into 8x8 chunks of pixel data, which represent individual sprites in memory. Since sprites are simply collections of pixel data that reference a color, the system attempts to match those colors to IDs that exist in the system’s `ColorChip`. It’s critical that the colors in your `sprite.png` match up to the same colors found in the `color.png` for the importer to work. Once the importer is done converting a sprite's pixel data; the `SpriteChip` stores the compressed data in a memory slot which becomes its ID.

