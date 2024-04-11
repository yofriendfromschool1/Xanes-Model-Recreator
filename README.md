# Xanes-Model-Recreator
Archive of Xanes Model Recreator just incase all creds to Xanes/xanem1
After Hyperion was introduced and Synapse X stopped working, there wasn't a good way to save simpler models (tools, accessories, and furniture). Since I wanted to continue saving things as RBXM and OBJ files through Studio, I wrote this script for my personal use. I think it could be useful to others, so it's now public!

This script converts most instance classes relevant to model/asset rips into a series of JSON files, which can be used to recreate the original instances when their contents are pasted into the companion Roblox Studio plugin! PLEASE DOWNLOAD THAT HERE: https://www.dropbox.com/scl/fi/xrv2mx9gpjlvks3vnisz4/XMDLRecreator_ImportTool.rbxm?rlkey=ltv22ona3z1r1uxz946zw9mdy&dl=0

This script has three _G settings, which I recommend defining before executing the script. You may get an error if you don't make _G.PageLength and _G.AntiLagInterval, which are number variables, and _G.SkipPreSaveVerify, a boolean value. See the description at the top of the script (linked in the LoadString script here) for details about what they are.

STEPS (IN-GAME)
1. Execute this script, and a button will appear at the top of the screen. Tap on it to open the capturing GUI!
2. Tap on a container (workspace, ReplicatedStorage, etc.) at the top of the window, then wait until all instances have been indexed.
3. A neat, indented list of the instances within that container will be shown. Tap on an instance's icon to select it. (To look at the object, tap the camera button, and right-click/long tap it to return to your character.). Don't select children! Just choose models, as their children will be automatically exported with them.
4 (optional). Feel free to tap on another container and select instances from any of them; The script will remember everything you've selected until you close the GUI using the top button.
5. Enter a name for your export in the textbox, then tap the "save" button to its right to start capturing any instances that still exist.

STEPS (PLUGIN)
1. Install the companion plugin by placing the .rbxm file in your plugins folder. (Go to plugins > Plugin folder in Studio to see it.).
2. Close your current place then re-open it; An undocked window will appear.
3. Transfer your exported JSON files from your executor's "workspace" folder to a folder on your PC.
4. Open all of the JSON files named after the export, then copy and paste their contents into the plugin's text box when it requests them. (It asks for _header then each _piece# file.)
5. Change your import settings as needed, then click the "Start" button at the top.
6. If nothing went wrong, your exported model (and other instances) should be placed in a Model within the container that you captured it from. (For now, all instances from Players are put in StarterGui.)
7. Repeat all of these steps to capture and import another model!

Q&A
Q: Why are there holes (or missing terrain) in my geometry?
A: Unfortunately, I don't know how to read and write terrain, so it isn't saved yet. Most holes are caused by unions, which can't be separated, so I can't save the steps to reconstruct them with the plugin. (It's Roblox's limited API!)

Q: A decal/texture is missing!
A: Usually, decals and textures are included in exports, but are usually always applied to the "front" surface for some reason. Select the affected part and manually fix the incorrectly-placed images yourself.

Q: I saved instances in Lighting, but the effects haven't activated!
A: All lighting instances are put in a Model by default for organization. Open Lighting and press CTRL+U while selecting the model to move its contents out into the container itself, which should cause things to look correct.

Q: The script stopped working while "trying to get a reference" or saving instances.
A: Oh no, my iffy scripting has failed you! Please press F9 or type "/console" in chat, scroll to the bottom, and leave a comment with the error message and the game/place you were trying to save instances from and I'll look into it (if my brain is alive by then).
