# TMAPINFO v0.1.0 Specification

TMAPINFO uses the syntax of TOML 1.0

TODO:

- figure out what to do when multiple defaults do something like define a sky
  - maybe just always apply in the order they appear in the maps default list?
  - global goes first
- should bossactions and compatibility flags should be additive? it seems like yes, but then how to clear *and* add new ones at the same time?
  - maybe we need something like clearepisodes for those...
- per-map complevel?
- can a defaults block have its own defaults property? or do we stop it at one level
- should label and levelname be combined into an object type maybe?
  - instead of `levelname = "name"` and `label = "label"`, do `name = "name"` for default label
  and `name = { label = "", name = "name" }` to clear the label or `name = { label = "label", name = "name" }` to override the label, with `name = "name"` still allowed for default label
  - and probably just make it name instead of levelname, like why is it called that but not levelmusic or levelsky

## Top-Level Keys

version

## Episodes

clearepisodes boolean + episodes array

## Map Blocks

list all keys and purpose here, most should be about the same as in umapinfo spec

## Defaults Blocks

allows all the same keys as map blocks, map block can specify multiple defaults blocks to inherit from

## `[defaults.global]`

default block that is automatically used by all maps

## Compatibility Flags

List all compat flags here

- `nofreelook`
- `nojump`

or instead of just a list should these be booleans or even allow more values?

## Default Map Property Values

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

## Vanilla Defaults

specifying "vanilla" as a default to inherit from will use any vanilla defaults that differ from the TMAPINFO defaults for a particular map

should basically match the umapinfo defaults

can put

```toml
[defaults.global]
defaults = [ "vanilla" ]
```

somewhere in the lump for basically the same behavior as umapinfo
