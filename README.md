### Mik's Scrolling Battle Text (MSBT) - Unofficial Update Changelog
**Version**: Unofficial Patch (March 24, 2025)  
**Updated By**: [Your Name/Handle] (Community Contributor)  
**Original Addon By**: Mikord  
**Addon Link**: [https://www.curseforge.com/wow/addons/mik-scrolling-battle-text/](https://www.curseforge.com/wow/addons/mik-scrolling-battle-text/)

#### Overview
This unofficial update addresses a compatibility issue causing an `OptionsButtonTemplate` error in Mik's Scrolling Battle Text, which appears to have surfaced due to changes in World of Warcraft's API, particularly in Cataclysm Classic. The original maintainer seems to have become inactive, so this patch aims to keep the addon functional for the community.

#### Changes
- **Fix: OptionsButtonTemplate Error**
  - Modified the `MSBTProfiles.lua` file to resolve an error where the `OptionsButtonTemplate` frame was causing issues in certain game versions.
  - Replaced the conditional frame creation logic on line 3330:
    - **Old**: `local button = CreateFrame("Button", nil, frame, IsCataClassic and "OptionsButtonTemplate" or "UIPanelButtonTemplate")`
    - **New**: `local button = CreateFrame("Button", nil, frame, "UIPanelButtonTemplate")`
  - This change ensures the addon uses `UIPanelButtonTemplate`, which is believed to be compatible across all WoW versions, removing the dependency on the `IsCataClassic` check.

#### Installation Instructions
1. **Backup**: Before applying this update, make a backup of your `MSBTProfiles.lua` file (located in `WTF/Account/[YourAccount]/SavedVariables/`).
2. **Edit**: Open `MSBTProfiles.lua` in a text editor and locate line 3330. Replace the old line with the new one as shown above.
3. **Test**: Reload your game and verify the options menu works without errors.

#### Notes
- **Compatibility**: This fix has been tested in **Cataclysm Classic** and is believed to work in other versions (e.g., Retail, Classic Era), as `UIPanelButtonTemplate` is a widely supported template. However, testing outside of Cataclysm Classic has not been performed by the contributor.
- **Disclaimer**: This is a community-driven update and not an official release. Use at your own risk, and keep backups of your original files.
- **Feedback**: If you encounter issues or have suggestions, please share them with the community (e.g., via CurseForge comments or relevant forums).

#### Acknowledgements
- Thanks to the WoW addon community for reporting the issue and testing solutions.
- Credit to Mikord for creating this fantastic addon that continues to enhance our gameplay experience.
