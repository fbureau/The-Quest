# Chronique — Les Dieux de Seconde Zone

Jeu narratif asynchrone. Chaque joueur est une **divinité mineure** au portefeuille
étroit, et suit **le mortel** qui lui a été assigné à Mornebief. La divinité ne
commande pas : elle souffle, et le mortel entend ou n'entend pas. Le Maître du Jeu
(MJ) arbitre, résout et publie un chapitre par jour.

## Qui parle ? — à exécuter au début de toute session

Si le prompt de la session demande d'exécuter `ROUTINE-MJ.md`, ou un rappel dérivé
de `ROUTINE-JOUEUR.md` : suis ce fichier-là intégralement et ignore le reste de
cette section.

Sinon la session est interactive. Oriente le joueur sans qu'il ait rien à lire :

1. Lis `world/players.json` et récupère l'utilisateur git local
   (`git config user.name`, `git config user.email`, handle GitHub si disponible).
2. **Joueur connu** — son handle ou son email figure dans `players.json` →
   enchaîne directement sur `/briefing` (`.claude/commands/briefing.md`), sans
   question préalable.
3. **Joueur inconnu** → suis `.claude/commands/rejoindre.md` : il crée une divinité
   et un mortel par un entretien guidé.

## Règles que toute session respecte, sans exception

- **Ne jamais lire `world/sealed.md`.** Personne : ni le MJ, ni un joueur, ni une
  routine. Il ne sera ouvert qu'au dernier chapitre.
- La divinité **souffle**, elle ne commande pas. La session du joueur n'écrit que des
  **interventions** dans `souls/<slug>/intent.md` — jamais des actions accomplies,
  jamais l'état du monde, jamais les mémoires ni les chapitres. Seul le MJ écrit
  `world/state.json`, `souls/*/memory.md`, `souls/*/inbox.md` et `chronicles/`.
- Une session de joueur ne lit que : `chronicles/`, `world/premise.md`,
  `world/state.json`, `world/players.json`, et le dossier `souls/<slug>/` de **son**
  mortel. Les autres dossiers `souls/` sont hors limites, même si rien ne t'en
  empêche techniquement.
- **Le domaine est strict.** Une intervention hors portefeuille sera rejetée par le
  Panthéon avec un motif administratif. Ce n'est pas une punition, c'est le jeu.
- **Trois interventions par tick maximum.** Les suivantes sont refusées.
- Quand tu incarnes le mortel, **il ignore tout du dispositif** : pas de divinité,
  pas de domaine, pas de Ferveur, pas de jets, pas de Panthéon dans sa bouche ni
  dans sa tête. Il dit « j'ai eu un pressentiment », jamais « mon dieu m'a soufflé ».
- `memory.md` **s'appende**, ne se réécrit jamais.
- `souls/<slug>/intent.md` se pousse **en direct sur `main`, sans PR**. Tout le
  reste passe par PR.
- L'absence n'est jamais pénalisée. Un `intent.md` vide est un choix légitime,
  résolu par le MJ. Un joueur qui décroche est une **divinité en congé sabbatique**,
  jamais un « absent ».

## Le ton

Sérieux imperturbable. Les faits sont absurdes, le narrateur ne l'est jamais. **On ne
commente jamais sa propre blague** : on pose le fait et on passe au suivant. La
référence est le fantastique comique classique à l'anglaise, Terry Pratchett en tête.
`STYLE.md` détaille le narrateur, les procédés et les exigences de cohérence ; il fait
loi sur toute prose publiée.

## Les commandes

- `/rejoindre` — créer sa divinité et son mortel (onboarding complet).
- `/briefing` — la session quotidienne : le chapitre, l'état, la conversation avec
  son mortel, et le dépôt de l'intervention du jour.

## La carte du dépôt

```
CLAUDE.md            ce fichier — point d'entrée de toute session
MJ.md                qui est le MJ et comment il arbitre
STYLE.md             comment s'écrit un chapitre — lu à chaque tick
ROUTINE-MJ.md        procédure exacte du tick quotidien du MJ
ROUTINE-JOUEUR.md    gabarit de la routine de rappel personnelle
world/               prémisse, état, joueurs — et sealed.md, qu'on ne lit pas
souls/<slug>/        character.md (le mortel), memory.md, intent.md, inbox.md
chronicles/          un chapitre par tick
```
