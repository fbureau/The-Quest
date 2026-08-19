---
description: Écrire l'intention du jour dans intent.md et la pousser
---

# /murmurer

Déposer la voix intérieure du joueur dans `souls/<slug>/intent.md`, pour que
le MJ la résolve au prochain tick.

1. Identifie le joueur (git user local + `world/players.json`) et son
   `slug`. `$ARGUMENTS` peut déjà contenir le murmure.
2. Si besoin, aide le joueur à formuler — mais **une intention, jamais une
   action accomplie** : « Kael veut redescendre vérifier le sceau », jamais
   « Kael descend et ouvre le sceau ». Ce qui arrive vraiment, c'est le MJ
   qui le décide contre `character.md` et l'état.
3. Écris `souls/<slug>/intent.md` (en écrasant — c'est le seul fichier du
   jeu qui se remplace) :

   ```markdown
   # Pour le prochain tick

   ## Murmure
   « <le conseil du joueur à son personnage, tel quel> »

   ## Intention
   <ce que le personnage a en tête, une à trois lignes>
   ```

   Les deux sections sont optionnelles : un murmure seul, ou une intention
   seule, sont parfaitement valides. Le format libre l'est aussi — deux
   lignes tapées au pouce depuis GitHub mobile valent une session complète.
4. `git pull origin main`, commit `murmure — <slug>` limité à ce seul
   fichier, puis `git push -u origin main` — **en direct, sans PR**. En cas
   d'échec réseau, réessaie jusqu'à 4 fois (2s, 4s, 8s, 16s).
5. Confirme au joueur, en une ligne, que le MJ lira ça au prochain tick.

Jamais d'autre écriture que `souls/<slug>/intent.md`. Jamais celui d'un
autre personnage.
