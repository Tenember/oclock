# Feedback - Projet de l'Élève 1

## Étape 1 : Détail d'une carte
### dataMapper.js

Votre méthode `getOneCard` dans le fichier `dataMapper.js` fonctionne correctement et renvoie les informations d'une carte en fonction de son identifiant. Cependant, je vous recommande d'ajouter une gestion du cas où aucune carte n'est trouvée pour l'identifiant donné. Vous pouvez ajouter une clause `else` pour renvoyer un message d'erreur approprié.

```javascript
getOneCard: async (id) => {
  const query = `
    SELECT *
    FROM "card"
    WHERE "id" = $1
  `;
  const result = await database.query(query, [id]);
  if (result.rowCount === 1) {
    return result.rows[0];
  } else {
    throw new Error("La carte correspondant à cet identifiant n'a pas été trouvée.");
  }
},
```

## Étape 2 : Recherche

Il est préférable de commenter ou supprimer le code inutilisé ou en commentaire pour maintenir une base de code propre et compréhensible. Vous pouvez supprimer les lignes de code commentées qui ne sont pas utilisées dans les méthodes searchByElement, searchByValues et searchByName.

Assurez-vous de déclarer les variables searchedResults avec let ou const avant de les utiliser dans les méthodes searchByElement, searchByValues et searchByName. Par exemple, remplacez `searchedResults = await dataMapper.searchByElement(searchedElement);` par `const searchedResults = await dataMapper.searchByElement(searchedElement);`.

Dans la méthode `searchByElement`, vérifiez si `searchedElement` est égal à `'null'` en utilisant une condition correcte. Actuellement, vous avez `searchedElement === 'null' ? ' sans élément' : + searchedElement`, qui ajoute un + avant searchedElement lorsqu'il n'est pas égal à `'null'`. Pour obtenir la condition correcte, vous pouvez utiliser `searchedElement === 'null' ? ' sans élément' : searchedElement`.

Assurez-vous de déclarer la variable `searchedResults` avec `let` ou `const` dans la méthode `searchByValues` avant la condition if. Par exemple, remplacez `let searchedResults = [];` par `const searchedResults = [];`.

Dans la méthode `searchByName`, assurez-vous de déclarer la variable `searchedResults` avec `let` ou `const` avant de l'utiliser. Par exemple, remplacez `searchedResults = await dataMapper.searchByName(name);` par `const searchedResults = await dataMapper.searchByName(name);`.

Pour éviter des problèmes potentiels, il est recommandé de déclarer toutes les variables (searchedResults) avec `const` ou `le`t et de ne pas les utiliser directement sans les déclarer.

Assurez-vous de gérer correctement les erreurs lors de l'appel à `dataMapper` en utilisant des blocs `try...catch`. Cependant, il serait préférable de fournir un message d'erreur plus informatif à l'utilisateur plutôt que simplement `An error occured.` Vous pouvez personnaliser le message d'erreur pour donner plus de détails sur la nature de l'erreur.

## Étape 3 : Construire un deck

Globalement, le code semble bien implémenté et répond aux exigences de l'étape 3. Attention tout de même au code commenté inutilisé.

## Bonus: finir les recherches

Félicitations pour avoir implémenté toutes les méthodes dans le fichier searchController.js ! Vous avez fait un excellent travail en allant au-delà des attentes et en ajoutant des fonctionnalités supplémentaires. Votre motivation et votre volonté d'approfondir vos connaissances sont remarquables.

Je tiens à souligner l'importance de l'exploration et de l'expérimentation dans le domaine du développement logiciel. En explorant au-delà des exigences initiales, vous avez pu approfondir votre compréhension du code et acquérir une expérience pratique précieuse.

Je vous encourage vivement à continuer d'explorer et d'expérimenter avec d'autres fonctionnalités ou améliorations potentielles. Cela vous permettra de perfectionner vos compétences et d'élargir votre expertise. Vous avez fait preuve d'une grande initiative et d'un excellent travail. Continuez ainsi !

## Commentaires généraux

Félicitations pour votre projet ! Vous avez montré une bonne compréhension du sujet et avez suivi une approche méthodique pour résoudre les problèmes. Votre code est globalement bien structuré et lisible, ce qui facilite la compréhension. Cependant, poussez plus loin sur les quelques points à améliorer pour rendre votre code plus clair et efficace et vous irez loin.