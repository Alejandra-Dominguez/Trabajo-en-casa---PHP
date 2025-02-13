# Funciones en PHP
Una función es un conjunto de instrucciones que a lo largo del programa van a ser ejecutadas multitud de veces.
Las funciones pueden ser llamadas y ejecutadas desde cualquier punto del programa.

## Sintaxis general para declarar una función en PHP
    function nombre_funcion($parametro1, $parametro2, ...) {
    // Código a ejecutar
    return $resultado; // Opcional: retorna un resultado
    }
#### Ejemplo: 
    function saludar() {
    echo "¡Hola, mundo!";
    }
## Parámetros y Retorno de Funciones:
Las funciones pueden recibir parámetros, que son valores que se utilizan dentro de la función. También pueden retornar un resultado usando la palabra clave return.
#### Ejemplo:
    function sumar($a, $b) {
    $resultado = $a + $b;
    return $resultado;
    }
    $suma = sumar(10, 5); // Llama a la función y almacena el resultado
    echo "La suma es: $suma"; // Esto imprimirá "La suma es: 15"
##  Funciones con Valor Predeterminado:
Puedes asignar valores predeterminados a los parámetros de una función. Si no se proporciona un valor al llamar la función, se utilizará el valor predeterminado.
### Ejemplo:
    function saludo_personalizado($nombre = "Usuario") {
    return "Hola, $nombre.";
    }
    echo saludo_personalizado(); // Esto imprimirá "Hola, Usuario."
    echo saludo_personalizado("Carlos"); // Esto imprimirá "Hola, Carlos."
## Cuando utilizar las funciones de PHP
**Reutilización de Código:** Permite usar el mismo bloque de código en múltiples lugares.

**Simplicidad y Organización:** Divide el código en bloques lógicos, facilitando su comprensión.

**Facilita el Mantenimiento:** Si hay cambios, solo necesitas modificar la función en un solo lugar.
 
# Array en PHP
Un array es un mapa ordenado donde los datos tendrán una clave (key) pero muchos valores (values).
#### Ejemplo:
Podríamos guardar los días de la semana bajo el mismo nombre de variable.

    $semana = [
    'Lunes',
    'Martes',
    'Miércoles',
    'Jueves',
    'Viernes',
    'Sábado',
    'Domingo'

# Crear
Para declarar un array vacío solamente debemos crear una variable donde asignemos unos corchetes.
        
    $planetas = [];

# Añadir
Y para ir añadiendo elementos.

    $planetas[] = 'Marte';
    $planetas[] = 'Tierra';

# Modificar
Para cambiar un valor hay que indicar la posición y el nuevo valor a introducir.

    $planetas[2] = 'Saturno';

# Borrar
Eliminar un elemento es un poco más marciano, debes usar una función nativa llamada *unset*.

    // Elimino la Tierra
    unset($planetas[1]);
    // Declaro mi nuevo array
    $planetasSinTierra = [];
    // Lo asigno elemento por elemento
    foreach ($planetas as $posicion => $nombre) {
    $planetasSinTierra[] = $nombre;
    }

# Foreach
Recorrer un array asociativo con PHP

    foreach ($values as $item => $value){
    echo $item.": ".$value.";
    }

# For 
Supongamos que tenemos un array de marcas de motos:

    var motos = ["Yamaha", "Suzuki", "Kawasaki", "KTM", "Honda"];

Una vez tenemos ese array queremos recorrerlo para mostrar por consola el nombre de las 5 marcas (ahora son 5, pero podrían ser 100 o x cantidad)

    for (var i = 0; i < motos.length; i++) {
	console.log(motos[i]);
    }
Mientras i sea menor a la longitud de el arreglo que contiene las motos vamos a incrementar i en 1, de esta manera a cada vuelta del bucle podemos mostrar motos[i] que en la primera vuelta sera 0, después 1, después 2… Así hasta que lleguemos a la longitud del array.

# array_search - Buscar elementos de un array
Busca un valor determinado en un array y devuelve la primera clave correspondiente en caso de éxito

    array_search(mixed $needle, array $haystack, bool $strict = false): mixed
Busca la *needle* (aguja) en *haystack* (pajar).

# Parámetros

## Needle 
El valor a buscar. 
## Haystack
El array
## Strict
se define como true entonces la función array_search() también buscará elementos idénticos en el haystack.
## Valores devueltos 
Devuelve la clave de la needle si se encuentra en el array, o false si no.

## Ejemplo:
    <?php
    $array = array(0 => 'azul', 1 => 'rojo', 2 => 'verde', 3 => 'rojo');
    
    $clave = array_search('verde', $array); // $clave = 2;
    $clave = array_search('rojo', $array);  // $clave = 1;
    ?>

# Otros 
1. array_keys() - Devuelve todas las claves de un array o un subconjunto de claves de un array
2. array_values() - Devuelve todos los valores de un array
3. array_key_exists() - Verifica si el índice o clave dada existe en el array
4. in_array() - Comprueba si un valor existe en un array

# array_merge - Combina dos o más arrays
    array_merge(array $array1, array $... = ?): array
Combina los elementos de uno o más arrays juntándolos de modo que los valores de uno se anexan al final del anterior. Retorna el array resultante.

# Parámetros
## array1
Array inicial a combinar.
## ...
Lista variable de arrays para combinar.
## Valores devueltos 
Retorna el array resultante.
## Ejemplo:
    <?php
    $array1    = array("color" => "red", 2, 4);
    $array2    = array("a", "b", "color" => "green", "shape" => "trapezoid", 4);
    $resultado = array_merge($array1, $array2);
    print_r($resultado);
    ?>
## Resultado 
    Array
    (
    [color] => green
    [0] => 2
    [1] => 4
    [2] => a
    [3] => b
    [shape] => trapezoid
    [4] => 4
    )

# Fuentes: 
- [php](https://www.php.net/manual/es/function.array-search.php)
- [ProgramadorWeb](https://programadorwebvalencia.com/cursos/php/arrays/)
- [Nelkodev](https://nelkodev.com/blog/arrays-asociativos-en-php-una-guia-completa/)

