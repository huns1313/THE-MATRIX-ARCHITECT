# THE MATRIX ARCHITECT // SYSTEM_OPTIMIZED
### Un filtre d'objets personnalisé pour Project Diablo 2 (PD2)
**Architecte :** [GOD] HYUUNNS  
**Philosophie de conception :** Efficacité pure, zéro encombrement, forgé avec plus de 25 ans d'expérience pointue sur l'itemisation de Diablo 2.

---

## APERÇU DE LA CONFIGURATION DU SYSTÈME

### [0.0] Configurations globales & Alias
La structure principale utilise trois commutateurs de mode actifs pour ajuster la visibilité en fonction de votre progression.
* `MODE_NORMA` (Mode 1) : Optimisation pour le début de jeu.
* `MODE_NIGHT` (Mode 2) : Filtres de suivi pour le mid-game et le mode Cauchemar.
* `MODE_hellYa` (Mode 3) : Filtres et cartes absolus pour le endgame tardif.
* Inclut des blocs de regroupement dynamiques pour les runes empilées ou non, du premier au dernier niveau (`RUNES_NORMA` jusqu'à `RUNES_GODLY`).

### [1.0] Overlays maîtres & Architecture des accessoires
* **Intercepteurs de qualité :** Déclencheurs initiaux vérifiant l'état brut des objets (`ETH SUP`, `ETH !SUP`, `!ETH SUP`) pour appliquer des métadonnées visuelles uniformes avant de passer l'exécution aux lignes inférieures.
* **Bloqueurs de silence absolu :** Impose des barrières de niveau d'objet (ILVL) strictes selon le mode actif. Les bijoux et charmes de bas/moyen niveau sont supprimés silencieusement dès que la difficulté augmente (`FILTLVL=3` efface les bijoux en dessous d'`ILVL 80`).
* **Matrices de bijoux :** Règles strictes qui filtrent dynamiquement les amulettes, les anneaux et les charmes selon leur niveau d'objet spécifique (`n.`, `NM.`, `Ya!!`).

### [2.0] Overrides de visibilité forcée (Joyaux & Armes de jet)
* **[2.0.1] Override maître du système de joyaux :** Outrepasse les contraintes de base en isolant nativement les structures de joyaux (`jew`). Utilise des icônes de carte personnalisées et des alertes audio dédiées (`SOUNDID-9`) tout en triant les joyaux par niveau (`ILVL`).
* **[4.0.2] Master Overlay des armes de jet :** Isole nativement toutes les armes de jet (`WP5`). Empêche les objets de qualité normale ou exceptionnelle d'envahir les zones de haute progression grâce à des lignes de filtrage de type absolu (`WP5 NORM FILTLVL>1`).

### [3.0] Consommables & Bases de classe prioritaires
* **L'aspirateur Matrix :** Système de nettoyage automatisé pour les objets de récupération de bas niveau, les parchemins utilitaires et les potions de base dès que les paliers de difficulté Cauchemar et Enfer sont atteints (`FILTLVL>1`).
* **Nœuds de priorité absolue :** Ancres de visibilité permanentes pour les éléments fondamentaux (objets de quête, clés) et logique d'affichage forcé pour les boucliers de Nécromancien (`CL4`).
* **Matrice de tri des objets de classe :** Gère les pièces d'armure et d'arme spécifiques aux classes, en imposant des critères structurels dynamiques (comme un nombre minimum de châsses `SOCK>1`) avant d'activer la visibilité.

### [4.0] Bases de mots runiques & Nœuds du marché Endgame
* **Hub des armes et armures d'élite pour mercenaire :** Lignes de vérification ultra-agressives surveillant des listes de codes spécifiques (`utp`, `uld`, `ucl`, etc.) pour retenir les meilleures bases éthérées avec ou sans châsses (`SOCK=0` et `SOCK=4`).
* **Matrice Caster & Fléaux indestructibles :** Traceurs d'actifs natifs conçus pour filtrer et afficher les armes de progression ciblées (ex. Fléaux, Arcs d'élite, Boucliers de Paladin à hautes résistances).
* **La purge finale :** La barrière sanitaire absolue du fichier. Élimine automatiquement les modèles d'armes blancs à 0 châsse (`SOCK=0 !RARE`), les objets normaux non rares et les objets obsolètes avant l'exécution des moteurs de visibilité inférieurs.

### [5.0] Uniques, Sets & Blocs maîtres de monnaie
* **Affichage échelonné de l'équipement :** Ajustement visuel dynamique selon la rareté. Les Uniques, Sets et Rares affichent des badges typographiques personnalisés selon leur niveau (`[Ya!!]`, `[NM.]`, `[n.]`).
* **Suivi de l'économie PD2 :** Indicateurs visuels universels surveillant les objets d'échange, les cartes, la monnaie (Currency), les matériaux d'artisanat et les composants pour Uber Tristram.

### [6.0] Rune Master Control & Catch-All des cartes
* **Intercepteurs de couleur pour runes :** Remplacements de noms personnalisés affichant le niveau exact des runes (`r01` à `r33`) avec des couleurs tactiques dédiées pour suivre les runes de haut niveau sans effort.
* **Assainissement des cartes tardives :** Blocs de filtrage de l'or dynamiques et règles environnementales conçus pour masquer l'encombrement des objets obsolètes lors des sessions de mapping (`MAPID>137`).

### [7.0] Cartes & Filtres environnementaux dynamiques
La phase d'optimisation finale qui s'active automatiquement dès que vous entrez dans les zones de mapping à haute densité du endgame.
* **Suivi de progression des cartes :** Catégorise instantanément le contenu endgame par indicateurs de paliers (`T1` à `T3`), en appliquant un préfixe doré persistant pour identifier les modifications de zone.
* **L'aspirateur de cartes :** Un script de nettoyage environnemental très agressif qui s'initialise dans les instances (`MAPID>137`). Il masque complètement les drops normaux et exceptionnels (`NORM OR EXC`) une fois les objectifs de progression du personnage atteints (`CLVL<80`).
* **Matrice dynamique des seuils d'or :** Filtrage contextuel de l'or qui s'ajuste avec le niveau de votre personnage. Il nettoie l'écran en masquant les petites piles d'or (`GOLD<100` au début, jusqu'à masquer tout tas inférieur à `5000` pièces d'or une fois le niveau 80+ atteint).

### [8.0] Catch-All post-process maître (Finitions structurelles)
La zone de réception sécurisée pour les propriétés d'objets exceptionnelles de haute valeur qui ont réussi à franchir vos phases strictes d'aspiration.
* **Extraction d'actifs éthérés :** Crochets visuels explicites suivant les codes d'objets d'élite magiques et rares non identifiés tombant à l'état éthéré (`MAG ETH ELT` / `RARE ETH ELT`).
* Attribue des étiquettes violettes nettes et très visibles (`[Ya!!Magic]` / `[Ya!!Rare]`) pour s'assurer que les bases de trophées ou d'artisanat de premier plan sont correctement identifiées.

### [9.0] Système de secours d'urgence (Emergency Fallback)
Le filet de sécurité final situé tout au bas de la structure d'analyse du fichier.
* **La garde des blueprints :** Agit comme une ancre de secours automatisée pour garantir que si un objet unique, de panoplie ou divers non documenté franchit vos règles personnalisées strictes, il utilise par défaut la couche de configuration native du client (avec alertes audio standard et indicateurs de minicarte)—assurant ainsi zéro perte de données et aucun drop ultra-rare manqué.
