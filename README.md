# Exercicis de Fonaments de JavaScript

Aquest repositori conté diferents exercicis per a practicar els fonaments de JavaScript. Cada exercici es troba en una carpeta diferent dins de la carpeta `/src`.

## Requisits

Aquest entorn es basa en el "boilerplate" que vam fer servir per l'anterior pràctica.Pots utilitzar NodeJS per veure el resultat dels teus exercicis o fer-ho a través del navegador.

## Instruccions

1. Clona aquest repositori a la teva màquina.
2. Executa `npm install` per instal·lar les dependències.
3. Si vols fer ús de NodeJS per executar el teu codi:
   3.1 Navega fins a la carpeta de l'exercici que vulguis executar.
   3.2. Executa el fitxer que hagis fet `exercici.js` amb Node.js per a veure el resultat de l'exercici.

### Exercici 1: Mode modern - "use strict"

Durant molt de temps, JavaScript va evolucionar sense tenir problemes de compatibilitat. Es van afegir noves característiques sense que la funcionalitat canviés. L'any 2015, amb la "famosa" versió del llenguatge ECMAScript 2015 o ES6, es van introduir moltes millores i canvis i van modificar algunes d'existents. Per garantir la retrocompatibilitat, gran part d'aquestes millores no s'apliquen automàticament. Per a poder utilitzar-les, cal indicar a l'intèrpret que volem utilitzar el mode modern. Per això, s'ha d'afegir la següent línia al principi del fitxer: `'use strict';`.

Busca com està afectant 'use strict' en cada cas:

#### Exemple 1

```javascript
function myFunction() {
  'use strict';
  x = 3.14;
  return x * 2;
}
```

#### Exemple 2

```javascript
function myFunction() {
  'use strict';
  let x = 3.14;
  delete x;
  return x * 2;
}
```

### Exercici 2: Treballant amb variables

Podem declarar variables per emmagatzemar dades utilitzant les paraules clau **var, let, const**.

- `let`: És la forma moderna de declaració de variable.
- `var`: És la declaració "old-school". Normalment, no s'utilitza gaire avui en dia però la podem trobar en codi antic.
- `const`: És com let, però el valor de la variable no pot ser alterat.

Ja sabem prou com funcionen però està bé que coneguem algunes bones pràctiques. Fes un cop d'ull al següent recurs: https://es.javascript.info/variables i digues si la segÜent manera de declarar variables és correcta o no:

```javascript
let message;
const COLOR_RED = "#F00";
const pageLoadTime = /* el temps que ha trigat a carregar la pàgina */
const myBirthday = '18.04.1982';
let 1a;
let user = 'John', age = 25, message = 'Hola';
let my-name;
var mensaje = 'Hola';
const BIRTHDAY = '18.04.1982';
let num = 5;
```

### Exercici 3: Conversions de Tipus

Ara ja coneixem els diferents tipus de dades que podem utilitzar a JS. Tenim un total de 8 tipus bàsics:

**7 tipus de dades primitius**:

- **number** per a números de qualsevol tipus: enteros o de punt flotant, els enters estan limitats per ±(253-1).
- **bigint** per a números enters de longitud arbitrària.
- **string** per a cadenes. Una cadena pot tenir zero o més caràcters, no hi ha un tipus especial per a un únic caràcter.
- **boolean** per a vertader i fals: true/false.
- **null** per a valors desconeguts – un tipus independent que té un sol valor nul: null.
- **undefined** per a valors no assignats – un tipus independent que té un únic valor "indefinit": undefined.
- **symbol** per a identificadors únics.

**1 un tipus de dada no primitiu**

- **object** per a estructures de dades complexes.

L'operador `typeof` ens permet veure quin tipus està emmagatzemat en una variable.

Hi ha dues formes: `typeof x` o `typeof(x)`. Retorna una cadena amb el nom del tipus. Per exemple, "string".

> 📌 Pel valor `null`, retorna "object": això és un error en el llenguatge, en realitat no és un objecte.

D'altra banda, la majoria de vegades, els operadors i funcions converteixen automàticament els valors que els passen al tipus correcte. Això ho anomenem "Conversió de tipus". Per exemple `alert` fa la conversió de qualssevol valor a string per mostrar-ho. O els operadors aritmètics converteixen els valors a números.

Ara bé, a vegades ens pot anar bé poder fer nosaltres mateixos la conversió. Fes un cop d'ull al següent recurs si ho necessites https://es.javascript.info/type-conversions i afegeix les conversions necessàries per realitzar els següents exercicis:

#### Exercici 3.1:

```javascript
// Codi inicial
let num1 = prompt('Introdueix el primer número:');
let num2 = prompt('Introdueix el segon número:');

let resultat = num1 + num2;

alert('El resultat de la suma és: ' + resultat);
```

#### Exercici 3.2:

Realitza un petit codi que demani a l'usuari un número i mostri a través d'un alert si l'usuari ha introud ït un número parell o senar.

```javascript
let entrada = prompt('Introdueix un número entre 1 i 100:');
//...
```

