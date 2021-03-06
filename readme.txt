---------------------------------------------------------------------------------------------------
-- Supported games (IWADs)                                                                       --
---------------------------------------------------------------------------------------------------

  The HUD was originally made for Doom only, but it now supports Heretic, Hexen, Strife (partial),
  Chex Quest 3, Hacx v1.2 and Harmony, as well. There are no plans to support other games at the
  moment.

---------------------------------------------------------------------------------------------------
-- I do not see the HUD!                                                                         --
---------------------------------------------------------------------------------------------------

  NC HUD is a fullscreen HUD, thus it replaces GZDoom's own fullscreen HUD, not the game's standard
  status bar. To view the HUD, switch to the fullscreen mode by pressing the '=' key (default),
  while making sure the alternative HUD is disabled. To disable the alternative HUD, go to:

    Options -> HUD Options -> Alternative HUD

  Set the "Enable alternative HUD" option to "Off".

---------------------------------------------------------------------------------------------------
-- The HUD is small!                                                                             --
---------------------------------------------------------------------------------------------------

  If you are using a high in-game resolution and the HUD elements seem a little too small, then try
  adjusting the HUD scaling. To do that, go to:

    Options -> HUD Options -> Scaling Options

  In there, you will find a slider which is called "Fullscreen HUD". Adjust it as necessary. If
  adjusting it has no effect, then your in-game resolution is not big enough for the HUD to be
  scaled up.

