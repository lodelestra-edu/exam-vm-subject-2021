# Sujet examen - Administration système et virtualisation

## Connection a votre machine d'examen par ssh
domain : examen[num].training.ovh
mot de passe root sur votre feuille

exemple pour l'etudiant 42

```
ssh root@examen42.training.ovh
```

**vous trouverez votre numéro de machine et votre mot de passe root sur la feuille de consigne de votre poste de travail**
**Vous devez dater et signer à côté de votre nom et laisser toutes les feuilles de consignes avant de sortir de la salle d'examen**


### Tout votre travail durant cet examen machine se déroulera dans le répertoire **/root/exam/**.
### Il vous est demandé d'écrire les commandes docker utilisées dans un fichier **/root/exam/reponses.sh** avec le format suivant.
```sh
# reponses.sh
# NOM
# PRENOM
# 1
Commande de reponse a la question 1
Commande de reponse a la question 1
# 2
Commande de reponse a la question 2
# 3
...
```
## A la fin de l'examen *ce répertoire /root/exam* sera automatiquement archivé en un fichier tar exemple **exam42.training.ovh.tar** et sauvegardé pour évaluation

---

1. Donner les commandes pour: supprimer tous les containers, supprimer toutes les images. (soit un total de deux commandes)

1. Donner la commande utilisée pour créer et démarrer un container à partir d'une image **ubuntu** en version 14.04 et obtenir un shell dans le container. (une seule commande)

1. Donner la commande pour lancer un container **ubuntu 14.04**, que vous nommerez **pinger**, et qui effectue en arrière-plan (en mode détaché) une série de 20 ping sur l'adresse **uca.fr** .
Donner la commande qui permet d'afficher les logs de ce container.
Donner la commande permettant d'obtenir un terminal sur ce container déjà créé et démarré. (soit un total de trois commandes)

1. Créer les repertoires et le fichier **root/exam/nginx_site/index.html**. Ecrivez votre nom dans le fichier index.html.
Donner la commande pour demarrer un container **nginx** avec un montage entre votre repertoire nginx_site sur la machine host et le repertoire /usr/share/nginx/html du container et un mapping du port 80 du container sur le port 8881 de l'host. (une seule commande)

1. Donner la commande pour demarrer en arrière plan un container nommé **database** basé sur l'image **mongo**.
Donner la commande pour créer un deuxième container en arrière plan basé sur l'image **mongo-expess**, avec un lien réseau vers le container database et effectuant un mapping du port 8081 du container sur le port 8882 de l'host . Ce lien utilisera l'alias **mongo**. (soit un total de deux commandes)

1. Cloner le repository git suivant **https://github.com/lodelestra-edu/express_site.git** dans le dossier **/root/exam/express_site**
Dans src/app.js écrire votre nom à la place de <your_name>
Dans ce dossier **express_site**. Écrire un Dockerfile répondant aux critères suivant:
- Utilise **node** comme image de base
- créer un repertoire de travail /usr/src/app/
- Copie le fichier **package.json** et le contenu du dossier **src** (fournis) dans le repertoire de travail.
- Installe les dépandances avec **npm install**
- Permets un mapping automatique sur le port 3000
- Définis en commande par défaut **npm start**

  Donner la commande pour builder une image à partir de ce Dockerfile, cette image doit utiliser le tag <votre_nom>/express_site:1.0
  Donner la commande pour démarrer un container basé sur cette image et avec un port mapping sur le port 8883.

7. Dans le même dossier **express_site**.
Vous souhaitez construire une application composée de deux services.
Le premier, que vous nommerez **database**, est une base de données basée sur l'image **mysql**.
Le second, que vous nommerez **web**,  est votre site web. Le fichier Dockerfile de **web** est celui que vous avez créé précédement. Votre service **web** devra être accessible sur le port 8884 et utilisera un lien vers la base de données avec l'alias **db**.
\
Écrire le fichier docker-compose.yml. Donner la commande permettant de créer et démarrer les deux services.
