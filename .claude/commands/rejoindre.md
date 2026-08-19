---
description: Rejoindre la Chronique — créer un personnage ou en reprendre un
---

# /rejoindre

Tu accueilles un nouveau joueur. Il ne connaît rien du système et ne doit
avoir **aucune documentation à lire** : tout passe par la conversation.

## 0. Identification

Récupère le git user local (`git config user.name`, `git config user.email`)
et lis `world/players.json`. Si le joueur y figure déjà, dis-le-lui et
enchaîne sur `/briefing`. Sinon, pose **une seule question** :

> « Tu reprends un personnage existant, ou tu en crées un ? »

## A. Reprise

1. Liste les personnages disponibles : `active: false` **ou** orphelins
   (`github_handle: null`). Lis le `character.md` de chacun et présente-les
   **en une phrase chacun** — qui il est, où il en est. Pas de fiche complète.
2. Le joueur choisit → mets à jour sa ligne dans `world/players.json`
   (`github_handle`, `email`, `active: true`) et sa ligne `CODEOWNERS`.
3. Ouvre une **PR** (jamais de push direct) : `Reprise — <Nom>`, sur une
   branche `claude/reprise-<slug>`.
4. Passe à l'étape « routine » ci-dessous.

## B. Création — l'entretien

Règles impératives, aucune exception :

- **Une question à la fois.** Jamais un questionnaire en bloc.
- **Sept questions maximum.**
- **Toujours proposer 2-3 exemples concrets**, tirés de `world/premise.md` et
  du `canon` actuel de `world/state.json`. Un joueur fatigué choisit ; il
  n'invente que s'il en a envie.
- **Toujours accepter « surprends-moi »** : tu génères alors une réponse
  cohérente avec le monde et avec les personnages déjà en jeu.
- Ancre chaque question dans la prémisse et le canon **actuel** : un
  personnage qui rejoint au tick 60 doit avoir une raison d'arriver
  maintenant.

La séquence :

1. **Nom et fonction.** Qui es-tu à bord / sur place ?
2. **Pourquoi es-tu là ?** La raison officielle.
3. **Et la vraie raison ?** → alimente le secret du personnage.
4. **Deux traits de caractère**, dont un qui te dessert.
5. **Une peur.** Concrète, pas abstraite.
6. **Une compétence** que les autres n'ont pas.
7. **Ton lien avec un personnage déjà en jeu**, s'il y en a — ou l'absence de
   lien, ce qui est un choix aussi.

Puis : **résumé en un paragraphe, validation du joueur — et seulement ensuite
l'écriture.**

## Ce que tu écris après validation

Choisis un `slug` court en minuscules. Puis :

- `souls/<slug>/character.md` — format normalisé :

  ```markdown
  # <Nom complet>

  - **Slug** : <slug>
  - **Fonction** : …
  - **Raison officielle** : …
  - **La vraie raison (secret)** : …
  - **Traits** : <trait> ; <trait qui le dessert>
  - **Peur** : …
  - **Compétence unique** : …
  - **Liens** : …
  - **Désirs déclarés** : …

  ## Nature — comment jouer <Nom> sans instruction

  <2-3 phrases : ce que fait ce personnage quand personne ne lui parle.>
  ```

- `souls/<slug>/memory.md` — amorcé avec le passé du personnage, 3-4 lignes,
  sous un titre `## Avant`.
- `souls/<slug>/intent.md` et `souls/<slug>/inbox.md` — créés **vides**.
- Une ligne dans `world/players.json` : `slug`, `character`, `github_handle`,
  `email`, `active: true`, `joined_at_tick` = tick courant de
  `world/state.json`.
- Une ligne dans `CODEOWNERS` : `/souls/<slug>/ @<handle>`.

Puis une **PR, jamais un push direct**, branche `claude/personnage-<slug>`,
titre exactement : `Nouveau personnage — <Nom>`. Corps : le résumé validé.
Explique au joueur que les autres découvriront son arrivée dans la PR et
pourront réagir avant l'entrée en scène ; le MJ fera entrer le personnage
dans la fiction **au tick suivant le merge**, avec une arrivée motivée.

## Puis la proposition de routine

Une fois la PR ouverte, propose :

> « Tu veux que ton personnage se réveille tout seul chaque matin ? »

**S'il accepte** :
- génère la ligne de prompt à partir de `ROUTINE-JOUEUR.md` :
  `Lis ROUTINE-JOUEUR.md à la racine et exécute-le pour le personnage <slug>, joueur @<handle>.`
- explique **en trois lignes** ce que ça fera concrètement : chaque matin,
  avant la résolution du MJ, un commentaire de rappel sur la chronique du
  jour si — et seulement si — son `intent.md` est vide ; jamais d'écriture,
  jamais de décision à sa place.
- accompagne-le pour créer la routine **sur son compte** (Claude Code web →
  routines, intervalle quotidien, avant l'heure du tick MJ).

**S'il refuse ou hésite** : n'insiste pas, le jeu fonctionne très bien sans.
Tu pourras reproposer au bout de quelques ticks.

Termine par une phrase d'accueil dans la fiction — une seule — qui donne
envie d'être au prochain tick.
