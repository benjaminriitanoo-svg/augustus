# Augustus Duel HTML5 — concept compétitif 2 joueurs sur carte partagée

## Vision

**Augustus Duel** transpose l'esprit de *Caesar III* et d'**Augustus 4.0+** vers une expérience **compétitive à deux gouverneurs** sur **une seule carte partagée**.

Les deux joueurs construisent simultanément sur le même territoire, exploitent les mêmes gisements, se disputent les mêmes axes routiers, et cherchent à dominer Rome par :

- la **population** ;
- la **richesse** ;
- le **favor impérial** ;
- la **maîtrise logistique** des routes et des walkers.

### Conditions de victoire

La partie s'achève immédiatement lorsqu'un gouverneur atteint l'un des seuils suivants :

- **5 000 habitants**, ou
- **10 000 denarii** en trésorerie nette.

### Tiebreakers si les deux joueurs atteignent un seuil dans le même tour

1. Plus haut **favor impérial** ;
2. Plus haut **rating de prospérité** ;
3. Plus haut **stock total de nourriture + biens finis** ;
4. Si l'égalité persiste : **victoire partagée proclamée par le Sénat**.

---

## 1. Boucle de jeu : rester fidèle à Augustus sans tomber dans le chaos

Le risque principal d'un mode 2 joueurs partagé est le **chaos systémique** : embouteillages de walkers, griefing permanent, ruine irréversible après une seule erreur. Pour éviter cela, il faut une structure lisible.

## Format de partie recommandé

### Option A — temps réel pausé avec impulsions stratégiques

C'est le mode le plus fidèle à Augustus.

- La ville tourne en **temps réel**.
- Toutes les **90 secondes**, une **Impulsion du Sénat** gèle brièvement le jeu pendant **12 secondes**.
- Pendant cette fenêtre, chaque joueur peut dépenser des **ordres d'autorité** :
  - poser un roadblock spécial ;
  - lancer une action diplomatique ;
  - déclencher un sabotage ciblé ;
  - acheter une priorité d'import/export ;
  - activer un édit temporaire.

**Pourquoi ça marche :**
- on garde le rythme “vivant” des walkers d'Augustus ;
- on évite le spam d'actions agressives à la milliseconde ;
- on crée des moments de lecture tactique très addictifs.

### Option B — tours simultanés courts

Si l'objectif est un HTML5 plus simple à implémenter :

- **Phase de planification** : 20 secondes ;
- **Phase de simulation** : 40 secondes ;
- **Phase sénatoriale** : 10 secondes ;
- puis tour suivant.

Les deux joueurs planifient en parallèle, puis la simulation résout les conséquences sur la carte partagée.

**Recommandation :** démarrer avec l'option B en prototype, puis migrer vers l'option A.

---

## 2. Règles d'équilibrage précises

## 2.1 Ressources limitées et contrôle du territoire

### Gisements et terres fertiles

Chaque ressource majeure est présente en quantité finie sur la carte :

- argile, fer, marbre, bois ;
- zones agricoles fertiles ;
- accès fluviaux ou maritimes ;
- points de carrefour commerciaux.

### Règle de propriété d'exploitation

Un gisement devient **concédé** à un joueur si :

- celui-ci construit le premier bâtiment d'extraction valide, **et**
- relie ce bâtiment à **son** réseau routier certifié.

### Anti-snowball

Pour éviter qu'un joueur prenne tout dès les 5 premières minutes :

- un même joueur ne peut contrôler au maximum que **60 % des gisements stratégiques** de la carte sans pénalité ;
- au-delà, il subit :
  - **+15 % de coût salarial** sur les industries lointaines ;
  - **-10 favor impérial** si des demandes impériales restent non satisfaites ;
  - **+20 % de temps de trajet** pour les caravanes hors district.

Cela pousse à la spécialisation et laisse une fenêtre de retour au joueur en retard.

## 2.2 Population et travailleurs

Chaque joueur a :

- son **propre pool de travailleurs** ;
- ses **propres logements** ;
- ses **propres migrants** ;
- ses **propres besoins en services**.

### Règle clé

Un bâtiment d'un joueur **ne peut jamais** recruter directement dans le pool de l'autre.

### Zones résidentielles neutres interdites

Pour garder la lisibilité, chaque maison a une **allégeance fixe** : rouge ou bleu.

### Catch-up économique sur la population

Si un joueur a au moins **20 % de population en moins** que son rival :

- ses migrants arrivent **15 % plus vite** ;
- le coût de ses maisons de base baisse de **10 %** ;
- les salaires impériaux lui accordent un bonus de **+5 popularité**.

