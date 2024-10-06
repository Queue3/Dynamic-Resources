# Dynamic Resources

## Changelog

Update 1.3.0

- Added new Game Rules
	- Resource Distribution: Determines which resources can Generate in each state.
		- Focused: Only Generates resources with Resource Potential in a state.
		- Random: Generates resources regardless of Resource Potential in a state.
	- Only Starting Generations
	- Sets Per Generation: How many Sets of resources Generate per Generation
- Event dr.1 is now used to trigger a Generation
- Code Refactor

Update 1.2.0

- Restructured events - you can now use event dr.9 to trigger a generation regardless of Game Rules unless you disabled the mod.

Update 1.1.0

- Added a Jackpot drop to each generation, this will generate a x24 base amount of a random resource Set.
- Added new Game Rules
	- Resource Multiplier: The higher the Resource Multiplier the more resources that generate in a Set.
	- Starting Generations: A Starting Generation is an immediately triggered resource Generation at game start.
- Opium Sets now also add an equivalent amount of Arable Land
- Increased chance of Opium, Oil, Rubber, and Gold Sets

Update 1.0.0

- Initial Release

## Technical Summary

The mod is pretty simple, monthly on_action is used to trigger scripted_effects from the #1 country, the scripted_effects that trigger are based off the Game Rules. Lists all the way down.
