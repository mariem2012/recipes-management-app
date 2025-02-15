# API RESTful de Gestion des Recettes

Cette API permet de gérer une collection de recettes. Vous pouvez l'utiliser pour créer, lire, mettre à jour et supprimer des recettes.

### Prérequis

- [Node.js](https://nodejs.org/) (version 14 ou supérieure)
- [MySQL](https://www.mysql.com/) (version 5.7 ou supérieure)
- [Express.js](https://www.npmjs.com/package/express) (version 4.21 ou supérieure)

## Installation

Suivez ces étapes pour configurer le projet sur votre machine locale :

1. **Clonez le repository :**

    ```bash
        https://github.com/Ousmanly/gestion_recette_api.git
    ```

2. **Accédez au dossier du projet :**

     ```bash
        cd gestion_recette_api
    ```

3. **Installez les dépendances :**

    ```bash
      npm install
    ```
4. **Configurer la base de données**

  - Assurez-vous que Mysql est en cours d'exécution sur votre machine locale.
  - Mettez les paramètres de connexion dans `db.js`.
  - Créez un fichier .env avec la configuration de votre base de données :
    ```js
        DB_HOST=localhost
        DB_USER=root
        DB_PASSWORD=yourpassword
        DB_NAME=recipes_db
    ```

## Utilisation

Pour démarrer l'application, exécutez la commande suivante :

```bash
  npm start
```

## Endpoints de l'API

 **Récupérer toutes les recettes**
  - URL : /recettes
  - Méthode HTTP : GET
  - Description : Récupère la liste de toutes les recettes.
  - Exemple : ` http://localhost:3000/recettesv`
  - Reponse :
    ```JSON
        [
            {
                "id": 1,
                "title": "Tarte aux pommes",
                "ingredient": "Pommes, pâte brisée, sucre",
                "type": "Dessert"
            },
            {
                "id": 2,
                "title": "Salade César",
                "ingredient": "Laitue, poulet, parmesan, croûtons",
                "type": "Entrée"
            }
        ]
    ```
 **Créer une nouvelle recette**
  - URL : /recettes
  - Méthode HTTP : POST
  - Description : Crée une nouvelle recette.
  - Exemple : 
    `http://localhost:3000/recettes`
    - body
    ```JSON
        {"title": "Omelett", 
        "ingredient": "Oeuf, Huile", 
        "type": "Plat"}
    ```
  - Reponse :  
    ```JSON
        {
            "id": 1
        }
    ```
 **Mettre à jour une recette**
  - URL : /recettes/:id
  - Méthode HTTP : PUT
  - Description : Met à jour une recette existante.
  - Exemple : 
    `http://localhost:3000/recettes/1`
    - body
    ```JSON
        {"title": "Omelett", 
        "ingredient": "Oeuf, Huile", 
        "type": "Plat"}
    ```
  - Reponse :
    ```JSON
        {
        "message": "recipe has been updated successfully"
        }
    ```
 **Supprimer une recette**
  - URL : /recettes/:id
  - Méthode HTTP : DELETE
  - Description : Supprime une recette par son ID.
  - Exemple : 
    `http://localhost:3000/recettes/1`
  - Reponse :
    ```JSON
        {
        "message": "recipe has been deleted successfully"
        }
    ```
# Collection Postman
    Vous pouvez importer la collection Postman fournie Recipe_collection.json pour tester facilement tous les endpoints de l'API.

## Author
- **GitHub** : [Ousmane Ly](https://github.com/Ousmanly)
- **GitHub** : [Mariem Dianifaba](https://github.com/mariem2012)