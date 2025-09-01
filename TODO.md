
# TODO List
A list of TODO comments I've put in the code so I don't forget about them and know why I've put them aside

 - [card_constants.asm](src/constants/card_constants.asm) - index
   comments need to be updated to account for newly added cards
 - [card_constants.asm](src/engine/duel/core.asm) - bug where Basic Pokemon have a different tile graphic loading on one of the card info pages than the base game. In my opinion I think it actually works better, but leaving it here so I don't forget about the differing behaviour in case I want to change it
 - [bg_map.asm](src/home/bg_map.asm) - When VRAM1 is loaded, WriteByteToBGMap0 function will write the bytes with BGP0 applied - investigate whether there are any scenarios where a coloured tile is incorrectly being printed in B&W
	 - Also consider possibility of loading parts of the duel UI in colour
 - [mason_laboratory.asm](src/scripts/mason_laboratory.asm) - there is an NPC who gives you a  bunch of free Energy cards if you have less than 10 spare Energy cards outside of your decks. I don't think this accounts for new Energy types properly, so should be investigated.
  - [deck_configuration.asm](src/engine/menus/deck_configuration.asm)
    - the NUM_DECK_CONFIRMATION_VISIBLE_CARDS const can be renamed and have its value changed if the confirmation screen is reworked into something else as planned.
    - the filter cursor currently loads in with the same BG Palette as the icon tile that is selected. Ideally it should be set to BG0 (will require more work than you'd think to ensure the filter icon doesn't turn grey so not a huge priority atm)
    - With current number of types, pressing up/down at the end of the top row causes a glitch because there's more filters on the top row than the bottom (will be fixed with next changes to deck config screen)
  - [wram.asm](src/wram.asm) - Pretty sure most/all of the comments with registers are incorrect after things have been moved around and expanded
  - [effect_functions.asm](src/engine/duel/effect_functions.asm) - Colour changing option for Shift and Conversion does not work properly with the new types and VRAM changes - proper type icons are not loaded and the new types exceed the bounds of the list
    - [pkmn_powers.asm](src\engine\duel\ai\pkmn_powers.asm) - Relatedly, the code for the AI using Shift will run into issues as well
  - Unknown - the game currently freezes when an AI uses Ditto's Morph attack. Need to investigate to see why this happens and whether it occurs when a player uses it as well

# Pre-existing TODOs
These TODOs were already in the codebase

 - [charmaps.asm](src/constants/charmaps.asm) - change symbol syntax
 - [menu_constants.asm](src/constants/menu_constants.asm) - hardcoded values
 - [deck_selection.asm](src/engine/menus/deck_selection.asm) - something to do with the modify deck function?
 - [intro_sequence_commands.asm](src/engine/sequences/intro_sequence_commands.asm) - potentially rename function