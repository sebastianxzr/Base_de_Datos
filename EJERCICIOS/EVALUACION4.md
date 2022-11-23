## Práctica 8.
### Disparadores (Triggers)

Objetivo: Demostrar las operaciones que se realizan en una base de datos.

Ejercicio: Crea una base de datos llamada test que contenga una tabla llamada
alumnos con las siguientes columnas. (valor 18)

Evaluación:

Creación de la base de datos : 9 puntos.

Creación de los Disparadores(Triggers): 9 puntos.

Tabla alumnos:

● id (entero sin signo)

● nombre (cadena de caracteres)

● apellido1 (cadena de caracteres)

● apellido2 (cadena de caracteres)

● nota (número real)

Una vez creada la tabla escriba dos triggers con las siguientes características:

● Trigger 1: trigger_check_nota_before_insert

  o Se ejecuta sobre la tabla alumnos.
  
  o Se ejecuta antes de una operación de inserción.
  
  o Se almacena la leyenda 'se ingreso un registro'

● Trigger2 : trigger_check_nota_before_update
  o Se ejecuta sobre la tabla alumnos.
  
  o Se ejecuta antes de una operación de actualización.
  
  o Se ingresa la leyenda 'se modifico un regisstro'
  
Una vez creados los triggers escribe varias sentencias de inserción y actualización
sobre la tabla alumnos y verifica que los triggers se están ejecutando
correctamente.

Respuesta:

DROP DATABASE IF EXISTS test;
CREATE DATABASE test;
USE test;

CREATE TABLE alumnos (
    id INT UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    apellido1 VARCHAR(50) NOT NULL,
    apellido2 VARCHAR(50), 
    nota FLOAT
DROP TRIGGER IF EXISTS trigger_check_nota_before_insert$$
CREATE TRIGGER trigger_check_nota_before_insert
BEFORE INSERT
ON alumnos FOR EACH ROW

DROP TRIGGER IF EXISTS trigger_check_nota_before_update$$
CREATE TRIGGER trigger_check_nota_before_update
BEFORE UPDATE
ON alumnos FOR EACH ROW

