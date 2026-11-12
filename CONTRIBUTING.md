# Contribuer à boutique

## Le tableau de tâches

Chaque travail commence par une issue, sur GitHub et sur GitLab.
L'issue avance sur le tableau, de « à faire » à « terminé ».

## Les branches

Une branche par issue. Son nom commence par le numéro de l'issue :

    <numéro>-<description-courte>

Exemple : `1-ecrire-la-convention`.

## Les messages de commit

Le format suit Conventional Commits 1.0.0 :

    <type>: <description>

    <corps : pourquoi ce changement>

    Closes #<numéro>

Types utilisés :

- `feat` : une nouvelle fonctionnalité ;
- `fix` : la correction d'un bug ;
- `docs` : la documentation seulement.

La première ligne fait 50 caractères au plus.
La ligne `Closes #<numéro>` ferme l'issue quand le commit arrive sur `main`.

Référence : https://www.conventionalcommits.org/en/v1.0.0/
