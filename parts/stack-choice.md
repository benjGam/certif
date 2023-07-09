# Identification des technologies à utiliser

Nous avons réalisé des études quant aux technologies adaptées à ce projet, nous avons donc établi des tableaux comparatifs des différentes solutions.

## La base de données : PostgreSQL

Dans le cadre de ce projet, il nous fallait une base de donnée afin de permettre la persistance des données, nous avons donc réalisés des études comparatives entre différents types de SGBD et avons selectionnés PostgreSQL

PG est un SGBDRO (Système de Gestion de Base de Donnée Relationnel et Objet) ce qui signifie que PostgreSQL prends en charge les bases de données relationnelles ainsi que des bases de données non relationnelles (NoSQL)

De plus, PG robuste, il indique des performances satisfaisante en terme d'accès aux ressources de l'application.
PG permet une approche scalable de la base de donneé et ainsi du projet.

De plus PostgreSQL met en place des systèmes de sécurité interne et permet d'appliquer des sécurités supplémentaire sur certaines tables selon certains critères (Row-Level Security).
PostgreSQL est open-source, ce qui en fait un SGBDRO flexible et adaptable aux besoins rencontrés pour le projet.

C'est pour toutes ces raisons que PostgreSQL a été sélectionné comme solution de persistance de nos données.

## Choix du langage

Dans une équipe réduite comme la notre, il nous fallait un langage relativement simple à prendre en main par tous les membres de l'équipe, assez léger pour être mis en place côté serveur sans nécessiter de coûts de machine trop élevés.

### TypeScript

TypeScript est un langage plus robuste que JavaScript. Il s'agit d'un "superset" de JavaScript qui introduit de nombreux concepts que JavaScript vanilla n'implémente pas, tels que la POO (Programmation Orientée Objet).

Dans un projet de cette envergure, il est absolument nécessaire de pouvoir utiliser la Programmation Orientée Objet. Même si un bot peut sembler très basique de l'extérieur, à l'intérieur, c'est une autre affaire. Ce projet aurait pu être réalisé dans les délais avec du JavaScript vanilla, cependant, la maintenabilité du code aurait été quasiment impossible pour une équipe devant reprendre le projet.

TypeScript est un langage dit de "Typage Fort" qui ne permet pas l'assignation de valeur aux variables de façon dynamique, chaque variable à un type et il n'est pas possible de stocker n'importe quel type de donnée dans n'importe quelle variable.

De plus, par le biais de son transpileur Typescript apporte une gestion des erreurs et un affichage de ces dernières bien moins verbeux et plus claire, ce qui permet de comprendre plus rapidement les erreurs de transpilation et ainsi de les règler plus vite.

C'est pour ces raisons que TypeScript a été préféré à JavaScript. En terme de pérennité du projet, JavaScript n'était pas le choix adapté.

## API

Aussi, puisque nous avions besoin de stocker des données, nous avions besoin de contrôler l'accès à ces données. C'est pourquoi nous avons décidé de mettre en place une API afin de contrôler l'accès aux ressources de l'application.

### Stateless

Notre API n'avait pas besoin d'être stateful. Nous n'avions pas besoin que les requêtes de l'API s'adaptent en fonction du contexte dans lequel elles étaient faites. C'est pourquoi nous avons décidé de mettre en place une API stateless plutôt qu'une API stateful.

### RESTful API

Une API RESTful est une API qui respecte 5 principes fondamentaux de l'architecture REST :

- Architecture client <-> serveur
- Requête sans conservation d'état (stateless)
- Cacheable : Permettant de mettre en cache les ressources pour optimiser les performances
- Interface uniforme : Une interface uniforme qui permet la communication entre les composants du système (les composants peuvent interagir les uns avec les autres)
- Construction en couches : Permet de hierarchiser les différents composants de l'API

Nous avons également choisi une architecture RESTful pour notre API, car il fallait qu'elle soit accessible par un large éventail de clients, et donc qu'elle fournisse des réponses structurée de façon standardisée pour chaque client souhaitant la consommer.

La mise en place d'une architecture RESTful semblait être la solution la plus adaptée dans le cadre de ce projet.

## Analyse du Framework Back End (API)

0 = Moins Intéressant
2 = Plus Intéressant