---------------------------------------------------------------------------------------------------
-- NC HUD options menu (Accessing: Options -> NC HUD Options)                                    --
---------------------------------------------------------------------------------------------------

  | Note that if you load a mod on top of the HUD which happens to redefine the Options menu,   |
  | the HUD's own menu may be overridden and thus become inaccessible. The options below can be |
  | changed without having access to the menu. To do that, enter the option's CVAR into the     |
  | console, setting it to the desired value.                                                   |

  --------------------------------------- General Options ---------------------------------------

    - Statistics
      CVAR: nchud_toggletally
      Default: Off (0)

      Controls the toggling of the statistics display (kill, items, secrets, etc.). Setting this to
      "Counters" (1), toggles the display on; setting it to "Counters and %" (2), draws the stats
      as percentages, as well; setting it to "Off" (0), toggles the display off.

    - Received damage
      CVAR: nchud_toggledamage
      Default: Off (0)

      Controls the toggling of the received damage display. Setting this to "On" (1), toggles the
      display on, while setting it to "Off" (0), toggles it off.

    - Air supply bar
      CVAR: nchud_toggleair
      Default: On (1)

      Controls the toggling of the air supply display. Setting this to "On" (1), toggles the display
      on (while underwater, that is), while setting it to "Off" (0), toggles it off.

    - Active powerups
      CVAR: nchud_togglepowerups
      Default: On (1)

      Controls the toggling of the active powerups display. Setting this to "On" (1), toggles the
      display on, while setting it to "Off" (0), toggles it off.

  -------------------------------------- Ammo List Options --------------------------------------

    - Draw mode
      CVAR: nchud_toggleammo
      Default: Off (0)

      Controls the drawing mode of the ammo list. Setting this to "Owned weapons only" (1), draws
      ammo for weapons which are in the player's inventory only, while setting it to "All" (2),
      draws all relevant ammo regardless. "Off" (0) disables drawing of the list.

    - Allow list override?
      CVAR: nchud_allowammolistoverride
      Default: Yes (1)

      Controls whether or not to allow patches to override the list. Setting this to "Yes" (1),
      allows the list to be overridden, while setting it to "No" (0) does not.

  ---------------------------------- Overmax Bar Mode Options -----------------------------------

      --------------------------------------- Health ----------------------------------------

    - Mode
      CVAR: nchud_hpovermaxbarmode
      Default: Over max (0)

      Handles drawing of the over-max blue bar for health. If this is set to "Over 100" (1), the bar
      is drawn if the player has above 100 health, and up to 200 (default). If this is set to
      "Over max" (0), however, player's health points are handled as a percentage, and the bar is
      drawn when player's health is over its max value, and up to double that max value.

    - Bar maxes out at
      CVAR: nchud_hpovermaxbarvalue
      Default: 200

      Sets the value at which player's health needs to be for the over-max blue bar to become full.
      Setting this to any value which is below or equal to 100 results in using the default value.
      This option is only relevant if the above mode option is set to "Over 100" (1).

      --------------------------------------- Armor -----------------------------------------

    - Mode
      CVAR: nchud_arovermaxbarmode
      Default: Over max (0)

      Handles drawing of the over-max blue bar for armor. If this is set to "Over 100" (1), the bar
      is drawn if the player has above 100 armor, and up to 200 (default). If this is set to
      "Over max" (0), however, player's armor points are handled as a percentage, and the bar is
      drawn when player's armor is over its max value, and up to double that max value.

    - Bar maxes out at
      CVAR: nchud_arovermaxbarvalue
      Default: 200

      Sets the value at which player's armor needs to be for the over-max blue bar to become full.
      Setting this to any value which is below or equal to 100 results in using the default value.
      This option is only relevant if the above mode option is set to "Over 100" (1).

  --------------------------------- Bars Low State (%) Options ----------------------------------

    - Health
      CVAR: nchud_hplowstate
      Default: 35

      The low state of health is entered if health, as a percentage, is below the set value.
      Setting this to 0, disables the low state altogether.

    - Armor
      CVAR: nchud_arlowstate
      Default: 35

      The low state of armor is entered if armor, as a percentage, is below the set value.
      Setting this to 0, disables the low state altogether.

    - Primary ammo
      CVAR: nchud_am1lowstate
      Default: 35

      The low state of the primary ammo used by the weapon is entered if ammo, as a percentage, is
      below the set value. Setting this to 0, disables the low state altogether.

    - Secondary ammo
      CVAR: nchud_am2lowstate
      Default: 35

      The low state of the secondary ammo used by the weapon is entered if ammo, as a percentage,
      is below the set value. Setting this to 0, disables the low state altogether.

    - Air supply
      CVAR: nchud_airlowstate
      Default: 35

      The low state of the air supply is entered if the air supply, as a percentage, is below the
      set value. Setting this to 0, disables the low state altogether.

  --------------------------------- Monster Health Bar Options ----------------------------------

    - Draw mode
      CVAR: nchud_monsterhpbar
      Default: Off (0)

      Controls the drawing mode of the monster health bar. Setting this to "On" (1), draws the bar,
      while setting it to "Off" (0), does not. "Always" (2) forces the drawing of the bar for all
      monster types, even those that otherwise would not have the bar display when being aimed at.

      Note that for the bar to be displayed, the monster being aimed at needs...

        - ...not to have the bar display explicitly disabled (see the note just below).
        - ...not to have a spawn health value below the spawn health threshold value (see the
          "Spawn health threshold" option below).
        - ...not to be stealth, or be stealth but only if its alpha is greater than 0.5.
        - ...to not have the "Fuzzy" render style.
        - ...to not have the "OptFuzzy" render style, or have it but only if its alpha is greater
          than 0.5.

      * By giving a 'NCH_NoHpBar' item to the monster, the bar will not be displayed when the
        monster is aimed at. The item is ideally to be given upon the monster's spawning. Example:

        Spawn:
            BLAH A 0 NoDelay A_GiveInventory("NCH_NoHpBar")
            Goto Idle

        Idle:
            BLAH AB 10 A_Look
            Loop

    - Name is generic?
      CVAR: nchud_monsterhpbar_genname
      Default: No (0)

      Controls whether a generic name is displayed for the name or not. Setting this to "Yes" (1),
      displays "<Target>" as the name, while setting it to "No" (0), displays the monster's name.

    - Include friendlies?
      CVAR: nchud_monsterhpbar_friend
      Default: No (0)

      Controls whether friendly monsters should display a health bar or not. Setting this to
      "Yes" (1), displays it, while setting it to "No" (0), does not.

    - Health counter
      CVAR: nchud_monsterhpbar_hpcounter
      Default: Health only (1)

      Controls the display of the health counter. Setting this to "Health only" (1), displays it, while
      setting it to "Health and spawn health" (2), displays it along with the spawn health counter.
      Set it to "Off" (0) to hide the counter entirely.

    - Spawn health threshold
      CVAR: nchud_monsterhpbar_threshold
      Default: 0

      Sets the value at or above which a monster's spawn health needs to be for the bar to be drawn.

  ---------------------------------------- Color Options ----------------------------------------

    - Backgrounds
      CVAR: nchud_bgcolor
      Default: Default (-1)

      Sets the color used for the background graphics, including the status bar background. Setting
      this to "Default" (-1), allows usage of whatever color chosen by the HUD as the default color.

    - Highlight
      CVAR: nchud_hicolor
      Default: Default (-1)

      Sets the color used for highlighting. It affects statistics, weapon slots, inventory items,
      ammo list and inventory bar's arrows and selection box. Setting this to "Default" (-1), allows
      usage of whatever color chosen by the HUD as the default color.

