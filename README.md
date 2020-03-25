# ModCheck

Update of Nightinggales mod for RimWorld 1.1
https://steamcommunity.com/sharedfiles/filedetails/?id=1544705976

[img]https://raw.githubusercontent.com/emipa606/RimWorld-Wrapper/master/Notice.png[/img]

Support-chat:
https://discord.gg/SuhwVpM

Non-steam version:
https://github.com/emipa606/ModCheck
	
--- Original Description ---
Toolkit for xml modders. Adds 13 new patch operations. Eliminate the need for patchmods. Patch according to presence, order or version of mods. Reorder xml elements, write patching results and test results to the log. Allow faster patching (shorter startup time) and measure how long each patch spends patching.

The primary task for ModCheck is to remove the need for patch mods. It's done by adding test operations, which can tell if another mod is loaded, if one mod is before another, is of at least a certain version, either in About or in ModSync. Each of those can be reversed (not loaded etc).

Adds logic operators, like sequence, AND, OR, If else conditions. This can be used together with the test operations or vanilla operations to make complex test conditions if needed.

Boost performance. Need to do multiple patching operations on the same building? Search, keep the result and run a list of patches without performing a full xpath search for each operation.

Added a bed and want it to appear in the build menu next to the vanilla beds? The Move operation allows you to alter where your modded building will appear.

Feature rich log writing. Get operations to write messages, warnings and errors if operations succeed or fail. Tell the user if a needed mod isn't loaded or load order is incorrect. Also allow writing conditionless with whatever message you might want to add.

Profile patches. Measure how much time is spend on each patch. ModCheck is aware of which mod owns which patch, meaning you can get a precise view of the startup time of your mod. You can name your patches if root operation is from ModCheck, like ModCheck.Sequence. This will allow performance printout with names rather than just patch 1,2,3....


Forum Thread[ludeon.com]
GitHub[github.com]
Manual of each operation[github.com]

Mod Load Order:
In most cases this doesn't matter, but early is recommended.

The only problem with load order comes from mods including an outdated version of ModCheck. If that is the case, then the newest version of ModCheck needs to be first. If this happens, then ModCheck will provide an error, which should make the issue easy to fix, both for players and mod creators.

Changelog:
Updating ModCheck will not break existing xml files unless stated otherwise.

v1.8.1
- Fixed compatibility issue with updated Rimworld. Profiling works again.
- Updated version URL for Fluffy's Mod Manager

v1.8 (RW 1.0)
Update to about only. The DLL file will not even have to be updated.

- RimWorld 1.0 support
- Added support for Fluffy's Mod Manager

v1.8
This is a significant update from a coding point of view. B19 vanilla changed completely regarding patching.
While the code is significantly better, all Harmony calls from ModCheck had to be redesigned and rewritten.

- Added B19 support
- Added Search operation to speed up patching when the same object is patched multiple times in a row
- Added Move operation to control cases where order matters (like order of building buttons)
- Patch profiling now measures the time more accurately (less rounding errors)

XML BREAKING ALERT!!!
Removed FindFile operation (vanilla rewrite renders it both obsolete and impossible to implement)
Any xml file with FindFile will need updating.


Earlier versions mentioned in the B18 mod page
