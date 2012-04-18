TiledSharp
==========
A .NET C# library for importing Tiled TMX tile maps

About TiledSharp
----------------
TiledSharp is a .NET C# library for importing [TMX] tilemaps and TSX tilesets
generated by [Tiled], a tile map generation tool. The data is saved as a
[Map] object, whose structure closely resembles the original TMX file.

As a generic TMX and TSX parser, TiledSharp does not use any XNA Game Studio
libraries. However, it can be used as an interface between TMX data and XNA
games or libraries.

Usage
-----
To import a TMX file into your C# application:

- Include a reference to TiledSharp, either as source or DLL.

- Import the TiledSharp namespace.

    ```csharp
    using TiledSharp;
    ```

- Create a Map object using the constructor.

    ```csharp
    var map = new Map("yourFile.tmx");
    ```
    
    TiledSharp supports both resource names and file paths, and should work as
    expected in most situations. For more details, please consult the wiki.

- Access the TMX data using the Map fields. Principal classes can be accessed
  by either name or index.

    ```csharp
    var map = new Map("yourFile.tmx");

    var version = map.version;
    var myTileset = map.tileset["myTileset"];
    var myLayer = map.layer[2];
    var hiddenChest = map.objectgroup["Chests"].object["hiddenChest"];
    ```

Map data fields correspond closely to the TMX file structure. For a complete
listing, see the [TiledSharp Data Hierarchy].
 
Although TiledSharp can handle objects with the same name, it is not
recommended. For more information, see the [TiledList] specification.

Notes
-----
TiledSharp parses XML files produced by [Tiled], an open-source (GPL) tile
map editor developed and maintained by Thorbjørn Lindeijer.

Zlib decompression in TiledSharp uses the Zlib implementation of [DotNetZip]
v1.9.1.8.

Licensing
---------
[TiledSharp] is distributed under the [Apache 2.0 License].

[DotNetZip] is distributed under the [Microsoft Public License][Ms-PL].

Contact
-------
Marshall Ward (<marshall.ward@gmail.com>)

[TiledSharp]: https://github.com/marshallward/TiledSharp
[Tiled]: http://mapeditor.org
[Map]: https://github.com/marshallward/TiledSharp/wiki/Map
[TMX]: https://github.com/bjorn/tiled/wiki/TMX-Map-Format
[TiledSharp Data Hierarchy]: https://github.com/marshallward/TiledSharp/wiki/TiledSharp-Data-Hierarchy
[TiledList]: https://github.com/marshallward/TiledSharp/wiki/TiledList
[DotNetZip]: http://dotnetzip.codeplex.com
[Apache 2.0 License]: http://www.apache.org/licenses/LICENSE-2.0.txt
[Ms-PL]: http://www.microsoft.com/en-us/openness/licenses.aspx#MPL
