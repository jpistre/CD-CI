## TD - Julien Pistre

Étapes :
- Création d'un Dockerfile qui copie le JAR généré par `./mvnw clean install -DskipTests` ;
- Ajout du service `app` qui build ce Dockerfile ;
- Création d'un réseau avec le driver `bridge` pour lier `mysql` et `app` ;
- Utilisation de `depends_on` pour démarrer `app` après `mysql` ;
- Ajout d'un healthcheck pour Petclinic avec Actuator  ;
- Ajout d'un healthcheck pour la base de données avec `mysqladmin ping` ;
- Création d'un pipeline Jenkins qui build le projet et l'image Docker.
