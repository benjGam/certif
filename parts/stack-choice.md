# Identification des technlogies à utiliser

Nous avons réalisés des études quant aux technologies adaptée à ce projet, nous avons donc établis des Benchmarks

## Choix du langage

Dans une équipe composé comme la notre et avec ces délais, il nous fallait un langage relativement simple à prendre en main par tous les membres de l'équipe, assez léger pour être mis en place coté serveur sans nécessité des coûts de machine trop elevés.

C'est pourquoi notre choix s'est orienté sur Typescript

### Typescript

Typescript est un langage plus robuste que Javascript, il s'agit d'un "super-set" ou "super-ensemble" de Javascript qui amène de nombreux conceptes que Javascript vanilla ne met pas en place, tel que la POO.

Dans un projet de cet envergure, il est absolument nécessaire de pouvoir utiliser la Programmation Orientée Objet, car si de l'exterieur, un bot peut sembler très basique, à l'intérieur, c'est une autre affaire, ce projet aurait pû être réalisé dans les délais avec du Javascript vanilla, cependant, la maintenabilité du code aurait été quasimenet impossible pour une équipe devant reprendre le projet.

C'est pour ces raisons que Typescript à été préféré à Javascript, en terme de périnité du projet, Javascript n'était pas le choix adapté.

## Analyse du Framework Back End

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
| Documentation            | 0       | 1       | 2       | 2       |
| Magie                    | 0       | 0       | 0       | 0       |
| Mariage librairies       | 2       | 2       | 2       | 0       |
| Prise Politique          | 2       | 2       | 0       | 2       |
| License                  | MIT     | MIT     | MIT     | MIT     |
| Total                    | 11      | 16      | 19      | 8       |

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

Si on s'attarde sur le Benchmark de l'ORM on peut voir que TypeORM semblait être designé à la place de Prisma, cependant notre équipe à dû choisir la solution la plus adaptée au projet, et il apparaissait que pour une équipe aussi réduite que la notre et dans les délais imposé, TypeORM semblait être trop lourd pour être intégrer au projet de façon optimisée, c'est pourquoi malgré l'analyse des caractéristiques de ces ORM notre équipe à préféré utilisé Prisma plutôt que TypeORM.

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
