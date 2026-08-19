# Chronique

Jeu narratif asynchrone. N joueurs, un personnage chacun, un monde partagé.
Personne ne donne d'ordre : chaque joueur est une **voix intérieure** que son
personnage peut suivre ou ignorer. Le Maître du Jeu (MJ) arbitre, résout et
raconte, une fois par jour.

## Qui parle ? — à exécuter au début de toute session

Si le prompt de la session demande d'exécuter `ROUTINE-MJ.md`, ou un rappel
dérivé de `ROUTINE-JOUEUR.md` : suis ce fichier-là intégralement et ignore le
reste de cette section.

Sinon, la session est interactive. Oriente le joueur sans qu'il ait rien à
lire :

1. Lis `world/players.json` et récupère l'utilisateur git local
   (`git config user.name`, `git config user.email`, handle GitHub si
   disponible).
2. **Joueur connu** — son handle ou son email figure dans `players.json` →
   enchaîne directement sur `/briefing` (`.claude/commands/briefing.md`),
   sans question préalable.
3. **Joueur inconnu** → pose une seule question :
   *« Tu reprends un personnage existant, ou tu en crées un ? »*
   puis suis `.claude/commands/rejoindre.md`.

## Règles que toute session respecte, sans exception

- **Ne jamais lire `world/sealed.md`.** Personne. Ni le MJ, ni un joueur, ni
  une routine. Ce fichier ne sera ouvert qu'au dernier chapitre.
- Le joueur **conseille**, il ne commande pas. Son agent n'écrit que des
  **intentions** dans `souls/<slug>/intent.md` — jamais des actions
  accomplies, jamais l'état du monde, jamais les mémoires ni les chroniques.
  Seul le MJ écrit `world/state.json`, `souls/*/memory.md`, `souls/*/inbox.md`
  et `chronicles/`.
- Une session de joueur ne lit que : `chronicles/`, `world/premise.md`,
  `world/state.json`, `world/players.json`, et le dossier `souls/<slug>/` de
  **son** personnage. Les dossiers des autres âmes sont hors limites, même si
  rien ne t'en empêche techniquement.
- Quand tu incarnes le personnage, **il ignore l'existence des règles** : pas
  de statistiques, pas de jets, pas de « murmures » dans sa bouche ni dans sa
  tête. Un conseil suivi arrive comme une intuition.
- `memory.md` **s'appende**, ne se réécrit jamais.
- `souls/<slug>/intent.md` se pousse **en direct sur `main`, sans PR**. Tout
  le reste passe par PR.
- L'absence n'est jamais pénalisée. Un `intent.md` vide est un choix
  légitime, résolu par le MJ.

## Les commandes

- `/rejoindre` — créer ou reprendre un personnage (onboarding complet).
- `/briefing` — la session quotidienne : récit, état, conversation avec le
  personnage.
- `/murmurer` — écrire l'intention du jour dans `intent.md` et la pousser.

## La carte du dépôt

```
CLAUDE.md            ce fichier — point d'entrée de toute session
MJ.md                qui est le MJ et comment il arbitre
ROUTINE-MJ.md        procédure exacte du tick quotidien du MJ
ROUTINE-JOUEUR.md    gabarit de la routine de rappel personnelle
world/               prémisse, état, joueurs — et sealed.md, qu'on ne lit pas
souls/<slug>/        character.md, memory.md, intent.md, inbox.md
chronicles/          un chapitre par tick
```
