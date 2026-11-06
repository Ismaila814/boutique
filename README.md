# boutique

La boutique en ligne de la série « Moussa devient DevOps ». C'est une application Django.

## Prérequis

- Ubuntu 24.04, ou WSL2 avec Ubuntu 24.04
- Python 3.12 et son module venv : `sudo apt install python3.12-venv`
- Git

## Lancer le projet en local

1. Récupère le code. Remplace `<compte>` par le compte GitHub qui héberge le dépôt.

   ```bash
   git clone git@github.com:<compte>/boutique.git
   cd boutique
   ```

2. Crée et active l'environnement virtuel.

   ```bash
   python3.12 -m venv .venv
   source .venv/bin/activate
   ```

3. Installe les dépendances.

   ```bash
   python -m pip install -r requirements.txt
   ```

4. Génère une clé secrète dans l'interpréteur Python.

   ```text
   python
   >>> import secrets
   >>> secrets.token_urlsafe(50)
   >>> quit()
   ```

5. Donne la clé à Django. Colle la clé affichée, avec ses apostrophes, après `SECRET_KEY=`.
   L'espace au début de la ligne évite de garder la clé dans l'historique de Bash.

   ```bash
    export SECRET_KEY='colle-ta-cle-ici'
   ```

6. Crée la base de données locale, puis démarre le serveur.

   ```bash
   python manage.py migrate
   python manage.py runserver
   ```

## Vérifier que ça marche

Dans un deuxième terminal :

```bash
curl http://127.0.0.1:8000/health/
```

Résultat attendu :

```text
{"status": "ok"}
```

## À savoir

- La clé secrète ne va jamais dans le code ni dans Git.
- La variable `SECRET_KEY` disparaît quand tu fermes le terminal. Dans un nouveau terminal, refais `source .venv/bin/activate`, puis les étapes 4 et 5.
- `runserver` sert seulement au développement, jamais en production.
