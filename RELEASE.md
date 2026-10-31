# Livrer Embed Link Copier

Recette suivie par `/test-app`, `/preprod`, `/version` et `/prod`. Lire aussi `CLAUDE.md`.

## Flux

`/forge` → `/test-app` → commit → `/version` → `/prod` → **toi : Chrome Web Store**

## Test

Claude in Chrome, sur les sites visés, extension chargée non empaquetée. Firefox : `npx web-ext lint` dans Docker.

## Preprod

Aucune.

## Version

1. Relire `README.md`, `CHANGELOG.md`, `CONTRIBUTING.md`, `site/` et la fiche des stores : pas de listes de domaines ou de mots clés (Chrome a déjà rejeté une version pour ça). Vraies captures seulement.
2. Numéro dans les manifests et `CHANGELOG.md`. Conserver les CRLF. `bash scripts/prepare-*.sh` puis `bash scripts/package-*.sh` ; zip dans `packages/`.

## Prod

1. Vérifier que le zip porte le bon numéro et que tout est poussé, avec accord.
2. Firefox : envoi sur AMO après confirmation du fichier et de la version.
3. **Réservé à la personne : Chrome Web Store**, Claude n'y a pas accès. Lui donner le zip et les étapes.
