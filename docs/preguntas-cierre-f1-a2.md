# Preguntas de cierre - EC1 F1 A2
**Nombre: Miguel Angel Pineda Chenoweth**
**Grupo: 01**

## 1. ¿Qué problema resuelve la interfaz Gif dentro del proyecto?
Ya no se tiene que crear los mismos atributos para cada gif y simplemente el main.ts puede mandar a llamarlo

## 2. ¿Qué diferencia existe entre una interfaz y un objeto literal?
La interfaz simplemente valida la forma de los datos mientras que el objeto es una instancia y esta ejecutandose

## 3. ¿Qué significa Gif[] y qué error evita en el arreglo local?
Gif[] es la creación de un arreglo que todos son Gif y evita que puedas meter elementos que no cumplan con el formato
correcto

## 4. ¿Por qué username y description pueden declararse como propiedades opcionales?
Porque como el username y la descripción no vienen con todos los gifs, si no fueran opcionales tuvieras que agregar un dato como placeholder

## 5. ¿En qué situación utilizarías let en lugar de const dentro de esta actividad?
Si quisiera llevar un contador de Gifs que permanezca por todo el codigo, pudiera utilizar una variable let

## 6. ¿Qué reciben y qué devuelven normalizeText, searchGifs y createGifCard?
normalizeText recibe un string y le quita los espacios, todo en minuscula y de acuerdo a las reglas del español mx
searchGifs recibe la colección de todos los gifs y un string y devuelve un arreglo nuevo basado en si el string tiene los datos del matches query
createGifCard recibe un Gif (no el arreglo entero) y devuelve codigo en HTML que establece como se ve la carta con todos los datos del Gif

## 7. ¿Qué diferencia existe entre forEach, filter, map y find?
forEach ejecuta el código por cada elemento en el arreglo
filter es lo mismo que forEach pero tiene que cumplir una condición especifica
map recorre el arreglo y modifica un elemento en otro
find busca en el arreglo y encuentra el primero que cumple con alguna condición

## 8. ¿Por qué find puede devolver undefined y cómo se controló ese resultado?
Porque si find no encuentra algo con el dato especificado entonces queda como undefined
para controlarlo se agrega un ? para marcar que es opcional y el ?? llena un valor por default

## 9. ¿Qué es un callback? Identifica dos callbacks presentes en tu solución.
Es una función que usa como parte de su argumento otra función

form.addEventListener("submit", (event: SubmitEvent) => {
  event.preventDefault();
  const results = searchGifs(gifs, input.value);
  renderGifs(results);
});

return collection.filter((gif) => matchesQuery(gif, query));

## 10. ¿Qué ventaja ofrecen las template strings al construir las tarjetas?
Permiten insertar variables dentro de las tarjetas

## 11. ¿Para qué se utilizó la destructuración y el valor predeterminado de username?
Destructurar ayuda a que en vez de escribir de sacar todos los valores del arreglo uno por uno
se sacan una sola vez, el valor default se establecio porque username es opcional

## 12. ¿Por qué querySelector puede devolver null y cómo se validaron los elementos?
Porque puede haber un caso donde el typescript no encuentre app y se usa el if app! y manda error para validarlo

## 13. ¿Qué función cumple preventDefault en el envío del formulario?
Normalmente cuando haces un submit recarga la página entera, el preventDefault para ese comportamiento.

## 14. ¿Cómo responde la aplicación cuando la búsqueda no obtiene coincidencias?
Muestra un mensaje predeterminado

## 15. ¿Qué cambiará cuando el arreglo local sea sustituido por datos de Giphy API?
Iba a cambiar en que los datos los tiene que cargar usando una conexión constante a la API, si esa falla o un dato no lo puede agarrar correctamente sera más complicado

## 16. ¿Qué error o dificultad encontraste y cómo comprobaste que quedó resuelto?
No encontre ningun error mayor.