Le bonus disparaît dès que l'écart retombe sous 10 %.

## 2.3 Richesse, taxes et commerce

### Trésorerie

Chaque gouverneur a :

- son propre trésor ;
- ses propres taxes ;
- ses propres dettes ;
- ses propres dépenses militaires et de service.

### Commerce externe partagé, créneaux séparés

Les routes commerciales impériales sont communes, mais les contrats sont limités.

#### Système proposé

- Chaque route commerciale dispose de **3 créneaux de quota** par saison.
- Les joueurs enchérissent pour la priorité pendant la phase sénatoriale.
- Le premier créneau va au meilleur enchérisseur.
- Le deuxième va au rival s'il paie au moins 60 % de l'enchère gagnante.
- Le troisième reste neutre ou réservé à l'IA impériale selon le scénario.

### Anti-monopole commercial

Si un joueur exporte plus de **70 %** d'une même ressource sur 3 saisons consécutives :

- le prix de vente pour lui chute de **12 %** ;
- le rival obtient un bonus de **+8 %** sur cette même ressource pendant la saison suivante.

## 2.4 Favor impérial

Le **favor impérial** est crucial, mais il ne doit pas écraser le reste.

### Gains de favor

- **+8** : satisfaire une demande impériale majeure ;
- **+4** : envoyer une aide militaire demandée ;
- **+2** : organiser un grand festival sans dette ;
- **+1** par saison : maintenir une ville sans incendie/effondrement/émeute.

### Pertes de favor

- **-6** : échouer une requête impériale ;
- **-4** : dette prolongée pendant 2 saisons ;
- **-3** : taux de criminalité critique ;
- **-2** : sabotage découvert par les agents impériaux.

### Rôle gameplay

Le favor sert de **ressource d'agression contrôlée**.

Un joueur peut dépenser du favor pour :

- obtenir une priorité commerciale ;
- demander un édit protecteur ;
- commander un désastre ciblé mineur ;
- annuler une pénalité de réputation.

### Garde-fou

Aucun joueur ne peut dépenser plus de **15 favor par saison** en actions hostiles.

Cela empêche le harcèlement permanent.

## 2.5 Routes, vols de routes et roadblocks

C'est ici que le mode devient mémorable.

### Types de route

- **Route publique** : accessible aux deux joueurs ;
- **Route concédée** : propriété d'un joueur si elle a été bornée par ses bornes civiques ;
- **Route contestée** : segment touché par les deux réseaux.

### Vol de route

Un joueur peut **revendiquer un segment ennemi** s'il remplit simultanément :

1. il contrôle les deux intersections aux extrémités ;
2. il y maintient une présence de service/logistique pendant **30 secondes simulées** ;
3. le rival n'a ni préfet ni ingénieur dans le district ;
4. il paie une taxe de réaménagement en denarii.

### Effets du vol

- le segment passe en **route contestée** pendant 20 secondes ;
- les walkers ennemis peuvent encore le quitter, mais n'y planifient plus de nouvel itinéraire ;
- après la fenêtre de contestation, la route devient concédée au nouveau propriétaire.

### Roadblocks

Deux familles :

- **Roadblock civil** : filtre les walkers par propriétaire et catégorie ;
- **Barricade contentieuse** : bloque totalement pendant 15 secondes, puis s'effondre.

### Limites anti-chaos

- maximum **3 roadblocks spéciaux** actifs par joueur ;
- impossible de bloquer une sortie unique de spawn migrant ;
- impossible de couper **100 %** des accès d'un district résidentiel pendant plus de 20 secondes ;
- une route contestée ne peut pas être recontestée pendant 45 secondes.

---

## 3. Mécaniques uniques deux joueurs

## 3.1 Alliances temporaires

Le Sénat tolère des pactes courts.

### Pacte de non-agression — 1 saison

Effets :
- interdiction de sabotage direct ;
- routes publiques communes sur les nouvelles poses frontalières ;
- bonus de **+5 favor** à chaque joueur si le pacte est respecté jusqu'au bout.

### Pacte de ravitaillement

Un joueur peut vendre automatiquement à l'autre :
- nourriture ;
- huile ;
- poteries ;
- meubles.

Le vendeur gagne des denarii ; l'acheteur reçoit une stabilité sociale immédiate.

**Twist très Augustus :** le pacte peut être rompu, mais Rome punit la perfidie :
- **-8 favor impérial** ;
- **-10 réputation commerciale** pendant une saison.

## 3.2 Sabotages ciblés par désastres

Le sabotage ne doit pas ressembler à un “sort d'annihilation”. Il faut du coût, de la télégraphie, et des contres.

