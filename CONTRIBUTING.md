# Contribuer à un projet TLF Studio

Merci de votre intérêt. Ce guide vaut pour tous les repos de l'organisation `tlf-studio` qui n'ont pas le leur.

## Processus

1. **Ouvrez une issue avant toute PR non triviale** (nouvelle fonctionnalité, changement de comportement, refonte). Décrivez le besoin et la solution envisagée, puis attendez un retour avant de coder. Une faute de frappe ou un correctif d'une ligne peut aller directement en PR.
2. Créez une branche depuis `main` : `feat/…`, `fix/…`, `docs/…` ou `chore/…`.
3. Ouvrez une PR liée à l'issue (`Closes #12` dans la description) en suivant le modèle de PR.
4. Mettez à jour `CHANGELOG.md` (section `Unreleased`) si la PR change quelque chose de visible.

## Conventions de commit

Conventional Commits, description en français, à l'impératif, sans majuscule ni point final :

```
<type>(<scope>): <description>

[corps facultatif : le pourquoi]

Signed-off-by: Votre Nom <vous@exemple.fr>
```

- Types : `feat`, `fix`, `docs`, `chore`, `ci`, `style`, `refactor`.
- Le scope est facultatif et désigne la partie du projet touchée.
- Un commit par unité logique : une correction, une fonctionnalité, un renommage. Pas de commit « divers ».

Exemple : `fix(config): ignore les valeurs négatives du rayon`.

## Signature DCO obligatoire

Chaque commit doit être signé selon le [Developer Certificate of Origin 1.1](DCO). Il n'y a pas d'accord de contribution (CLA) à signer : la ligne `Signed-off-by` suffit.

```bash
git commit -s -m "fix(config): ignore les valeurs négatives du rayon"
```

`-s` ajoute la ligne `Signed-off-by: Nom <email>` à partir de votre configuration git (`user.name`, `user.email`). La vérification automatique exige que le nom de la signature soit identique au nom de l'auteur du commit.

Le nom peut être un pseudonyme connu, à condition qu'il vous identifie de façon stable : c'est la règle du noyau Linux depuis 2023. Un nom jetable ou différent à chaque PR ne convient pas.

### Signer des commits oubliés

```bash
git rebase --signoff <base>      # ex. git rebase --signoff origin/main
git push --force-with-lease
```

Pour le dernier commit seulement : `git commit --amend --signoff --no-edit`.

## Licence des contributions

- Votre code est publié sous la licence du repo (fichier `LICENSE`) : MIT pour les mods et les outils, propriétaire pour les jeux.
- N'incluez aucun asset (texture, modèle, son, musique, police, image) dont vous ne détenez pas les droits. Les assets d'un mod relèvent de son `ASSETS-LICENSE` : en proposer un, c'est accepter qu'il soit diffusé à ces conditions.
- Signalez dans la PR tout contenu repris d'ailleurs, avec sa source et sa licence.

## Rémunération

Aucune contribution n'est rémunérée. Les contributeurs sont crédités dans le README ou les notes de version du projet.

## Sécurité

Ne signalez pas une faille dans une issue publique : voir [SECURITY.md](SECURITY.md).
