Diegetic Audio Control: In-world volume control for STALKER Anomaly, by Damian
Latest: 1.0.4 (xlibs 1.2.1)
GitHub: https://github.com/damiansirbu-stalker/Diegetic-Audio-Control

Anomaly has no way to control the volume of radios, megaphones, guitars, and harmonicas independently from the game's audio sliders. You can't turn down Duty propaganda without killing ambient sounds. Diegetic Audio Control fixes this.

The mod hooks directly into the audio subsystems that play in-world sound: ph_sound for radios and megaphones, guitar_anim for campfire guitar, harmonica_anim for harmonica. Each source gets its own volume slider, enable/disable toggle, and where applicable a pause multiplier that controls silence between tracks or announcements.

A master volume multiplier sits on top of everything. All changes apply immediately through MCM.

Missing dependencies are handled gracefully. If you don't have the guitar or harmonica mods installed, those controls simply do nothing.

Features:

Radios:
  Volume control for faction base radios and music
  Pause multiplier between tracks (longer silence or shorter)
  Enable/disable toggle

Megaphones:
  Volume control for Duty propaganda, Arena announcer, alarms
  Pause multiplier between announcements
  Enable/disable toggle

Guitar:
  Volume control for campfire guitar (requires Guitar Animation mod)
  Enable/disable toggle

Harmonica:
  Volume control for harmonica (requires Harmonica mod)
  Enable/disable toggle

Master volume multiplier applied to all sources

Requirements:
Anomaly 1.5.3
Modded exes
xlibs (https://www.moddb.com/mods/stalker-anomaly/addons/xlibs-1001)
MCM
Radio_Remastered or similar (for radio/megaphone control)
Guitar Animation by Daiviey (optional, for guitar control)
Harmonica by Daiviey (optional, for harmonica control)

Install (MO2):
1. Install xlibs
2. Install Diegetic Audio Control
3. Load order does not matter
4. Configure via MCM

Uninstall (MO2):
Disable or remove in MO2.

Configuration:
All settings in MCM under Diegetic Audio Control. All defaults are 1.0 (unchanged from game behavior).

Compatibility:
Tested with GAMMA. Hooks into ph_sound, guitar_anim, and harmonica_anim. If those mods are not present the relevant controls are inactive. No base script modifications.

Development:
Written against X-Ray Monolith engine source, Demonized exes source code, and Anomaly 1.5.3 unpacked gamedata.
Code patterns and engine usage validated against established work by reputable GAMMA modders (Demonized, Vintar0, RavenAscendant, xcvb).
The code is validated in real time by a multi-stage pipeline: luacheck, selene, tree-sitter AST analysis, contract rules, cross-file dependency resolution, cyclomatic complexity analysis, crash and vulnerability pattern detection, lua54 integration testing with X-Ray engine stubs, gitleaks secret scanning.
Full report in doc/test-report.log.

Credits:
Stalker_Boss - Russian translation

Usage and License:
  Modpacks: allowed and encouraged. Keep the readme and license files.
  Addons, patches, integrations: allowed. Credit "Diegetic Audio Control by Damian Sirbu" visibly on your mod page.
  Full license in LICENSE file and on GitHub.

Versions:

1.0.4
  Changed: xlibs dependency updated to 1.2.1

1.0.3
  MCM snapshot pattern and performance improvements.
  Changed: MCM configuration uses snapshot pattern (xmcm.create_config) for faster reads
  Changed: MCM reset button support (mcm_option_restore_default callback)
  Fixed: uncached engine globals (CreateTimeEvent, RegisterScriptCallback)
  Changed: xlibs dependency updated to 1.2.0

1.0.2
  Fixed: dependency gate uses exact version match instead of string comparison

1.0.1
  Dependency gate and Russian translation.
  Added: dependency gate - clear error message if xlibs is missing or outdated
  Added: Russian translation (Stalker_Boss)

1.0.0
  First release. Volume and pause control for radios, megaphones, guitar, harmonica.
  Added: per-source volume sliders with master multiplier
  Added: pause/frequency control for radios and megaphones
  Added: per-source enable/disable toggles
  Added: graceful handling of missing audio mods