### Actions possibles

#### 1. Incendiaires soudoyés
- Coût : **600 denarii + 4 favor** ;
- Cible : un bâtiment industriel ou de service ;
- Contre : préfets, couverture du risque, guetteurs ;
- Télégraphie : agitation dans le district + rumeur sénatoriale.

#### 2. Inspecteurs corrompus
- Coût : **350 denarii + 2 favor** ;
- Effet : un entrepôt rival opère à **-40 %** pendant 45 secondes ;
- Contre : bureau du magistrat ou édit de transparence.

#### 3. Trouble civique
- Coût : **3 favor** ;
- Effet : baisse temporaire de moral dans un quartier, ralentissant immigration et taxes ;
- Contre : temples, divertissement, forums.

#### 4. Malédiction locale orchestrée
- Coût : sacrifice + favor + temple dédié ;
- Effet : petit désastre ciblé si le rival a négligé les dieux ;
- Contre : couverture religieuse correcte.

### Règle d'équilibrage majeure

Toute action hostile doit être :

- **annoncée** par un signal visuel/sonore ;
- **contre-jouable** ;
- **limitée par un cooldown saisonnier** ;
- **moins rentable** qu'un bon développement économique si elle est spammée.

## 3.3 Influence sénatoriale sur la carte

Ajout très romain et très “one more turn”.

Tous les 3 tours, le Sénat publie une **motion** aléatoire :

- “Rome réclame plus de blé.”
- “Les jeux sont à l'honneur.”
- “Les districts pollués sont mal vus.”
- “Le commerce du marbre est encouragé.”

Le joueur qui s'adapte le mieux pendant la fenêtre active gagne :

- denarii,
- favor,
- bonus de vitesse de commerce,
- ou immunité partielle à un sabotage.

## 3.4 Frontières administratives

Le joueur peut poser des **bornes civiques**.

Effets :
- elles créent des districts ;
- elles stabilisent la propriété routière ;
- elles réduisent les captures opportunistes ;
- elles donnent une identité visuelle forte à la rivalité.

---

## 4. Comment éviter le chaos systémique

## Quatre règles d'or

### 1. Pas de destruction instantanée sans réponse
Toute attaque doit laisser une fenêtre de réaction.

### 2. Le contrôle routier doit être local, pas global
On vole un axe, un carrefour, un district — jamais toute la ville d'un clic.

### 3. Les walkers doivent rester compréhensibles
Le joueur doit savoir :
- à qui appartient un walker ;
- quel réseau il utilise ;
- pourquoi il est bloqué ;
- pourquoi il change de trajet.

### 4. L'économie doit battre l'agression à long terme
Le sabotage sert à ouvrir une fenêtre tactique, pas à remplacer la gestion urbaine.

## Valeurs recommandées de garde-fou

- **1 sabotage majeur maximum** par joueur et par saison ;
- **2 sabotages mineurs maximum** ;
- **3 segments contestés maximum** en même temps par joueur ;
- **coût de reconstruction réduit de 20 %** pour le défenseur sur un bâtiment saboté ;
- **protection de grâce de 60 secondes** après reconstruction d'un bâtiment ciblé.

---

## 5. Architecture JavaScript : deux simulations de walkers sans lag

Le piège serait de dupliquer naïvement toute la simulation et recalculer tous les chemins à chaque frame.

## 5.1 Principe général

Utiliser un **monde partagé** avec des systèmes spécialisés :

- **SharedMap** : terrain, routes, districts, ownership, ressources ;
- **GovernorState[2]** : économie, population, logements, favor, workers ;
- **WalkerSystem** : tous les walkers des deux joueurs dans une seule boucle ECS-lite ;
- **RoutingSystem** : graphe routier partagé avec caches par faction ;
- **ConflictSystem** : contestation de route, roadblocks, sabotages ;
- **SenateSystem** : tours, motions, pactes, actions de phase.

## 5.2 Ne pas faire “deux moteurs complets”

Il faut **une seule simulation de carte**, pas deux copies du monde.

Chaque entité reçoit simplement :

- `ownerId` ;
- `factionMask` ;
- `permissions` ;
- `districtId`.

Ainsi, les systèmes communs peuvent traiter tous les walkers d'un coup.

## 5.3 Tick fixe et rendu découplé

### Boucle recommandée

- simulation en **tick fixe** : 8 à 20 ticks/seconde ;
- rendu en `requestAnimationFrame` ;
- interpolation visuelle entre deux ticks.

Exemple sûr pour navigateur :

- **10 ticks/seconde** pour la logique ;
- **60 fps** pour l'affichage si disponible.

