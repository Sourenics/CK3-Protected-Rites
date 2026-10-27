<p align="center"><img src="mod/protected_rites/thumbnail.png" width="256" alt="Protected Rites"></p>

# Protected Rites

A Crusader Kings III mod that stops the AI from rewriting a rite you founded. Since update 1.20, the Head of Rite can edit the rite's tenets and doctrines once per lifetime. If you found a rite and its Head of Rite is an AI (for example, the clerical vassal of a secular ruler), the AI can reshape it until it has nothing in common with what you created, and push it towards heresy without you ever choosing it. The Pope and other AI Heads of Faith can change it too: through Ecumenical Councils, by reaffirming a doctrine, or when a newly elected Pope swaps a tenet of his own rite. With this mod, nobody but a player can change the tenets and doctrines of the rites you follow, while the game's own rites work as in vanilla.

- **Game version:** 1.20.x
- **Mod version:** 1.1.0
- **Author:** [Sourenics](https://github.com/Sourenics)
- **Steam Workshop:** [Protected Rites](https://steamcommunity.com/sharedfiles/filedetails/?id=3826064639)

> **⚠️ Not compatible with [Head of Faith Council Veto](https://github.com/Sourenics/CK3-Head-of-Faith-Council-Veto).** See [Compatibility](#compatibility).

## Features

- **An AI Head of Rite cannot change a protected rite.** It cannot edit it, and the yearly drift that lets an AI Head of Rite swap a rite's tenets or doctrines on its own skips protected rites. Their tenets and doctrines stay as they were.
- **Heresy outbreaks never pick a protected rite to diverge.** They pick another rite of the faith instead.
- **An AI Head of Faith cannot change a protected rite either:**
  - A newly elected AI Pope does not swap a core tenet of a protected rite.
  - An AI Head of Faith cannot use **Reaffirm Doctrine** on a protected rite.
  - An AI Head of Faith does not proclaim **Armed Pilgrimages** (or **Struggle and Submission**) a core tenet of a protected mainline rite.
- **Ecumenical Councils called by the AI cannot change a protected mainline rite.** A proposal to make a tenet core or to change a doctrine fails at the vote, even with a majority, and the result explains why. Proposals that only permit a tenet or make it known do not change the rite and work as in vanilla. Councils you call, or that your theological puppet calls, work as in vanilla.
- **Which rites are protected:** a rite is protected while a player follows it, as long as it is not one of the game's own rites (Roman, Byzantine, Ambrosian, Carolingian, the heresies and so on). Rites founded during the game have no rite type, so any of them counts, including rites in an existing save. Rites founded by a player, or by a player's theological puppet, are also marked when they are founded.
- **Players edit as usual.** If you are the Head of Rite, the vanilla rules apply: once per lifetime, piety cost and so on. Compatible with [Free Rite Editing](https://github.com/Sourenics/CK3-Free-Rite-Editing).
- **Game rule PRR: Protect Mainline Rites**, in the game rules screen when starting a new game:

  | Setting | When a protected rite becomes the mainline rite |
  |---|---|
  | Protected (default) | it stays protected: an AI Head of Faith cannot edit it either |
  | Not Protected (vanilla) | its Head of Faith can edit it as in the base game, until it stops being the mainline rite |

- **Game rule PRR: Prohibit Protected Tenets**: whether the AI can prohibit, for the whole faith, a tenet that is a core tenet of a protected rite. A prohibited tenet stays a core tenet of your rite; it only raises its divergence.

  | Setting | The AI prohibiting a core tenet of a protected rite |
  |---|---|
  | Allowed (vanilla, default) | it can, with an Ecumenical Council, a papal bull or a Head of Faith decision |
  | Blocked | it cannot; players still can |

- **Everything else stays vanilla.** Permitting or prohibiting tenets for the faith, declaring a rite a heresy and the game's historical changes to every rite of a faith (the Head of Faith after the Great Schism, clerical succession after the Investiture Crisis) work as in the base game. None of them changes the tenets you chose; you can edit your rite again afterwards.
- **A warning if something slips through.** If a protected rite changes its tenets or doctrines without a player edit while its Head of Rite is AI, you get a message, so a change the mod could not stop never goes unnoticed.

### Languages

The game rules and messages are in English and Spanish; players using any other game language see them in English. Translations are welcome: open an [issue](../../issues/new/choose) or post them on the Steam Workshop page.

## Installation

### Steam Workshop

Subscribe on the Steam Workshop page and enable the mod in the Paradox launcher.

### Manual

1. Download this repository (green **Code** button → **Download ZIP**).
2. Copy the contents of the `mod/` folder (`protected_rites/` and `protected_rites.mod`) into:
   - **Windows:** `Documents/Paradox Interactive/Crusader Kings III/mod/`
   - **Linux:** `~/.local/share/Paradox Interactive/Crusader Kings III/mod/`
   - **macOS:** `~/Documents/Paradox Interactive/Crusader Kings III/mod/`
3. Enable **Protected Rites** in the Paradox launcher.

## Compatibility

> **⚠️ Not compatible with [Head of Faith Council Veto](https://github.com/Sourenics/CK3-Head-of-Faith-Council-Veto).** Both mods replace the vote tally of Ecumenical Councils (`ecumenical_council_events.0080`), so only one of them works at councils: if both are loaded, the game uses the one from Protected Rites and the Head of Faith's veto does not apply. Use only one of them. From version 1.1.0 (and Head of Faith Council Veto 1.1.1), an event tells you once per game if both are loaded.

- No DLC required. The Head of Faith changes it blocks (Ecumenical Councils, the new Pope's tenet, Reaffirm Doctrine) come from By God Alone.
- Redefines one vanilla scripted rule, `can_edit_rite`, in its own file (`common/scripted_rules/zzz_prr_rules.txt`); the rule keeps the vanilla check and adds the protection.
- Overrides three vanilla scripted effects in its own file (`common/scripted_effects/zzz_prr_rite_effects.txt`): `rite_yearly_hor_divergence_drift_effect` (the Head of Rite's yearly drift), `pam_heresy_c1_pick_diverging_rite_effect` (the rite a heresy outbreak diverges) and `head_of_faith_change_core_tenet_effect` (the tenet a newly elected AI Pope swaps).
- Overrides five vanilla scripted triggers in its own file (`common/scripted_triggers/zzz_prr_triggers.txt`): `pam_doctrine_can_be_reaffirm` (Reaffirm Doctrine), `pam_ai_can_proclaim_armed_pilgrimages_core_trigger` and `pam_ai_can_proclaim_struggle_submission_core_trigger` (the AI making those tenets core), and `pam_tenet_can_be_prohibited_trigger` and `pam_tenet_can_be_prohibited_no_actor_trigger` (prohibiting a tenet with a bull or decision).
- Overrides the Ecumenical Council vote tally event, `ecumenical_council_events.0080`, through `id_override_priority`.
- Each override is a copy of the vanilla script with small, marked changes. Other mods that change the same rule, effects, triggers or event are not compatible without a patch.
- Adds to the `on_rite_created`, `on_rite_updated`, `on_game_start_after_lobby` and `yearly_global_pulse` on_actions without overriding them.
- Can be added to an existing save: rites founded during the game are recognised from the moment you enable it. Game rules cannot be changed after a game has started, so an existing save uses the default settings (Protected, and Allowed). Can be removed at any time.

## Reporting bugs

Please open an [issue](../../issues/new/choose) using the **Bug report** template. To be able to fix the problem we need:

1. **The `error.log` file** from the session where the problem happened:
   - **Windows:** `Documents/Paradox Interactive/Crusader Kings III/logs/error.log`
   - **Linux:** `~/.local/share/Paradox Interactive/Crusader Kings III/logs/error.log`
   - **macOS:** `~/Documents/Paradox Interactive/Crusader Kings III/logs/error.log`

   The log is overwritten every time the game starts, so copy it right after the problem happens, before launching the game again. Ideally, reproduce the problem in a session with **only Protected Rites enabled**.
2. **The game version** (shown in the main menu, for example 1.20.1) and **the mod version**.
3. **Your active DLCs** and **your full mod list in load order**.
4. **The rite** that changed or could not be edited, who founded it, who its Head of Rite is, whether it is the mainline rite, what changed it (Head of Rite, Pope, Ecumenical Council…), and **the game rule settings**.
5. **Screenshots** of the rite and of any message you got, if possible.

## Credits

Idea and testing by Sourenics.

## License

**Protected Rites** © 2026 Sourenics, licensed under [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).

Forks, translations and alternative versions are welcome, provided that you:

- **Credit the original author** (Sourenics) and link to this repository.
- **Indicate the changes** you made.
- **Release your version under the same license** (CC BY-SA 4.0).

### Paradox Interactive content

Crusader Kings III and its content are © Paradox Interactive AB and are **not** covered by this license. This includes the `can_edit_rite` scripted rule and the overridden scripted effects, scripted triggers and event, which are copies of Paradox script with small changes by this mod. This project is an unofficial fan-made mod, not affiliated with or endorsed by Paradox Interactive. Like every CK3 mod, it must be distributed free of charge.
