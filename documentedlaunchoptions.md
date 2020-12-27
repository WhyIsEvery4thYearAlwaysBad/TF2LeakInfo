# Context

Please note that this documentation is unfinished, and descriptions may not be correct. If you feel that these explanations are wrong, please tell me!

Also note that some of the launch options may not neccessarily be in TF2 itself, but rather it's utility programs.

# Core Game (hl2.exe)

## Processing

* `-yieldcycles` - Forces the Game Manager to yield execution after updating. Useful for running 2 instances of the same game.

## Graphics

### OpenGL

* `-glmenablefakesrgb` - Force the simulation of sRGB mode.

* `-glmnosystemcheck` - Bypasses the forbidden Graphics Processor check for GMA950, X3100, or NV G7x cards, and the version check for OS X 10.6.7 or later. Only works on OS X.

* `-glmdisableclipplanes` - Force disable clip planes for OpenGL.

* `-glmenableclipplanes` - Force enable clip planes for OpenGL.

* `-glmenabletrustblit` and `-glmdisabletrustblit` - (Unfinished)

* `-glmenableperfpackage` and `-glmdisableperfpackage` - Force enable/
disable certain GL optimizations on Unix.

* `-gl_enable_scaled_resolve` - Enable availability of Scaled Resolve if the OS X version has SLGU and is newer than 10.7.0. Versions prior to 10.6.5 do not have Scaled Resolve, and later versions determine Scaled Resolve support through the `GL_EXT_framebuffer_multisample_blit_scaled` string.

* `-gl_force_enable_scaled_resolve` - Force availability Scaled Resolve.

* `-glmenablemallocworkaround` and `-glmdisablemallocworkaround` - Enable/Disable a workaround to a GLSL bug in the Intel HD4000 OpenGL driver on OS X 10.8 (aka Mountain Lion).
Note that the *activation* of Scaled Resolve is tied to the convars `gl_minify_resolve_mode` and `gl_magnify_resolve_mode`.

## Audio

* `-wavonly` - Forces the game to only use WAVs.
* `-forcesound` - Forces sound initialization routine, regardless if the game is running of Source Dedicated Server (srcDS).

## SDL

* `-nonquerty` - Use the keyname to workout the scan code when handling key input. This is an experimental feature.
* `-exclusivefs` - Tells the game to minimize the window if in fullscreen mode, and the player Command-Tabs. Only works on OS X.