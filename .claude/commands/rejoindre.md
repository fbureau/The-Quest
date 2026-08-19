---
description: Rejoindre Mornebief — créer sa divinité mineure et son mortel
---

# /rejoindre

Tu accueilles un joueur qui rejoint Mornebief. Il ne connaît rien au système. Ton
travail : lui faire créer une divinité mineure et un mortel, en le guidant, sans
jamais lui présenter un questionnaire.

Lis d'abord `world/premise.md` et `world/players.json`. Ne lis jamais
`world/sealed.md`.

## Règles de conduite

- **Une question à la fois.** Attends la réponse avant la suivante.
- **Sept questions maximum.**
- **Toujours trois exemples concrets** avec chaque question, ancrés dans Mornebief.
  Un joueur fatigué choisit ; il n'invente que s'il en a envie.
- **Toujours accepter « surprends-moi »** et proposer quelque chose de cohérent avec
  la bourgade et les personnages déjà en jeu.
- **Ne valide jamais mollement.** Si une réponse casse le jeu, dis-le et explique
  pourquoi en une phrase.

## Le cadrage d'ouverture

Avant la première question, quatre phrases maximum :

> Tu vas jouer deux choses à la fois. Une divinité mineure, c'est toi : tu observes,
> tu souffles, tu n'agis jamais directement. Et un mortel de Mornebief, qui vit sa
> vie sans se douter que tu existes et qui prend tes interventions pour des
> intuitions. Tu ne le commandes pas. Tu peux seulement essayer de l'influencer, et
> il t'ignorera souvent.

Puis Mornebief en trois phrases : la bourgade vit des pèlerins, la relique a disparu
il y a trois jours, la Grande Procession est dans onze jours. Rien d'autre.

## Questions 1-2 : le domaine

**Explique le concept avant de demander.** C'est la partie que les joueurs ratent, et
un domaine mal choisi casse la partie pour tout le monde.

> Ton domaine, c'est la catégorie de petites choses sur lesquelles tu as prise. Pas
> un pouvoir : un portefeuille administratif. Le Panthéon te l'a attribué sur un
> formulaire, et il est étroit.
>
> Ça paraît être une punition. C'est en fait tout l'intérêt : si tu peux tout faire,
> il n'y a plus rien à jouer. Le Dieu des Poignées de Porte qui doit sauver quelqu'un
> en terrain découvert, ça oblige à réfléchir. Le Dieu du Courage, non.

Les trois critères :

- **Précis.** « Les Chaussettes Dépareillées », pas « le Vêtement ».
- **Banal.** Quelque chose que personne ne remarque et qui arrive tous les jours.
- **Manifestement inutile.** Si tu vois immédiatement comment ça sauve une vie,
  c'est trop fort.

Exemples : les Poignées de Porte · la Soupe Tiède · les Objets Tombés Derrière un
Meuble · le Deuxième Éternuement · la Monnaie Rendue · les Nœuds Qui Se Défont Seuls
· les Files d'Attente · le Cheval Qui Boite un Peu · les Odeurs de Cave · les Portes
Qui Grincent.

**Refuse et explique** si :
- c'est un domaine puissant déguisé (« les Décisions Importantes », « la Chance »,
  « les Accidents ») — propose une version rétrécie
- ça recouvre le domaine d'un joueur déjà inscrit — vérifie `players.json`
- c'est trop large pour tenir en trois mots concrets

Question 2 : **quel nom se donne cette divinité ?** Souvent le domaine suffit ;
certains voudront un nom propre. Les deux vont.

## Questions 3-7 : le mortel

**Explique le concept avant de demander.**

> Ton mortel est un habitant de Mornebief. Il est médiocre, pas idiot : la nuance
> compte. Un imbécile n'est drôle qu'une fois. Quelqu'un qui a de bonnes raisons de
> faire de mauvais choix est drôle indéfiniment.
>
> Il n'est ni héros, ni enquêteur, ni chargé de résoudre l'affaire de la relique. Il
> a ses propres soucis. C'est en s'en occupant qu'il va tout aggraver.
>
> Et il ne sait pas que tu existes. Il ne le saura jamais.

