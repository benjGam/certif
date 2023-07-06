# Spécifications fonctionnelles

## Règles de gestion <a id='gestion-rules'></a>

Les règles de gestion sont une suite de règles que les membres d'une équipe définissent pour répartir les possibilités et les devoirs des entités constituant un système. Suite au recueil des besoins du client, notre équipe a établi les règles de gestion du projet.

- Le bot doit disposer d'un système de configuration.
  - Le bot doit avoir une commande de génération d'embed (dans un canal) pour l'ajout des membres du staff.
    - L'embed doit disposer d'une liste déroulante permettant de sélectionner le rôle et de générer un lien d'invitation.
  - Le bot doit avoir une commande de génération d'embed (dans un canal) pour la création d'un nouveau type de formation.
    - L'embed doit disposer d'un bouton permettant d'envoyer une demande de nom pour le nouveau type de formation.
- Le bot doit avoir une commande de génération d'embed (dans un canal) pour l'ajout de formations.
  - L'embed doit disposer d'une liste déroulante permettant la sélection du type de formation.
    - Une demande doit être envoyée pour demander de compléter le nom de la formation.
    - Un nouvel embed doit être envoyé avec un bouton permettant de créer une nouvelle formation.
    - Le bot doit envoyer un message demandant la date de début et de fin de la formation.
- Le bot doit avoir une commande de génération d'embed (dans un canal) pour l'ajout d'apprenants à une formation.
  - L'embed doit disposer d'une liste déroulante permettant de générer un lien d'invitation pour un nouvel apprenant, pour une formation spécifique.
    - Le lien d'invitation doit être valide pour une seule personne.
- Le bot doit avoir une commande de génération d'embed (dans un canal) pour l'ajout de nouveaux utilisateurs déjà présents sur le serveur Discord, à une formation.
  - L'embed doit disposer d'une liste déroulante permettant de sélectionner une formation spécifique.
    - Lors de la sélection de la formation, un nouvel embed doit être envoyé, avec un bouton permettant d'afficher un formulaire d'ajout d'utilisateur.
- Le bot doit avoir une commande de génération d'embed (dans un canal) pour l'ajout ou la modification de modèles de catégories de formation.
  - Une catégorie de formation est un ensemble de canaux dédiés à une formation.
  - Lors de la création d'une formation, le bot doit générer un embed de configuration dans un canal propre à sa catégorie.
- Le lien d'invitation généré par le bot ne doit fonctionner que pour une personne.
- Le lien d'invitation doit être temporaire.
- Le bot ne doit pas pouvoir créer deux fois le même embed de configuration.
- Le bot doit pouvoir détecter si un embed a été supprimé pour permettre la création d'un nouveau.
- L'administrateur peut supprimer un embed.

- Lors de l'ajout d'un utilisateur à une formation, le bot doit envoyer une demande de vérification (dans un canal dédié à cette formation).
- Le bot doit exiger une identification lors de l'arrivée d'un nouvel apprenant ou d'un nouveau membre du staff.
  - Lors de l'arrivée d'un nouvel apprenant, le bot doit envoyer un message de demande de vérification (dans un canal dédié à cette formation).
  - Lors de l'arrivée d'un nouveau membre du staff, le bot doit envoyer un message de demande de vérification (dans un canal dédié au staff).
    - Une fois l'identité vérifiée, le rôle doit être attribué par le bot à l'utilisateur du lien.
- Le bot doit mettre en place un embed (dans un canal) permettant de sélectionner les formations visibles pour le staff.