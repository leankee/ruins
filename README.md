# Ruins
A repository for the Portal 2 mappack that offers an exciting journey through the ruined parts of Aperture Science.<br/>
You will face interesting puzzles, explore the consequences of the destruction caused by GLaDOS' absence, and strive for freedom from this dark scientific realm of testing!
### Synopsis
You assume the role of one of the test subjects who survived after the Relaxation Center shutdown. Your goal is to escape from the Enrichment Center, and to achieve it you will have to go through a testing track that shows the gradual destruction of Aperture Science after the death of GLaDOS.
## How to work with it
### Installation
First of all you have to install [Github Desktop](https://desktop.github.com/) and clone repository to your Portal 2 directory:
```
<Steam install location>/steamapps/common/Portal 2/
```
Then you have to add ```Game				ruins/ruins``` line to `SearchPaths` of `gameinfo.txt` located in:
```
<Steam install location>/steamapps/common/Portal 2/portal2/gameinfo.txt
```
For example your `gameinfo.txt` may look like this:
```
"GameInfo"
{
	game 		"PORTAL 2"
	title 		"PORTAL 2"
	GameData	"portal2.fgd"
	gamelogo 	1

	SupportsDX8     0
	SupportsXbox360 1

	FileSystem
	{
		SteamAppId				620		// This will mount all the GCFs we need (240=CS:S, 220=HL2).
		ToolsAppId				211		// Tools will load this (ie: source SDK caches) to get things like materials\debug, materials\editor, etc.
		
		//
		// The code that loads this file automatically does a few things here:
		//
		// 1. For each "Game" search path, it adds a "GameBin" path, in <dir>\bin
		// 2. For each "Game" search path, it adds another "Game" path in front of it with _<langage> at the end.
		//    For example: c:\hl2\cstrike on a french machine would get a c:\hl2\cstrike_french path added to it.
		// 3. For the first "Game" search path, it adds a search path called "MOD".
		// 4. For the first "Game" search path, it adds a search path called "DEFAULT_WRITE_PATH".
		//

		//
		// Search paths are relative to the base directory, which is where hl2.exe is found.
		//
		// |gameinfo_path| points at the directory where gameinfo.txt is.
		// We always want to mount that directory relative to gameinfo.txt, so
		// people can mount stuff in c:\mymod, and the main game resources are in
		// someplace like c:\program files\valve\steam\steamapps\half-life 2.
		//

		SearchPaths
		{
			Game				|gameinfo_path|.
			Game				ruins/ruins
		}
	}
}
```
### Directories
This repository contains the following directories:
- `ruins` - contains custom assets, such as materials, models, sounds and etc;
- `sdk_content/maps` - contains maps sources;
- `docs` - contains documentation files.

The `maps` directory of `sdk_content` contains following:
- `examples` - contains map examples, such as style examples, asset park and etc;
- `instances` - contains intances/prefabs for maps;
- `puzzlemaker` - contains puzzle maps exported from [Portal 2 Puzzle Maker](https://developer.valvesoftware.com/wiki/Portal_2_Puzzle_Maker);
- `ruins` - contains main maps sources.
