# spark-exercice

Projet d'analyse de commandes, de livraisons et de trajets GPS avec Apache Spark et PySpark. L'environnement local est fourni par Docker Compose; le notebook principal est `notebooks/exercice_livraisons.ipynb`.

## Prérequis

- Docker Desktop avec Docker Compose
- Environ 4 Go de mémoire disponibles pour Spark

## Démarrer

Depuis la racine du projet :

```powershell
docker compose up --build
```

Ouvrir JupyterLab sur http://localhost:8888, puis `notebooks/exercice_livraisons.ipynb`. Les interfaces Spark sont disponibles sur http://localhost:8080 et http://localhost:18080.

Pour arrêter les conteneurs, utiliser `Ctrl+C`, puis `docker compose down` si nécessaire. Les données MongoDB résident dans un volume Docker nommé et persistent après l'arrêt.

## Données

Les fichiers d'entrée attendus dans `data/` sont le catalogue produits, le journal des commandes, les communes et les traces GPS mensuelles des véhicules. Le dossier `data/` est volontairement exclu de Git; place les fichiers localement avant de démarrer. Les dossiers `events/` et `resultats/` contiennent des artefacts générés et ne sont pas suivis.

## Sécurité

La configuration de développement démarre Jupyter sans jeton ni mot de passe. Elle est destinée à un usage local de confiance uniquement : ne pas exposer les ports du compose à un réseau public ou non fiable.

Avant toute redistribution des données, vérifier que leur publication est autorisée, en particulier pour les journaux de commandes et les coordonnées GPS.

## Licence

Aucune licence n'est définie pour le moment. La visibilité publique du dépôt n'accorde pas automatiquement de droits de réutilisation.