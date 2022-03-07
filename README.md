# Advisor 
![with-docker](https://user-images.githubusercontent.com/92017625/157022460-86b3500d-43e3-42a7-a8c5-b8b6ff77e017.svg)![sanctum](https://user-images.githubusercontent.com/92017625/157023772-5223cda5-31d8-42f3-9ab8-7419f953e282.svg)


Pour le projet "Advisor" on a mis en place une api REST laravel sous un docker. 

## 1ère Partie : API

### Déploiement

Voici les commandes pour déployer le docker qui contient l'API: 

`docker-compose up`

A la fin la sortie du code sera 0. A ce moment là il faudra "cut" le programme en faisant : 

- crtl+x 
- crtl+c 

Aller dans le fichier `docker-compose.yml` situé à la racine du dossier puis s'assurer que la variable myapp est bien comme présenté ci-dessous : 

```dockerfile
  myapp:
    image: docker.io/bitnami/laravel:8
    #command: composer update
    ports:
      - '8000:8000'
    environment:
      - DB_HOST=db
      - DB_PORT=3306
      - DB_USERNAME=root
      - DB_DATABASE=advisor
      - DB_PASSWORD=my_secret_password
```

En commantant la ligne `command: composer update` le dossier `vendor/` de l'application se générera. 
Félicitation votre application est désormais déployée. 
