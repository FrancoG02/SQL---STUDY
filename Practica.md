# SQL-STUDY

SESIÓN 1

--Práctica SQL para tablas en PGadmin. 

Sentencias DDL

Data Definition Language

Operaciones con Bases de datos:

•	Crear base de datos: CREATE DATABASE employees2;
•	Borrar una base de datos: DROP DATABASE employees2;

Operaciones con Tablas:

•	Crear tablas: CREATE TABLE IF NOT EXISTS employees (...);

•	Borrar tablas: DROP TABLE IF EXISTS employees;

•	Cambiar el nombre de una tabla:
o	ALTER TABLE IF EXISTS employees RENAME TO employees_2021;

•	Agregar columnas a una tabla:
o	ALTER TABLE employees ADD COLUMN email VARCHAR(100);

•	Borrar columnas de una tabla:
o	ALTER TABLE employees DROP COLUMN IF EXISTS salary;


Tipos de datos en tablas:

•	INT
•	BOOLEAN
•	CHAR, VARCHAR, TEXT
•	NUMERIC
•	DATE
•	TIME
•	SERIAL
Restricciones en las columnas de las tablas:

•	PRIMARY KEY
•	NOT NULL
•	UNIQUE
•	CHECK






Sentencias DML
Data Manipulation Language
Operaciones CRUD:
•	==C==: Create --> INSERT INTO
•	==R==: Retrieve o Read --> SELECT FROM
•	==U==: Update --> UPDATE
•	==D==: Delete --> DELETE FROM


1. Recuperar datos (SELECT)
Recuperar todos los empleados:
SELECT * FROM employees;


2. Insertar nuevos datos (INSERT)
Insertar un nuevo empleado:
INSERT INTO employees (married, name, email, genre, salary, birth_date, start_at) VALUES (TRUE, 'Employee2', 'employee1@company.com', 'M', 29567.23, '1990-12-25', '08:30:00');





PostgreSQL

Puerto por defecto 5432.

Incorpora el programa pgAdmin.

MySQL

Puerto por defecto 3306.
Descargar MySQL Installer, ejecutar y seleccionar instalación completa para que instale:
•	MySQL Community Server
•	MySQL Workbench


Herramientas GUI
•	pgAdmin
•	MySQL Workbench
•	DBeaver
•	DataGrip
Conexión a bases de datos


•	PostgreSQL: abrir pgAdmin y crear nuevo servidor para conectarse con usuario:
o	usuario: postgres
o	password: admin
•	MySQL Workbench: Crear nueva conexión con los datos:
o	usuario: root
o	password: admin

Bases de datos de prueba
Para PostgreSQL:
•	pagila


SESIÓN 2

/* Sentencias DML: Data Manipulation Language
		CRUD: 
		
		Create (INSERT INTO)
		Read (SELECT FROM), 
		Update (UPDATE SET)
		Delete (DELETE FROM)
	*/
	

	-- 1. Consultas o recuperación de datos
	

	SELECT * FROM employees;
	

	SELECT id FROM employees;
	

	SELECT id, email FROM employees;
	

	SELECT email, id FROM employees;
	

	SELECT id, email, salary FROM employees;
	

	-- Filtrar filas
	SELECT * FROM employees WHERE id = 1;
	

	SELECT * FROM employees WHERE name = 'Employee1';
	

	SELECT * FROM employees WHERE married = 'true';
	

	SELECT * FROM employees WHERE married = TRUE;
	

	SELECT * FROM employees WHERE birth_date = '1990-12-25';
	

	SELECT * FROM employees WHERE married = TRUE AND salary > 10000;
	

	

	-- 2. Inserción de datos
	

	INSERT INTO employees(name, email) VALUES ('Juan', 'juan@company.com');
	

	INSERT INTO employees(name, email, married, genre, salary) 
	VALUES ('antonio4', 'antonio4@company.com', TRUE, 'M', 23566.43);
	

	INSERT INTO employees(name, email, married, genre, salary, birth_date, start_at) 
	VALUES ('francisco', 'francisco@company.com', TRUE, 'M', 23566.43, '1987-5-29', '10:00:00');
	

	INSERT INTO employees(name, email, married, genre, salary, birth_date, start_at) 
	VALUES ('Rosa', 'rosa@company.com', FALSE, 'F', 34543.43, '1990-5-29', '10:00:00');
	

	INSERT INTO employees(name, email, married, genre, salary, birth_date, start_at) 
	VALUES ('Alberto', 'alberto@company.com', FALSE, 'M', 32421.43, '1988-5-29', '10:00:00');
	

	INSERT INTO employees
	VALUES (9, TRUE, 'francisco3', 'francisco3@company.com', 'M', 23566.43, '1987-5-29', '10:00:00');
	

	

	-- 3. Actualizar o editar
	

	UPDATE employees SET birth_date = '2000-03-12';
	

	UPDATE employees SET birth_date = '2000-03-12' WHERE id = 5;
	

	UPDATE employees SET salary = 45000 WHERE email = 'juan@company.com';
	

	UPDATE employees SET genre = 'M', start_at = '08:30:00' WHERE email = 'juan@company.com';
	

	UPDATE employees SET genre = 'M', start_at = '08:30:00' WHERE email = 'noexiste@company.com';
	

	UPDATE employees SET genre = 'M', start_at = '08:30:00' WHERE email = 'juan@company.com' RETURNING *;
	

	UPDATE employees SET genre = NULL WHERE id = 14;
	

	-- 4. Borrar
	SELECT * FROM employees;
	

	DELETE FROM employees;
	

	DELETE FROM employees WHERE married = TRUE;
	

	DELETE FROM employees WHERE salary < 33000;
	

	DELETE FROM employees WHERE salary IS NULL;











