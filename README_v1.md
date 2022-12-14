# Randy-Poké - Random Pokémon API (v1)

Randy-Poké is a simple NodeJs + Express REST API, connected to a MongoDB database, which returns random pokémons, from the first 6 generations (the rest will be added soon!).
Filters by type and generation already available.

## Available filters

- type1: To find pokémons with this type. If type2 is not speficied, this filter will search pokémons with any combination that includes type1. Can be combined with generation filter.
- type2: To find pokémons with a specific secondary type. Type1 must be specified in order for this to work. Can be combined with generation filter.
- gen: To find pokémons from speficic generations (1 to 6, currently avilable). Can be combined with type1 and type2 filters.

## GET Single Random Pokémon (/api/v1/)

This method will return a random pokémon, from any type and generation, unless speficied with filters.

### Example 1: `/api/v1/?type1=grass` will return a random

- Grass-only type pokémon, from any generation, like Chikorita from Gen 2.
- Grass + Other type pokémon, from any generation, like Abomasnow (Grass + Ice), from Gen 4.
- Other Type + Grass pokémon, from any generation, like Trevenant (Ghost + Grass), from Gen 6.

### Example 2: `/api/v1/?type1=grass&gen=4` will return a random

- Grass only type pokémon, from generation 4, like Cherrim.
- Grass + Other Type pokémon, from generation 4, like Budew (Grass + Poison).
- Other Type + Grass pokémon, from generation 4, like Wormadam (Bug + Grass).

### Example 3: `/api/v1/?type1=grass&type2=poison` will return a random

- Grass and Poison pokémon, from any generation, like Bulbasaur.

### Example 4:  `/api/v1/?type1=grass&type2=poison&gen=3` will return a random

- Grass and Poison pokémon, from generation 3, like Roselia.

## GET Multiple Random Pokémon (/api/v1/N)

This method will return N random pokémon, from any type and generation, unless speficied with filters.

### Example 1: `/api/v1/10/?type1=grass` will return 5 random

- Grass-only type pokémon, from any generation, like Chikorita from Gen 2.
- Grass + Other type pokémon, from any generation, like Abomasnow (Grass + Ice), from Gen 4.
- Other Type + Grass pokémon, from any generation, like Trevenant (Ghost + Grass), from Gen 6.

### Example 2: `/api/v1/4/?type1=grass&gen=4` will return 4 random

- Grass only type pokémon, from generation 4, like Cherrim.
- Grass + Other Type pokémon, from generation 4, like Budew (Grass + Poison).
- Other Type + Grass pokémon, from generation 4, like Wormadam (Bug + Grass).

### Example 3: `/api/v1/3/?type1=grass&type2=poison` will return 3 random

- Grass and Poison pokémon, from any generation, like Bulbasaur.

#### Example 4:  `/api/v1/2/?type1=grass&type2=poison&gen=3` will return 2 random

- Grass and Poison pokémon, from generation 3, like Roselia.
