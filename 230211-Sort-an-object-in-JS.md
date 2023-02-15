![sort qui tue](https://media.giphy.com/media/xT5LMxGzbgJkUZjdte/giphy.gif)

# Donner un sort à un JS Object? o_O

## Un objet `Users` écrit en condensé

```js
const users = { toto: 12, tata: 15, titi: 4, tutu: 8 };
```

où on associe l'âge au nom de l'utilisateur

## Que tu veux ordonnancer du plus jeune au plus vieux

L'objet `users` à un ordre, il dépend de la séquence d'insertion des données dans l'objet.

```js
console.table(Object.entries(users));
```

On obtient:

| (index) | 0      | 1   |
| ------- | ------ | --- |
| 0       | 'toto' | 12  |
| 1       | 'tata' | 15  |
| 2       | 'titi' | 4   |
| 3       | 'tutu' | 8   |

## Avec un `sort` et un `reduce`

```js
const usersSorted = Object.entries(users)
  .sort(([, a], [, b]) => a - b)
  .reduce((a, v) => ({ ...a, [v[0]]: v[1] }), {});
```

## Tu obtiens le résultat voulu

```js
console.table(Object.entries(usersSorted));
```

On obtient :

| (index) | 0      | 1   |
| ------- | ------ | --- |
| 0       | 'titi' | 4   |
| 1       | 'tutu' | 8   |
| 2       | 'toto' | 12  |
| 3       | 'tata' | 15  |

## Mais le mieux reste l'utilisation d'un `Array`

Tu gagnes en lisibilité

```js
const usersArray = Object.entries(users).map(([name, age]) => ({ name, age }));
```

Et tu peux utiliser toute la puissance des tableaux

```js
const usersArraySorted = usersArray.sort((a, b) => a.age - b.age);
console.table(Object.entries(usersArraySorted));
```

On obtient :

| (index) | name   | age |
| ------- | ------ | --- |
| 0       | 'titi' | 4   |
| 1       | 'tutu' | 8   |
| 2       | 'toto' | 12  |
| 3       | 'tata' | 15  |
