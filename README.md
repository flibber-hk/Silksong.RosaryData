# Rosary/Shell data in silksong

This repo contains datamined data for rosaries and shell shards in silksong.

### General

The data for each object includes:
* sceneName - self explanatory. Respects additive scenes.
* gameObject - object name in hierarchy, so no slashes means it's a root game object.
* active - if this is false, the object may be activated by something else,
and if this is true, the object may have an inactive parent making it inactive
* componentType - this is a component that is guaranteed to be on the object.
If it is omitted, then it is the same for all objects in the file.
* localPosition - position relative to parent.
* worldPosition - position in the scene. This may be inaccurate for additive scenes.

### breakable_holder.json

This enumerates items with a BreakableHolder component that give rosaries
or shell shards. For an object that drops medium/large rosaries, the amount
is the amount of currency, not the number of objects spawned.

Items in this category are typically either shell deposits, or
Hunter's March-style rosary strings.

### geo.json

This enumerates items with a GeoControl component, which are exactly the
persistent rosary beads which exist in the world. The GeoControl componentType
has been omitted for objects in this file.

### georock.json

This enumerates items with a GeoRock component. These are typically the piles of
rosary beads and skulls that often appear in The Marrow and similar areas.
The geoAmount is the amount of currency, not the number of objects spawned.

### rosary.json

This enumerates objects with a RosaryCache component, or one of its subclasses.
The actual component is given as the componentType.

The cacheAmt and stringAmount represent two ways in which such components can give
their currency, and the rosaryAmountGuess is the sum of those two values.
It is possible that there are other ways to give currency that haven't been accounted
for.

Typically objects with a RosaryCacheHanging component represent hanging rosary strings
that are empty (whereas RosaryCacheString represents hanging rosary strings that are
not empty).

## Missing Files

As well as components I haven't thought of, things like the consumable rosary/shell deposits
(rosary necklaces, beast shards, pristine cores etc) and chests have not been included.
