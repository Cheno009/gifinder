# Preguntas de cierre - EC1 F3 A4

## 1. ¿Qué diferencia existe entre una operación síncrona y una asíncrona?
Una operación síncrona bloquea la ejecución hasta terminar; una asíncrona (como `fetch`) se ejecuta en segundo plano y el resto del código sigue corriendo mientras espera la respuesta.

## 2. ¿Cuáles son los estados de una promesa y qué relación tienen con async/await?
Una promesa puede estar `pending`, `fulfilled` o `rejected`. `await` pausa la función hasta que la promesa pasa a `fulfilled` (devuelve el valor) o `rejected` (lanza el error, capturable con `try/catch`).

## 3. ¿Qué devuelve fetch y qué devuelve response.json()?
`fetch` devuelve una `Promise<Response>` con la información de la petición (estado, cabeceras, etc.). `response.json()` devuelve otra promesa que resuelve con el cuerpo de la respuesta ya parseado como objeto JavaScript.

## 4. ¿Por qué es necesario comprobar response.ok?
Porque `fetch` solo rechaza la promesa por errores de red, no por códigos HTTP de error (404, 500...). Comprobar `response.ok` permite detectar esas respuestas fallidas y lanzar un error propio, como se hace en `requestGifs`.

## 5. ¿Cómo se utilizan try, catch y unknown para manejar errores en GIFinder?
En `main.ts` las llamadas a `getTrendingGifs`/`searchGifs` van dentro de un `try`; si fallan, el `catch (error: unknown)` captura el error sin asumir su tipo, y `showRequestError` comprueba con `error instanceof Error` antes de usar `error.message`.

## 6. ¿Qué diferencia existe entre GiphyGif y Gif, y qué responsabilidad tiene mapGiphyGif?
`GiphyGif` es la forma cruda que devuelve la API de GIPHY; `Gif` es el modelo propio y simplificado que usa la aplicación. `mapGiphyGif` se encarga de transformar un `GiphyGif` en un `Gif`, adaptando y limpiando los datos (título por defecto, imagen de previsualización, rating validado, etc.).

## 7. ¿Por qué se utiliza URLSearchParams al construir la solicitud?
Porque construye y codifica automáticamente los parámetros de la URL (api_key, limit, rating, q...) con el formato correcto, evitando errores manuales al concatenar strings.

## 8. ¿Qué significa Promise<Gif[]> en el tipo de retorno?
Indica que la función es asíncrona y que, cuando se resuelva, entregará un arreglo de objetos `Gif`.

## 9. ¿Qué diferencia existe entre .env.local y .env.example, y por qué una variable VITE_ no debe considerarse secreta?
`.env.local` contiene los valores reales (la API key) y no se versiona; `.env.example` es una plantilla sin valores sensibles que sí se sube al repositorio para guiar la configuración. Una variable `VITE_` no es secreta porque Vite la incluye en el bundle final, quedando visible en el código del cliente.

## 10. ¿Cómo comprobaste que .env.local no está versionado?
Revisando el `.gitignore` (incluye `.env.*`) y ejecutando `git check-ignore -v .env.local`, que confirma que el archivo está ignorado por esa regla.

## 11. ¿Por qué Loading puede observarse con mayor claridad al consultar una API?
Porque la petición a GIPHY tarda un tiempo real de red, así que el estado `Loading` permanece visible durante ese intervalo, a diferencia de una operación local e instantánea donde el cambio de estado casi no se nota.

## 12. ¿Qué dificultad se presentó durante la integración y cómo comprobaste que quedó resuelta?
Se me olvido agregar la imagen al final y ya :D