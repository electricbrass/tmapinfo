# tmapinfo

The spec for TMAPINFO, a TOML based MAPINFO for Doom ports

Examples:

```toml
# TMAPINFO
version = "1.0.0"

clearepisodes = true
# episode = clear doesnt work with toml
# tbh i think episode definition being its own block isnt a bad idea
# otherwise a simple top level thing to clear like this is simple in toml
episodes = [
    { startmap = "MAP01", patch = "M_EPI1", name = "episode 1", key = "b" },
    { startmap = "MAP02", patch = "M_EPI2", name = "episode 2" }
]

# an equivalent way to define those episodes would be
[[episodes]]
startmap = "MAP01"
patch = "M_EPI1"
name = "episode 1"
key = "b"

[[episodes]]
startmap = "MAP02"
patch = "M_EPI2"
name = "episode 2"

[defaults.compat_stuff]
compatibility = [
  "nojump",
  "nofreelook"
]

[defaults.episode1]
sky = "sky1"

[defaults.episode2]
sky = "sky2"

[maps.MAP01]
defaults = [ "compat_stuff", "episode1" ]
levelpic = "CWILV01"
intertext = """
Hey look its some intertext
with multiple lines
"""
next = "MAP02"
bossactions = [] # equivalent to bossaction = clear

[maps.MAP02]
defaults = [ "compat_stuff", "episode2" ]
levelpic = "CWILV02"
bossactions = [
  { thingtype = "Cyberdemon",       linespecial = 10, tag = 4 },
  { thingtype = "SpiderMasterMind", linespecial = 23, tag = 7 }
]
```

To inherit all vanilla defaults:

```toml
# TMAPINFO
version = "1.0.0"

[defaults.global]
defaults = [ "vanilla" ]

# now all map definitions will have vanilla defaults for skies, bossactions, etc
```
