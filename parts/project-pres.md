# Le client : Simplon

Dans ce projet, notre client était l'organisme de formation Simplon HDF (Hauts-de-France).
Simplon HDF compte 21 000 apprenants et 7 fabriques numériques.

La communication est également un enjeu majeur pour Simplon HDF, dont le principal support de communication est Discord, dans le cadre des communications entre les équipes et les apprenants.

## Contextualisation du projet : Discord Communautaire <a id="context"></a>

Dans le cadre de ce projet, nous avons mis l'accent sur la manière dont Simplon HDF communique. En tant qu'apprenants, nous avons remarqué une tendance de la part des équipes de Simplon HDF à répéter des actions qui pourraient être automatisées facilement. De plus, nous avons constaté que la communication notamment lorsqu'il s'agit de communiquer avec les apprenants, était fastidieuse.

C'est pourquoi mon équipe a réfléchi à des solutions afin de remédier à ces problèmes.

Aussi, notre équipe a discuter avec les membres des équipes Simplon afin de recueillir les problèmatiques rencontrées par ces derniers : 

## Recueil du besoin client <a id='client'></a>

Pour recueillir les besoins du client, notre équipe a d'abord discuté avec les différents membres des équipes Simplon.
Suite à ces discussions, nous avons été en mesure d'établir une liste des problèmes les plus fréquemment rencontrés par les membres des équipes Simplon.

<table>
    <tr>
        <td>Problématiques</td>
        <td>Problèmes</td>
    </tr>
    <tr>
        <td rowspan="4">Utilisation inappropriée de Discord dans un cadre professionnel</td>
        <td>Multiplicité des supports de communication</td>
    </tr>
    <tr>
        <td>Mauvaise identification lors des interactions</td>
    </tr>
    <tr>
        <td>Actions répétitives du personnel</td>
    </tr>
    <tr>
        <td>Manque d'ergonomie de Discord</td>
    </tr>
    <tr>
        <td rowspan="4">Communication inefficace</td>
        <td>Multiplicité des messages inutiles (FLOOD)</td>
    </tr>
    <tr>
        <td>Perte de contact avec les anciens apprenants</td>
    </tr>
    <tr>
        <td>Pas de mentorat</td>
    </tr>
    <tr>
        <td>Problème de sourcing</td>
    </tr>
</table>

### Utilisation inappropriée de Discord dans un cadre professionnel

#### Multiplicité des supports de communication

Concernant ce problème, nos équipes ont compris que pour les membres de Simplon, il existe une multitude de serveurs Discord permettant de discuter avec différentes entités.
Il y a notamment 12 serveurs Discord sur une période d'un an et demi pour un formateur, en ne comptant que les serveurs réservés aux promotions concernant ce formateur et non les serveurs nécessaires au formateur pour discuter avec les membres des équipes Simplon.

#### Mauvaise identification lors des interactions

Discord met nativement en place un système de pseudonymes, ce qui n'est pas adapté à une utilisation professionnelle, où les membres d'une organisation ont besoin d'être identifiables. Cela peut entraîner des complications concernant l'identification des utilisateurs avec lesquels nous sommes amenés à discuter via Discord.

#### Actions répétitives du personnel

Il a également été remarqué que les membres des équipes Simplon, notamment les formateurs, effectuent un nombre considérable d'actions répétitives.
Par exemple, lors du démarrage d'une nouvelle promotion chez Simplon HDF, voici ce qu'un formateur doit faire pour permettre aux apprenants de discuter entre eux :

![](../imgs/scenario-crea-promo.png)

Et cela doit être répété pour chaque nouvelle promotion dont le formateur a la charge.

#### Manque d'ergonomie de Discord

Les membres des équipes nous ont avoué ne pas se sentir très à l'aise avec l'utilisation de Discord, notamment dans un contexte professionnel. En effet, son utilisation présente des lacunes ergonomiques.

### Communication inefficace

#### Multiplicité des messages inutiles

Il a également été remarqué une tendance chez les apprenants à envoyer des messages de rappel aux membres du staff dans des scénarios où ces derniers

n'ont pas reçu de réponse à leurs sollicitations. Cela peut sembler anodin, mais cela entraîne des messages inutiles ainsi que des distractions pour les membres des équipes.

#### Perte de contact avec les anciens apprenants

Certains membres des équipes Simplon nous ont interpellés quant à la perte de contact avec les anciens apprenants. En effet, dans la configuration actuelle de l'organisme de formation, il n'existe pas de réelle solution permettant de garder le contact avec les anciens apprenants. Une fois leur formation terminée, ils quittent le serveur Discord attribué à leur promotion, ce qui le rend inutilisé.

#### Problème de sourcing

Les membres ont également signalé des problèmes de sourcing. Selon eux, il est relativement compliqué de remplir les promotions avec des profils correspondant aux critères de ces promotions.

## L'équipe en charge du projet <a id="team"></a>

**BOURREZ Bastien** Aka le pro Discord

**PHILIPPE Nelson** Aka l'aventurier

**LEROY Cédric** Aka l'encyclopédie / Redacteur en chef

**GAMACHE Benjamin** Aka moi même

## Proposition de solution : Discord VS Application From Scratch

Notre équipe s'est alors intérroger quant à la meilleure solution entre utilisé Discord qui d'un côté

- Est déjà utilisé par la majorité des membres des équipes
- Est utilisé par la majorité des apprennants
- Est gratuit à l'utilisation
- Est déjà un support de communication stable
- Est maléable par tout type d'équipe de développement

Ou refaire une application From Scratch spécialement dédié à Simplon

- Doit être imposé à tous les membres des équipes
- Doit être imposé à tous les apprennants
- Ajoute un support de communication à tous les utilisateurs
- Coute un certains prix en terme de graphisme
- Représente un grand cout en terme de serveur d'hebergement
- Nécessite des connaissances avancées dans certains langages lourds

C'est pour toutes ces raisons que nous avons choisi d'utiliser Discord plutôt que de repartir d'une application From Scratch