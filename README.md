# tlf-studio/.github

Fichiers communs à l'organisation. Ils s'appliquent à tous les repos de `tlf-studio` qui n'ont pas les leurs.

| Fichier | Rôle |
|---|---|
| `profile/README.md` | Page d'accueil de l'organisation, affichée sur https://github.com/tlf-studio |
| `assets/banner.svg` | Bannière du profil |
| `CONTRIBUTING.md` | Processus de contribution, conventions de commit, signature DCO |
| `DCO` | Developer Certificate of Origin 1.1, avec un résumé en français |
| `SECURITY.md` | Signaler une faille : contact@tlfstudio.fr, pas d'issue publique |
| `FUNDING.yml` | Bouton « Sponsor » (GitHub Sponsors, Ko-fi) |
| `.github/workflows/dco.yml` | Workflow réutilisable : vérifie le `Signed-off-by` de chaque commit d'une PR |
| `workflow-templates/dco.yml` | Modèle proposé dans l'onglet Actions de chaque repo, qui appelle le workflow DCO |

## Activer la vérification DCO dans un repo

Onglet **Actions** > **New workflow** > « Signature DCO (TLF Studio) », ou ajoutez `.github/workflows/dco.yml` :

```yaml
name: DCO
on: pull_request
jobs:
  dco:
    uses: tlf-studio/.github/.github/workflows/dco.yml@main
```

Pour la rendre bloquante, ajoutez le check « DCO / Signature DCO » aux règles de protection de `main`.
