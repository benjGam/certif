# Sécurisation du BackEnd

## Moindre privilège

Le principe de moindre privilèges consiste à restreindre les permissions d'un composant systèmes aux permissions strictement nécessaires à son bon fonctionnement, ce qui signifie qu'un compose n'aura pas de permissions supérieures à ses fonctions.

Ce qui permet d'empêcher une potentielle exploitation des composants systèmes mis en place afin de réaliser des actions malveillantes au sein d'un système.

## Défense en profondeur

La défense en profondeur est un concepte selon lequel il prévaut d'aborder un aspect de sécurité dans chaque composants d'un système plutôt que de concentrer la sécurité en un seul et même point.

En sécurisant chaque composant individuellement, ces composants participe à la sécurité générale du système.

## Réduction de la surface d'attaque

![](imgs/voile.jpg)

Leg : L'exposition

La réduction de la surface d'attaque est un concept selon lequel il n'est nécessaire d'exposer les composants d'un système uniquement et uniquement si cela est obligatoire.
Qu'il s'agisse d'exposer des composants ou des sous-services de ses composants il est important de se poser la question de savoir si un choix à été fait de façon réfléchi et de comprendre les causes qui mène à l'exposition des composants.

Par exemple, dans une architecture comme la notre nous avons, 1 BackEnd API, 1 FrontEnd, 1 Base de Donnée

Dans ce cas, nous savons que nous allons epxoser les ports :

- 80 : HTTP
- 443 : HTTPS
- 22 : SSH
- 3000 : Port de connexion de l'API

Et exposer notre machine sur le réseau uniquement par ces ports, nous avons réduis la surface d'attaque réseau à 4 services exposés.

## CORS

Cross Origin Ressources Sharing (CORS) ou Partage de Ressources Inter-Origin
est une sécurité permettant d'échanger des ressources entre différentes origines
de cette façons, il sera possible de récupérer des informationss sur des sites partenaires,
cependant grace à CORS il est possible d'établir une liste de domaine avec lesquels échanger des informations.

Pour qu'un échange de donnée entre origines puisse avoir lieu avec CORS
il est nécessaire que les 2 origines acceptent l'échange l'un avec l'autre
sans quoi l'échange de donnée n'aura pas lieu.

Dans le cadre du projet de la Mission Locale, CORS sera mis en place afin d'échanger des contenus provennant de partenaires.

## Request Rate Limit (RRL)

Une alternative à considérer en terme de sécurité de l'API est le Request Rate Limit ou Limite des Requêtes.
Il est possible de définir un nombre limité de requête à l'API dans un temps donnée, ce qui constitue une sécurité en terme de structure système, sur un serveur de petite composition, il est intéressant d'évaluer cette possibilité afin d'empêcher l'API d'être surchargé et de faire tomber toute l'infrastructure réseau, cependant cette solution n'est pas une solution absolue en cas d'attaque DDos (Distributed Denial of Service) par exemple

## Base de donnée

### Politique des mots de passe

Une politique de mot de passe est un ensemble de recommandations à suivre afin d'établir une certaines sécurié concernant les mots de passe possiblement entrés par les utilisateurs.
Dans le cadre de cette strategie, la politique des mots de passes sera la suivante :

- Une longueur comprise entre 8 et 80 caractères.
- Une composition (A-z, 0-9, caractères spéciaux sans exception) des mots de passe.
- La vérification de la robustesse du mot de passe entré en temps réel par la vérification des facteurs ci-dessus.
- Un temps d'attente de 2 minutes par tranche de 3 tentatives de connexions échouées.
- Une stratégie de recouvrement par le biais d'un lien envoyé par mail afin de regénérer un mot de passe.

#### Chiffrement : BCrypt

Un algoritme de chiffrement est utile lorsque l'on veut qu'une information ne soit pas découverte
on insère alors cette information dans un algoritme de chiffrement afin que cette information ne soit plus compréhensible en l'état.

Dans le cadre de ce projet, l'algoritme de chiffrement retenu pour chiffrer les mots de passes des utilisateurs sera BCrypt.

