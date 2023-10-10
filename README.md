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

- Exemple 1

```javascript
function myFunction() {
  'use strict';
  x = 3.14;
  return x * 2;
}
```

- Exemple 2

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
let message; (Correcte)
const COLOR_RED = "#F00"; (Correcte)
const pageLoadTime = /* el temps que ha trigat a carregar la pàgina */
const myBirthday = '18.04.1982'; (Correcte)
let 1a; (Incorrecte)
let user = 'John', age = 25, message = 'Hola'; (Correcte)
let my-name; (Incorrecte)
var mensaje = 'Hola'; (Acceptable)
const BIRTHDAY = '18.04.1982'; (Correcte)
let num = 5; (Correcte)
```

### Exercici 3: Nivell de dificultat alt

Aquests són els resultats de les operacions que has proporcionat:

```javascript
let a, b, c, d;
a = '5' + 5; // "55" (string)
b = 5 + '5'; // "55" (string)
c = '5' - 5; // 0    (number)
d = '5' * '5'; // 25   (number)

a = '15' > 5; // true     15 > 5
b = 5 > '15'; // false     5 > 15
c = '15' > '5'; // false    "15" no és major que "5" en comparacions de cadena
d = '5' > '15'; // true    "5" és major que "15" en comparacions de cadena
```

Els resultats es deriven de les regles de JavaScript per a les operacions entre cadenes i números, així com de les comparacions de cadenes. Per a les operacions d'addició (`+`), qualsevol operand de tipus cadena es converteix en cadena i es realitza una concatenació. Per a les operacions de resta (`-`) i multiplicació (`*`), JavaScript intenta convertir les cadenes en números, i si és possible, realitza l'operació numèrica.

En les comparacions entre cadenes, JavaScript compara els valors llexicogràficament. En el cas de `"15" > "5"`, les cadenes es comparen caràcter a caràcter i `"5"` és major que `"15"` en aquesta comparació, ja que el caràcter `"5"` és major que el caràcter `"1"`.

### Exercici 4: Condicionals - Ternaris

Aquí tens les solucions per als exercicis de conversió de codi amb `if...else if` a expressions ternàries:

1. **Convertir IF a Ternari:**

   ```javascript
   let hour = 12;
   let greeting = hour < 12 ? 'Bon dia' : hour < 18 ? 'Bona tarda' : 'Bona nit';
   ```

2. **Classificar el Número:**

   ```javascript
   let num = -5;
   let result = num > 0 ? 'Positiu' : num < 0 ? 'Negatiu' : 'Zero';
   ```

3. **Classificar l'Edat:**

   ```javascript
   let age = 25;
   let label = age < 13 ? 'Nen' : age < 20 ? 'Adolescent' : 'Adult';
   ```

4. **Nullish coalescing operator:**

   ```javascript
   let firstName = null;
   let lastName = null;
   let nickName = 'Supercoder';
   // mostra el primer nom no nul·l
   alert(firstName ?? lastName ?? nickName ?? 'Anonymous'); // Supercoder
   ```

Aquestes solucions utilitzen expressions ternàries per aconseguir el mateix resultat que les declaracions `if...else if` dels exercicis originals. Això demostra com pots simplificar i fer més llegible el teu codi en situacions senzilles com aquestes utilitzant expressions ternàries.
