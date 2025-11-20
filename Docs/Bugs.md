# Route B Update Form Change Bug
## Bug
When the player enters Route B, the game will attempt to execute a NG+ style carryover update that forces all units in the army to their final forms. Reimu and Marisa have a special exception where form updates are dependent on whether the player set the special old costume flags `SC_Reimu`/`SC_Marisa` at the start of the Dream Arc.

Usually the game should update either Reimu or Marisa to their final forms `ReimuR04`/`MarisaR03` that have the True Trichromatic Lotus Butterfly attack. Unfortunately, form updates also have another list of parameters that determine which chapter a form is available on; the game uses this list to check whether a form should be available for selection on the loadout menu. 

`ReimuR04`/`MarisaR03` are set to only appear on chapter 77 (Route A Final Chapter) and chapters 78-80 (Dream Again chapters). Because Route B only goes up to chapter 75, these forms will never appear in the selection unless Reimu or Marisa are already in their upgraded forms prior to entering Route B. 

Since these forms are not available, the game performs a separate run through the remaining list of form updates, which results in the old costumes `Reimu04`/`Marisa07` and pre-TTLB forms `ReimuR03`/`MarisaR02` being selectable. If you choose to select these forms and switch from their previously set `ReimuR04`/`MarisaR03` forms, you will be permanently locked out of selecting the TTLB forms since they're not available on the Route B chapters.

  * When Reimu/Marisa are carried over for NG+, this bug does not affect them because the game falls back on another special exception for form updates that only occur when they are carried over units.

## Solutions
* Workaround: Requires a change to the `Data_Change` resource file for the chapter availability of the final forms `ReimuR04`/`MarisaR03` in the same row as the `SC_Reimu`/`SC_Marisa` flags. For columns with chapterIDs from 70-75, replace the empty values with a `1` to make `ReimuR04`/`MarisaR03` also available on Route B.
  * This will have the unintended consequence of making the final forms available earlier on Route A, but a more comprehensive fix needs to update the flag handling logic to account for exceptions on this bug.																																																
* Cleaner solution: Update flag handling logic to account whether player is on Route B and/or has hit the old costume flags.