| Critères                 | Koa     | Fastify | Nest    | Adonis  |
| ------------------------ | ------- | ------- | ------- | ------- |
| Personnalisation         | 0       | 0       | 2       | 0       |
| Rapidité                 | 1       | 2       | 2       | 1       |
| Popularité               | 1       | 1       | 2       | 0       |
| Maturité                 | 2       | 1       | 0       | 1       |
| Releases                 | 0       | 2       | 1       | 1       |
| Bonnes pratiques         | 0       | 0       | 2       | 0       |
| Stars Github             | 1       | 1       | 2       | 0       |
| Equipe Développement     | 0       | 2       | 1       | 1       |
| Communauté Github        | 1       | 1       | 1       | 0       |
| Communauté StackOverflow | 1       | 1       | 2       | 0       |
| Sécurisé By Design       | 0       | 0       | 2       | 2       |
| Documentation            | 0       | 1       | 2       | 2       |
| Magie                    | 0       | 0       | 0       | 0       |
| Mariage librairies       | 2       | 2       | 2       | 0       |
| Prise Politique          | 2       | 2       | 0       | 2       |
| License                  | MIT     | MIT     | MIT     | MIT     |
| Total                    | 11      | 16      | 19      | 8       |

## Choix du framework Back-End (bot)

Notre équipe a décidé d'utiliser le framework Discord.js pour développer les bots Discord. Discord.js est un framework très complet, maintenu par une grande communauté de développeurs et surtout, le seul framework parfaitement compatible avec TypeScript. C'est pourquoi, pour le choix du framework Back-End concernant les bots, notre équipe s'est tournée vers Discord.js.

## Analyse du Framework Front End

0 = Moins Intéressant
2 = Plus intéressant

| Critères                 | ReactJS | Angular | Vue.js  |
| ------------------------ | ------- | ------- | ------- |
| Personnalisation         | 2       | 0       | 1       | 
| Rapidité                 | 1       | 1       | 2       |
| Popularité               | 2       | 1       | 0       |
| Maturité                 | 1       | 1       | 1       |
| Releases                 | 0       | 2       | 1       |
| Bonnes pratiques         | 1       | 2       | 2       |
| Stars Github             | 2       | 1       | 2       | 
| Equipe Développement     | 2       | 1       | 0       |
| Communauté Github        | 1       | 1       | 0       |
| Communauté StackOverflow | 1       | 2       | 0       |
| Qualité Documentation    | 1       | 2       | 1       |
| Côté Magique             | 2       | 2       | 2       |
| Mariage librairies       | 0       | 0       | 0       |
| Prise Politique          | 0       | 2       | 2       |
| License                  | MIT     | MIT     | MIT     |
| Total                    | 16      | 18      | 14      |

## Analyse de l'ORM (Object Relationnal Mapping)

0 = Moins Interessant
2 = Plus Intéressant

| Critères                 | TypeORM | Prisma  |
| ------------------------ | ------- | ------- |
| Rapidité                 | 2       | 1       | 
| Popularité               | 2       | 1       | 
| Maturité                 | 2       | 1       |
| Releases                 | 1       | 2       |
| Bonnes pratiques         | 1       | 2       | 
| Stars Github             | 2       | 1       |
| Equipe Développement     | 1       | 2       |
| Communauté Github        | 2       | 1       |
| Dernier commit           | 1       | 2       |
| Sonsors                  | 2       | 1       |
| Communauté StackOverflow | 2       | 2       |
| Documentation            | 1       | 2       |
| Prise Politique          | 1       | 0       |
| License                  | Apache2 | MIT     |
| Total                    | 20      | 18      |

Si l'on s'attarde sur le benchmark de l'ORM, on peut voir que TypeORM semblait être préféré à la place de Prisma. Cependant, notre équipe a dû choisir la solution la plus adaptée au projet, et il est apparu que, pour une équipe aussi réduite que la nôtre et dans les délais imposés, TypeORM semblait être trop lourd pour être intégré de manière optimisée au projet. C'est pourquoi, malgré l'analyse des caractéristiques de ces ORM, notre équipe a préféré utiliser Prisma plutôt que TypeORM.

#### Pourquoi utiliser un ORM ?

##### La sécurisation

En utilisant un ORM nous déleguons le travail de sécurisation de l'accès aux donnée à l'ORM qui va se charger d'executé des requêtes préparés permettant ainsi l'échappement des caractères et rendant de fait impossible l'exploitation d'une **Injection SQL**

##### L'abstraction

En effet, un ORM est très bon dans le domaine de l'abstraction, il permet d'éxecuter des requêtes SQL préparée (et donc sécurisée) de façon plus confortable pour les développeurs qui n'ont pas à écrire manuellement les requêtes à la main et qui peuvent simplement utiliser l'ORM dans le langage dans le quel ils developpent.

### Tableau récapitulatif 