Pourquoi :
- résultats déterministes ;
- coût CPU prévisible ;
- debug multijoueur plus simple ;
- replays possibles.

## 5.4 Pathfinding performant

### Recommandation

- représenter la route comme un **graphe de segments et intersections** ;
- recalculer les chemins seulement si :
  - la destination change ;
  - un segment est contesté ;
  - un roadblock modifie les permissions ;
  - un district devient inaccessible.

### À éviter

- A* tuile par tuile pour chaque walker à chaque frame.

### À préférer

- A* ou Dijkstra **sur graphe routier compressé** ;
- cache de route par tuple :
  - `(ownerId, fromNode, toNode, permissionProfile, graphRevision)`.

Quand une route change, on incrémente `graphRevision` seulement pour le district concerné.

## 5.5 Mise à jour des walkers

Traiter les walkers en lots :

1. walkers de service ;
2. walkers logistiques ;
3. migrants ;
4. militaires / sabotage ;
5. effets spéciaux.

Chaque walker garde :

- sa position continue ;
- son segment courant ;
- sa distance sur segment ;
- sa destination logique ;
- son “stuck timer” ;
- son propriétaire.

Si bloqué :
- attendre une courte fenêtre ;
- tenter une route alternative ;
- sinon rebrousser chemin ;
- sinon entrer dans un état d'échec proprement géré.

## 5.6 Structures de données recommandées

### Carte

```js
class SharedMap {
  width;
  height;
  tiles;          // Uint16Array ou objets compacts
  roadGraph;      // noeuds + segments
  districts;      // zones administratives
  resources;      // gisements / fertilité
  graphRevision;  // incrément global ou par district
}
```

### Joueurs

```js
class GovernorState {
  id;
  color;
  denarii;
  population;
  favor;
  workersAvailable;
  workersEmployed;
  buildings = [];
  walkers = [];
  cooldowns = {};
  senateOrders = [];
}
```

### Walker compact

```js
class Walker {
  id;
  ownerId;
  type;
  segmentId;
  distanceOnSegment;
  speed;
  state;
  targetNode;
  homeBuildingId;
  cargoType;
  cargoAmount;
  stuckTicks;
}
```

## 5.7 Réduction du lag navigateur

### Bonnes pratiques

- Canvas 2D pour prototype, WebGL seulement si nécessaire ;
- atlas de sprites partagé ;
- pas de création d'objets dans la boucle chaude ;
- tableaux préalloués ;
- spatial hash pour collision légère et sélection ;
- simulation hors écran possible dans un `Worker` si la charge monte.

### Architecture évolutive

- **Main thread** : UI, input, rendu ;
- **Web Worker** : simulation/ticks ;
- échange via `postMessage` de snapshots compacts ;
- plus tard : `SharedArrayBuffer` pour versions avancées.

Pour un premier prototype jouable, rester mono-thread mais bien structuré est souvent suffisant.

---

## 6. Squelette de code conseillé pour le prototype HTML5

Un prototype jouable minimal doit inclure :

- carte partagée ;
- deux gouverneurs ;
- routes de couleur ;
- roadblocks ;
- walkers des deux camps ;
- phases de tour ;
- capture de route simple ;
- objectifs population / richesse.

Voir le fichier prototype : `doc/prototypes/duel_canvas.html`.

---

## 7. Boucle d'addictivité “très Augustus”

Pour retrouver l'effet *encore un tour / encore une saison* :

1. **Rareté spatiale** : un gisement ou un carrefour change toute la partie.
2. **Lisibilité des walkers** : voir les flux réussir ou s'effondrer donne une satisfaction immédiate.
3. **Poussée impériale** : le Sénat force les adaptations.
4. **Méchanceté dosée** : sabotage oui, annihilation non.
5. **Reconstruction rapide mais coûteuse** : toujours une chance de retour.
6. **Compétition visible** : frontières, routes, district, monuments de prestige.

---

## 8. Recommandation de MVP

Pour une première version jouable HTML5 :

### À garder
- carte partagée ;
- deux couleurs/factions ;
- routes capturables ;
- roadblocks ;
- population, denarii, favor ;
- sabotage mineur ;
- motion du Sénat ;
- victoire à 5000 / 10000.

### À repousser
- combats militaires complets ;
- religion très détaillée ;
- commerce maritime fin ;
- walkers spécialisés trop nombreux ;
- diplomatie complexe multi-contrats.

Le cœur du fun viendra d'abord de :

**construire vite, couper proprement, défendre ses flux, exploiter une fenêtre, et voir sa ville prospérer sous les yeux du rival.**
