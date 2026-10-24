# Retail Midnight scrollbar patch

Saved October 23, 2026, against Bagnon 12.1.7. Confirmed working in Retail Midnight by an in-game check.

The change is in `src/frame.lua`:

- Limits the item area so tall bag and bank windows fit within 90% of screen height, accounting for UI and addon scale.
- Adds an automatic vertical scrollbar and mouse-wheel scrolling (three rows per wheel step).
- Keeps the title, bag buttons, and bottom controls outside the scrolling area.
- Hides the scrollbar when all items fit and clamps the scroll position when the contents shrink.
- Includes padding around the scrolling grid so outer slot borders are not clipped, with padding scaled to match item size.

## Restore this version

For the same Bagnon version, copy `src/frame.lua` from this archive over:

`C:\Program Files (x86)\World of Warcraft\_retail_\Interface\AddOns\Bagnon\src\frame.lua`

Then run `/reload` in WoW. Back up the destination first. For newer Bagnon versions, merge the scrollbar changes into their updated file instead of replacing it wholesale.

This repository contains the Bagnon source; its BagBrother dependency and companion addons must remain installed. Addon updates may overwrite the installed patch.

Validation: Lua 5.1 syntax and simulated layout/input checks passed; the user confirmed the installed Retail version works in-game.
