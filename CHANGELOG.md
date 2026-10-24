# Changelog

## 1.0.1

- Fixed: an AI Head of Rite could still change a protected rite through the yearly Head of Rite drift added in By God Alone, which swaps a rite's tenets or doctrines on its own and does not use the rite editor. The drift now skips protected rites.
- Heresy outbreaks no longer pick a protected rite to diverge; they pick another rite of the faith instead.
- Changes already made to a rite are not undone.

## 1.0.0

- First release.
- An AI Head of Rite cannot edit a protected rite: a rite a player follows that is not one of the game's own rites.
- Rites founded by a player, or by a player's theological puppet, are marked as protected when founded.
- New game rule **PRR: Protect Mainline Rites**: Protected (default) or Not Protected (vanilla), for protected rites that become the mainline rite.
- Players get a message if a protected rite changes without a player edit while its Head of Rite is AI.
- English and Spanish localization; other languages fall back to English.
