From `org/tetragen/Tetragen.kt`

# Specifying an Environment
Because of problems of interacting with the Bukkit API, Tetragen now requires a generation environment for each world. This guide will show you how to add a generation environment.
### Using Bukkit.yml
If you use `bukkit.yml` to register your worlds, all you need to do is specify an environment at the end of the plugin name. For example:
```yml
#Environment is unspecified 
worlds:
  world:
    generator: TetragenPlugin
  world_nether: 
    generator: TetragenPlugin
    #...
```
can instead be replaced by this:
```yml
#The environment is now specified :) 
worlds:
  world:
    generator: TetragenPlugin:NORMAL
  world_nether: 
    generator: TetragenPlugin:NETHER
    #...
```
Note that the environment is essentially the *type* of world that we generate. The 3 environments are `NORMAL`, `NETHER`, and `END`
### Using a World Generator plugin (Multiverse, Multiworld, etc.)
If you were trying to create a world using a World Generator Plugin and you got this error, just add a `:` and the environment for that world when you specify Tetragen. For example, instead of using `/mv create sample NORMAL -g TetragenPlugin`, you use `/mv create sample NORMAL -g TetragenPlugin:NORMAL`.

Hope this helps. If you have any other questions related to setting up Tetragen, you can go to the [Setting up](https://github.com/croissant676/Tetragen/blob/main/Setup.md) page.
