# 003-cli

## Installez les dépendances
```
npm install
```

### Lancez le serveur
```
npm run serve
```

### SPEC

- Recuperer les users depuis `https://jsonplaceholder.typicode.com/users` au clic sur le bouton 

  **tips**
  ```js
  fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => response.json())
  .then(users => console.log(users))
  ```

- stockez les users dans les data

- affichez les users avec un seul block de code avec la directive  ` v-for `

- afficchez les champs name / email / company name / website

- créez un lien hyper vers le website

- ajoutez une image avatar au users grace au placeholder suivant 
  `https://i.pravatar.cc/150?u=uniqueKey`

**15min** 

### BONUS

- entre le clic et l'affichage des users affichez un état de chargement, `Chargement en cours...`

- mettre la methode de fetch en async/await, c'est pas du Vue mais plus du ES moderne.
