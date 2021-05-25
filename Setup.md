# How to set up Tetragen.
There are several steps that are required to set up Tetragen and use it properly. This guide will go through all of them. I will assume that you already have a server and know how 
to run / manage it. (To optimize Tetragen, use [Paper servers](https://papermc.io), as it is both faster and has a larger api. Tetragen *will* work with only Spigot, but may 
cause problems and will probably run slower)
 - First things first, you need to go open the file `bukkit.yml`. To actually use Tetragen, you need to register the worlds as Tetragen-generated worlds. During this time, any worlds
   that you registered must also be deleted to prevent weird generation problems caused by the vanilla generator interacting with Tetragen. This *will* cause any progress to be lost!
 - Register the worlds by first adding a `worlds` section (full example below). Next, for each of the worlds that you want to register, add a subsection. Finally, add a generator tag
   to every world with `Tetragen:` and the world type you want generated there. 
   Example: I want to generate the worlds `world`, `world_nether`, and `world_the_end` with the corresponding world types. This would be the section added at the end of `bukkit.yml`.
   ```yml
   #  - Other bukkit.yml stuff up here -
   # Add section 
   worlds:
    # For world "world"
    world:
      # Set the generator to a normal generation type
      generator: Tetragen:NORMAL # Could also be Tetragen:OVERWORLD
    # For world "world_nether"
    world_nether:
      # Set the generator to generate nether terrain
      generator: Tetragen:NETHER
    # For world "world_the_end"
    world_the_end:
      #Finally, we want to generate end terrain in the end
      generator: Tetragen:END
   # And with that, we're done :)
   ```
 - When you are done registering your `bukkit.yml`, you'll need to configure Tetragen itself to match your needs. Want Tetragen to spawn animals? How should it generate ore veins? Should it pre-generate chunks? You can configure all of this in `config.yml`, which can be found in plugins -> Tetragen (The folder, not jar). This will only happen
   after you've run the server at least once.
 - Lastly, you can double-click the actual jar file to manage the technical aspects, such as file logging, error reporting, privacy and other things (If nothing happens after you double click, try right clicking, selecting "Open with" and selecting your JDK). This process is highly encouraged, and a warning will be posted in the console if you run the server. 
   
   ~~ For the people that are using Multiverse to create worlds. 
  To generate a world using Tetragen, you can do `/mv create <world> <ID> -g Tetragen:<TID>`
  - ID represents the world environment. You can see a list of possible environments for the server by using `/mv env`
  - TID represents the Tetragen ID, which is the one that you would put if you used `bukkit.yml`
  Example: `/mv create typical_world NORMAL -g Tetragen:NORMAL ` generates the world "typical_world" using Tetragen.

If anyone has problems, you can contact me in discord or post them in github discord. Post the stacktrace when you do (The error message), as it will help me figure out what went wrong. You can post them in Spigot Reviews, but I don't check it as often as discord / github.