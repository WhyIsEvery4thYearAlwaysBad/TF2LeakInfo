# Leaked Weapons

# Leaked Buildings
## Mini Dispenser

The Mini Dispenser is a smaller building of the dispenser. It is identically functional to its bigger counterpart, except that it costs 70 metal to build, and on destruction, it deals between 50 and 300 damage based on metal amount. It has a heal rate of 10hp/sec and 20% ammo/sec, which is the equivalent of a level one Dispenser.

Related files:
* game/server/tf/tf_obj_dispenser.cpp

## Speed Pad

The Speed Pad is a teleporter that when walked on, it gives a conditional speed boost thats last for 4 seconds. It takes 25 less metal, so it could have costed 75 metal, or 25 metal with the Eureka Effect. The recharge duration formula is 2 - (level / 3).

Interestingly enough, there is conflicting code to make the conditional speed bost last (3 + level) seconds, located in the function CObjectTeleporter::ApplySpeedBoost(CTFPlayer), which is called in CObjectTeleporter::TeleporterTouch(CBaseEntity). If this code took priority, these are the attributes it would have.

Level | Boost Duration
------|---------------
1 | 4 sec
2 | 5 sec
3 | 6 sec