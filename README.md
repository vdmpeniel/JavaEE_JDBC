Clase 1:
	JDBC significa Java Data Base Conenectivity
	Es un driver que nos ayuda a conectarnos con un sistema gestor de base de datos

	proporciona acceso a varios SGBD (En ingles: DBMS)
	Establece una conexion
	Permite la manipulacion de una BBDD
		Utilizando SQL
	Cada driver es proporcionado por el propio fabricante del respectivo SGBD

	JAVA ----> JDBC -----> SGBD: Sybase, Microsoft SQL Server, MySQL, MariaDB, Oracle, Access... etc


	Para establecer la conexion entre Java y nuestro SGBD vamos a necesitar manejar dos
	paquetes fundamentalmente:
		Java.sql y Javax.sql

	Estos paquetes contienen clases e interfaces con sus correspondientes metodos que nos van a permitir 
	realizar la conexion y la manipulacion de la informacion. Los mas utilizados son:

	Clase DriverManager

	Interfaces ResultSet, Connection, Statement, DataSource

	
	El proceso a segir desde que establecemos la conexion hasta que logramos leer los datos devueltos es como
	sigue:
	Establecer conexion ---> Crear objeto Statement ---> Ejecutar sentencia SQL ---> Leer resultSet devuelto al ejecutar la sentencia SQL

	
	Paso 1: 
		Establecer conexion
		Necesitamos una cadena de conexion para crear un objeto de tipo conexion
	
		Ejemplos:
			jdbc:mysql://localhost:9999/gestionPedidos

			jdbc:odbc:DNS_gestionPedidos

			jdbc:oracle:usuario@servidor:9999:gestionPedidos


		Vamos a necesitar datos adicionales al conectarnos a un SGBD como por ejemplo usuario y contrasena

		Las conexiones pueden lanzar excepciones, por ejemplo porque la cadena de conexion hayan sido escritas incorrectamente
		o porque haya un problema de comunicacion con el servidor
		Esto por supuesto significa que nuestro codigo necesitara estar dentro de un bloque try/catch

	Paso 2:	
		Crear objeto de tipo statement
		Con nuestro objeto conexion creado podemos usar el metodo createStatement() lo cual nos va a devolver un objeto de 
		tipo statement.

	Paso 3:
		Con el objeto statement ya en existencia podemos llamar a su metodo executeQuery("SQL query") lo cual va a ejecular la sentencia SQL
		y nos devolvera un objeto de tipo resulrSet que es una tabla virtual (almacenado en memoria)

	Paso 4:
		Dado el objeto resultset vamos a recorrerlo para obtener los datos deseados.
		Puede usarse getString() o next() con un bucle while, until, etc 


	Para hacer nuestras pruebas practicas vamos a utilizar un servidor local del tipo MySQL o mariaDB


































































































