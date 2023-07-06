# Gestion du projet

Avant de démarrer un projet, il est important de se poser les bonnes questions, telles que la façon dont le projet devra être géré, quels objectifs le projet se fixe, et bien d'autres questions auxquelles mon équipe a tenté d'apporter des réponses les plus adaptées possible.

## Méthodologie de travail

### SCRUM

Notre équipe a adopté une méthodologie de travail Agile avec la méthode SCRUM, qui permet d'améliorer la collaboration et la communication au sein de l'équipe de développement, notamment en impliquant chaque membre de l'équipe dans la prise de décision concernant le projet.

SCRUM est une méthodologie flexible qui permet de s'adapter aux changements de priorité du projet. En utilisant SCRUM, nous sommes capables de gérer les incertitudes et de répondre aux attentes du client.

Voici comment se constitue SCRUM :

![](../assets/illu/scrum.png)

#### Définition des rôles

GAMACHE Benjamin occupe le rôle de Product Owner, qui consiste notamment à prendre en charge les interactions entre l'équipe en charge du projet et le client.

BOUREZ Bastien occupe le rôle de Scrum Master, qui consiste à diriger les membres de l'équipe en charge du projet et à assigner des tâches à chacun.

PHILIPPE Nelson et LEROY Cédric occupent tous deux le rôle de Développeur, qui consiste à développer les différentes solutions élaborées par tous les membres de l'équipe en charge du projet et validées par le client.

### Jira

Pour nous organiser sur ce projet, mon équipe et moi-même avons choisi Jira, qui est une plateforme permettant d'organiser les différentes tâches d'un projet en les découpant en Epic, puis en User Story, et enfin en tâches.

## Versionnage

Le versionnage est un concept selon lequel il existe plusieurs versions d'un code. Par exemple, pour une application en version 1.0.0, on dit que la version du code est à sa première version majeure. Le chiffre du milieu représente les versions du code où celui-ci a subi des modifications mineures (MINOR), et enfin le troisième chiffre représente le nombre de versions "patch" du code.

Notons aussi que si une version mineure est publiée, les versions patch du code sont remises à 0 et la version mineure du code est incrémentée de 1. De même pour les versions majeures, si une version majeure est publiée, les versions mineures et patch sont remises à 0.

Grâce au versionnage, il est possible de structurer les différentes versions du code et d'apporter des informations claires et détaillées quant aux modifications que le code a subies.

### Git

Git est un outil permettant de versionner son code. Avec Git, il est possible d'écrire du code et de le séparer sur des branches, de revenir à des versions antérieures du code. Git permet aussi d'envoyer son code sur des plateformes en ligne comme BitBucket, GitLab, GitHub, ou de l'envoyer sur des plateformes de self-hosting pour héberger du code en ligne.

Cela permet la collaboration d'une équipe sur un projet.

### GitFlow

GitFlow est une extension de l'outil Git permettant de créer plus

facilement des branches Git. Par exemple, il apporte un module permettant de créer des branches nommées "Feature" qui permettent d'identifier les modifications apportées au code. Une branche de travail "feature" est une branche sur laquelle les modifications apportées au code sont liées à l'ajout de fonctionnalités.

### GitHub

GitHub est une plateforme en ligne qui sert d'outil collaboratif de versionnage de code. Elle permet d'héberger du code en ligne et de retrouver différentes versions du code. GitHub permet donc de partager son code avec une équipe restreinte (comme c'est le cas ici) ou de le partager de façon publique. Nous avons donc utilisé GitHub afin de travailler en équipe sur ce projet.

#### Mono Repository VS Multi Repository

Pour choisir la meilleure façon d'organiser le projet sur GitHub, nous nous sommes posé des questions sur la solution optimale entre le Mono Repository et le Multi Repository.

Le Mono Repository :

- Centralise toute la conception de l'application.
- Centralise tout le code de l'application.
- Mise en place de pipelines de déploiement (CI/CD) plus complexes.
- Centralisation de toutes les dépendances de l'application, qu'elles soient utiles à un module ou non.

Le Multi Repository :

- Décentralise la conception de l'application.
- Décentralise les sources de l'application.
- Mise en place de pipelines de déploiement (CI/CD) plus légères.
- Répartition des dépendances de chaque partie de l'application dans des dépôts séparés.

Nous avons adopté une approche mixte en hébergeant notre application avec 3 dépôts :

- 1 dépôt pour l'API et la base de données.
- 1 dépôt pour l'application Web (front-end).
- 1 dépôt pour tous les bots constituant l'application.

#### GitFlow VS Fork

Bien qu'il était initialement prévu de travailler en forkant le dépôt du projet, notre équipe est revenue sur sa décision quant à la méthodologie à adopter pour travailler avec GitHub, car elle ne convenait pas à tous les membres de l'équipe.

De plus, avec une petite équipe de 4 membres, le fork n'est pas une obligation. Nous pouvons tout à fait utiliser GitFlow en raison de la taille de l'équipe, créer des branches et les envoyer sur le dépôt distant.

Le fork est plus apprécié dans les projets Open-Source où la taille des équipes de développement n'est pas fixe, et dans lesquels les contributions sont émises par des collaborateurs qui ne sont pas à l'initiative du projet. Le fork permet une meilleure organisation dans les équipes de grande taille.

#### Convention de formatage des commits

Pour réaliser nos commits, notre équipe a adopté la convention "Angular Style Commits" qui permet de définir :

- Un type.
- Une portée (optionnelle).
- Une description.
- Un corps de commit (optionnel).
- Un footer de commit (optionnel).

Un commit rédigé selon le style Angular se présente la plupart du temps comme suit : "<type> (scope): [description]". Ce formatage des commits permet aux membres de l'équipe de développement de comprendre rapidement les modifications apportées au projet. C'est pourquoi notre équipe a opté pour cette convention dans le formatage de nos commits.

#### Critères des Pull Requests

Pour qu'une Pull Request

soit acceptée, nous avons mis en place des critères sur la branche de développement (develop). Ainsi, avant chaque fusion de branche vers develop, les modifications de la branche devaient être approuvées par un autre membre de l'équipe.

Chaque membre de l'équipe pouvait soumettre son travail aux autres et s'assurer que ses modifications étaient conformes aux objectifs du projet. Pour qu'une Pull Request soit acceptée, il fallait donc :

- Que les commits de cette Pull Request soient rédigés selon le style Angular.
- Que les commits soient rédigés en anglais.
- Que les commits soient suffisamment explicites pour comprendre les modifications apportées au projet par ce commit.
- Que les modifications apportées par la Pull Request soient approuvées par un ou plusieurs membres de l'équipe.

#### GitHub Actions

GitHub Actions est une fonctionnalité proposée par GitHub qui permet d'exécuter des actions à partir des dépôts. Par exemple, il est possible de mettre en place une pipeline CI/CD avec GitHub Actions en créant un script YAML sur le dépôt et en y exécutant les opérations souhaitées. Nous aborderons plus en détail GitHub Actions dans la section Déploiement de ce dossier.