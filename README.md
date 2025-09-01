
  

# Pokemon TCG Rainbow Engine

Expansion of the Pokemon TCG disassembly project that takes the classic Game Boy game and adds in a bunch of new features for ROM hackers to make use of. Openly available for you to make use of, so long as you credit me and anyone in the Credits section.

**NOTE:** This is not a game in of itself - while you can download and compile it, all it will currently produce is a near-copy of the original game with some different menu options. It's designed to be used as a base for people to create their own hacks of the game with.

Based off of [ElectroDeoxys' Pokemon TCG Extended repo](https://github.com/ElectroDeoxys/Pokemon-TCG-Extended) which is based off their [tinytcg repo](https://github.com/ElectroDeoxys/poketcg/tree/tinytcg) which is based off the original [poketcg disassembly](https://github.com/pret/poketcg). *[deep breath]*

## Features:

- Fully functional Darkness, Metal, Fairy and Dragon types, including the accompanying icons, Basic Energy card, and filter for the deck construction menu.
	- **Note:** No Pokemon cards of these types have been added as of yet, and as a result no boosters rewarding cards of these types.
	- **Note 2:** A Dragon energy type is coded into the game for logical convenience, but there is no accompanying Energy Card as there is no Dragon Energy in the real TCG.
- New deck construction screen that better accounts for more types of cards
- Changes to the way certain symbols and graphics are loaded into VRAM, leveraging the GBC's additional VRAM banks to load more type symbols and status condition markers. In the future I'd like to extend this to allow for more colourful sprites like the sequel game has.
- Support for up to 511 cards as opposed to the 254 limit of the original ROM (thanks to ElectroDeoxys' extended engine)

## Removed content
The Pokemon TCG Extended engine removes some code and functionality from the game in order to make space for cards:
- GameBoy tilemaps and compatibility functionality
- Unused content (Japanese title screen, unreferenced routines, unused text, debug menus)
- Printer functions
- Card Pop!
- Gift Center
- Link duels

## Planned content
There's plenty of things I want to add to this engine over time, but note that I am still inexperienced with assembly and this is mostly pie-in-the-sky wishful thinking at the moment. New types are the priority, and then I'll play it by ear.
- Updated deck construction menu
	- Initial functionality of this screen that accounts for new types is currently in place
	- Aiming to have a filter that shows all the cards currently in the deck without needing to open the Confirm Deck screen
	- If the above is achieved then the Confirm Deck screen will be replaced with a new Deck Analysis screen that shows helpful information about your deck (e.g. number of Pokemon vs. Trainers, Energy types required by your Pokemon's attack vs. Energy types in the deck)
	- I've been toying around with different layouts; if any of them work out I'll provide optional files to give people a choice
	- The UX on this screen is generally a bit messy so there's a few QOL changes I can implement
- Burn status condition
- Pokemon TCG 2 backports
	- Cards (the sequel has cards up to the Team Rocket series plus a few outliers)
	- Graphics systems that allow for more colourful card sprites (the original game was designed around base Game Boy and Super Game Boy compatibility whereas the sequel was designed specifically for the GBC)
- New Trainer card types (Pokemon Tool, Stadium, Supporter etc.)
- Options for different rules (i.e. being able to switch a hack to using more modern TCG rules like the starting player not being able to attack, or turning the more powerful Trainer cards into Supporters that can only be played once per turn)
- Adding in cards from expansions even further than Team Rocket
	- I'm mostly concerned with the Neo sets, and am not likely to go further than the e-series (if I get that far)
	- Even with the extended ROM base there's still limitations on how many cards can be added so these will most likely be separated into different branches
- Seeing if there's a way to work in something similar to [pokecrystal16](https://github.com/vulcandth/pokecrystal16)'s indirection tables to boost the card count even further. A version with every card from the Base Set to Skyridge is the dream.
	- Essentially these are a very clever system set up by people much smarter than me that allows Pokemon Crystal to have way more Pokemon, moves, and items than usual.
	- The game uses 8-bit indexes for this content, which limits how much you can add. Indirection tables allow you to use 16-bit indexes for Pokemon, moves etc. while the game only loads in the data that it needs to and assigns it an 8-bit id that links to that index
- Adding multiplayer functionality back in LOL (even if just as an optional extra in a separate branch)
- Miscellaneous mechanical and QOL improvements (e.g. optional tutorial, fixed bugs from the base game)
## Installation
This is a Game Boy disassembly so if you're familiar with [rgbds](https://rgbds.gbdev.io/) and GB development you can just make this like any other GB ROM.

If none of that makes any sense to you then these [installation instructions](https://github.com/pret/pokecrystal/blob/master/INSTALL.md) from the pokecrystal disassembly break things down by operating system (obviously, though, you would clone this depository instead of the pokecrystal one). Personally I am on Windows and use the Cygwin method. 

## Branches:

- [poketcgext](https://github.com/MarioBones/PokeTCG-Rainbow-Engine/tree/poketcgext)
	- Current, stable branch. **You want this branch in 99% of circumstances**
- [develop](https://github.com/MarioBones/PokeTCG-Rainbow-Engine/tree/develop)
	- Development branch for testing new features. More up-to-date than main, but also very likely unstable and full of in-progress, not-fully-tested code.

## Credits:

### Graphics:

- Me (Mario_Bones):
	- Type symbols for Darkness, Metal, Fairy and Dragon types
	- Card icons for Darkness, Metal, Fairy and Dragon types
- PaperFire88:
	- [Darkness, Metal and Fairy Energy card graphics](https://www.deviantart.com/paperfire88/art/Fairy-Metal-Darkness-Energy-GB1-and-2-Shiny-956324645)

### Code:
- Me (Mario_Bones):
	- Support for new types
	- New deck construction screen
- [ElectroDeoxys](https://github.com/ElectroDeoxys/):
	- Pokemon TCG Extended engine that allows for adding of more cards

### Special Thanks:
- Hudson Soft and Creatures Inc. for developing the original TCG Game Boy game and Game Freak for creating Pokemon
- Everyone who's submitted any code or improvements to the [poketcg disassembly](https://github.com/pret/poketcg) project
- Imakuni for those dance moves
- My girlfriend for listening to me talk about VRAM banks and why they're exciting