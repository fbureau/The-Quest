# Chronique — Les Dieux de Seconde Zone

Un jeu narratif par GitHub, à plusieurs, à distance, cinq minutes par jour.

Vous êtes une **divinité mineure**. Pas une grande : le Panthéon vous a attribué, sur
formulaire, un portefeuille étroit et manifestement inutile — les Poignées de Porte,
la Soupe Tiède, les Objets Tombés Derrière un Meuble. Vous suivez **un mortel** de
Mornebief, qui ignore votre existence et la gardera ignorée jusqu'au bout.

Vous ne le commandez pas. Vous soufflez, et il entend ou n'entend pas. Quand il
entend, ça lui arrive comme une intuition.

Mornebief vit des pèlerins venus voir le Doigt de Sainte Ombeline. Il y a trois
jours, le reliquaire a été retrouvé vide. La Grande Procession est dans dix jours.
Personne n'a encore prononcé le mot « vol » à voix haute.

Chaque jour, un Maître du Jeu automatisé résout ce que chacun a tenté et publie un
chapitre en issue GitHub : deux minutes de lecture. Si vous ne dites rien, votre
mortel vit sa vie — **l'absence n'est jamais pénalisée**, c'est un congé sabbatique.

## À quoi ça ressemble

Un chapitre, tous les personnages entrelacés, narrateur omniscient — le lecteur voit
ce que les mortels ignorent :

> Barnabé n'avait pas prévu d'entrer dans la cave. Il s'y trouvait pourtant, une
> chandelle à la main, parce que la porte s'était ouverte toute seule et qu'il avait
> jugé impoli de ne pas y répondre.
>
> Dans les hauteurs, le Dieu des Poignées de Porte considérait son travail avec une
> satisfaction mesurée. C'était la première fois en onze jours qu'une intervention
> aboutissait. Il ignorait encore que la cave contenait le percepteur.

Puis, en pied de chapitre et seulement là, ce que la mécanique a donné :

```
── Barnabé (Dieu des Poignées de Porte) · cave · peur 6 · Ferveur 4
   ⚡ "n'entre pas" → NON ENTENDU (score 5, jet 13)
   ✨ "la porte cède" → ENTENDU — Ferveur +1
── Mornebief · J-8 avant la Procession · quotas 4/6
```

La **Ferveur**, c'est la foi de votre mortel en vous : elle monte quand un conseil
suivi tourne bien, elle tombe quand il tourne mal. À zéro, il n'entend plus rien —
vous voyez tout et vous ne pouvez plus rien.

## Comment jouer

**Première fois :**

```
git clone https://github.com/fbureau/The-Quest
cd The-Quest
claude
```

La session vous reconnaît, ou vous fait créer votre divinité et votre mortel par un
entretien guidé. Rien à lire avant.

**Ensuite, une journée type :**

1. Le matin, le chapitre du jour paraît dans les [issues](../../issues).
2. Quand vous voulez, ouvrez `claude` dans le dépôt : votre mortel vous raconte sa
   journée et vous discutez avec lui. Il a son propre avis et ne s'en prive pas.
3. Vous déposez jusqu'à **trois interventions** dans
   `souls/<votre-slug>/intent.md` — ce que vous tentez de lui souffler.
4. Le lendemain, le MJ résout tout le monde en même temps et publie la suite.

**Pas le temps ?** Éditez `souls/<votre-slug>/intent.md` depuis l'app GitHub sur
votre téléphone. Deux lignes suffisent, c'est prévu pour.

## Les deux commandes

| Commande | Ce qu'elle fait |
|---|---|
| `/rejoindre` | Créer votre divinité et votre mortel |
| `/briefing` | Le point du jour, la discussion, le dépôt des interventions |

## Les règles qui comptent

- **Le domaine est strict.** Hors portefeuille, l'intervention est rejetée par le
  Panthéon avec un motif administratif. C'est la contrainte qui fait le jeu.
- **Trois interventions par jour.** Quota.
- **La Ferveur à zéro rend muet.** Un mortel qui ne croit plus n'entend plus rien.
- **La Procession a lieu au chapitre 11**, qu'on soit prêt ou non.
- On ne lit pas les dossiers `souls/` des autres, ni `world/sealed.md` — la réponse
  du mystère, scellée jusqu'au dernier chapitre.

## Pourquoi personne ne peut tricher

Trois couches, chacune dans son propre contexte : votre mortel raisonne sur **votre**
machine, vous lui parlez depuis la vôtre, et l'arbitrage tourne ailleurs, chez le MJ.
Aucune fuite d'information n'est possible entre personnages — ce n'est pas une règle
de politesse, c'est la structure. Et comme votre session n'écrit jamais une action,
seulement une intervention, c'est toujours l'arbitre qui tranche.

## Ce qu'il y a dans le dépôt

```
CLAUDE.md            point d'entrée — c'est lui qui guide les sessions
MJ.md                les règles d'arbitrage du Maître du Jeu
STYLE.md             comment s'écrit un chapitre (le MJ le lit chaque jour)
ROUTINE-MJ.md        la procédure du tick quotidien (routine cloud)
ROUTINE-JOUEUR.md    gabarit du rappel quotidien optionnel
world/               prémisse, état, joueurs, mystère scellé
souls/<slug>/        votre mortel : fiche, mémoire, interventions, courrier
chronicles/          un chapitre par jour
```

---

## Administration (à lire seulement si vous installez le jeu)

Ordre de mise en route, à ne pas brûler :

1. **Le monde est écrit** : `world/premise.md` (Mornebief, les quatre figures, les
   trois lois dures, l'horloge, le Panthéon) et `world/sealed.md`, déposé sans être
   lu et qui ne se rouvre qu'au dernier chapitre.
2. **Tester `/rejoindre`** en créant une divinité jetable. Si l'onboarding n'est pas
   fluide, personne ne jouera.
3. **Faire tourner le tick à la main** sur 3 chapitres : en session interactive,
   « Lis ROUTINE-MJ.md et exécute-le ». Vérifier que le canon tient, que le chapitre
   reste sous 500 mots, et que le MJ ne commente pas ses propres blagues.
4. **Automatiser le MJ** : une routine quotidienne Claude Code, sur un compte dédié
   de préférence, dont le prompt tient en une ligne :
   `Lis ROUTINE-MJ.md à la racine et exécute-le intégralement.`
   Piège classique : par défaut une routine ne pousse que sur des branches
   `claude/*`. Activer **« Allow unrestricted branch pushes »**, sinon l'état ne
   s'accumule jamais sur `main`.
5. Laisser tourner 1 à 4 une semaine en réel avant d'ajouter le reste : routines de
   rappel des joueurs, boîte aux lettres, entretien de mi-parcours.

**Branches et permissions.** Les `intent.md` des joueurs et les commits du MJ vont
directement sur `main`, sans PR — c'est voulu. Tout le reste (nouvelles divinités,
règles, `world/`) passe par PR, avec `CODEOWNERS` comme garde-fou. Si vous activez
une protection de branche exigeant des PR, prévoyez un bypass pour le compte du MJ ;
au démarrage, le plus simple est de ne rien activer.

**Les prompts sont dans le dépôt** (`ROUTINE-MJ.md`, `ROUTINE-JOUEUR.md`), pas dans
l'interface web : ils évoluent par PR, comme le reste.
