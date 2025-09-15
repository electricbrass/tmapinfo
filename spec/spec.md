# TMAPINFO v0.1.0 Specification

TMAPINFO uses the syntax of TOML 1.0

## Map Defaults

For each map defined by a TMAPINFO lump, the following defaults are to be used for any field that is left unspecified.

```toml
sky = "SKY1"
music = "D_RUNNIN"
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
label = the map lump idk how to say this yet
next = idk how to say this either
nextsecret = defaults to next
partime = 100
```
