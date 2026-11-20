# Contribuer

Règles communes aux dépôts Extern-SN. Un dépôt qui a son propre `CONTRIBUTING.md` suit le sien.

## Issues

Partir d'un formulaire : Tâche, Bug ou Constat d'audit. Une tâche porte une taille XS à XXL, à comparer au temps réel en la fermant.

Une issue créée en ligne de commande ne passe pas par le formulaire. Ajouter alors une section `## Taille` à son corps.

## Branches

Partir de la branche d'intégration à jour et nommer la branche par son intention, avec si possible le numéro de l'issue :

| Préfixe | Usage |
|---|---|
| `feature/` | nouvelle capacité |
| `fix/` | correction sans urgence |
| `hotfix/` | correction d'un incident en cours |

Exemple : `feature/gh-12-export-mensuel`.

La maintenance et la documentation passent aussi par ces préfixes. Leur nature est portée par le label de la PR, pas par le nom de la branche.

## Commits

Les messages suivent *Conventional Commits*, en français :

```
<type>(<portée>): <description à l'impératif, sans majuscule ni point final>
```

Types : `feat`, `fix`, `hotfix`, `refactor`, `chore`, `docs`, `ci`, `test`. La portée est le composant touché et reste facultative.

```
feat(paiement): mesure les refus de paiement
fix(ci): aligne la date du cache APT sur le Dockerfile
```

Le corps explique pourquoi, pas ce que le diff montre déjà.

## Pull requests

- Le titre reprend la forme du commit principal.
- Le corps suit le modèle : `Closes #N`, changements, tests, mise en production.
- Exactement un label de version : `feature` (mineure), `fix`, `hotfix` ou `chore` (correctif), `breaking` (majeure). Dans les dépôts qui appellent `validate-pr`, la CI refuse la PR sinon.
- Pas de fusion de sa propre PR sans relecture, pas de poussée en force sur la branche principale.

## Ce qui n'entre pas dans un dépôt

Mot de passe, jeton, clé, certificat privé, fichier `.env` rempli, dump de base, donnée personnelle réelle. Un secret se documente par un fichier d'exemple aux valeurs vides.

Un secret poussé par erreur est considéré comme compromis : le signaler (voir `SECURITY.md`) et le faire changer, le retirer de l'historique ne suffit pas.
