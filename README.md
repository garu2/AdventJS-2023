<div align="center">
<img height="150"  src="https://res.cloudinary.com/dqd5x0s7w/image/upload/v1702933536/github/adventjs-logo_yyvhkp.png"  alt="css image">
<h1 align="center">AdventJS 2023</h1>
⭐️Aquí están algunas soluciones del <a target="_blank" href="https://adventjs.dev/es">AdventJS 2023</a>. Esto se publica con el fin de aprender y entender las distintas soluciones que se aplican a los diferentes problemas.⭐️
</div>

## Retos

1. [🎁 ¡Primer regalo repetido!](#Primer-regalo-repetido)
1. [🏭 Ponemos en marcha la fábrica](#Ponemos-en-marcha-la-fábrica)
1. [😏 El elfo travieso](#El-elfo-travieso)
1. [😵‍💫 Dale la vuelta a los paréntesis](#Dale-la-vuelta-a-los-paréntesis)

---

### Primer regalo repetido

```js
function findFirstRepeated(gifts) {
  // Creamos un conjunto (Set Es una estructura de datos en JavaScript que representa una colección de valores únicos) para rastrear los números que hemos visto
  const onlyNumbers = new Set();
  // Iteramos sobre los números de regalos
  for(let i = 0; i < gifts.length; i++) {
    // Creamos una variable auxiliar para el elemento actual de la iteracion 
    const currentNum = gifts[i];
    // Revisamos si nuestro elemento actual ya está en nuestra estructura de datos Set.
    if(onlyNumbers.has(currentNum)) {
      // Si es así, retornamos el número actual.
      return currentNum;
    }
    // Si no entra en la condición entonces agregamos a nuestro Set. 
    onlyNumbers.add(currentNum);
  } 
  // Si no se encontraron números repetidos
  return -1;
}
```
<sup>⬆️ [back to table of contents](#tips) </sup>

---

### Ponemos en marcha la fábrica

```js
function manufacture(gifts, materials) {
  // Inicializar una lista para almacenar los regalos fabricados
  const manufacturedGifts = [];

  // Iterar a través de cada regalo en la lista
  for (const gift of gifts) {
    // Inicializar una variable para rastrear si el regalo se puede fabricar
    let contain = true;

    // Iterar a través de cada letra del regalo
    for (const char of gift) {
      // Verificar si la letra está presente en los materiales
      if (!materials.includes(char)) {
        // Si falta alguna letra, no se puede fabricar el regalo
        contain = false;
        // Salir del bucle interno, ya que no es necesario verificar más letras
        break;
      }
    }

    // Verificar si todos los caracteres del regalo están en los materiales
    // Si es así, agregar el regalo a la lista de regalos fabricados
    contain && manufacturedGifts.push(gift);
  }

  // Devolver la lista de regalos fabricados
  return manufacturedGifts;
}
```
<sup>⬆️ [back to table of contents](#tips) </sup>

---
### El elfo travieso

```js
function findNaughtyStep(original, modified) {
  // Determinar cuál de las dos cadenas es más larga
  const longer = original.length > modified.length ? original : modified;

  // Iterar a través de los caracteres de la cadena más larga
  for (let i = 0; i < longer.length; i++) {
    // Verificar si el carácter actual en ambas cadenas es diferente
    if (original[i] !== modified[i]) {
      // Si es diferente, devolver el carácter de la cadena más larga
      return longer[i];
    }
  }

  // Si no se encuentra ninguna diferencia, devolver una cadena vacía
  return '';
}
```
<sup>⬆️ [back to table of contents](#tips) </sup>

---
### 😵‍💫 Dale la vuelta a los paréntesis

```js
function decode(message) {
  // Inicializar una pila y una variable auxiliar (result)
  let stack = [];
  let result = '';

  // Iterar a través de cada carácter en el mensaje
  for (let i = 0; i < message.length; i++) {
    // Verificar si el carácter actual es un '('
    if (message[i] === '(') {
      // Si es '(', agregar la cadena actual a la pila
      stack.push(result);
      // Reiniciar la variable result a vacio
      result = '';
    } else if (message[i] === ')') {
      // Si es ')', stack.pop() => Sacamos el ultimo elemento de nuestra pila. Concatenamos lo siguiente
      // result.split('') => Convierte nuestra cadena en un arreglo
      // reverse() => Invierte nuestro arreglo
      // join('') => Vuelve a convertir nuestro arreglo en una cadena
      result = stack.pop() + result.split('').reverse().join('');
    } else {
      // Agregar los demas caracteres a nuestra variable auxiliar
      result += message[i];
    }
  }

  // Devolver la cadena resultante después de procesar todos los caracteres
  return result;
}
```
<sup>⬆️ [back to table of contents](#tips) </sup>

---
