## Práctica 9.
### Operaciones en una base de datos.
Objetivo: Demostrar las operaciones que se realizan en una base de datos, aplicar el modelo relacional y el lenguaje SQL

Evaluación: Para poder tener correcto cada ejercicio deberán de mostrar el resultado que se da en cada respuesta.

Lista el nombre de todos los productos que hay en la tabla producto.


1. Lista los nombres y los precios de todos los productos de la tabla producto.

  SELECT nombre FROM productos

2. Lista todas las columnas de la tabla producto.

  SELECT * FROM productos

3. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de
todos los productos de la base de datos.

  SELECT producto.nombre, precio, fabricante.nombre
FROM producto INNER JOIN fabricante
ON producto.codigo_fabricante = fabricante.codigo

Subconsultas (En la cláusula WHERE)
1. Devuelve todos los productos del fabricante Lenovo. (Sin utilizar INNER
JOIN).

  SELECT * FROM producto WHERE codigo_fabricante = (   SELECT codigo   FROM
fabricante  WHERE nombre WHERE nombre = 'Lenovo')

2. Devuelve todos los datos de los productos que tienen el mismo precio que el
producto más caro del fabricante Lenovo. (Sin utilizar INNER JOIN).

  SELECT   *   FROM   producto   WHERE   precio   =   (   SELECT   MAX(precio)   FROM
producto  WHERE producto.codigo_fabricante = (  SELECT codigo  FROM fabricante  
WHERE nombre WHERE nombre = 'Lenovo'))

3. Lista el nombre del producto más caro del fabricante Lenovo.
  
  SELECT producto.nombre  FROM   producto  WHERE  (SELECT MAX(precio)   FROM
producto, fabricante WHERE fabricante.nombre = "Lenovo");
