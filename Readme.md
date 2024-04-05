# Tutoriel

# Introduction

Dans le cadre de la sécurité dans un cycle de DevOps, on souhaite proposer des améliorations de la sécurité du projet Doodle.

## Prérequis

- Java 11
- Maven
- Docker
- Docker Compose

## Démarrage du docker

On doit tout d'abord compiler le projet Quarkus. Pour cela on doit utiliser la version 11 de Java en modifiant le `JAVA_HOME` par exemple. On lance la compilation via Maven du projet avec la commande suivante :

```sh
./mvnz packge -Dmaven.test.skip=true
```
On ignore les tests lors de la compilation, il faut lancer les dépendances via le docker compose de l'api. Un fichier `tlcdemoApp-1.0.0-SNAPSHOT-runner.jar` doit alors se situer dans le dossier `api/target`.

On se place ensuite à la racine du projet pour lancer les conteneurs.
```sh
docker compose -f docker-compose.yaml up
```

Docker va ensuite automatiquement construire les différents conteneurs nécessaires au projet puis les lancer.

## Amélioration de la sécurité

### Utilisation de NGINX

NGINX est un serveur web largement utilisé. Il possède un nombre important de fonctionnalité permettant d'améliorer la sécurité.

On peut notamment citer le reverse proxy permettant de limiter le nombre de ports ouvert des conteneurs en se limitant au port 80 (pour la connexion HTTP). 

# Conclusion

C'était super.

# Auteurs

- Noam GEFFROY
- Pol JAOUEN
- Stevan METAYER
- Fanny SHEHABI