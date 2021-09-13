<a name="top"></a> <br>
![Shield](https://img.shields.io/badge/Tarea%203-La%20tarea%20esta%20terminada-blue) <br> <br>
![This is an image](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/Firma_TEC.svg/1280px-Firma_TEC.svg.png)
## Tarea #3: Estandar de nombres || Base de Datos					
#### Estudiante: Bryan Pérez Rojas 
#### Carnet: 2017120035

## Introducción
El siguiente documento tiene el fin único de mostrar una guía al utilizar SQL, esto con el fin de mantener
un estandar para lograr crear una base de datos en un equipo de una manera más legible y que todos puedan
utilizar un mismo método al crear las tablas, llaves primarias y distintos atributos que se lleguen a utilizar.
Más adelante se encontrará un índice donde se podrá observar las distintas áreas a cubrir, al hacer clic sobre
cualquiera de los títulos en el índice, se dirigirá inmediatamente al apartado seleccionado. 

***¿Alguna vez se han preguntado si existe una forma correcta de escribir SQL?***<br>
La respuesta es que sí y no, todos tenemos una forma distinta de hacer las cosas, pero se podría decir que hay
de alguna manera un camino en que podamos estandarizar el cómo hacemos esto.

## Justificación
En el área del desarrollo de bases de datos o inclusive en programación, podemos llegar a encontrar un sin fin de 
métodos al desarrollar o crear una nueva base de datos, inclusive para llegar a entenderlas cuando leemos documentos
existen diferentes estándares. 

Si nos encontramos dentro de una empresa que apenas va a empezar con el desarrollo,  lo esencial para un futuro e 
inclusive para el momento en que se está llevando a cabo sería tener un estándar para el grupo de desarrolladores, 
ya que si no se encuentra ninguna guía, podríamos llegar a crear algo que unos entenderán una parte y otros solo 
otra parte, lo que se desearía es que todos podamos entender lo que se ha hecho y para futuras personas que entren 
a la empresa que puedan entender sin ningún problema y llegar a agregar nuevas funciones con este mismo estándar ya
establecido. <br>
El estándar que se utilizará en el siguiente documento es obtenido de [SQL Style Guide](https://www.sqlstyle.guide/), desarrollado por [Simon Holywell](https://www.simonholywell.com/).

Mi idioma preferido personalmente para hacer este desarrollo es el inglés, ya que esto nos permite crear un estándar 
más entendible y amplio para más personas, ya sea que estemos trabajando con personas de un mismo país o inclusive 
con un equipo de personas de distintos países. <br>
Aunque el inglés no sea 100% necesario para llegar a ser un desarrollador, gran parte de la buena documentación se 
encuentra en inglés y esto nos obliga de alguna manera a poder entenderlo para llegar a evacuar dudas o comprender
algunos procesos. 


## Índice de Contenidos

- [General](#1)  
    - [Que se debe hacer](#11)
    - [Que ***no*** se debe hacer](#12)
- [Reglas para el uso de nombres](#2)
    - [General](#21)
    - [Tablas](#22)
    - [Columnas](#23)
    - [Stored Procedures](#24)
- [Data Types](#3)
    - [Caracteres](#31)
    - [Numérico](#32)
    - [Otros tipos de datos](#33)
- [Primary Key and Foreign Key](#4)
    - [Primary Key](#41)
    - [Foreign Key](#42)
- [Palabras reservadas](#5)
- [Bibliografía](#6)


##  General <a name="1"></a>

En este apartado veremos un par de reglas generales de lo que se debería y ***no*** se debería hacer cuando estamos
creando una base de datos 

### Que se debe hacer <a name="11"></a>
- Utilizar identificadores y nombres consistentes y descriptivos. 
- Debemos utilizar espacios en blanco y de identación correctamente de manera que el código pueda leerse de manera más legible. 
- Usar el estándar ISO 8601 para datos de horas y fechas (YYYY-MM-DD HH:MM:SS.SSSSS).
- Intentar utilizar solamente funciones SQL por razones de portabilidad.
- Matener el código fuera de la redundancia, como por ejemplo el uso innecesario de paréntesis o `WHERE`.
- Incluir comentarios en el código SQL donde sea necesario. Utilizar el estilo C de /* para abrir y */ para cerrar donde sea posible,
también podríamos utilizar -- para hacer comentarios y al final del comentario crear una nueva linea. 

### Que ***no*** se debe hacer <a name="12"></a>
- Evitemos utilizar CamelCase, su lectura es complicada. 
- Uso de la notación húngara, como tbl o sp_.
- El uso de plurales, como es el caso del uso de "staff" en vez de "employees".
- No se deben usar los principios de diseño de programación orientada a objetos en SQL o estructuras de bases de datos.

## Reglas para el uso de nombres <a name="2"></a>

### General <a name="21"></a>
- Tomar en cuenta que el nombre es único y que no es una palabra reservada.
- No sobrepasar los 30 caracteres. 
- Los nombres deben iniciar con una letra y **no** deben terminar con un guion bajo [ _ ].
- Solamente debemos utilizar letras, números y guiones bajos.
- El uso de los guiones bajos es cuando normalmente tendríamos un espacio en blanco entre palabras.
- Evitar abreviaciones y si se utilizan, tener en cuenta que sean abreviaciones que normalmente se entiendan.

### Tablas <a name="22"></a>
Las tablas son objetos de base de datos que contienen todos sus datos. En las tablas, los datos se organizan con arreglo a un formato de filas y columnas.

- No utilizar un prefijo tal como tbl o alguna abreviación o algún otro tipo de notación húngara.
- No debemos nombrar una tabla con el mismo nombre de una de sus columnas o vice versa. 

### Columnas <a name="23"></a>
Una columna, campo o atributo es cada uno de los valores únicos (datos) que proporcionan la estructura según la cual se descomponen las filas (registros o tuplas) de una tabla.

- Utilizar nombres singulares.
- Siempre que sea posible, utilizar `id` como el identificar primario de la tabla.
- No agregar columnas con el mismo nombre que sus tablas.
- Intentar utilizar siempre letras minúsculas.

### Stored Procedures <a name="24"></a>
- El nombre debe contener un verbo.
- No utilizar prefijos como `sp_` o ningún tipo de notación húngara.


## Tipos de datos para las columnas <a name = "3"></a>

### Caracteres <a name = "31"></a>
- char: Pueden ir de 0 a 255. 
Ejemplo: En la tarea anterior creamos un char de 1, `estado char (1)`
- varchar: Puede ir de 0 a 65,535.
Ejemplo: De igual forma en la tarea usamos varchar, `nombre varchar (30)`. <br>
Este podríamos variarlo depende para lo que lo usemos, en el caso de mi nombre con un varchar de 30 sería
suficiente pero para estar seguros de que tendremos espacio suficiente podemos usar un varchar 50.

### Numérico <a name = "32"></a>
- smallint: Puede llegar a tener un valor en espacio hasta de 32767. El espacio es de 2 bytes por valor.
Ejemplo: `edad smallint`
- int: Pueder llegar a tener un valore en espacio hasta de 2147483647. El espacio es de 4 bytes por valor.
Ejemplo: `codigo_empleado int`

### Otros tipos de datos <a name = "33"></a>
En el siguiente link podemos ver los datos anteriores y otros más que se pueden llegar a utilizar
conforme los vamos necesitando: https://www.sqlstyle.guide/#column-data-types

## Primary and Foreign Keys <a name = "4"></a>

### Primary Key <a name = "41"></a>
Un primary key es esencial para cada tabla en una base de datos. Está diseñado para identificar de forma única cada registro de la tabla.
Ejemplo: `empresa_id int primary key auto_increment`. 
- Debe contener un valor único para cada fila de datos.
- No puede contener valores nulos.
- Cada fila debe contener un valor en el primary key.

### Foreign Key <a name = "42"></a>
Un foreign key es una columna o grupo de columnas en una tabla de base de datos relacional que proporciona un vínculo entre los datos de dos tablas. Trabaja como una conexión cruzada entre tablas porque hace referencia al primary key de otra table, de esta manera establece una conexión entre ellas. <br>
Ejemplo: `CONSTRAINT FK_Carnet_Estudiante FOREIGN KEY (carnet_estudiante) REFERENCES Estudiante (carnet)`


## Palabras reservadas <a name = "5"></a>
En el siguiente link podemos encontrar la lista de palabras reservadas para ANSI SQL (92, 99 and 2003), MySQL 3 to 5.x, PostgreSQL 8.1, MS SQL Server 2000, MS ODBC y Oracle 10.2<br> 
  ***Palabras reservadas:*** https://www.sqlstyle.guide/#appendix

### Bibliografía <a name = "6"></a>
* https://dev.mysql.com/doc/refman/8.0/en
* https://www.sqlstyle.guide/
* https://docs.microsoft.com/es-es/sql/relational-databases/tables/tables?view=sql-server-ver15#:~:text=Las%20tablas%20son%20objetos%20de,un%20campo%20dentro%20del%20registro
* https://es.wikipedia.org/wiki/Columna_(base_de_datos)
* https://www.techopedia.com/definition/5547/primary-key
* https://www.techopedia.com/definition/7272/foreign-key


[Ir al principio](#top)