| Question  | Réponse  |
|---|---|
| Machine Learning  | Non |
| Architecture | API |
| Asynchrone  | Oui |
| SEO | Non |
| Rendu | CSR |
| Hébergement | Serveur Perso |
| Environnement | NodeJS |
| Langage | Typescript |
| Framework Back End | NestJS |
| Framework Front End | Angular |
| BDD | PostregreSQL (SQL Relationnelle) |
| ORM | Prisma |

Dans le cadre de ce projet, nous n'avions aucunement besoin de "Machine Learning". Il nous fallait une application construite autour d'une architecture API, car cette architecture est plus modulable qu'une architecture monolithique. Le type de programmation qui a été sélectionné a été le développement asynchrone, car il ne fallait pas que notre API ait un fil d'exécution bloquant.

#### SEO

SEO signifie Search Engine Optimization, il s'agit d'une liste de critères à remplir lors de la création d'un site Web afin de permettre un bon référencement de celui-ci par les moteurs de recherche. En voici une liste non exhaustive :

- Rédaction de contenu de qualité pour les pages
- Bonne structuration sémantique des pages
- Utilisation de mots-clés dans les métadonnées des pages
- Présence de liens internes et externes significatifs dans les pages
- Rendu des pages en SSR (Server-Side Rendering)

Notre application Web, ayant pour but de gérer les différents bots depuis un panel d'accès Web, il était inutile de se préoccuper du référencement du site Web dans le cadre de ce projet. L'application Web n'a pas vocation à ouverte au public et est restreinte à une communauté Simplonnienne.

#### CSR vs SSR

Le SSR est un mode de rendu des pages Web côté serveur, il est intéressant de mettre en place ce mode de rendu lorsque le référencement d'un site Web est nécessaire.
Cependant, lorsqu'il n'est pas interessant d'améliorer son SEO, le SSR n'est pas recommandé car ce mode de rendu s'effectue côté serveur et donc consomme les ressources de ce dernier.

Le CSR est un mode de rendu des pages Web côté client, c'est-à-dire que le rendu des pages Web est effectué côté client et non côté serveur, ce qui impacte directement les performances d'affichage d'une page Web selon la machine du client voulant la consulter. Il n'était pas utile de mettre en place un mode de rendu SSR dans le cadre de ce projet, car cela aurait nui aux performances du serveur qui aurait alors dû gérer le rendu des pages.

Il était plus intéressant de laisser le rendu des pages Web au client plutôt qu'au serveur dans le cadre de ce projet.

Note: Il n'existe plus de framework qui utilise pûrement l'un ou l'autre de ces modes de rendu, les frameworks utilisent un hybride en fonction des besoins de l'application.

#### Hébergement

Nous avons choisi d'héberger l'application sur des serveurs dédiés internes à Simplon HDF. Cependant, à l'heure actuelle, nous nous sommes trompés, car l'application est hébergée sur des VPS.

### Testing

#### JEST

![](../imgs/jest.png)

JEST est un framework Javascript permettant d'exécuter des tests unitaires pour des applications de tout type.
Avec JEST il est facile d'écrire des tests et de les exécuter.

#### TDD

TDD signifie Test Driven Developpement, ce qui se traduit par "Le développement piloté par les tests".
Le TDD est un concepte selon lequel un développeur décrit un test pour une fonction, lance ce test qui échoue FORCEMENT.
Ensuite le développeur écrira la fonction à tester.

De cette façon, une fonction sera écrite en fonction du test qu'elle doit passée et le développeur.

#### Coverage

Le Coverage est une métrique permettant de connaitre le taux de code exécuté lors des tests d'une application.
Cette metrique permet de savoir à combien de pourcent le code est testé.

#### Le test Unitaire

Le test unitaire est un test réalisé sur une partie non divisible du code, un test unitaire est écrit pour tester une fonction du code, on décrit la valeur attendu à la sortie de la fonction et on vérifie si la donnée est bien celle attendu, le cas echéant, le test est un succès sinon le test échoue et le développeur modifie sa fonction tant que le test ne se solde pas par un succès.

#### Le test d'intégration

Le test d'intégration permet de tester l'intégration des composants au sein du code déjà existant, il assure que les composants individuelles s'intègre correctement au sein du code déjà existant sans que ce dernier n'est à subir de modification afin de permettre l'intégration du composant.

### Conclusion du Testing

Il était initialement prévu de développer en TDD et d'incorporer ces différents tests au sein de notre procéssus de développement, cependant notre organisation, ou désorganisation dans ce cas ne nous a pas permis de mettre en place de test unitaire de façon structurée.