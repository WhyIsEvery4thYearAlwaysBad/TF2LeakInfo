# Disclaimer

Please note that this documentation is unfinished, and descriptions may not be 100% correct. If you feel that these explanations are wrong, please tell me through the issues section!

Also note that some of the launch options may not neccessarily be in TF2 itself, but rather it's utility programs. I'll make a separate section for those after I am finished with all the launch options in TF2 itself.

# Core Game (hl2.exe)

## Processing

* `-yieldcycles` - Forces the Game Manager to yield execution after updating. Useful for running 2 instances of the same game.

* `-enable_keyvalues_cache` - Enables the KV cache. This launch option is disabled because "players used it to bypass sv_pure 1". Comment is mentioned in hl2_src/tier1/KeyValues.cpp @ lines 660-683.

* `-sv_pure_verify_hashes` - Recalculate VPK hashes after enabling whitelist file tracking if sv_pure is set. Only works in dedicated servers.

## Memory

* `-no_gpu_buffer_allocator` (![Xbox 360](assets/360logo.png) only) - Disables allocations of memory pools in the GPU Buffer. Only works on Xbox 360.

## Graphics

* `-caps_noclipplanes` - Makes CAPSLOCK toggle clip planes between on and off. Only works if GLMDEBUG is defined.

* `-disablemaxvertexshaderconstanthints` - Maximum vertex shader constant hints is set to 256 and doesn't change.

### DirectX

* `-disable_d3d9_hacks` - Disables the following D3D9 hacks: 
	* "CENT" - causes flashlight passes to appear brighter on NVidia drivers.

### OpenGL

* `-glmenablefakesrgb` - Force the simulation of sRGB mode.

* `-glmnosystemcheck` (![OS X](assets/osxlogo.png) only) - Bypasses the forbidden Graphics Processor check for GMA950, X3100, or NV G7x cards, and the version check for OS X 10.6.7 or later.

* `-glmenableclipplanes` and `-glmdisableclipplanes` - Force enable/disable clip planes for OpenGL.

* `-glmenabletrustblit` and `-glmdisabletrustblit` - Force enable or disable trusted blitting.

* `-glmenableperfpackage` and `-glmdisableperfpackage` (![OS X](assets/osxlogo.png)![and Linux](assets/linuxlogo.png) only) - Force enable/disable certain OpenGL optimizations on Unix.

* `-gl_enable_scaled_resolve` (![OS X](assets/osxlogo.png) only) - Enable Scaled Resolve if the OS X version has SLGU and is newer than 10.7.0. Versions prior to 10.6.5 do not have Scaled Resolve, and later versions determine Scaled Resolve support through the `GL_EXT_framebuffer_multisample_blit_scaled` string.

* `-gl_force_enable_scaled_resolve` - Force enable Scaled Resolve.

Note that the *activation* of Scaled Resolve is tied to the convars `gl_minify_resolve_mode` and `gl_magnify_resolve_mode`.

* `-glmenablemallocworkaround` and `-glmdisablemallocworkaround` (![OS X](assets/osxlogo.png) only) - Enable/Disable a workaround to a GLSL memory allocation bug in the Intel HD4000 OpenGL driver on OS X 10.8 (aka Mountain Lion).

* `-gl_time_shader_compiles` - Keeps track of total cycle count spent on shader compiles.

* `-gl_validate_shader_early` - "Check shader validity at creation time.  This will cause the driver to not be able to multi-thread/defer shader compiles, but it is useful for getting error messages on the shader when it is compiled." (Comment located in hl2_src/togl/linuxwin/cglmprogram.cpp @ lines 479-481.)

* `-glslcontrolflow` (![OS X](assets/osxlogo.png) only) - Enables static control flow support.

* `-noglslcontrolflow` - Disables static control flow support.

## Audio

* `-forcesound` - Forces sound initialization routine regardless if the game is running on Source Dedicated Server (srcDS).

* `-audiolanguage <string>` - Sets audio language based on \<string\>.

* `-snd_openal` (![OS X](assets/osxlogo.png) only) - Forces the game to use OpenAL instead of AudioQueue.

## Video

* `-noquicktime` - Disables QuickTime initalization routine.

## SDL

* `-nonquerty` (![OS X](assets/osxlogo.png) only) - Use the keyname to workout the scan code when handling key input. This is an experimental feature.

* `-exclusivefs` (![OS X](assets/osxlogo.png) only) - Tells the game to minimize the window if the player is in fullscreen mode and the player does the Cmd-Tab key combination.

* `-displayindex <value>` - Sets display index to \<value\>. Only works if USE_SDL is defined and SWDS is not defined.

## Misc
* `-menupaintduringinit` - Forces the main menu override to immediately perform paint traversal when `CHudMainMenuOverride::PaintTraverse()` is called, instead of waiting until the main menu layout initialization routine is finished.

* `-gamestatsfileoutputonly` - Logs Valve match data after exiting the game in a Key-Value file named "gamestats.dat" in the tf folder, instead of uploading it to steam.
KVs:
	* IsPC - Client is on PC.
	* Version - Version of format which is currently "1".
	* srcid - ID to identify the user.
	* CPUID - ID of the client's CPU.
	* CPUGhz - Client CPU's clock speed in Ghz.
	* CPUModel - Model of the client's CPU.
	* CPUFeatures\<0-2\> - Client CPU features.
	* NumCores - Number of physical processors Source identifies in the client's CPU.
	* PhysicalRamMbTotal - Amount of total physical memory not taken up by the OS in Megabytes (or Mebibytes?).
	* PhysicalRamMbAvailable - Amount of free physical memory in Megabytes (or Mebibytes?).
	* VirtualRamMbTotal - Amount of total virtual memory not taken up by the OS in Megabytes (or Mebibytes?).
	* VirtualRamMbAvailable - Amount of free virtual memory in Megabytes (or Mebibytes?).
	* GPUDrv - Drive name of the GPU.
	* GPUVendor - ID of the GPU vendor.
	* GPUDeviceID - ID of the GPU.
	* GPUDriverVersion - GPU driver version.
	* DxLvl - Client's DXLevel.
	* Width - Client's width in resolution.
	* Height - Client's Height in resolution.
	* Windowed - Client's game is windowed.
	* MaxDxLevel - Maximum DXLevel accessible.
	* appid - Steam game id.
	* tf_configdata
		* QuickListBitField - Undocumented.
		* TextLanguage - Textual language set in steam.
		* AudioLanguage - Audio language set in steam.
		* CountryCode - Client's country location.
	* map - There will be multiple of these for every map you play.
		* mapname - The name of the map played.
	* playtime
		* TotalLevelTime - Amount of time spent in all maps played. *(todo: in what unit?)*
		* NumLevels - Number of maps played.
	* LoadTimeMap - Amount of time spent loading the map. *(todo: in what unit?)*