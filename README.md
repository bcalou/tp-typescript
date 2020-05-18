# TP TypeScript

## Installation

```
npm install
```

## Developement

```
npm run serve
```

## Exercices

Votre alliée : [Documentation de TypeScript](https://www.typescriptlang.org/docs/home.html)

### 1. Fonction d'addition

Voici une fonction retournant la somme de deux nombres.

```
function sum(a, b) {
  return a + b;
}
```

Ajoutez les informations de type nécessaires pour convertir cette fonction en TypeScript :

- le type du premier paramètre
- le type du second paramètre
- le type de retour de la fonction

### 2. Fonction de présentation

Voici une fonction qui met en majuscule le nom d'un étudiant, puis l'imprime.

```
function printStudentName(name) {
  const formattedName = name.toUpperCase();
  console.log(`L'étudiant s'appelle ${formattedName});
}
```

Ajoutez les informations de type nécessaires pour convertir cette fonction en TypeScript :

- le type du paramètre `name`
- le type de retour de la fonction (un type existe pour les fonctions ne retournant rien)
- le type de la constante `formattedName`

### 3. Fonction de listing

Voici une fonction qui prend en paramètre un tableau d'éléments textuels, les range par ordre alphabétique et les imprime un par un.

```
function printAlphabetically(items) {
  const sortedItems = items.sort();
  sortedItems.forEach(item => console.log(item));
}
```

Ajoutez les informations de type nécessaires pour convertir cette fonction en TypeScript :

- le type du paramètre `items` (un tableau, mais un tableau de quoi ?)
- le type de retour de la fonction
- le type de la constante `sortedItems`

### 4.1 Les objets

Voici une fonction qui prend en paramètre un objet représentant un étudiant et imprime ses informations.

```
function printStudent(student) {
  console.log(`L'étudiant(e) s'appelle ${student.firstName} ${student.lastName}`);
  console.log(`Il/elle a ${student.age} ans`);

  if (student.graduated) {
    console.log(`Il/elle a son diplôme !`);
  }
}
```

Ajoutez les informations de type nécessaires pour convertir cette fonction en TypeScript :

- le type du paramètre `student` (comment représenter un paramètre qui contient plusieurs clés possédant chacune un type ?)
- le type de retour de la fonction

### 4.2 Les interfaces

Il n'est pas très pratique de déclarer le type d'un objet dans la fonction elle même. On peut utiliser les interfaces TypeScript.

Voici par exemple une interface qui représente une chanson et ses propriétés :

```
interface Song {
  artist: string;
  title: string;
  duration: number;
  favorite: boolean;
}
```

En reprenant l'exercice précédent, écrivez une interface `Student` et utilisez-là pour typer la fonction `printStudent`.

### 5. Classes

Voici une classe `ES6` classique représentant un objet `Party`.

```
class Party {
  constructor(name, author) {
    this.name = name;
    this.author = author;
    this.items = [];
  }

  getPartyDescription() {
    return `${this.name} - Proposé par ${this.author}`;
  }

  addItem(item) {
    this.items.push(item);
  }
}
```

On pourrait l'utiliser de cette façon :

```
const party = new Party("Pot de départ", "Patrick");

party.getPartyDescription();
party.addItem('champagne');
party.addItem('caviar');
party.addItem('toasts');
```

Ré-écrivez cette classe à l'aide de TypeScript pour :

- Typer les deux paramètres du constructeur
- Supprimer les trois lignes à l'intérieur du constructeur
- Typer les paramètres et les retours des deux fonctions

Le code d'utilisation doit fonctionner à l'identique, mais vous pouvez maintenant préciser le type de l'objet créé :

```
const party: Party = new Party('Pot de départ', 'Patrick');
```
