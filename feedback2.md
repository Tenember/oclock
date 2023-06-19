# Feedback - Projet de l'Élève 2

## Commentaires généraux

Bravo pour vos efforts dans la réalisation de ce projet ! Vous avez réussi à implémenter la majeure partie des fonctionnalités demandées, ce qui est une réalisation encourageante. Cependant, il y a quelques points sur lesquels vous pouvez vous concentrer pour améliorer votre code et renforcer vos compétences en développement.

Tout d'abord, prenez le temps d'examiner attentivement les instructions fournies et de vous assurer que vous comprenez bien les exigences du projet avant de commencer à coder. Cela vous permettra d'avoir une vision claire de ce qui est attendu et de prendre les bonnes décisions tout au long de votre développement.

Lorsque vous écrivez du code, assurez-vous d'utiliser des noms de fonctions, de variables et de commentaires explicites afin que le code soit facilement compréhensible pour les autres développeurs et pour vous-même à l'avenir. La clarté et la lisibilité du code sont essentielles pour une maintenance et une évolution plus fluides.

N'oubliez pas de gérer les erreurs de manière appropriée en utilisant des blocs try-catch pour capturer les exceptions. Cependant, essayez d'éviter de révéler des informations sensibles dans les messages d'erreur renvoyés aux utilisateurs. Optez plutôt pour des messages d'erreur génériques qui ne divulguent pas de détails internes sur le fonctionnement de votre application.

Pour vous améliorer davantage, je vous recommande de consulter régulièrement la documentation des bibliothèques et des outils que vous utilisez, ainsi que de pratiquer régulièrement en résolvant des exercices de programmation. Cela vous aidera à approfondir vos connaissances et à renforcer votre maîtrise du développement.

Continuez à travailler avec persévérance et passion, en cherchant toujours à vous améliorer. Vous avez déjà fait un bon début et je suis convaincu que vous pouvez atteindre de meilleurs résultats à l'avenir. Bonne chance pour vos futurs projets !

## Étape 1 : Détail d'une carte
### dataMapper.js

Votre code fonctionne correctement et remplit l'objectif de récupérer les détails d'une carte à partir de son identifiant et de les afficher dans la vue.

Quelques pistes d'amélioration :

1. Nommage cohérent des fonctions : Dans votre code, la fonction est nommée item. Il est préférable d'utiliser des noms de fonctions explicites et descriptifs pour améliorer la lisibilité et la compréhension du code, `cardDetails` par exemple.
2. Commentaires : Ajouter des commentaires dans votre code peut aider à clarifier l'intention et le fonctionnement de certaines parties du code, en particulier pour les sections plus complexes. Cela facilitera également la lecture et la maintenance du code à l'avenir.
3. Gestion des erreurs : Si l'utilisateur essaie d'afficher une carte avec un id inexistant, suite à un bug ou en forcant par l'url du navigateur, une erreur s'affiche. Il suffirait de renvoyait une erreur 404 après avoir testé si l'object card existe bien pour prévenir cela.

## Étape 2 : Recherche

Votre code fonctionne et la recherche affiche bien le résultat des cartes par élément.

Quelques pistes d'amélioration :

1. Vous récupérez toutes les cartes contenant des éléments lors de la requête SQL, puis vous filtrer celles qu vous intéressent en javascript. Ça fonctionne oui, mais si il y avait 10 millions de cartes ? Il est préférable d'optimiser la quantitée de donées que l'on doit traiter avant d'optimiser le code javascript, c'est potentielement des dizaines de seconde gagnées contre des millisecondes. Vous auriez donc pu filtrer au niveau de la requête SQL en passant en paramêtre votre élément au `dataMapper.js`.

## Étape 3 : Construire un deck

L'ajout de carte au Deck fonctionne, cependant des erreurs visuels en front s'affichent, plus de 5 carte sont ajoutables et les cartes ne sont pas supprimables. Si tu as manqué de temps, ce n'est pas grave, pense à regarder la correction pour voir comment faire, au vu de ton code précédent, tu serais capable de faire cette partie en essayant.

## Bonus: finir les recherches
