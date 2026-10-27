# Changelog

## 1.1.0

- An AI Head of Faith can no longer change a protected rite:
  - A newly elected AI Pope no longer swaps a core tenet of a protected rite.
  - An AI Head of Faith can no longer use Reaffirm Doctrine on a protected rite.
  - An AI Head of Faith no longer proclaims Armed Pilgrimages (or Struggle and Submission) a core tenet of a protected mainline rite.
- Ecumenical Councils called by the AI can no longer change a protected mainline rite: a proposal to make a tenet core or to change a doctrine fails at the vote, even with a majority, and the result explains why. Councils called by a player work as in vanilla.
- New game rule **PRR: Prohibit Protected Tenets**: Allowed (vanilla, default) or Blocked, for the AI prohibiting a tenet that is a core tenet of a protected rite.
- Not compatible with Head of Faith Council Veto, which overrides the same vote tally event. The game now tells you once per game if both mods are loaded (with Head of Faith Council Veto 1.1.1 or later).
- Changes already made to a rite are not undone.

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
