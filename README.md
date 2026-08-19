# Chronique

Un jeu narratif asynchrone à N joueurs. Chacun pilote — non : **conseille** —
un personnage autonome dans un monde partagé. Personne ne donne d'ordre :
chaque joueur est une voix intérieure que son personnage peut suivre ou
ignorer. Un Maître du Jeu automatisé arbitre et publie chaque jour un
chapitre de 500 mots, en issue GitHub.

L'absence n'est jamais pénalisée : disparaissez deux semaines, votre
personnage sera vivant et son histoire aura avancé.

## Jouer

```
git clone <ce repo>
cd The-Quest
claude
```

C'est tout. La session détecte qui vous êtes et vous guide (`CLAUDE.md`).
Trois commandes existent, mais la session vous les proposera d'elle-même :
`/rejoindre`, `/briefing`, `/murmurer`.

Depuis un téléphone, sans session : éditez `souls/<votre-slug>/intent.md`
dans l'app GitHub — deux lignes suffisent. **L'interface est le fichier, pas
l'outil.**

## L'architecture en trois couches

| Couche | Où ça tourne | Rôle |
|---|---|---|
| Le personnage | Claude Code du joueur | Décide, ressent, agit |
| Le joueur | conversation avec son personnage | Conseille, argumente, ne commande pas |
| Le MJ | routine cloud dédiée | Arbitre, résout, raconte |

L'isolation est structurelle : le cerveau de chaque personnage vit sur la
machine de son joueur. Aucune fuite d'information entre personnages.

## Mise en service (fondateur)

1. **Relire/réécrire `world/premise.md` et `world/sealed.md`** à plusieurs,
   une demi-heure, pas plus. Le monde se découvre tick par tick. Une version
   d'amorce est en place ; `sealed.md` ne se relit plus ensuite.
2. **Tester `/rejoindre`** en créant un personnage de test — c'est la
   première chose à faire tourner. Un personnage d'amorce, Kael, existe déjà
   (orphelin, reprenable).
3. **Jouer le tick MJ à la main**, en session interactive (« Lis
   ROUTINE-MJ.md et exécute-le »), sur 3 ticks. Vérifier que le canon tient
   et que la chronique respecte les 500 mots.
4. **Créer la routine MJ** sur un compte dédié, quotidienne (8h par ex.),
   champ du prompt en une ligne :
   `Lis ROUTINE-MJ.md à la racine et exécute-le intégralement.`
   ⚠️ Activer **« Allow unrestricted branch pushes »** côté web, sinon la
   routine ne pousse que sur `claude/*` et l'état ne s'accumule jamais —
   c'est le blocage n°1 au premier run. Intervalle minimum d'une heure,
   quota journalier selon le plan ; un déclencheur API existe pour un tick
   manuel.
5. Ensuite seulement : `/briefing` en réel, routines joueurs (rappel à 20h
   par ex., via `/rejoindre`), boîte aux lettres, récapitulatif
   hebdomadaire. **Ne rien pousser au-delà de l'étape 4 avant que 1-4
   tournent une semaine en réel.**

### Protection de branche

`CODEOWNERS` exige une approbation sur le cœur (`MJ.md`, `ROUTINE-*.md`,
`world/`) dès qu'une ruleset impose les PR. Mais les `intent.md` et la
routine MJ poussent **en direct sur `main`** : si vous activez une ruleset
« require pull request », ajoutez le compte MJ en bypass et n'imposez pas de
PR sur `souls/*/intent.md` — ou, plus simple au démarrage, pas de ruleset du
tout : la convention fait loi, et git garde l'historique.

Les prompts des routines sont versionnés ici (`ROUTINE-MJ.md`,
`ROUTINE-JOUEUR.md`) : la logique se modifie par PR, jamais dans une
interface web.
