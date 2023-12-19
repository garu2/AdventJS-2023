<div align="center">
<img height="150"  src="https://res.cloudinary.com/dqd5x0s7w/image/upload/v1702933536/github/adventjs-logo_yyvhkp.png"  alt="css image">
<h1 align="center">AdventJS 2023</h1>
⭐️Aquí están algunas soluciones del <a target="_blank" href="https://adventjs.dev/es">AdventJS 2023</a>. Esto se publica con el fin de aprender y entender las distintas soluciones que se aplican a los diferentes problemas.⭐️
</div>

## Retos

1. [🎁 ¡Primer regalo repetido!](#Primer-regalo-repetido)
2. [Background Image con Overlay](#background-image-con-overlay)

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