- Exercici 3.3:
  A vegades hi ha comportaments que no son del tot "lògics". Fes un cop d'ull als següents exemples, prova'ls i intenta extreure'n conclusions del funcionament de JS:

```javascript
let a, b, c, d;
a = '5' + 5;
b = 5 + '5';
c = '5' - 5;
d = '5' * '5';
```

```javascript
a = '15' > 5;
b = 5 > '15';
c = '15' > '5';
d = '5' > '15';
```

### Exercici 4: Condicionals - Ternaris

1. **Convertir IF a Ternari:**

   Transforma el següent codi d'ús de `if...else if` a una expressió ternària:

   ```javascript
   let hour = 12;
   let greeting;

   if (hour < 12) {
     greeting = 'Bon dia';
   } else if (hour < 18) {
     greeting = 'Bona tarda';
   } else {
     greeting = 'Bona nit';
   }
   ```

   La teva tasca és reescriure aquest codi utilitzant una expressió ternària i assignar el resultat a la variable `greeting`.

2. **Classificar el Número:**

   Tens un número `num` i vols assignar la cadena 'Positiu' si és positiu, 'Negatiu' si és negatiu, i 'Zero' si és igual a zero. Utilitza una expressió ternària per aconseguir-ho.

3. **Classificar l'Edat:**

   Donada una edat, vols assignar una etiqueta que indiqui si és un "Nen", "Adolescent" o "Adult". Utilitza una expressió ternària per aconseguir-ho.

> 📌 Operador Nullish Coalescing '??'
>
>     El resultat de l'expressió "a ?? b" és el següent:
>     - Si "a" està "definit", el resultat serà "a".
>      - Si "a" no està "definit", el resultat serà "b".
>
>      En altres paraules, l'operador "??" retorna el primer argument quan aquest no és null ni undefined. En cas contrari, retorna el segon argument. 
>      https://es.javascript.info/nullish-coalescing-operator

4. Suposem que tenim tres variables per guardar els nom, el cognom i el "nickname" d'un usuari. Ara bé, no estem segurs que tinguem tota aquesta informació. Només sabem que com a mínim en tenim una d'aquestes i que volem mostrar a alerta seguint la següent prioritat:
   nom --> cognom --> nickName --> 'anònim'
   Escriu el codi que ens ho soluciona fent ús de "??".

### Exercici 5: Funcions - Fonaments

#### Exercici 5.1

```javascript
function checkAge(age) {
  if (age > 18) {
    return true;
  } else {
    // ...
    return confirm('¿Tus padres te permitieron?');
  }
}
```

Funcionarà el codi si borrem `else`? Per què?

#### Exercici 5.2

```javascript
function checkAge(age) {
  if (age > 18) {
    return true;
  } else {
    return confirm('¿Tienes permiso de tus padres?');
  }
}
```

Escriu la funció de dalt, però aquest cop fent servir un operador `?`.
També ho podem fer fent servir l'operador `||`. Inclus més curt. Investiga com fer-ho.

#### Exercici 5.3 - Variables globals i locals

Declara una variable global anomenada MAX_PRICE i establix el seu valor a 10.

Defineix la funció calculaTotal. Dins de la funció, declara una variable local anomenada total i establix el seu valor com a preu \* quantitat.

Utilitza una declaració if per comprovar si el preu és menor o igual a MAX_PRICE. Si ho és, retorna el valor de total. Si no ho és, retorna un missatge d'error.

Prova la teva funció cridant-la amb diferents valors per al preu i la quantitat, i assegura't que retorni el resultat correcte o el missatge d'error.

### Exercici 6: Funcions - Arrow Functions

> 📌 Arrow Functions

**Variant sense Corxetes:** Les funcions de flecha sense corxetes són útils per a operacions senzilles. El seu format és el següent:

```javascript
(...arguments) => expressió;
```

En aquest cas, el costat dret de la fletxa (`=>`) és una expressió i la funció avalua aquesta expressió i en retorna el resultat. Si només hi ha un argument, pots omitir els parèntesis. Exemple:

```javascript
const duplica = (n) => n * 2;
console.log(duplica(5)); // Hauria de mostrar 10
```

**Variant amb Claus:**

      Les funcions de flecha amb claus són més adequades per a tasques que involucren més de una operació. El seu format és el següent:

```javascript
    (...arguments) => { bloc de codi }
```

En aquest cas, pots escriure diverses declaracions dins del bloc de codi i, si vols retornar un valor, cal que utilitzis la paraula clau `return`.Exemple:

```javascript
const sumaNombres = (nombres) => {
  let suma = 0;
  for (const nombre of nombres) {
    suma += nombre;
  }
  return suma;
};

console.log(sumaNombres([1, 2, 3, 4, 5])); // Hauria de mostrar 15
```

#### Passa aquestes funcions a **Arrow Functions**.

```javascript
// Function to arrow function
function multiply(a, b) {
  const result = a * b;
  return result;
}
```

```javascript
// Function to arrow function
function calculateTotal(price, quantity) {
  let total = price * quantity;

  if (price > 10) {
    total = total * 0.9;
  }

  return total;
}
```