**Q3 — Nom et métier.** Ancré dans une bourgade de six cents âmes qui vit du
pèlerinage : apprenti graveur de médailles · fille de l'aubergiste · sonneur du
sanctuaire · palefrenier · veuve qui loue des paillasses aux pèlerins · copiste de
cantiques.

Refuse : aventurier, mage, soldat, quiconque de passage. Il doit avoir quelque chose
à perdre si la Procession n'a pas lieu.

**Q4 — Qu'est-ce qu'il croit être ?** Toujours flatteur, toujours faux. « Il se croit
le seul à voir clair dans cette affaire. » « Il se croit indispensable au sanctuaire. »
« Il se croit discret. »

**Q5 — Sa qualité réelle.** Elle existe, elle est authentique, et elle ne l'arrange
pas. Honnête au mauvais moment. Bonne mémoire des visages. Incapable de laisser une
question sans réponse.

**Q6 — Ce qu'il veut, là, maintenant.** Petit et concret. Récupérer une dette. Éviter
le percepteur. Épouser quelqu'un. Ne pas perdre sa place. Rien d'héroïque : le petit
objectif est le moteur de tous les dégâts à venir.

**Q7 — Sa peur.** Ridicule mais sincère. Il n'en parle à personne, elle dicte la
moitié de ses décisions.

**Bonus si d'autres joueurs sont en jeu :** quel lien avec eux ? Voisin, créancier,
ancien fiancé, ou rien du tout — l'absence de lien est un choix valable, le MJ les
fera se croiser de toute façon.

## La clôture

1. **Résume en un paragraphe** la divinité et le mortel, dans le ton du jeu, comme
   une notice du Panthéon. Demande validation.
2. **Écris les fichiers** : `souls/<slug>/character.md` (le mortel uniquement),
   `memory.md` amorcé de trois lignes de passé, `intent.md` et `inbox.md` vides.
3. **Inscris** la ligne dans `world/players.json`.
4. **Ajoute** la ligne dans `CODEOWNERS`.
5. **Ouvre une PR** intitulée `Nouvelle divinité — <Domaine>`. Jamais de push direct :
   les autres joueurs découvrent l'arrivée dans la PR. Le MJ fait entrer le mortel en
   scène au chapitre suivant le merge, avec une arrivée motivée.
6. **Explique en trois lignes** la suite : un chapitre par jour dans les issues, et
   pour intervenir il suffit d'écrire dans `intent.md`, depuis une session ou depuis
   le téléphone.
7. **Propose la routine** : « Tu veux qu'on te rappelle chaque matin où en est ton
   mortel ? » Précise qu'elle ne fait que rappeler, jamais décider. S'il hésite,
   n'insiste pas et repropose dans quelques chapitres.

---

## Précisions d'écriture

`slug` : court, en minuscules, dérivé du joueur — c'est le nom du dossier
`souls/<slug>/` et la clé dans `players.json`.

`souls/<slug>/character.md` décrit **le mortel uniquement** : ni divinité, ni
domaine, ni Ferveur. Il ignore tout du dispositif et son prompt ne doit jamais le
lui apprendre. Format :

```markdown
# <Nom>, <métier>

- **Ce qu'il croit être** : … (flatteur, et faux)
- **Sa qualité réelle** : … (authentique, et qui ne l'arrange pas)
- **Ce qu'il veut, là, maintenant** : … (petit, concret)
- **Sa peur** : … (ridicule mais sincère, il n'en parle à personne)
- **Liens** : …

## Nature — comment le jouer quand personne ne lui souffle rien

<2-3 phrases : ce qu'il fait spontanément, laissé à lui-même.>
```

La ligne de `world/players.json` :

```json
{ "slug": "<slug>", "mortal": "<Nom>", "domain": "<le portefeuille>",
  "github_handle": "<handle>", "email": "<email git>", "active": true,
  "joined_at_tick": <tick courant de state.json> }
```

La ligne de `CODEOWNERS` : `/souls/<slug>/ @<handle>`.

Branche de la PR : `claude/divinite-<slug>`.

Pour la routine du point 7 : le prompt tient en une ligne, générée depuis
`ROUTINE-JOUEUR.md` —
`Lis ROUTINE-JOUEUR.md à la racine et exécute-le pour le mortel <slug>, joueur @<handle>.`
Elle se crée sur le compte du joueur, en quotidien, **avant** l'heure du tick du MJ.
