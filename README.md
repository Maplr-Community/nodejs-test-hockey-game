## Test Développeur Node.js intermédiaire

## Objectif du test

Votre objectif pour ce test est de créer un API Rest avec node.js et express.js pour ajouter et obtenir les joueurs et les informations de l'équipe de Hockey des Canadiens du Montréal. Le but est donc d'avoir la composition de cette équipe pour chaque année ou elle a participé à la Ligue Nationale de Hockey.

**Vous devez créer les endpoints suivants dans l'API:**

- Un GET pour obtenir la composition de l’équipe en fonction de l'année dans la base de données.
- Un POST pour t'ajouter en tant que nouveau joueur de l'équipe d'une année définie dans la base de données.
- Un PUT pour mettre à jour le capitaine de l'equipe pour une année définie.

## **Présomptions**

- Ne vous souciez pas de valider l'entrée de l'utilisateur, vous pouvez présumer que la requête sera toujours valide.
- Il n'est pas nécessaire d'implémenter un mécanisme de sécurité.

## Critères

- 3 endpoints REST fonctionnels
- Qualité du code
- Utilisation des meilleurs pratiques de développement

## Outils à utiliser

- Node.js
- Express.js
- Base de données SQL au choix (mysql, postgresql, mariadb etc..)
- Test unitaire (Optionnel)
- Typescript (Optionnel)

## Modèle

Team

```
{
    "id": 1,
    "coach": "Dominique Ducharme"
    "year" : 2020
    "players": [
        {
            "number": 99,
            "name": "John",
            "lastname": "Doe",
            "position": "defenseman",
            "isCaptain" : false
        }
    ]
}
```

## Endpoints

### GET /api/team/{year}

- Requête: Year dans l'URI

- Réponse: Objet Team (Voir modèle ci-dessus)

- Status: 200 OK

  http://localhost:8080/api/team/2020 { "id":2, "coach":"Dominique Ducharme", "year":"2020", "players":[ { "number":31, "name":"Carey", "lastname":"Price", "position":"goaltender" }, { "number":14, "name":"Nick", "lastname":"Suzuki", "position":"forward" }, { "number":15, "name":"Jesperi", "lastname":"Kotkaniemi", "position":"forward" }, { "number":71, "name":"Jake", "lastname":"Evans", "position":"forward" }, { "number":27, "name":"Alexander", "lastname":"Romanov", "position":"defenseman" }, { "number":6, "name":"Shea", "lastname":"Weber", "position":"defenseman", "isCaptain" : true } ] }

  http://localhost:8080/api/team/2019 { "id":1, "coach":"Dominique Ducharme", "year":"2019", "players":[ { "number":31, "name":"Carey", "lastname":"Price", "position":"goaltender" }, { "number":14, "name":"Nick", "lastname":"Suzuki", "position":"forward" }, { "number":15, "name":"Jesperi", "lastname":"Kotkaniemi", "position":"forward" }, { "number":71, "name":"Jake", "lastname":"Evans", "position":"forward" }, { "number":27, "name":"Alexander", "lastname":"Romanov", "position":"defenseman" }, { "number":6, "name":"Shea", "lastname":"Weber", "position":"defenseman", "isCaptain" : true } ] }

### POST /api/team/{Year}

- Requête: Objet Joueur dans le body
- Réponse: Objet Joueur crée
- Status: 201 CREATED

```
http://localhost:8080/api/player --header "Content-Type:application/json"

{
  "number":99,
  "name":"Antonin",
  "lastname":"Bouscarel",
  "position":"forward",
  "isCaptain" : false
}
```

### PUT /api/player/captain/{ID}

- Requête: ID du joueur dans l'URI
- Réponse: Objet Player
- Status: 200 OK

## Validation des endpoints

Vous pouvez utiliser la collection postman incluse dans le projet si vous désirez valider votre API avec des assertions.

Celle-ci se retrouve dans le dossier **postman** du projet.

## Soumettre le test

Une fois terminé, veuillez créer un nouveau dépot sur GitHub et l'envoyer par courriel.

**Bonne chance et bon game ! 🏒**
