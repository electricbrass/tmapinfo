# TMAPINFO v0.1.0 Specification

TMAPINFO uses the syntax of TOML 1.0

TODO:

- figure out what to do when multiple defaults do something like define a sky
  - maybe just always apply in the order they appear in the maps default list?
  - global goes first
- should bossactions and compatibility flags should be additive? it seems like yes, but then how to clear *and* add new ones at the same time?
  - maybe we need something like clearepisodes for those...

## Compatibility Flags

List all compat flags here

- `nofreelook`
- `nojump`

or instead of just a list should these be booleans or even allow more values?

## Map Defaults

For each map defined by a TMAPINFO lump, the following defaults are to be used for any field that is left unspecified.

```toml
sky = "SKY1"
music = "D_RUNNIN" # doesnt make sense for doom 1, maybe this should be no default? or just match vanilla defaults?
label = the map lump idk how to say this yet
levelname = "Unnamed Level"
intertext = ""
intertextsecret = ""
interbackdrop = "FLOOR4_8"
intermusic = "" # not sure either cause this has iwad specific handling
author = ""
levelpic = "" # or should this actually have a cwvilv default?? idk
# do we wann clean these up somehow?
exitpic = ""
exitanim = ""
enterpic = ""
enteranim = ""
endfinale = ""
endgame = ""
endpic = ""
endbunny = ""
endcast = ""
nointermission = false # is this the best way to handle this
bossactions = []
next = idk how to say this either
nextsecret = defaults to next
partime = 100
```
