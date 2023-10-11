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

> ✅ Use strict no permet declarar variables sense utilitzar `var`, `let` o `const`.

#### Exemple 2

```javascript
function myFunction() {
  'use strict';
  let x = 3.14;
  delete x;
  return x * 2;
}
```

> ✅ Use strict no permet utilitzar la paraula clau `delete` per eliminar variables. Si podríem fer-la servir per eliminar propietats d'objectes.
> Ex: `objecte = {a: 1, b: 2}; delete objecte.a;`
> Tot i així no és una bona pràctica fer-ho. https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Operadores/delete

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

> ✅ A continuació pots veure les respostes correctes:

```javascript
let message; // ✅
const COLOR_RED = "#F00"; // ✅ És una bona pràctica utilitzar majúscules per a les constants sempre i quan coneixem el seu valor abans de la seva declaració (hard-coded)
const pageLoadTime = // ✅  Encara no coneixem el seu valor.
const myBirthday = '18.04.1982'; // ❌  Hauria de ser en majúscula ja que coneixem el seu valor abans de la seva declaració.
let 1a; // ❌  No podem començar el nom d'una variable amb un número.
let user = 'John', age = 25, message = 'Hola'; // ✅
let my-name; // ❌  No podem utilitzar el caràcter "-" en el nom d'una variable.
var mensaje = 'Hola'; // ❌  No utilitzem var.
const BIRTHDAY = '18.04.1982'; // ✅  És una bona pràctica utilitzar majúscules per a les constants sempre i quan coneixem el seu valor abans de la seva declaració (hard-coded)
let num = 5;  // ✅
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

!!! Warning Pel valor `null`, retorna "object": això és un error en el llenguatge, en realitat no és un objecte.

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

> ✅ El prompt sempre retorna un string. Per tant, hem de convertir els valors a números abans de fer la suma. Ho podem aconseguir fent servir la funció `Number()`: https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Number
>
> ```javascript
> let num1 = Number(prompt('Introdueix el primer número:'));
> let num2 = Number(prompt('Introdueix el segon número:'));
> ```

#### Exercici 3.2:

Realitza un petit codi que demani a l'usuari un número i mostri a través d'un alert si l'usuari ha introud ït un número parell o senar.

```javascript
let entrada = prompt('Introdueix un número entre 1 i 100:');
//...
```

> ✅ Mateixa idea que en l'exercici anterior:
>
> ```javascript
> let entrada = Number(prompt('Introdueix un número entre 1 i 100:'));
> alert(entrada % 2 === 0 ? 'El número és parell' : 'El número és senar');
> //...
> ```

#### Exercici 3.3:

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

> ✅ Els operadors aritmètics (+, -, \*, /) converteixen els valors a números. Per tant, aquestes operacions sempre retornen un número.

```javascript
let a, b, c, d;
a = '5' + 5; // '55'
b = 5 + '5'; // '55'
c = '5' - 5; // 0
d = '5' * '5'; // 25
```

> ✅ Els operadors de comparació (>, <, >=, <=) converteixen els valors a números. Per tant, aquestes operacions sempre retornen un boolean.

```javascript
a = '15' > 5; // true (compara com si fossin números)
b = 5 > '15'; // false  (compara com si fossin números)
c = '15' > '5'; // false (compara els caràcters un a un)
d = '5' > '15'; // true (compara els caràcters un a un)
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

   > ✅ La solució seria la següent:
   >
   > ```javascript
   > let hour = 12;
   > let greeting =
   >   hour < 12 ? 'Bon dia' : hour < 18 ? 'Bona tarda' : 'Bona nit';
   > ```

2. **Classificar el Número:**

   Tens un número `num` i vols assignar la cadena 'Positiu' si és positiu, 'Negatiu' si és negatiu, i 'Zero' si és igual a zero. Utilitza una expressió ternària per aconseguir-ho.

   > ✅ La solució seria la següent:
   >
   > ```javascript
   > let num = 0;
   > let resultat = num > 0 ? 'Positiu' : num < 0 ? 'Negatiu' : 'Zero';
   > ```

3. **Classificar l'Edat:**

   Donada una edat, vols assignar una etiqueta que indiqui si és un "Nen", "Adolescent" o "Adult". Utilitza una expressió ternària per aconseguir-ho.

   > ✅ La solució seria la següent:
   >
   > ```javascript
   > let age = 15;
   > let resultat = age < 13 ? 'Nen' : age < 18 ? 'Adolescent' : 'Adult';
   > ```

4. **Nullish coalescing operator**
   Suposem que tenim tres variables per guardar els nom, el cognom i el "nickname" d'un usuari. Ara bé, no estem segurs que tinguem tota aquesta informació. Només sabem que com a mínim en tenim una d'aquestes i que volem mostrar a alerta seguint la següent prioritat:
   nom --> cognom --> nickName --> 'anònim'
   Escriu el codi que ens ho soluciona fent ús de "??".
   > ✅ La solució seria la següent:
   >
   > ```javascript
   > let nom = 'John';
   > let cognom = 'Doe';
   > let nickName = 'Johnny';
   > alert(nom ?? cognom ?? nickName ?? 'anònim');
   > ```
   >
   > ✅ Si no tinguéssim el nom, cognom ni nickName, el resultat seria 'anònim'.

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