---------------------------------------------------------------------------------------------------
-- Overriding icons                                                                              --
---------------------------------------------------------------------------------------------------

  Overriding the icons is simply achieved through the use of the ALTHUDCF lump:

    https://zdoom.org/wiki/ALTHUDCF

  Note that the HUD only supports overriding icons for keys, ammo, "artifacts" and powerups.

---------------------------------------------------------------------------------------------------
-- Overriding ammo list                                                                          --
---------------------------------------------------------------------------------------------------

  Overriding the ammo list is done by overriding the virtual function NCHF_AddAmmos() in your
  status bar class and then simply calling the NCHF_AddSingleAmmo() function for each ammo
  class you want to be listed.

    Example #1 --------------------------------------------------------------------------------

      A basic example. It merely flips the order of Doom's four ammo types

        override void NCHF_AddAmmos ()
        {
            NCHF_AddSingleAmmo("Cell");
            NCHF_AddSingleAmmo("RocketAmmo");
            NCHF_AddSingleAmmo("Shell");
            NCHF_AddSingleAmmo("Clip");
        }

    Example #2 --------------------------------------------------------------------------------

      This example demonstrates conditional list creation. Depending on which player class the
      player is playing as, a list is created for that class.

        override void NCHF_AddAmmos ()
        {
            name playerclassname = CPlayer.mo.GetClassName();

            if (playerclassname == 'ExamplePlayerA')
            {
                NCHF_AddSingleAmmo("RocketAmmo");
                NCHF_AddSingleAmmo("Cell");
            }
            else if (playerclassname == 'ExamplePlayerB')
            {
                NCHF_AddSingleAmmo("Clip");
                NCHF_AddSingleAmmo("Shell");
            }
            else
            {
                NCHF_AddSingleAmmo("Clip");
                NCHF_AddSingleAmmo("Shell");
                NCHF_AddSingleAmmo("RocketAmmo");
                NCHF_AddSingleAmmo("Cell");
            }
        }

---------------------------------------------------------------------------------------------------
-- Overriding statistics                                                                         --
---------------------------------------------------------------------------------------------------

  Overriding the statistics is done by overriding the virtual function NCHF_AddStats() in your
  status bar class and then simply calling the NCHF_AddSingleStat() function for each statistic
  item you want to be listed. Refer to the nch_basehud.zsc file for documentation on how to use
  the function.

    Example #1 --------------------------------------------------------------------------------

      This example draws a level time, kills and a "gold" counter.

        override void NCHF_AddStats ()
        {
            int curmonsters = level.killed_monsters;
            int totmonsters = level.total_monsters;

            NCHF_AddSingleStat(NCHC_STATLABELTYPE_TEXT, StringTable.Localize("$NCH_LABEL_TIME"), NCHC_STATFORMAT_SINGLE,
                level.TimeFormatted(), 0, 0, Thinker.Tics2Seconds(level.time) < level.partime);
            NCHF_AddSingleStat(NCHC_STATLABELTYPE_TEXT, StringTable.Localize("$NCH_LABEL_KILLS"), NCHC_STATFORMAT_RATIO,
                "", curmonsters, totmonsters, curmonsters == totmonsters, totmonsters > 0);
            NCHF_AddSingleStat(NCHC_STATLABELTYPE_ICON, "I_GOLD", NCHC_STATFORMAT_SINGLE, FormatNumber(GetAmount("Gold")));
        }

    Example #2 --------------------------------------------------------------------------------

      This example adds a "gold" counter to the already-existing level time, kills, items and
      secrets stats list, placing it at the bottom of the list. It does that by calling the
      the base HUD's instance of the NCHF_AddStats() function.

        override void NCHF_AddStats ()
        {
            NCH_BaseHUD.NCHF_AddStats(); // Tip: you can replace 'NCH_BaseHUD' with 'Super' if your
                                         // status bar class inherits directly from the base HUD.
            NCHF_AddSingleStat(NCHC_STATLABELTYPE_ICON, "I_GOLD", NCHC_STATFORMAT_SINGLE, FormatNumber(GetAmount("Gold")));
        }

---------------------------------------------------------------------------------------------------
