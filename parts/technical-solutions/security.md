# Menaces les plus répandues

## XSS

La faille XSS est une faille majeure, l'utilisation de faille XSS consiste à injecter du code malveillant
d'un site vers un autre afin de récupérer les informations de connexion de l'utilisateur par exemple.

L'utilisation de faille XSS peut-être dévastatrice et de nombreuses pratiques frauduleuses peuvent en découler.
Prenons un exemple d'utilisation de faille XSS:

Un utilisateur nommé Gérard reçoit un mail provenant de sa banque lui indiquant un besoin de rectification,
Gérard clique alors sur ce lien, malheureusement, il est déjà trop tard.

L'émetteur de ce mail frauduleux avait glissé du code malveillant dans ce lien par le biais d'une faille XSS inconnue
sur le site de la banque de Gérard, l'attaquant a alors été en mesure de faire exécuter du code malveillant
au site de la banque de Gérard, l'attaquant à redirigé Gérard par le biais d'un lien récupérant ses cookies de connexion
à sa banque, l'attaquant a récupéré le cookie de connexion de Gérard et a maintenant la possibilité
de se connecter au compte de ce dernier.

La plupart du temps, les attaques XSS si elles sont bien faites ne sont même pas visibles par la vicitime.

Il existe des possibilités infinies quant à l'exploitation de faille XSS telles que :

Requêtes silencieuses
Les requêtes silencieuses sont un moyen d'appeler certaines pages sur le Web sans qu'un utilisateur s'en apercoivent.
Exemple d'exploitation de requêtes silencieuses, nous reprendrons notre ami Gérard :

L'attaquant à placer du code effectuant une requête silencieuse afin de demander à une page de tracage d'effectuer un tracage sur la page actuelle,
la page récupére alors le cookie de connexion de Gérard à sa banque et l'attaquant n'a plus qu'à récupérer ce cookie,

Gérard ne s'est rendu compte de rien, la requête étant silencieuse,
il peut continuer sa navigation sans le moindre soucis mais surtout sans s'être rendu compte qu'il venait de donner l'accès à son compte bancaire à un tiers.

Le clickjacking
Le clickjacking est une pratique consistant à remplacer le contenu d'un site Web légitime par un contenu frauduleux.
Exemple d'exploitation de clickjacking, nous reprendrons notre ami Gérard :

Gérard est assez chanceux, sa banque à mis en place un système d'authentification par JWT et donc l'attaquant n'a qu'une partie de son jeton d'authentification, il n'ira pas bien loin avec ceci.

Cependant, l'attaquant à placer du code malveillant afin de remplacer le formulaire de connexion au site de la banque de Gérard ressemblant trait pour trait,

Gérard entre ses informations de connexion et les valides, le formulaire envoi un mail à l'attaquant avec les informations de connexion de Gérard et Gérard est reconduit sur la page de son compte en banque.

Il est très important de développer avec précaution afin d'éviter les failles de type XSS (Cette faille mériterait elle aussi une documentation à part entière).

## CSRF

L'attaque par CSRF ou Forge de Requête par site Interposés est un type d'attaque semblable à une attaque par XSS, le but de l'attaque par CSRF est enfaite d'exécuter des actions sur un site Web légitime à l'insu de l'utilisateur, poster un message sur un forum par exemple, il est aussi possible de récupérer les informations de connexion de l'utilisateur par le biais d'attaque CSRF.

## DDos (Distributed Denial of Service / Attaque par déni de service) 

Une attaque DDos est une attaque de grande envergure, elle consiste à bomber un système exposé au réseau de requête massive de façon à ce que le composant logiciel entraine la chute de l'infrastructure système.

Les attaque DDos n'ont pas de réelle solution en terme de développement, il est possible d'optimiser les sécurités au niveau des composants logiciels afin de réduire la charge de ces derniers sur les infrastructures, cependant dans 99.9% des cas une attaque DDos se solde par un succès si des mesures de protection au niveau de la couche Réseau ne sont pas prise.

## Front End

### CSP

La Politique de Sécurité du Contenu (CSP) est une politique mise en place par le navigateur,
grace à CSP il est possible de dresser une liste de ressources dont l'exécution sera authoriser,
à l'inverse si une ressource importée d'un autre domaine par le biais de CORS ne se trouve pas dans la liste de CSP,
cette dernière verra son importation ou son exécution bloquée par le navigateur afin de prévenir l'injection de code par exemple.

De ce fait, CSP permet d'endiguer en partie les failles de type XSS, cependant, CSP ne représente pas une contre-mesure suffisante à ce type de faille et ne doit donc pas se substituer à de bonnes pratiques en matière de développement.

### Sanitisation

La sanitisation est une solution permettant de nettoyer la donnée entrée par l'utilisateur, afin de ne pas permettre à un utilisateur d'entrer de chiffre dans un champ prévu pour un nom par exemple.

Il existe une sanitisation côté front-end et côté back-end
la solution de sanitisation côté front-end est un premier rempart mais trop peu suffisant
avec la sanitisation côté front-end, il est possible de nettoyer l'information entrée par un utilisateur lambda
mais pour quelqu'un d'experimenté, il est assez aisé de supprimer la sanitisation côte front-end.

C'est pourquoi la sanitisation côté back-end doit être mise en place, afin d'être assuré que les informations entrées sont conformes aux attentes et seront traitables.