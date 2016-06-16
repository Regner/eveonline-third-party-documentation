# Combat

## Target lock time

The target lock time (`$ t_{targetlock} $`) in seconds depends on the ship's scan resolution (`$ s $`) and the target's signature radius (`$ r $`)

```math
t_{targetlock} = {40000 \over s \cdot asinh(r)^2}
```

## Alignment time

The ship alignment time (`$ t_{align} $`) depends on the ship's inertia modifier (`$ i $`) and the ships mass (`$ m $`) 

```math
t_{align} = { ln(2) \cdot i \cdot m \over 500000 }
```

## External Killmail Hash
```python
sha1(victimCharacterID + attackerCharacterID + shipTypeID + killTime)
```
* victimCharacterID: the character ID of the victim. If the characterID is 0, this is the string "None" instead
* attackerCharacterID: the character ID of the attacker that got the final blow. If the characterID is 0, this is the string "None" instead
* shipTypeID: the typeID of the victim's ship
* killTime: a 64-bit timestamp. You can use the following math to convert from a regular unix timestamp: `(unixtime * 10000000) + 116444736000000000`

The CREST URL is then `https://crest-tq.eveonline.com/killmails/{killmail_id}/{killmail_hash}/`.

### Example using kill 40583728
* Our values are None + 93808108 + 24646 + 130521094800000000
* sha1(None9380810824646130521094800000000) = efd4bf9c4f2aee704d3f9a7f8ae0176a15eba19d

Putting it together we get: [https://crest-tq.eveonline.com/killmails/40583728/efd4bf9c4f2aee704d3f9a7f8ae0176a15eba19d/](https://crest-tq.eveonline.com/killmails/40583728/efd4bf9c4f2aee704d3f9a7f8ae0176a15eba19d/)