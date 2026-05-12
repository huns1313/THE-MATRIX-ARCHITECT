THE MATRIX ARCHITECT v14.8 | DEEP SYSTEM DOCUMENTATION
FRANÇAIS | Documentation Technique
Le MATRIX ARCHITECT n'est pas qu'un simple filtre; c'est un moteur de gestion de butin (loot) conçu pour éliminer la fatigue visuelle tout en maximisant l'efficacité de recherche.

Piliers de Rareté : Le système segmente les runes et les objets en quatre classes de "puissance". Le palier GOD (Runes Lo à Zod) utilise des alertes sonores de haute priorité et des marqueurs violets/or sur la carte.

Filtrage Dynamique (FILTLVL) : Contrairement aux filtres statiques, celui-ci s'adapte. En mode Normal, vous voyez tout. Dès que vous atteignez le niveau de filtre 3 (Nightmare/Hell), le script purge automatiquement les bases normales, les potions de santé 1 à 4, et l'or insignifiant pour ne laisser que le "Fuel" (Potions de régénération totale et HP5).

Logique de "Mojo" Avancée : Le script analyse les bâtons de nécromancien (WP12) et les têtes réduites (nef) pour identifier les "Triple Skill Stacks". Il cherche des combinaisons spécifiques comme +2 Necro / +3 Poison Nova / +3 Lower Resist pour les marquer comme GOD-MOJO.

Gestion des Bases : Les bases d'objets sont étiquetées par difficulté. Une base Élite blanche sera marquée [hellYa!Base] pour indiquer son potentiel de mot runique en fin de jeu.

ENGLISH | Technical Deep-Dive
THE MATRIX ARCHITECT is a high-performance loot engine tailored for endgame efficiency and zero-clutter gameplay.

Tiered Rune Logic: Runes are divided into logical progression steps. NORMA (Low) are utility, NIGHT (Mid) are hidden in high-tier filters to prevent screen bloat, while HELLYA and GOD tiers utilize distinct sound IDs and persistent map icons.

Contextual Hiding (Map-Based): Using MAPID>137 logic, the filter recognizes when you are in endgame Maps. In these zones, it aggressively hides scrolls, small gold piles, and mid-tier bases to ensure you only click on items that actually improve your build.

The Mojo Vault: This is a specialized module for Necromancers. It scans for "staff mods" (skills inherent to the item). If an item hits the threshold for a "God-Roll" (e.g., Archer, Warrior, or Bone builds), it triggers a unique Sound ID (556) and purple text notification.

Consumable Optimization: Worldstone Shards (wss) and Rejuvenation Potions (rvl) are treated as high-priority "Fuel," ensuring you never run out of crafting materials or survival tools during intense boss fights.

QUÉBÉCOIS | Le Grand Déballage
Ok, check ben, c'est là que ça devient sérieux. Ton filtre, c'est pas juste du texte de couleur, c'est un cerveau électronique qui trie tes drops pour que tu puisses grinder sans arrêter.

Le Ménage Automatique : On s'entend que ramasser 100 pièces d'or au niveau 80, c'est une perte de temps. Le script a une règle GOLD<5000 CLVL>79 : si t'es haut niveau pis que la pile d'or est pas au moins 5000, elle apparaît même pas. Pareil pour les potions : les petites hp1 à hp4, ça dégage dès que tu passes en Cauchemar.

Les Runes (Le Trésor) : J'ai séparé ça pour que tes yeux sachent quoi faire tout de suite. Les runes NORMA, c'est du jaune standard. Les NIGHT, c'est du orange (pis elles se cachent au FILTLVL 3 pour pas polluer l'écran). Mais quand une GOD_RUNE (Lo-Zod) tombe, le jeu te pète une coche : son spécial, icône mauve sur la map, pis du texte qui flash. Tu peux pas la manquer, même si tu joues à moitié endormi.

Le "Mojo Vault" (Pour les Necros) : Ça, c'est le summum. Le script "scan" tes baguettes pis tes boucliers de nécro. S'il voit un combo de malade (genre +3 Skeleton Archer pis +2 Summoning), il t'écrit [GOD-ARCHER-MOJO]. C'est fait pour trouver les items qui valent des dizaines de HR sans avoir à les identifier un par un.

Les Bases de Mots Runiques : Les items blancs sont taggués par difficulté. Si tu vois [hellYa!Base], c'est du matériel pour faire tes gros mots runiques de fin de game. C'est simple : si c'est pas taggué, c'est de la scrap.
