ENGLISH | Technical Deep-Dive THE MATRIX ARCHITECT is a high-performance loot engine tailored for endgame efficiency and zero-clutter gameplay.

Tiered Rune Logic: Runes are divided into logical progression steps. NORMA (Low) are utility, NIGHT (Mid) are hidden in high-tier filters to prevent screen bloat, while HELLYA and GOD tiers utilize distinct sound IDs and persistent map icons.

Contextual Hiding (Map-Based): Using MAPID>137 logic, the filter recognizes when you are in endgame Maps. In these zones, it aggressively hides scrolls, small gold piles, and mid-tier bases to ensure you only click on items that actually improve your build.

The Mojo Vault: This is a specialized module for Necromancers. It scans for "staff mods" (skills inherent to the item). If an item hits the threshold for a "God-Roll" (e.g., Archer, Warrior, or Bone builds), it triggers a unique Sound ID (556) and purple text notification.

Consumable Optimization: Worldstone Shards (wss) and Rejuvenation Potions (rvl) are treated as high-priority "Fuel," ensuring you never run out of crafting materials or survival tools during intense boss fights.
