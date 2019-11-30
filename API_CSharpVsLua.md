# C# vs Lua

The API documentation was designed to be used for creating C# or Lua games. If you are not familiar with one of the languages, this document contains some helpful hints when reading the documentation. 

## Data Structures

For the most part, C# and Lua share the same data structures such as string, int, and bool. Where C# and Lua differ are arrays and objects. Technically in Lua, there are only tables. These can act like objects or arrays. In C# there is no generic object type similar to Lua’s tables. The closest data structure would be a Dictionary.

In the documentation, you may see some of the following types. This chart will help you understand how Pixel Vision 8’s Lua interpreter converts them under the hood.

<table>
  <tr>
    <td>Type</td>
    <td>C#</td>
    <td>Lua</td>
    <td>Description</td>
  </tr>
  <tr>
    <td>int[]</td>
    <td>Array of integers</td>
    <td>Array (table) of integers </td>
    <td>This is commonly used when working with pixel data. PV8 uses 1D integer arrays to represent sprite pixel data.</td>
  </tr>
  <tr>
    <td>string[]</td>
    <td>Array of strings</td>
    <td>Array (table) of strings</td>
    <td>This is commonly used in text manipulation.</td>
  </tr>
  <tr>
    <td>Dictionary</td>
    <td>Dictionary</td>
    <td>Table</td>
    <td>Both data structures use strings for keys. In C# the value will be of a fixed type whereas Lua allows for mixing and matching types for each key’s value.</td>
  </tr>
  <tr>
    <td>Point</td>
    <td>Point</td>
    <td>Point</td>
    <td>While you can use the C# Point class in Lua, you will need to call CreatePoint() to get a new instance. The same API works in C# but you can use new Point() as well.</td>
  </tr>
  <tr>
    <td>Rect</td>
    <td>Rect</td>
    <td>Rect</td>
    <td>Similar to the Point class in Lua, you will need to call CreateRect() to get a new instance. The same API works in C# but you can use new Rect() as well.</td>
  </tr>
</table>


## Numbers

Both C# and Lua support multiple number types. Pixel Vision 8 on the other hand, uses integers internally. That means that in C# you’ll need to pass in integers to any API that accepts a number value. In Lua, you don’t have to convert the type, since the language doesn’t have explicit types. The one thing to keep in mind is that Pixel Vision 8’s APIs will always return integers. While you are welcome to use non-integer values in your game, you’ll want to pay attention to the removal of any fractions when a PV8 API returns a number.

The most common example of this is trying to keep track of an entity’s position. Pixel Vision 8 will for that position to "snap" to the gid since the geometry primitives, Point and Rectangle, use integers. You can track sub-pixel movement outside of Pixel Vision 8’s own data structures, just be sure to convert them to integers before applying them back to the entity’s draw call. You can use math.floor() in Lua or cast the number to int in C#.

The only place where PV8 uses float is in the update’s `timeDelta` argument. Since this is supplied externally by MonoGame, which PV8 runs on top of, it’s the only instance of where a float is used in the SDK.

## Array Index

Perhaps the biggest difference between C# and Lua are array indexes. C# is zero based and Lua is one based. That means you’ll need to manage to convert between the two by hand. Pure C# APIs that are exposed to Lua will be zero-based. When reading data structures in Lua, even ones returned by C#, you’ll use one-based indexing. This is probably one of the most common causes of bugs, especially when porting from Lua to C#.

The documentation will comment on when an API is zero-based regardless of language. API calls to colors, sprites, tiles, etc will all start at 0. For example, if you have 256 sprites, the first sprite ID will be 0 and the last will be 255. This works the same in C# and Lua. However, if you call Colors(), which returns a string array of the system’s colors, in C# you’ll access the first color at 0 and in Lua at 1.

## Null

In C#, an empty value is usually defined as null. In Lua, the equivalent is nil. Pixel Vision 8’s Lua interpreter automatically converts between the types based on which side of the engine the call is made from.

## Optional Arguments

Pixel Vision 8’s APIs may contain optional arguments. In C# these may appear with a question mark next to the type. The documentation will mention if an argument is optional or not and what default value it will use when not supplied. In cases where there are multiple optional arguments, you can use null in C# or nil in Lua to have the default value or behavior applied.

Keep in mind that some APIs have different functionality based on if an argument is provided or not. For example, calling Sprite(0) will return the pixel data for the first sprite. If you supply the optional value, an int array, it will update the first sprite’s pixel data and return the new pixel data int array.

 