Il était initalement prévu d'utiliser le module BCrypt afin de chiffrer les informations de connexion des utilisateurs au Dashboard Web, cependant nous n'avons pas eu le temps de mettre en place ce système de connexion.

##### Hashage

BCrypt est un algoritme de chiffrement dit de "Hashage", lorsque l'on parle de hashage
on parle de méthodologie de chiffrement découpant l'information en une quantité de tronçons de même taille
BCrypt utilise un système de coût (qui n'est ni plus ni moins que le nombre de fois que l'opération de hashage sera effectué sur l'information)

Cependant, le hashage en lui même ne représente pas une sécurité suffisante en elle-même
puis-ce qu'un algoritme de chiffrement est une simple opération mathématique applicable en fonction de certains facteur.

###### Salage 

Le salage est simplement le fait de rajouter une information (le sel) avant ou après l'information à hasher.

Le sel peut être une phrase telle que 'Je suis le sel, et je suis utilisé dans le but de rendre indéchiffrable le hash auquel je vais être appliqué' sur laquelle un traitement aléatoire de mélange sera appliqué afin de rendre chaque sel unique et par la même occasion chaque empreinte de hashage différente.

#### RGPD (Règlement Général sur la Protection des Données)

Le RGPD est un règlement en vigueur au sein de l'Union Européenne, grace au RGPD les utilisateurs dont les informations sont stockées sur un système afin d'assurer un service voient la protection de leurs données respectées.

Le RGPD traitent certains sujets tels que les suivants :

Un traitement de donnée (Récupération, Modification, Exctraction, etc) ne peut pas être effectué sans but précis.
Les données d'un utilisateur ne peuvent pas être stockées indéfiniment, il faut que les données soient supprimées à un moment.
Un utilisateur dont les données sont stockées sur un serveur doit avoir un droit de suppression, modification, regard sur ces dernières.
Dans le cadre de ce projet, le RGPD sera mis en oeuvre.

#### UUID (Universally Unique Identifiers)

Un UUID est un identifiant unique délivré par le serveur pour chaque utilisateur ayant besoin d'un enregistrement en base de donnée.

A l'inverse d'un simple ID pouvant être composé de digits allant de 0 à 9
l'UUID se compose d'un ensemble de caractère litteraux et numérique comme suit : 863cebfd-7875-45af-9e83-cd1e43aa1be4

De cette façon, il n'est pas envisageable qu'un attaquant puisse faire appelle à la base de donnée afin d'en récupérer les informations par le biais du champ 'ID' puis-ce qu'il faudrait être incroyablement chanceux pour tomber sur un UUID identique.

#### SQLInjection

La faille SQLi (SQL Injection) est un type de faille permettant d'exécuter des requêtes SQL non préevues.
Prenons un exemple d'exploitation de faille SQLi :

Un attaquant se trouve sur une page de connexion d'un site Web vulnérable à l'injection SQL
Il tape un nom d'utilisateur aléatoire et tape un mot de passe tel que celui-ci : SQL ' OR 1=1  .

Le serveur voit simplement le mot de passe et l'interprete comme suit : .. WHERE USERAME='nom utilisateur bidon' AND PASSWORD='' OR 1=1 .

Le serveur exécute la requête SQL et donne l'accès au premier compte contenu dans la base de donnée, l'attaquant est donc connecté sur le compte d'un utilisateur qui est dans 99% des cas le compte un compte à privilèges.

Il existe des déclinaisons à l'injection SQL, comme la suppression de toutes les données contenues de la base de données par l'interposition d'un ';' afin de faire exécuter toutes les requêtes envisageables à la base de donnée.
Afin de palier à ce type de faille, il existe des outils tels que des ORM permettant d'endiguer ce type de faille.

##### ORM

Un ORM permet de préparer des paternes de requêtes SQL et de préparer des requêtes lors de leur exécution en base de données
ce qui permet d'empêcher l'insertion de caractère d'échappement dans les requêtes, de cette façons
chaque informations sera écrite AS DATA et non plus AS LITTERAL et ne permettra plus l'exécution de code SQL arbitraire.

Dans le pire des cas avec un ORM bien configuré mais sans la gestion d'erreur relative
la réponse de la base de donnée sera une succession d'erreur et le script plantera.