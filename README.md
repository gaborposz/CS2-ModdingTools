# CS2-ModdingTools
Helper utilities for Cities Skylines 2 modding

## Features
### Automatic debugging of mods
It automatically enables Unity debugging in Debug build. For this 
- Unity Debug binaries and .pdb files are copied to the game's directory
- Debugging is enabled in the game's boot.config file

After these steps you can attach the Unity Debugger to the game (localhost) 
and debug the code of your mod.

In Release and Clean builds these steps are reverted to disable debugging.

> Please note that when you switch from Debug to Release (or vice versa) then 
the steps above might not be triggered if the sources have not changed since the last build.
In this case run a Rebuild (Clean + Build) to ensure that debugging is disabled/enabled.

## How to install
Simple reference the latest version of the CS-ModdingTools NuGet package 
from your Cities Skylines 2 modding project.
It is a build only dependency, i.e. it does not deploy anything to your project,
just adds MsBuild target files to customize build process.

## Troubleshooting
### CS2 modding is not available
`The Cities Skylines 2 and Unity installation paths are not set. Make sure you that you are using CS2-ModdingTools from a CS2 modding project!`

This error is displayed if the Cities Skylines 2 modding prop and target files are not available.
Make sure that modding is sucessfully installed in the game (see in the Options / Modding menu),
and that you have referenced the CS2-ModdingTools from a CS2 modding project.

### Missing game folder
`The Cities Skylines 2 folder (...) was not found!`

This error is displayed if modding libraries are available, 
but the game folder (`$(ManagedPath)`) is not found on the disk.
Make sure that modding is sucessfully installed in the game (see in the Options / Modding menu).
You can also override this path by the CSII_MANAGEDPATH environment variable.

### Missing Unity folder
`The Unity folder (...) was not found!`

You get this error if the Unity version that is used by the game is not available.
Make sure that modding is sucessfully installed in the game (see in the Options / Modding menu).
You can also override this path by the CSII_UNITYFOLDER environment variable.

## Feedback and contribution
Feel free to provide feedback (bug reports, feature requests, etc.) 
by creating a new GitHub Issue in the repository.

If you want to contribute then please fork the repo, 
and create a new Pull Request from your local branch.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.