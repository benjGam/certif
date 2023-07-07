# Identification des technologies à utiliser

Nous avons réalisé des études quant aux technologies adaptées à ce projet, nous avons donc établi des benchmarks.

## La base de données : PostgreSQL

Il nous fallait un moyen de faire persister des données, donc une base de données. Cependant, il existe plusieurs types de bases de données :

- Relationnelles (SQL)
- Non relationnelles (No SQL)
  

! REMPLACER LE BORDEL EN DESSOUS PAR : Robuste, Scalable, PG permet de faire du NoSQL, Sécurisé

Nous avons réalisé des comparatifs quant aux différentes solutions disponibles pour faire persister nos données, et notre équipe a choisi PostgreSQL en guise de SGBD (Système de Gestion de Base de Données).

En raison de l'utilisation de PostgreSQL dans de nombreux projets, nous avons déterminé que PG est fiable. De plus, PostgreSQL est performant, il est capable d'apporter des taux de performances satisfaisants dans des scénarios de grandes sollicitations de l'accès aux données.

PostgreSQL est open-source, ce qui en fait un SGBDRO flexible et adaptable aux besoins rencontrés pour le projet.

C'est pour toutes ces raisons que PostgreSQL a été sélectionné pour la persistance de nos données.

## Choix du langage

Dans une équipe composée comme la nôtre et avec ces délais, il nous fallait un langage relativement simple à prendre en main par tous les membres de l'équipe, assez léger pour être mis en place côté serveur sans nécessiter de coûts de machine trop élevés.

C'est pourquoi notre choix s'est porté sur TypeScript.

### TypeScript

TypeScript est un langage plus robuste que JavaScript. Il s'agit d'un "superset" de JavaScript qui introduit de nombreux concepts que JavaScript vanilla n'implémente pas, tels que la POO (Programmation Orientée Objet).

! TYPAGE FORT + ERREUR DE COMPIL PLUS CLAIRE

Dans un projet de cette envergure, il est absolument nécessaire de pouvoir utiliser la Programmation Orientée Objet. Même si un bot peut sembler très basique de l'extérieur, à l'intérieur, c'est une autre affaire. Ce projet aurait pu être réalisé dans les délais avec du JavaScript vanilla, cependant, la maintenabilité du code aurait été quasiment impossible pour une équipe devant reprendre le projet.

C'est pour ces raisons que TypeScript a été préféré à JavaScript. En termes de pérennité du projet, JavaScript n'était pas le choix adapté.

## API

Aussi, puisque nous avions besoin de stocker des données, nous avions besoin de contrôler l'accès à ces données. C'est pourquoi nous avons décidé de mettre en place une API afin de contrôler l'accès aux ressources de l'application.

### Stateless

Notre API n'avait pas besoin d'être stateful. Nous n'avions pas besoin que les requêtes de l'API s'adaptent en fonction du contexte dans lequel elles étaient faites. C'est pourquoi nous avons décidé de mettre en place une API stateless plutôt qu'une API stateful.

### RESTful API

Une API RESTful est une API qui respecte 5 principes fondamentaux de l'architecture REST :

- Architecture client <-> serveur
- Requête sans conservation d'état (stateless)
- Cacheable : permettant de mettre en cache les ressources pour optimiser les performances
- Interface uniforme : une interface uniforme qui permet la communication entre les composants du système (les composants peuvent interagir les uns avec les autres)
- Construction en couches : les composants font partie de leur couche, ce qui permet d'étendre les composants et de les remplacer de manière sûre sans perte de performance.

Nous avons également choisi une architecture RESTful pour notre API, car il fallait qu'elle soit accessible par un large éventail de clients, et donc qu'elle fournisse des standards de réponses valides pour chaque client souhaitant la consommer.

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

Expliquer pour l'ORM ?

- Sécurisation des requêtes via requêtes préparées

Si l'on s'attarde sur le benchmark de l'ORM, on peut voir que TypeORM semblait être préféré à la place de Prisma. Cependant, notre équipe a dû choisir la solution la plus adaptée au projet, et il est apparu que, pour une équipe aussi réduite que la nôtre et dans les délais imposés, TypeORM semblait être trop lourd pour être intégré de manière optimisée au projet. C'est pourquoi, malgré l'analyse des caractéristiques de ces ORM, notre équipe a préféré utiliser Prisma plutôt que TypeORM.

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

! Intro CSR vs SSR : Expliquer pourquoi CSR

Le CSR est un mode de rendu des pages Web côté client, c'est-à-dire que le rendu des pages Web est effectué côté client et non côté serveur, ce qui impacte directement les performances d'affichage d'une page Web selon la machine du client voulant la consulter. Il n'était pas utile de mettre en place un mode de rendu SSR dans le cadre de ce projet, car cela aurait nui aux performances du serveur qui aurait alors dû gérer le rendu des pages.

Il était plus intéressant de laisser le rendu des pages Web au client plutôt qu'au serveur dans le cadre de ce projet.

#### Hébergement

Nous avons choisi d'héberger l'application sur des serveurs dédiés internes à Simplon HDF. Cependant, à l'heure actuelle, nous nous sommes trompés, car l'application est hébergée sur des VPS.