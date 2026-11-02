# Organisation de l'équipe

Cette organisation suit l'ordre de réalisation du guide de démarrage. Chaque membre porte un périmètre, mais tout le monde reste capable de lire et de relire le code des autres.

## Rôles

| Membre | Responsabilité principale | Binôme de relecture |
| --- | --- | --- |
| Abdallah Alex | UI, Users, sécurité | Falcao Felipe |
| Falcao Felipe | Posts, photos | Caramella Enzo |
| Caramella Enzo | Feed, conteneurs, infrastructure | 

## Étapes

| Étape | Travail | Responsable | Appui | Résultat à vérifier |
| --- | --- | --- | --- | --- |
| Première séance | Conteneurs UI et Users, inscription et connexion | Membre 1 | Membre 3 (Docker Compose) | Je m'inscris, puis je me connecte |
| A - Comptes | UI + Users, inscription, connexion, jeton JWT | Membre 1 | Membre 3 | J'accède à une page authentifiée |
| B - Publications | Posts, création et liste des publications textuelles | Membre 2 | Membre 1 (pages UI) | Je retrouve mon texte sur mon profil |
| C - Abonnements | Feed, suivre et ne plus suivre | Membre 3 | Membre 1 (pages UI) | Je peux suivre un autre utilisateur |
| D - Fil | Feed récupère les publications auprès de Posts | Membre 3 | Membre 2 | Mon accueil affiche leurs publications dans l'ordre |
| E - Photos | Ajout des images | Membre 2 | Membre 1 (affichage) | Une publication affiche sa photo |

## Passage au cloud

À démarrer uniquement lorsque les étapes A à E fonctionnent en local.

| Palier | Travail | Responsable | Appui |
| --- | --- | --- | --- |
| Données | Adapter le stockage à DynamoDB, photos dans S3 | Membre 2 | Tous, chacun pour son service |
| Déploiement | ECS avec Terraform | Membre 3 | Membre 2 |
| Sécurisation | Secrets, droits d'accès, exposition des services | Membre 1 | Membre 3 |
| Événements (optionnel) | Diffusion avec SQS ou EventBridge | Membre 3 | Membre 2 |

## Méthode de travail

- **Branches :** `main` reste fonctionnelle. Chaque tâche part d'une branche courte, par exemple `feature/users-login`.
- **Pull requests :** toute modification passe par une pull request relue par une autre personne.
- **Issues :** une issue par tâche, avec un responsable et le résultat à vérifier.
- **Contrats d'API :** un changement de route met à jour [architecture.md](architecture.md) dans la même pull request et prévient les services concernés.
- **Point d'équipe :** un court point à chaque séance : ce qui est fini, ce qui bloque, ce qui suit.

## Définition de « terminé »

Une tâche est terminée lorsque :

1. Le résultat attendu est vérifié avec `docker compose up`.
2. La pull request est relue et fusionnée.
3. La documentation est à jour si l'API ou le lancement a changé.
4. Aucun secret n'a été ajouté au dépôt.
