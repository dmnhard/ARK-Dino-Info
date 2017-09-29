# ARK-Dino-Info

Author: dmnhard

*** Description
This is set of scripts to:
- Extract info about tamed and wild creatures from ARK save-files to XML-files.
- Create reports in Excel - all tamed and wild dinos on map and their stats.
- Create maps with location of dinos.


*** Downloading
https://github.com/dmnhard/ARK-Dino-Info/blob/master/ARK-Dino-Info.zip

*** Configuring
1. Configure Configs\Config.txt:
   Set SavePath to location of your save-file.
   By default it is C:\Program Files (x86)\Steam\steamapps\common\ARK\ShooterGame\Saved\SavedArksLocal\TheIsland.ark

   Set BaseLat and BaseLon to your base location. 
   It is used to calculate distance and direction to creatures relatively to your base.

   Set MapTemplate = name of file in MapTemplates folder.

   Set MapsConfigSource = txt to read maps config from Configs\MapsConfig.txt.
   Or set MapsConfigSource = excel to read maps config from ARK-Dino-Info.xlsx.

2. Add unnecessary creatures classes to Configs\ExcludeClasses.txt.
   See https://ark.gamepedia.com/Creature_IDs - "Entity ID" column.
   This is intended to speed up the data refresh in the Excel file.

3. Run FixExcel.cmd to fix absolute path to XML files in Excel file.

4. Configure required maps in ARK-Dino-Info.xlsx on "Maps Config" sheet or in Configs\MapsConfig.txt.
   Maps with # symbol at the beginning will not be generated.

5. Currently, only "The Island" map template is configured (in MapTemplates folder).
   For other maps you can create a config yourself.
   See MapTemplates\ARK-KronixCustomMap33.jpg.txt for details.
   Config name for map must be Map_File_Name+.txt eg ARK-KronixCustomMap33.jpg.txt.


*** Usage

Run _Update_All.cmd

Result:
- list of tamed and wild creatures in "ARK-Dino-Info.xlsx" (select any cell with data and press Alt+F5 to update data)
- maps in "Maps" folder


*** Notes
The application was tested under the following conditions:
- Windows 7 x64
- Excel 2010
- Saves from Single Player mode 
- "The Island" map
- App do not work if placed on network share

Maps config currently configured for max creature level 300 (OverrideOfficialDifficulty=10.0)


*** Used 3rd party tools, libs and other stuff
- ark-tools (https://github.com/Qowyn)
- Json.NET (http://www.newtonsoft.com/json)
- DocumentFormat.OpenXml
- Custom Map by Kronix, edited by PiTi (a-calc.de)


*** History

0.2:
- Maps are created in JPEG format
- Using DocumentFormat.OpenXml to read maps config from Excel. Removed dependency on "Microsoft Access Database Engine 2010". 
