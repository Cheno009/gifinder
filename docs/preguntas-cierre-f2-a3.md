# Preguntas de cierre - EC1 F2 A3

## 1. ¿Qué significa refactorizar una aplicación?
Refactorizar consiste en cambiar el orden y mejorar la estructura de un programa sin afectar la funcionalidad

## 2. ¿Por qué el proyecto se dividió en módulos?
De esta manera detectar errores resulta mucho más fácil ya que si un modulo falla sabes que parte del código especifica falla con más facilidad

## 3. ¿Cuál es la responsabilidad de main.ts?
El main le manda al #app todo el HTML y es el modulo principal que funcióna como una conexión a los demás

## 4. ¿Qué diferencias existen entre una interfaz, un tipo unión y una enumeración?
La interfaz define la forma de un objeto, el tipo unión se usa cuando un valor tiene distintos tipos posibles y una enumeración es un conjunto de constantes

## 5. ¿Para qué se utiliza import type?
Para solamente importar las declaraciones "type" de un modulo

## 6. ¿Dónde se aplicaron la desestructuración, spread y rest?
Desestructuración:
En src/components/gallery.ts, dentro de createGifCard: const { id, title, url, username = "Autor no disponible", tags, rating } = gif; — aquí también hay un valor por defecto para username.
En src/components/gif-detail.ts, dentro de renderGifDetail: la misma desestructuración de las propiedades de gif.

Rest:
En src/components/gif-detail.ts: const [mainTag = "Sin etiqueta", ...secondaryTags] = tags; — esto es desestructuración de array con rest: toma el primer tag como mainTag y agrupa el resto en secondaryTags.

Spread:
En src/services/gif.service.ts, dentro de matchesQuery: [gif.title, gif.username ?? "", ...gif.tags].join(" ") — usa spread para expandir el arreglo tags dentro de un nuevo arreglo.
También en searchGifs: return [...collection]; — usa spread para devolver una copia del arreglo cuando la búsqueda está vacía, evitando mutar el original.

## 7. ¿Por qué searchGifs recibe la colección como parámetro?
Porque se establece en la función que va a tomar el arreglo de Gif[] como parametro

## 8. ¿Por qué findGifById puede devolver undefined?
Porque a veces puede que no encuentre un gif

## 9. ¿Qué función cumple data-gif-id?
Ayuda a que muestre el detalle del gif correcto basandose en su id

## 10. ¿Qué es la delegación de eventos?
Técnica en JavaScript que consiste en asignar un único manejador de eventos a un elemento padre en lugar de agregar múltiples manejadores a cada uno de los elementos hijos.

## 11. ¿Por qué el estado Loading podría no observarse?
Como no hay funciones asincronas, no hay ningun punto donde el código necesita esperar

## 12. ¿Qué dificultad se presentó durante la refactorización y cómo se resolvió
Ninguna :D