PING PONG TOURNOI #2 — METTRE LE SITE SUR FIREBASE HOSTING
==========================================================

Avec Firebase Hosting, AUCUNE clé à copier : le site trouve tout seul la configuration
de ton projet. Ton site aura une adresse du genre  https://pingpong-tournoi.web.app
Tout est gratuit (forfait Spark). N'ajoute jamais de carte / compte de facturation.

Ce dossier contient :
  public/index.html   le site (inscription, tableau, horaire, profil, scores, organisateur)
  firestore.rules     les règles de sécurité (envoyées automatiquement au déploiement)
  firebase.json       la configuration du déploiement


A. DANS LA CONSOLE FIREBASE (navigateur, ~5 min)
   1. https://console.firebase.google.com > « Créer un projet » > nom : pingpong-tournoi
      > Google Analytics : non > Créer.
   2. Créer (Build) > Authentication > Commencer > onglet « Mode de connexion » :
      - Adresse e-mail/Mot de passe > Activer > Enregistrer
      - Ajouter un fournisseur > Google > Activer > ton courriel comme adresse d'assistance > Enregistrer
   3. Créer (Build) > Firestore Database > Créer une base de données
      > emplacement northamerica-northeast1 (Montréal) > mode production > Créer.
   4. Créer (Build) > Hosting > Commencer (tu peux cliquer « Suivant » jusqu'à la fin).


B. SUR TON ORDINATEUR (une seule fois, ~5 min)
   1. Installe Node.js (version LTS) : https://nodejs.org
   2. Ouvre le Terminal (Mac) ou l'Invite de commandes (Windows) et tape :
         npm install -g firebase-tools
   3. Puis :
         firebase login
      (une page s'ouvre : connecte-toi avec bartolomeovictor@gmail.com)


C. METTRE EN LIGNE (à refaire seulement si tu changes le site)
   Dans le Terminal, va dans ce dossier (glisse le dossier dans le Terminal après « cd ») :
         cd chemin/vers/tournoi-firebase
         firebase use --add          (choisis pingpong-tournoi, puis tape « default »)
         firebase deploy
   À la fin, le Terminal affiche l'adresse du site : Hosting URL: https://....web.app
   C'est ce lien que tu envoies aux joueurs.


D. DEVENIR ORGANISATEUR
   Ouvre ton site > « Continuer avec Google » avec bartolomeovictor@gmail.com
   > l'onglet « Organisateur » apparaît.


EN CAS DE PROBLÈME
   - « Permission denied » / rien ne s'enregistre : vérifie que l'étape A3 (Firestore) est faite,
     puis refais  firebase deploy  (il envoie aussi les règles).
   - Le bouton Google ne fait rien : vérifie l'étape A2 (fournisseur Google activé).
   - Ajouter un organisateur : ajoute son courriel dans public/index.html (ADMIN_EMAILS)
     ET dans firestore.rules, puis  firebase deploy.
