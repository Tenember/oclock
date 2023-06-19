# Explication avancée de la notion de Fetch (méthode JavaScript)

Le concept de Fetch en JavaScript est une fonctionnalité qui permet de réaliser des requêtes HTTP asynchrones vers des serveurs, afin d'échanger des données entre le client (le navigateur) et le serveur. Fetch est une méthode moderne et puissante pour effectuer des requêtes AJAX (Asynchronous JavaScript and XML) et récupérer des données depuis des API ou des ressources distantes.

## Aspect théorique de Fetch

Fetch utilise les promesses, introduites en JavaScript ES6, pour gérer les requêtes et les réponses de manière asynchrone. Une promesse représente une valeur future qui peut être disponible maintenant, dans le futur ou jamais. Elle peut être en attente (pending), résolue (fulfilled) avec une valeur, ou rejetée (rejected) avec une raison.

La syntaxe de base d'une requête Fetch est la suivante :

```javascript
fetch(url, options)
  .then(response => {
    // Gérer la réponse
  })
  .catch(error => {
    // Gérer les erreurs
  });
```

- `url` : l'URL de la ressource que vous souhaitez récupérer ou vers laquelle vous souhaitez envoyer des données.
- `options` (facultatif) : un objet contenant des options supplémentaires pour configurer la requête, telles que la méthode HTTP, les en-têtes, le corps de la requête, etc.

La fonction Fetch renvoie une promesse qui se résout avec un objet \`Response\` représentant la réponse de la requête. Vous pouvez ensuite utiliser les méthodes de l'objet Response pour extraire les données de la réponse.

## Exemple pratique de Fetch

Voici un exemple pratique de l'utilisation de Fetch avec le DataMapper que tu as fourni :

```javascript
// Importer le module 'node-fetch' pour pouvoir utiliser Fetch dans Node.js
const fetch = require('node-fetch');

// Définir une fonction asynchrone pour effectuer une requête Fetch
async function fetchCardData(cardId) {
  try {
    const response = await fetch(`http://localhost:3000/card/${cardId}`);
    if (response.ok) {
      const cardData = await response.json();
      console.log(cardData);
    } else {
      throw new Error('Erreur lors de la récupération des données de la carte');
    }
  } catch (error) {
    console.error(error);
  }
}

// Appeler la fonction pour récupérer les données d'une carte spécifique
fetchCardData(1);
```

Dans cet exemple, nous utilisons Fetch pour effectuer une requête GET vers l'URL 'http://localhost:3000/card/${cardId}' afin de récupérer les données d'une carte spécifique. Nous passons l'ID de la carte en tant que paramètre dans l'URL de la requête.

Nous utilisons l'instruction `await` pour attendre la résolution de la promesse retournée par `fetch()`. Ensuite, nous vérifions si la réponse est valide (`response.ok` renvoie `true` si le code de statut HTTP est compris entre 200 et 299) et nous utilisons la méthode `json()` pour extraire les données de la réponse sous forme d'objet JavaScript.

Si la requête échoue ou si une erreur se produit, nous capturons l'erreur avec `try/catch` et l'affichons dans la console.

N'oublie pas d'installer le module 'node-fetch' en exécutant la commande suivante dans ton projet Node.js : `npm install node-fetch`.

Voilà ! Cet exemple te montre comment utiliser Fetch pour récupérer des données de cartes spécifiques dans ton projet en utilisant le DataMapper que tu as développé.

N'hésite pas à adapter cet exemple en fonction de tes besoins et à explorer davantage les fonctionnalités de Fetch pour tirer le meilleur parti de cette méthode JavaScript puissante.