> ✅ La funció de dalt es pot simplificar de la següent manera:
>
> ```javascript
> function checkAge(age) {
>   if (age > 18) {
>     return true;
>   }
>   // ...
>   return confirm('¿Tus padres te permitieron?');
> }
> ```
>
> ✅ El return dins de la funció fa que la funció s'aturi i retorni el valor. Per tant, si la condició és certa, la funció s'atura i retorna true. Si la condició és falsa, la funció s'atura i retorna el resultat de la funció confirm.

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

> ✅ La funció de dalt es pot simplificar de la següent manera:
>
> ```javascript
> function checkAge(age) {
>   return age > 18 ? true : confirm('¿Tienes permiso de tus padres?');
> }
> ```

També ho podem fer fent servir l'operador `||`. Inclus més curt. Investiga com fer-ho.

> ✅ La funció de dalt es pot simplificar de la següent manera:
>
> ```javascript
> function checkAge(age) {
>   return age > 18 || confirm('¿Tienes permiso de tus padres?');
> }
> ```
>
> ✅ L'operador `||` mira si la condició de l'esquerra és certa. Si ho és, retorna el valor de l'esquerra. Si no ho és, retorna el valor de la dreta. En aquest cas, si la condició és certa, retorna true. Si no ho és, retorna el resultat de la funció confirm. Sempre haurà de tenir una condició a l'esquerra i un valor a la dreta.

#### Exercici 5.3 - Variables globals i locals

Declara una variable global anomenada MAX_PRICE i establix el seu valor a 10.

Defineix la funció calculaTotal. Dins de la funció, declara una variable local anomenada total i establix el seu valor com a preu \* quantitat.

Utilitza una declaració if per comprovar si el preu és menor o igual a MAX_PRICE. Si ho és, retorna el valor de total. Si no ho és, retorna un missatge d'error.

Prova la teva funció cridant-la amb diferents valors per al preu i la quantitat, i assegura't que retorni el resultat correcte o el missatge d'error.

> ✅ La funció de dalt es pot simplificar de la següent manera:
>
> ```javascript
> const MAX_PRICE = 10;
> function calculaTotal(preu, quantitat) {
>   let total = preu * quantitat;
>   if (preu <= MAX_PRICE) {
>     return total;
>   } else {
>     return 'El preu és massa alt';
>   }
> }
> ```
>
> ✅ La variable MAX_PRICE és una variable global. Això vol dir que es pot accedir a ella des de qualsevol lloc del nostre codi. En canvi, la variable total és una variable local. Això vol dir que només es pot accedir a ella des de dins de la funció.

### Exercici 6: Funcions - Arrow Functions

> ✅
>
> ```javascript
> const multiply = (a, b) => a * b;
> ```
>
> ✅
>
> ```javascript
> const calculateTotal = (price, quantity) => {
>   let total = price * quantity;
>   if (price > 10) total = total * 0.9;
>   return total;
> };
> ```
>
> ✅
>
> ```javascript
> const outerFunction = (a, b) => {
>   const innerFunction = (c, d) => c * d;
>   return innerFunction(a, b) + 10;
> };
> ```
>
> ✅ En aquest cas com que les funcions originals son anònimes hem de crear una variable per a poder cridar-les amb arrow functions.
> const numbers = [1, 2, 3, 4, 5];

// Callback function to arrow function
const doubledNumbers = numbers.map(function (number) {
return number \* 2;
});

> ✅ Arrow Function
>
> ```javascript
> const numbers = [1, 2, 3, 4, 5];
> const doubledNumbers = numbers.map((number) => number * 2);
> ```

Pel que fa al darrer cas:

- Funció anònima:

```javascript
const myObject = {
    name: name
    sayHello() {
      console.log(this.name); // Output: myObject
    },
};

myObject.myMethod();
```

> ✅ Arrow Functions
>
> ```javascript
> const myObject = {
>     name: name
>     sayHello: () => {
>       console.log(this.name); // Output: Window
>     },
> };
>
> myObject.myMethod();
> ```

> ✅ What happens here? The arrow function doesn’t have its own **this**. The this value of the enclosing lexical scope is used; arrow functions follow the normal variable lookup rules. So while searching for this which is not present in the current scope they end up finding this from its enclosing scope.

> ✅ Arrow Functions
>
> ```javascript
> const myObject(name) = {
>   name: name,
>   sayHello: function () {
>      setTimeout(() => {
>       console.log(this.name); // Output: John
>     }, 1000);
>   },
> };
> myObject.sayHello();
> ```
>
> ✅ Arrow Functions
>
> ```javascript
> const myObject(name) = {
>   name: name,
>   sayHello: () => {
>      setTimeout(() => {
>       console.log(this.name); // Output: John
>     }, 1000);
>   },
> };
> myObject.sayHello();
> ```

### Exercici 8

```javascript
function sumWithRest(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

function sumWithSpread(numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

const numbers = [1, 2, 3, 4, 5];

const result1 = sumWithRest(1, 2, 3, 4, 5);
const result2 = sumWithSpread([...numbers]);

console.log(result1); // Output: 15
console.log(result2); // Output: 15
``;
```
