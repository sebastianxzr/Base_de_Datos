
## Práctica 4
### Data warehouse

Objetivo: Demostrar la identificación de los elementos que componen data warehouse y
su esquema

Ejercicio:

1. ¿Qué es un DataWarehouse?(valor 2)

es un almacén electrónico donde generalmente una empresa u organización mantiene una gran cantidad de información

2. Realiza un diseño del modelo en estrella (valor 2)

3. Realiza un diseño del modelo copo de nieve (valor 2)


## Práctica 7
### Funciones en SQL
Objetivo: Demostrar el uso y aplicación en una base de datos para mejorar la gestión

Ejercicio:

1. Calcula el número total de productos que hay en la tabla productos. (valor 4.5)

SELECT COUNT() FROM producto

2. Muestra el número total de productos que tiene cada uno de los fabricantes. El listado
también debe incluir los fabricantes que no tienen ningún producto. El resultado
mostrará dos columnas, una con el nombre del fabricante y otra con el número de
productos que tiene. Ordene el resultado descendentemente por el número de
productos. (valor 4.5)

  SELECT fabricante.nombre, COUNT(producto.codigo)
  FROM fabricante LEFT JOIN producto
  ON producto.codigo_fabricante = fabricante.codigo
  GROUP BY fabricante.codigo
  ORDER BY 2 DESC
  
3. Muestra el precio máximo, precio mínimo y precio medio de los productos de cada
uno de los fabricantes. El resultado mostrará el nombre del fabricante junto con los
datos que se solicitan. (valor 4.5)

SELECT fabricante.nombre, MAX(producto.precio), MIN(producto.precio), AVG(producto.precio)
FROM fabricante INNER JOIN producto
ON producto.codigo_fabricante = fabricante.codigo
GROUP BY fabricante.codigo

4. Muestra el nombre de cada fabricante, junto con el precio máximo, precio mínimo,
precio medio y el número total de productos de los fabricantes que tienen un precio
medio superior a 200€. Es necesario mostrar el nombre del fabricante. (valor 4.5)

SELECT fabricante.nombre, 
MAX(producto.precio), MIN(producto.precio), 
AVG(producto.precio), COUNT(*)
FROM producto INNER JOIN fabricante
ON producto.codigo_fabricante = fabricante.codigo
GROUP BY fabricante.codigo
HAVING AVG(producto.precio) > 200

