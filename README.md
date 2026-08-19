# Chronique

Un jeu de rôle par GitHub, à plusieurs, à distance, cinq minutes par jour.

Chaque joueur a un personnage dans un monde partagé. Vous ne contrôlez pas
votre personnage : vous êtes sa **voix intérieure**. Vous lui parlez, vous lui
conseillez des choses — et il peut vous écouter ou non, selon son caractère.

Une fois par jour, un Maître du Jeu automatisé résout ce que chacun a tenté,
fait avancer le monde, et publie un court chapitre (une issue GitHub, deux
minutes de lecture). Personne n'est obligé d'être là : si vous ne dites rien,
votre personnage vit sa vie, et vous n'êtes jamais pénalisé.

## Comment jouer

**Première fois :**

```
git clone https://github.com/fbureau/The-Quest
cd The-Quest
claude
```

Rien d'autre à savoir : la session vous reconnaît (ou pas) et vous guide —
création de personnage par un court entretien, ou reprise d'un personnage
libre.

**Ensuite, une journée type :**

1. Le matin, le chapitre du jour est publié dans les
   [issues](../../issues). Vous le lisez, ou pas.
2. Quand vous voulez, ouvrez `claude` dans le dépôt : votre personnage vous
   raconte sa journée, et vous discutez avec lui. Vous pouvez le mettre en
   garde, l'encourager, le contredire — il a son propre avis.
3. Ce qui ressort de la conversation est déposé dans
   `souls/<votre-personnage>/intent.md` : c'est votre « murmure » du jour.
4. Le lendemain matin, le MJ résout tout le monde en même temps et publie la
   suite.

**Pas le temps d'ouvrir une session ?** Éditez directement
`souls/<votre-personnage>/intent.md` depuis l'app GitHub sur votre téléphone.
Deux lignes suffisent, c'est prévu pour.

**Pas là pendant deux semaines ?** Aucun problème. Votre personnage aura
continué à vivre selon son caractère, et vous reprendrez l'histoire en cours.

## Les commandes (la session les propose d'elle-même)

| Commande | Ce qu'elle fait |
|---|---|
| `/rejoindre` | Créer un personnage, ou en reprendre un libre |
| `/briefing` | Le point du jour + discussion avec votre personnage |
| `/murmurer` | Écrire votre conseil du jour et l'envoyer |

## Les règles en quatre lignes

- Vous **conseillez**, vous ne commandez pas. Votre personnage décide.
- Seul le MJ écrit l'histoire, l'état du monde et les mémoires.
- On ne lit pas les dossiers `souls/` des autres, ni `world/sealed.md`
  (la solution du mystère, scellée jusqu'au dernier chapitre).
- L'absence n'est jamais punie.

## Ce qu'il y a dans le dépôt

```
CLAUDE.md            point d'entrée — c'est lui qui guide les sessions
MJ.md                les règles d'arbitrage du Maître du Jeu
ROUTINE-MJ.md        la procédure du tick quotidien (routine cloud)
ROUTINE-JOUEUR.md    gabarit du rappel quotidien optionnel
world/               prémisse, état du monde, joueurs, mystère scellé
souls/<slug>/        votre personnage : fiche, mémoire, intention, courrier
chronicles/          un chapitre par jour
```

---

## Administration (à lire seulement si vous installez le jeu)

Ordre de mise en route, à ne pas brûler :

1. **Écrire le monde à plusieurs** — 30 minutes maximum : `world/premise.md`
   (la situation, trois lois, le ton) et `world/sealed.md` (la solution du
   mystère — plus personne ne l'ouvre ensuite). Une version d'amorce est
   déjà en place.
2. **Tester `/rejoindre`** en créant un vrai personnage. Si l'onboarding
   n'est pas fluide, personne ne jouera.
3. **Faire tourner le tick à la main** pendant 3 jours : en session
   interactive, taper « Lis ROUTINE-MJ.md et exécute-le ». Vérifier que le
   récit tient la longueur (500 mots max) et reste cohérent.
4. **Automatiser le MJ** : créer une routine quotidienne Claude Code (sur un
   compte dédié de préférence) dont le prompt tient en une ligne :
   `Lis ROUTINE-MJ.md à la racine et exécute-le intégralement.`
   Piège classique : par défaut une routine ne pousse que sur des branches
   `claude/*`. Activer **« Allow unrestricted branch pushes »**, sinon rien
   ne s'enregistre jamais sur `main`.
5. Laisser tourner 1 à 4 une semaine en réel avant d'ajouter le reste
   (routines de rappel des joueurs, courrier entre personnages,
   récapitulatif hebdomadaire).

**Branches et permissions.** Les `intent.md` des joueurs et les commits du
MJ vont directement sur `main`, sans PR — c'est voulu. Tout le reste
(nouveaux personnages, changements de règles, `world/`) passe par PR, avec
`CODEOWNERS` comme garde-fou. Si vous activez une protection de branche
exigeant des PR, prévoyez un bypass pour le compte du MJ ; au démarrage, le
plus simple est de ne rien activer du tout.

**Les prompts sont dans le dépôt** (`ROUTINE-MJ.md`, `ROUTINE-JOUEUR.md`),
pas dans l'interface web : on les fait évoluer par PR, comme le reste.
