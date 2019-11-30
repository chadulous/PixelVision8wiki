# Parsing System Data

The `data.json` file is perhaps the most important file in the load process. It contains all of the settings for each chip, which in turn defines the system limitations of your PV8 game. The `data.json` defines how the actual engine and the rest of the files are loaded into memory. This file is responsible for everything that makes your game’s system specs unique. 

Here is a sample of what a typical data.json file looks like:

`{`

    "ColorChip":
    {
        "total":16,
        "maxColors":128,
        "backgroundColor":0,
        "maskColor":"#FF00FF",
        "unique":false,
        "debug":false,
        
    },
    "DisplayChip":
    {
        "width":264,
        "height":248,
        "overscanX":1,
        "overscanY":1,
        "layers":6
        
    },
    "FontChip":
    {
    },
    "GameChip":
    {
        "lockSpecs":false,
        "maxSize":512,
        "saveSlots":8
    },
    "MusicChip":
    {
        "totalSongs":32,
        "notesPerTrack":127,
        "totalPatterns":24,
        "totalLoop":24
    },
    "SoundChip":
    {
        "totalChannels":5,
        "totalSounds":32,
        "channelTypes":[-1,-1,-1,-1,-1]
    },
    
    "SpriteChip":{
        "maxSpriteCount":0,
        "unique":false,
        "spriteWidth":8,
        "spriteHeight":8,
        "pages":8,
        "cps":8
    },
    "TilemapChip":
    {
        "columns":256,
        "rows":256,
        "totalFlags":16,
        "autoImport":false,
        
    }
`}`

Each block of data in the `.json` file defines a chip for the engine to initialize and its settings. Let’s take a look at the `SpriteChip `and how it gets serialized. The first line of the JSON object is the chip’s name: 

    "SpriteChip": {

When this file is parsed by the engine, the `ChipManager `automatically looks for an instance of a specific chip by name. Next, are properties that can be configured on the chip. Only a handful of properties can be defined in the `.json` file. Here are the four main properties of the `SpriteChip`:  

`"maxSpriteCount":0,`
`"unique":false,`
`"spriteWidth":8,`
`"spriteHeight":8,`
`"pages":8,`
`"cps":8`

After the chip’s properties are deserialized, they are passed to a special method built into Pixel Vision 8’s importer that goes through the values for each property and sets them. In this chip, you can change the size of sprites system-wide, as well as the memory size where sprites are stored. By default, sprite RAM can store 16 columns and 16 rows of sprites for a total of 256 sprites per page.

While you can manually change values in this file, it’s best not to do so unless you know exactly what you are doing. The underlying engine that runs PV8 is incredibly flexible and tries to account for all kinds of customizations but it’s best to use caution when modifying this file.
