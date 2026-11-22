# Blockstar

The whole game is one file: `index.html`.

## Adding a new world

Every world must get a portal block, so players can reach it from any other world, not only from the New Game menu. When you add a world:

1. Add its entry to `PLACES` and add its key to the **end** of `DESTS` (a portal's saved data is its position in that list, so never insert into the middle).
2. Add a portal tile with `makeTile('portal_<key>', ...)` after the other `makeTile` lines.
3. Add the block with `addBlock('portal_<key>', '<World Name> Portal', 'Portal', '<description with a fun fact>', {t:'portal_<key>'}, {portal:'<key>'})`. Put it **after the last `addBlock` line**: block numbers are saved in worlds, so adding a block anywhere else breaks saved games.
4. Test it: place the block in a Survival game and walk through the doorway.

Also add the world to the New Game menu (the `data-newcity` buttons).
