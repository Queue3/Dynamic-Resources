# Dynamic Resources

## Summary

Every decade a hidden event fires that researches some of the basic technologies for countries that don't have them, then generates Arable Land, Coal, Iron, Lead, Sulphur, Gold, Logging, Rubber, Opium, Oil, Fishing, and Whaling buildings based on basic criteria in various amounts in 51 random states.

The preview images show a simulated 10 Generations, if you're perceptive you'll see small amounts of resources in places they aren't present in Vanilla.

Please feel free to provide feedback or bug reports.

## Game Version Compatibility

Should be compatible with all game versions at this time.

## Mod Compatibility

I recommend having other mods overwrite this one, I have a few contingencies in place to deal with edge cases and it shouldn't cause too much trouble otherwise. Any new buildings from other mods will need to be manually added to to this mod.

## Save-game Compatibility

This should be compatible with save-games regardless of adding it part way through a save or if it were started with a prior version of this mod.

## Localisation

The localisation is only in English, I'm sorry for this.

## FAQ

Q: Why are some of my resource buildings getting overcapped?

A: This is intentional and a balancing decision, you're now encouraged to rush maxing out buildings as this will let you exceed the maximum cap permanently.

Q: Would it make more sense to have resources generate gradually instead of in bulk?

A: That's an alternative and the mod could be easily modified to work that way, but I chose the current way intentionally to create a bit of excitement at the next Generation taking place.

Q: Is this mod balanced?

A: This depends on the Game Rules you choose, the default ones are somewhat balanced, but given there is randomness involved it can vary.

Q: Why is basic technology automatically researched?

A: This has to do with a limitation of my implementation, the mod only creates buildings, it doesn't increase the underlying resource cap, the way the buildings are created requires the country that owns the state to have the necessary prerequisites, the only relevant one in this case is the technology. With the current implementation if I did not do this then any country without these basic technologies would not have many of the resources generate. The end result of this is very little actually changes as it's only a very few minor and the decentralised countries that are missing the technologies. (If anyone notices any issues with this please do let me know).

Q: How many resources generate?

A: One set of: Arable Land, Coal, Iron, Lead, Sulphur, Gold, Logging, Rubber, Opium, Oil, Fishing, and Whaling have a chance of generating in groups of 3, 6, 9, and 12, across 50 different random states every decade, the resource set and the amount in that set are both weighted.

The way it really works is it selects 50 random states, then it rolls if it should generate Arable Land or a resource, then it rolls the resource and quantity of resource (or just the amount of Arable Land generated). There is no restriction on how many times a state can get a resource generation.

Example: Gold has the lowest chance of generating, a set of 3 Gold is more likely to generate than a set of 12 Gold.

In each Generation there is an additional jackpot drop of 24, equally weighted between the resources.

These are the base values of the Sets and can be adjusted in game using Game Rules.

So in summary, 51 total Sets of resources of various sizes generate once per decade, there are optional Game Rules to adjust certain values.

Q: Why aren't many resources generating?

A: The resource generation is fairly random so there will be variance between runs. You can increase the resources using the Game Rules.

Q: Can I trigger a Generation manually?

A: Using the console yes, the relevant event ID is: dr.1

Q: Why aren't starting Generations happening immediately?

A: I may have lied slightly, they will happen at the end of the first month.

Q: Does this impact performance?

A: Not that I have noticed. If you do max Resource Multipliers and max Starting Generations there is a little lag spike with my system on the day it all generates though. I've personally used this mod on two computers (1070ti + 9600k + 16GB DDR4 and 4070 + 13700k + 32GB DDR5) and noticed no differences compared to Vanilla.

Q: What Game Rules do you use?

A: Defaults

Q: What happens if I add/update this mod in a current save?

A: It will work fine, it will use Default Game Rules

Q: Do I need permission to use this mod in other projects?

A: Feel free to use the mod as needed.

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
