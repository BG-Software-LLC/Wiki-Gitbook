# Register your own block-keys

The keys system is used to parse blocks and items into a comparable object, that supports both legacy & non-legacy versions. By registering custom keys, you can give your custom blocks a custom key, which will separate it from similar blocks. In this tutorial, I'll make "powerful sponges" to have custom keys.

In order to accomplish this, I'll use the `SuperiorSkyblockAPI.getBlockValues().registerKeyParser()` method. This method takes two parameters:

* customKeyParser: A CustomKeyParser interface, which we need to create.
* blockTypes: A list of block types which can be parsed by the parser.

First of all, I'll create my CustomKeyParser object. The interface contains two methods that needs to be implemented:

* getCustomKey(\<Location>): Handles the parsing part.
* isCustomKey(\<Key>): This method is used in the block counts menu, to parse the custom key into it's block form.

After creating the object and implementing basic parser, the code looks like this:

```java
    private static final Set<Location> powerfulSponges = new HashSet<>();
    private static final Key SPONGE_KEY = Key.of("SPONGE");
    private static final Key POWERFUL_SPONGE_KEY = Key.of("POWERFUL_SPONGE");

    private static final class PowerfulSpongeParser implements CustomKeyParser{

        @Override
        public Key getCustomKey(Location location) {
            /* All of my custom sponges are cached in powerfulSponges.
            I know that the block in that location will always be SPONGE, so I can return the sponge key
            if it's not a custom sponge. If it is, then I return my custom key. */
            return powerfulSponges.contains(location) ? POWERFUL_SPONGE_KEY : SPONGE_KEY;
        }

        @Override
        public boolean isCustomKey(Key key) {
            // If the key is "POWERFUL_SPONGE", then that key was created by this parser.
            return key.equals(POWERFUL_SPONGE_KEY);
        }

    }
```

The only thing left is to register the custom parser, and set the whitelisted block types. This can be done anytime after SuperiorSkyblock was enabled. I am registering it inside a task of bukkit, so I know it happens on the first tick - after all the plugins were enabled. The final version is the following:

```java
public final class PowerfulSpongesKey {

    private static final Set<Location> powerfulSponges = new HashSet<>();
    private static final Key SPONGE_KEY = Key.of("SPONGE");
    private static final Key POWERFUL_SPONGE_KEY = Key.of("POWERFUL_SPONGE");
    
    public static void registerKey(JavaPlugin plugin){
        Bukkit.getScheduler().runTask(plugin, () -> {
            SuperiorSkyblockAPI.getBlockValues().registerKeyParser(new PowerfulSpongeParser(), SPONGE_KEY); 
        });
    }

    private static final class PowerfulSpongeParser implements CustomKeyParser{

        @Override
        public Key getCustomKey(Location location) {
            /* All of my custom sponges are cached in powerfulSponges.
            I know that the block in that location will always be SPONGE, so I can return the sponge key
            if it's not a custom sponge. If it is, then I return my custom key. */
            return powerfulSponges.contains(location) ? POWERFUL_SPONGE_KEY : SPONGE_KEY;
        }

        @Override
        public boolean isCustomKey(Key key) {
            // If the key is "POWERFUL_SPONGE", then that key was created by this parser.
            return key.equals(POWERFUL_SPONGE_KEY);
        }

    }

}
```

That's it! Everytime I'll place a powerful sponge, it will be considered as "POWERFUL\_SPONGE" instead of a regular sponge. This is supported in counts menu, values menu, worth file, levels file and everything else!
