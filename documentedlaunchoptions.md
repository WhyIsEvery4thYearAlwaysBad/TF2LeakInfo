# Context

Please note that this documentation is unfinished, and descriptions may not be correct. If you feel that these explanations are wrong, please tell me!

Also note that some of the launch options may not neccessarily be in TF2 itself, but rather it's utility programs.

# Core Game (hl2.exe)

## Processing

* `-yieldcycles` - Forces the Game Manager to yield execution after updating. Useful for running 2 instances of the same game.

* `-enable_keyvalues_cache` - Enables the KV cache. This launch option is disabled, because players used it to bypass sv_pure 1. This is mentioned in hl2_src/tier1/KeyValues.cpp @ lines 660-683.

* `-sv_pure_verify_hashes` - Recalculate VPK hashes after enabling whitelist file tracking if sv_pure is set. Only works in dedicated servers.

## Memory

* `-no_gpu_buffer_allocator` - Disables allocations of memory pools in the GPU Buffer. Only works on Xbox 360.

## Graphics

* `-caps_noclipplanes` - Makes CAPSLOCK toggle clip planes between on and off. Only works if GLMDEBUG is defined.

* `-disablemaxvertexshaderconstanthints` - Maximum vertex shader constant hints is set to 256 and doesn't change.

### DirectX

* `-disable_d3d9_hacks` - Disables the following D3D9 hacks: 

	* "CENT" - causes flashlight passes to appear brighter on NVidia drivers.

### OpenGL

* `-glmenablefakesrgb` - Force the simulation of sRGB mode.

* `-glmnosystemcheck` - Bypasses the forbidden Graphics Processor check for GMA950, X3100, or NV G7x cards, and the version check for OS X 10.6.7 or later. Only works on OS X.

* `-glmenableclipplanes` and `-glmdisableclipplanes` - Force enable/disable clip planes for OpenGL.

* `-glmenabletrustblit` and `-glmdisabletrustblit` - Force enable or disable trusted blitting.

* `-glmenableperfpackage` and `-glmdisableperfpackage` - Force enable/disable certain OpenGL optimizations on Unix.

* `-gl_enable_scaled_resolve` - Enable Scaled Resolve if the OS X version has SLGU and is newer than 10.7.0. Versions prior to 10.6.5 do not have Scaled Resolve, and later versions determine Scaled Resolve support through the `GL_EXT_framebuffer_multisample_blit_scaled` string.

Note that the *activation* of Scaled Resolve is tied to the convars `gl_minify_resolve_mode` and `gl_magnify_resolve_mode`.

* `-gl_force_enable_scaled_resolve` - Force enable Scaled Resolve.

* `-glmenablemallocworkaround` and `-glmdisablemallocworkaround` - Enable/Disable a workaround to a GLSL bug in the Intel HD4000 OpenGL driver on OS X 10.8 (aka Mountain Lion).

* `-gl_time_shader_compiles` - Keeps track of total cycle count spent on shader compiles.

* `-gl_validate_shader_early` - "Check shader validity at creation time.  This will cause the driver to not be able to multi-thread/defer shader compiles, but it is useful for getting error messages on the shader when it is compiled." (Comment located in hl2_src/togl/linuxwin/cglmprogram.cpp @ lines 479-481.)

* `-glslcontrolflow` - Enables static control flow support. Only works on OS X.

* `-noglslcontrolflow` - Disables static control flow support.

## Audio

* `-forcesound` - Forces sound initialization routine regardless if the game is running on Source Dedicated Server (srcDS).

* `-audiolanguage <string>` - Sets audio language based on \<string\>.

* `-snd_openal` - Forces the game to use OpenAL instead of AudioQueue. Only works on OS X.

## Video

* `-noquicktime` - Disables QuickTime initalization routine.

## SDL

* `-nonquerty` - Use the keyname to workout the scan code when handling key input. This is an experimental feature.

* `-exclusivefs` - Tells the game to minimize the window if in fullscreen mode, and the player Command-Tabs. Only works on OS X.

* `-displayindex <value>` - Sets display index to \<value\>. Only works if USE_SDL is defined and SWDS is not defined.

## Misc

* `-menupaintduringinit` - Forces the main menu override to paint when PaintTraversal() is called, instead of waiting until the main menu layout finishes it's initialization routine.