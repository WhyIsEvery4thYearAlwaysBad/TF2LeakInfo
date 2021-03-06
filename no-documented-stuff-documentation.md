# Undocumented TF2 ConCommand, ConVar, and Entity Documentation

This file contains documentation for TF2-*only* commands, cvars, and entities that don't have any documentation. 

# Entities

## `_ballplayertoucher`

`_ballplayertoucher` is an unused entity that is only spawned as a child of the passtime ball.<sup>[1]</sup> This entity has its collision flag set to `SOLID_VPHYSICS` with players when the `passtime_ball` parent entity is in a free state (or when `CPasstimeBall::SetStateFree()` is called).<sup>[2]</sup> `_ballplayertoucher` will have its collision set to `SOLID_NONE` when the parent `passtime_ball` entity is in the out-of-play or carried state (or when `CPasstimeBall::SetStateOutOfPlay()` and `CPasstimeBall::SetStateCarried()` are called respectively).<sup>[3][4]</sup> In practice however, `_ballplayertoucher` doesn't seem to do anything regardless of its collision flag.

<sup>[1]</sup> - \<root dir\>/game/server/tf/tf_passtime_ball.cpp @ lines 366 - 367.  
<sup>[2]</sup> - \<root dir\>/game/server/tf/tf_passtime_ball.cpp @ lines 543 - 544.  
<sup>[3]</sup> - \<root dir\>/game/server/tf/tf_passtime_ball.cpp @ lines 611 - 612.  
<sup>[4]</sup> - \<root dir\>/game/server/tf/tf_passtime_ball.cpp @ lines 698 - 699.