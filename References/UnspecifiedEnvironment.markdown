Linked from `org/tetragen/Tetragen.kt`

# Specifying an Environment
Because of problems relating to the Bukkit API*, Tetragen now requires that an Environment ID is specified for each world being generated. This guide will show you how to add an Environment ID when registering worlds.

Mostly when you create a world, you'll register the world generator like this:
```yml
# If you actually try this with Tetragen, IT WILL NOT WORK!
generator: TetragenPlugin
```
However, we can give additional information about how to generate the world by giving an Environment ID, which is added to the end of the generator name.
Now, we'll do this:
```yml
# This will work
generator: TetragenPlugin:NORMAL
```
Creating a world using a world management plugin will look something like this
`/mv create sample NORMAL -g TetragenPlugin:NORMAL`

There are 3 Environment IDs that Tetragen Supports:
- NORMAL 
- NETHER 
- END 

So this is also valid:
```yml
# This will generate a Nether-type world
generator: TetragenPlugin:NETHER
```
and this, too:
`/mv create sample END -g TetragenPlugin:END`

Hopefully this helps you. If you have any problems, contact me through Discord or Github

*Namely, `Bukkit.getWorld()` always returns `null` when starting up, which prevents me from creating world-specific generators.