```javascript
function outerFunction(a, b) {
  function innerFunction(c, d) {
    return c * d;
  }

  let result = innerFunction(a, b);
  return result + 10;
}
```

```javascript
function outerFunction(a, b) {
  function innerFunction(c, d) {
    return c * d;
  }

  let result = innerFunction(a, b);
  return result + 10;
}
```

```javascript
const numbers = [1, 2, 3, 4, 5];

// Callback function to arrow function
const doubledNumbers = numbers.map(function (number) {
  return number * 2;
});
```

Fes un cop d'ull al segúent codi. Què passa quan l'executes?

```javascript
const myObject = {
  name: 'John',
  sayHello: function () {
    console.log(`Hello, my name is ${this.name}`);
  },
  sayHelloWithTimeout: function () {
    setTimeout(function () => {
      console.log(`Hello, my name is ${this.name}`);
    }, 1000);
  },
};

myObject.sayHello();

myObject.sayHelloWithTimeout();
```

Canvia ara el mètode "sayHello" i la funció "setTimeout" per **Arrow Functions** i torna a executar el codi. Què passa ara? Intent esbrinar per què?

#### Com expliquem el que succeeix en cada cas?

### Exercici 7: Funcions - Mètodes d'Objectes per defecte

No t'has preguntat com es que podem aplicar mètodes a alguns primitius, per exemple str.toUpperCase()? Abans de començar a fer aquest exercici, pots fer un cop d'ull al recurs: https://es.javascript.info/object-methods, si vols entendre que s'amaga darrera d'aquest comportament.

A continuació executa els següents codis i entendre que fan en cada cas.

```javascript
const str = '42';
const num = Number(str);
console.log(num);

//--------------------------

const randomNum = Math.floor(Math.random() * 10) + 1;
console.log(randomNum);

//--------------------------

const obj = { name: 'John', age: 30 };
const jsonStr = JSON.stringify(obj);
console.log(jsonStr);

//--------------------------

const num = 42;
const str = String(num);
console.log(str);

//--------------------------

const now = new Date();
const dateStr = now.toLocaleDateString('ca-ES');
const timeStr = now.toLocaleTimeString('ca-ES');
console.log(dateStr);
console.log(timeStr);
```

### Exercici 8: Rest i operador Spread

Existeixen dos operadors que ens poden ajudar a treballar amb arrays i objectes. L'operador **Rest** i l'operador **Spread**.

L'operador**"Spread" o de propagació (...)** és una característica de JavaScript que **permet expandir una expressió en lloc on es requereixen múltiples arguments o elements**. Això pot ser útil per **passar arguments a una funció, crear noves arrays o objectes, o combinar múltiples arrays o objectes**.

#### Exemple 1: Passar arguments a una funció

```javascript
function sum(a, b, c) {
  return a + b + c;
}

const numbers = [1, 2, 3];

const result = sum(...numbers);

console.log(result); // Output: 6
```

#### Exemple 2: Crear una nova array

```javascript
const numbers1 = [1, 2, 3];
const numbers2 = [4, 5, 6];

const combinedNumbers = [...numbers1, ...numbers2];

console.log(combinedNumbers); // Output: [1, 2, 3, 4, 5, 6]
```

#### Exemple 3: Crear un nou objecte

```javascript
const person = { name: 'John', age: 30 };
const address = { city: 'Barcelona', country: 'Spain' };

const personWithAddress = { ...person, ...address };

console.log(personWithAddress); // Output: { name: 'John', age: 30, city: 'Barcelona', country: 'Spain' }
```

El **Rest Operator** en canvi ens **permet representar un nombre indefinit de paràmetres com un array**. Això pot ser útil per **passar arguments a una funció, o per desestructurar un array**.

#### Exemple 1: Passar arguments a una funció

```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

const result = sum(1, 2, 3, 4, 5);

console.log(result); // Output: 15
```

#### Exemple 2: Desestructurar un array

```javascript
const numbers = [1, 2, 3, 4, 5];

const [first, second, ...others] = numbers;

console.log(first); // Output: 1
console.log(second); // Output: 2
console.log(others); // Output: [3, 4, 5]
```

#### Exemple 3: Desestructurar un objecte

```javascript
const person = { name: 'John', age: 30, city: 'Barcelona', country: 'Spain' };

const { name, age, ...address } = person;

console.log(name); // Output: John
console.log(age); // Output: 30
console.log(address); // Output: { city: 'Barcelona', country: 'Spain' }
```

#### Prova-ho tu mateix

1. Escriu una funció a JS faci el mateix que això sense fer ús de concat:

```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const array3 = [7, 8, 9];

const result = concat(array1, array2, array3);
```

Has aplicat "spread" o "rest"?

2. Fes un console-log de tots els paràmetres de l'array tret de "Oluwatobi" i "sofela".

```javascript
const [firstName, lastName, ...otherInfo] = [
  'Oluwatobi',
  'Sofela',
  'CodeSweetly',
  'Web Developer',
  'Male',
];
```
