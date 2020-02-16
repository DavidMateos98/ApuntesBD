 SQL
 
 INTRODUCCIÓN
 
Una consulta está compuesta por :
SELECT campo FROM tabla WHERE condición;
Donde:
  SELECT: elige el campo o conjunto de ellos que enseñará la tabla resultante.
  FROM: elige la tabla origen del campo seleccionado.
  WHERE: en ella irá la condición de nuestra consulta para reducir el número de resultados.
  
Existe otro tipo de predicados los cuales veremos más adelante, pero una consulta sencilla y básica sería:
SELECT *
FROM table
WHERE name ="Jose"
La cual nos sacaría todos los atributos de la tabla "table" donde el nombre sea la cadena "Jose".





PREDICADOS FROM


PREDICADOS WHERE

 IN
 
 Esta instrucción busca si en el campo se encuentra la cadena descrita. 
 Ej: WHERE name IN ('Jose','Álvaro') saca las tuplas de los nombres Jose y Álvaro únicamente.
 
 
LIKE

Nos permite asignar al predicado una expresión regular, como por ej:
WHERE name LIKE '%s%' lo cual nos sacaría todos los nombres que contengan la letra "s".
Si queremos introducir 0 o más carácteres usamos %.
Si queremos introducir 1 caracter usamos _.


BETWEEN

Crea un rango entre dos valores. 
Ej: WHERE population BETWEEN 2000 AND 2500; nos devuelve las tuplas cuya población sea entre 2000 y 2500.
AND nos obliga a la presencia de los dos valores, mientras que OR solo precisa la presencia de uno de ellos.


OTROS PREDICADOS


ORDER BY 

Si nuestra tabla aparece con las tuplas descolocadas, podemos utilizar ORDER BY para ordenar alfabéticamente tanto ascendente(ASC) como descendiente(DESC).

REPLACE 

Su expresión es REPLACE(f, s1, s2), donde toda la cadena s1 del campo f es reewmplazada por s2. Ej:
 REPLACE(name, 'a','') cambia todas las letras "a" de name por nada, por lo que eliminaría todas las letras a minúsculas de name.
 
 AS
 
AS renombra el campo que selecciona.
Ej: SELECT name AS 'nombre';

CONCAT 

Permite unir dos o más cadenas o campos. 
Ej:
CONCAT(name,' city') añadiría a todos los nombres de las ciudades la cadena " city"

ROUND

En ROUND (f,d) Arredondea la unidad f al numero d de décimas.
Ej: ROUND(250000/240,2) nos ejecutaría la división con dos decimales visibles.






