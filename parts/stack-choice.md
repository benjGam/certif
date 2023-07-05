# Choix de la solution de base

Notre équipe à décidé d'utiliser Discord comme support de communication de base pour plusieurs raisons.

## Le délai

Dans un délai aussi court (d'environ 6 mois) il était inconçevable qu'une équipe de 4 apprenants, peu importe leur niveau technique puisse réaliser une application depuis 0 qui prendrait en considération les problèmes rencontrés au sein des équipes Simplon.

## La multiplicité des outils

En effet, comment endiguer la multiplicité des outils en en créeant un nouveau, bien qu'il aurait été généralisé et que tous les acteurs Simplon s'y soient intéressé, il restait que créer une application de 0 et l'imposer aux équipes n'aurait pas été une mince afffaire.

Avec Discord, la majorité des membres des équipes Simplon n'ont pas à réinstaller un nouvel outil puis-ce que chaque membre l'utilise déjà

## Le coût

Les solutions possibles avec Discord serait de moindre cout, tant en terme d'hebergement qu'en terme de développement pur.

Pour toutes ces raisons, Discord semblait être un bien meilleur support de communication que de repartir d'une application de 0 qui n'aurait de toutes façons pas vu le jour dans les délais imposés.

# Identification des technlogies à utiliser

Nous avons réalisés des études quant aux technologies adaptée à ce projet, nous avons donc établis des Benchmarks

| Question  | Réponse  |
|---|---|
| Machine Learning  | Non |
| Architecture | API |
| Asynchrone  | Oui |
| SEO | Non |
| Rendu | SSR |
| Hébergement | Serveur Perso |
| Environnement | NodeJS |
| Langage | Typescript |
| Framework Back End | NestJS |
| Framework Front End | AngularJS |
| BDD | PostregreSQL (SQL Relationnelle) |
| ORM | Prisma |

Ce Benchmark à été basé sur 3 autres Benchmarks.

Notez que plus les points attribués aux technlogies des Benchmarks sont elevés, plus la technologie est encensé.

## Analyse du Framework Back End

0 = Moins Intéressant
4 = Plus Intéressant

| Critères                 | Koa     | Fastify | Nest    | Adonis  |
| ------------------------ | ------- | ------- | ------- | ------- |
| Personnalisation         | 1       | 1       | 4       | 1       |
| Rapidité                 | 3       | 4       | 4       | 2       |
| Popularité               | 3       | 2       | 4       | 1       |
| Maturité                 | 4       | 2       | 1       | 3       |
| Releases                 | 1       | 4       | 2       | 3       |
| Bonnes pratiques         | 1       | 1       | 4       | 1       |
| Stars Github             | 3       | 2       | 4       | 1       |
| Equipe Développement     | 1       | 4       | 2       | 2       |
| Communauté Github        | 2       | 2       | 3       | 1       |
| Communauté StackOverflow | 2       | 2       | 4       | 1       |
| Documentation            | 1       | 2       | 4       | 4       |
| Magie                    | 1       | 1       | 1       | 1       |
| Mariage librairies       | 4       | 4       | 4       | 1       |
| Prise Politique          | 4       | 4       | 1       | 4       |
| License                  | MIT     | MIT     | MIT     | MIT     |
| Total                    | 31      | 35      | 42      | 26      |

## Analyse du Framework Front End

0 = Moins Intéressant
1  

| Critères                 | ReactJS | Angular | Vue.js  |
| ------------------------ | ------- | ------- | ------- |
| Personnalisation         | 3       | 1       | 2       | 
| Rapidité                 | 2       | 2       | 3       |
| Popularité               | 3       | 2       | 1       |
| Maturité                 | 2       | 2       | 2       |
| Releases                 | 1       | 3       | 2       |
| Bonnes pratiques         | 2       | 3       | 3       |
| Stars Github             | 3       | 2       | 3       | 
| Equipe Développement     | 3       | 2       | 1       |
| Communauté Github        | 2       | 2       | 1       |
| Communauté StackOverflow | 2       | 3       | 1       |
| Qualité Documentation    | 2       | 3       | 2       |
| Côté Magique             | 3       | 3       | 3       |
| Mariage librairies       | 1       | 1       | 1       |
| Prise Politique          | 0       | 1       | 1       |
| License                  | MIT     | MIT     | MIT     |
| Total                    | 29      | 30      | 26      |

## Analyse de l'ORM (Object Relationnal Mapping)

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

Si on s'attarde sur le Benchmark de l'ORM on peut voir que TypeORM semblait être designé à la place de Prisma, cependant notre équipe à dû choisir la solution la plus adaptée au projet, et il apparaissait que pour une équipe aussi réduite que la notre et dans les délais imposé, TypeORM semblait être trop lourd pour être intégrer au projet de façon optimisée, c'est pourquoi malgré l'analyse des caractéristiques de ces ORM notre équipe à préféré utilisé Prisma plutôt que TypeORM.

## Choix du langage

Dans une équipe composé comme la notre et avec ces délais, il nous fallait un langage relativement simple à prendre en main par tous les membres de l'équipe, assez léger pour être mis en place coté serveur sans nécessité des coûts de machine trop elevés.

C'est pourquoi notre choix s'est orienté sur Typescript

### Typescript

Typescript est un langage plus robuste que Javascript, il s'agit d'un "super-set" ou "super-ensemble" de Javascript qui amène de nombreux conceptes que Javascript vanilla ne met pas en place, tel que la POO.

Dans un projet de cet envergure, il est absolument nécessaire de pouvoir utilisé la Programmation Orientée Objet, car si de l'exterieur, un bot peut sembler très basique, à l'intérieur, c'est une autre affaire, ce projet aurait pû être réalisé dans les délais avec du Javascript vanilla, cependant, la maintenabilité du code aurait été quasimenet impossible pour une équipe devant reprendre le projet.

C'est pour ces raisons que Typescript à été préféré à Javascript, en terme de périnité du projet, Javascript n'était pas le choix adapté.

## Choix de l'environnement d'éxecution

Bah.. NodeJS 

## Choix du Framework Back-End