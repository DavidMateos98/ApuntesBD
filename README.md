 <h1>SQL</h1>
  <h1>Índice</h1>
  <a href="#intro">Introducción</a><br>
  <a href="#funsel">Funciones SELECT</a><br>
  <a href="#funfro">Funciones FROM</a><br>
  <a href="#prewhe">Predicados WHERE</a><br>
  <a href="#otros">Otros predicados</a><br>
 

 <h2 name="intro">INTRODUCCIÓN</h2>
 
 Una consulta está compuesta por :
 SELECT campo FROM tabla WHERE condición;
 Donde:
   SELECT: elige el campo o conjunto de ellos que enseñará la tabla resultante.
   FROM: elige la tabla origen del campo seleccionado.
   WHERE: en ella irá la condición de nuestra consulta para reducir el número de resultados.

 Existe otro tipo de predicados los cuales veremos más adelante, pero una consulta sencilla y básica sería:
 SELECT *
 FROM table
 WHERE name ="Jose";
 La cual nos sacaría todos los atributos de la tabla "table" donde el nombre sea la cadena "Jose".


<h2 name="funsel">FUNCIONES SELECT</h2>

  <a href="#round">Introducción</a><br>
  <a href="#distinct">Funciones SELECT</a><br>
  <a href="#count">Funciones FROM</a><br>

<h3 name="round">ROUND</h3>

En ROUND (f,d) Arredondea la unidad f al numero d de décimas.
Ej: ROUND(250000/240,2) nos ejecutaría la división con dos decimales visibles.

 
<h3 name="distinct">DISTINCT</h3>

Lo empleamos para elegir sin repetidos, es decir, que sólo aparezca una vez.
Ej: SELECT DISTINCT(name) selecciona todos los nombres distintos.

<h3 name="count">MAX, AVG, COUNT, SUM</h3>

Son funciones de agregado que permiten devolver una única fila con un recuento, máximo, suma o media de todas las filas sellecionadas. Añadir a estas el predicado GROUP BY en el que introduciremos los campos que no estén afectados por los agregados.
Ej:SELECT name,COUNT(years)... GROUP BY (name) haría el recuento de years para cada name.


<h2 name="funfro">FUNCIONES FROM</h2>

<h3>JOIN</h3>

JOIN nos permite la unión de dos tablas para trabajar con atributos conjuntos.Al crear un JOIN es necesario igualar la clave principal de la primera tabla con el campo correspondiente al valor de la segunda tabla. Esto se hace mediante el predicado ON. de forma que un ejemplo de un JOIN sería:
FROM game JOIN goal ON (game.id= goal.matchid);
JOIN por defecto crearía el predicado INNER JOIN, pero existe INNER,LEFT y RIGHT JOIN para elegir, respectivamente, los atributos en común entre las dos tablas, los atributos que no contenga la segunda tabla pero sí la primera y los atributos que no contenga la primera tabla pero sí la segunda.




<h2 name="prewhe">PREDICADOS WHERE</h2>

  <a href="#in">Introducción</a><br>
  <a href="#like">Funciones SELECT</a><br>
  <a href="#between">Funciones FROM</a><br>
  
 <h3 name="in">IN</h3>
 
 Esta instrucción busca si en el campo se encuentra la cadena descrita. 
 Ej: WHERE name IN ('Jose','Álvaro') saca las tuplas de los nombres Jose y Álvaro únicamente.
 
 
<h3 name="like">LIKE</h3>

Nos permite asignar al predicado una expresión regular, como por ej:
WHERE name LIKE '%s%' lo cual nos sacaría todos los nombres que contengan la letra "s".
Si queremos introducir 0 o más carácteres usamos %.
Si queremos introducir 1 caracter usamos _.


<h3 name="between">BETWEEN</h3>

Crea un rango entre dos valores. 
Ej: WHERE population BETWEEN 2000 AND 2500; nos devuelve las tuplas cuya población sea entre 2000 y 2500.
AND nos obliga a la presencia de los dos valores, mientras que OR solo precisa la presencia de uno de ellos.


<h2 name="otros">OTROS PREDICADOS</h2>

  <a href="#orderby">Introducción</a><br>
  <a href="#replace">Funciones SELECT</a><br>
  <a href="#as">Funciones FROM</a><br>
   <a href="#concat">Introducción</a><br>
  <a href="#having">Funciones SELECT</a><br>


<h3 name="orderby">ORDER BY</h3> 

Si nuestra tabla aparece con las tuplas descolocadas, podemos utilizar ORDER BY para ordenar alfabéticamente tanto ascendente(ASC) como descendiente(DESC).

<h3 name="replace">REPLACE </h3>

Su expresión es REPLACE(f, s1, s2), donde toda la cadena s1 del campo f es reewmplazada por s2. Ej:
 REPLACE(name, 'a','') cambia todas las letras "a" de name por nada, por lo que eliminaría todas las letras a minúsculas de name.
 
<h3 name="as"> AS</h3>
 
AS renombra el campo que selecciona.
Ej: SELECT name AS 'nombre';

<h3 name="concat">CONCAT</h3> 

Permite unir dos o más cadenas o campos. 
Ej:
CONCAT(name,' city') añadiría a todos los nombres de las ciudades la cadena " city"

<h3 name="having">HAVING</h3>

Puede crear predicados de agregados.
EJ: HAVING SUM(population)<2500 condiciona a todos los valores cuya suma de filas de la población sea menor que 2500. 

