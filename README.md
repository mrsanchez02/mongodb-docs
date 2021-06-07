# **MongoDB**
## **La base de datos líder para aplicaciones modernas**

MongoDB es una base de datos distribuida, basada en documentos y de uso general que ha sido diseñada para desarrolladores de aplicaciones modernas y para la era de la nube. Ninguna otra ofrece un nivel de productividad de uso tan alto.

## **Como programador, seguramente pensará en objetos. Ahora, también lo hace así su base de datos.**

MongoDB es una base de datos documental, lo que significa que almacena datos en forma de documentos tipo JSON. Creemos que esta es la forma más natural de concebir los datos; frente al tradicional modelo de filas y columnas, esta es mucho más expresiva y potente.

### **Documentos JSON ricos**

* La forma más natural y productiva de trabajar con datos.
* Admite matrices y objetos anidados como valores.
* Trabaje con esquemas dinámicos y flexibles.

### **Potente lenguaje de consulta**

* Lenguaje de consulta rico y expresivo que permite filtrar y ordenar por cualquier campo, independientemente de cómo esté incrustado en un documento.
* Admite agregaciones y otros casos de uso modernos, como búsqueda de gráficos o texto, y búsqueda basada en información geoespacial.
* Las propias consultas son también JSON, por lo que se programan fácilmente. Olvídese de concatenar cadenas para generar consultas SQL de forma dinámica.

### **Todo el poder de una base de datos relacional y mucho más...**
* Transacciones ACID completas.
* Admite combinaciones en las consultas.
* Dos tipos de relaciones en vez de una: referencia e incrustada.

## **Comandos basicos de mongodb**

The mongo shell provides various help. The following table displays some common help methods and commands:

|Command|Description|
|---|---|
|`db.help()`|Show help for database methods.|
|`show dbs`|Print a list of all databases on the server.|
|`use <db>`| Switch current database to <db>. The mongo shell variable db is set to the current database.|
|`show collections`|Print a list of all collections for current database.|
|`show users`|Print a list of users for current database.|
|`show roles`|Print a list of all roles, both user-defined and built-in, for the current database.|
|`show profile`|Print the five most recent operations that took 1 millisecond or more. See documentation on the database profiler for more information.|
|`show databases`|Print a list of all available databases.|

## **Basic Shell JavaScript Operations**

The mongo shell provides a JavaScript API for database operations.

In the mongo shell, db is the variable that references the current database. The variable is automatically set to the default database test or is set when you use the use <db> to switch current database.

The following table displays some common JavaScript operations:

|Command|Description|
|---|---|
|`db.auth()`|If running in secure mode, authenticate the user.|
|`db.collection.find()`|Find all documents in the collection and returns a cursor.|
|`db.collection.insertOne()`|Insert a new document into the collection.|
|`db.collection.insertMany()`|Insert multiple new documents into the collection.|
|`db.collection.updateOne()`|Update a single existing document in the collection.|
|`db.collection.updateMany()`|Update multiple existing documents in the collection.|
|`db.collection.save()`|Insert either a new document or update an existing document in the collection.|
|`db.collection.deleteOne()`| Delete a single document from the collection.|
|`db.collection.deleteMany()`|Delete documents from the collection.|
|`db.collection.drop()`| Drops or removes completely the collection.|
|`db.collection.createIndex()`|Create a new index on the collection if the index does not exist; otherwise, the operation has no effect.|

## **Queries**

In the mongo shell, perform read operations using the `find()` and `findOne()` methods.

The `find()` method returns a cursor object which the mongo shell iterates to print documents on screen. By default, mongo prints the first 20. The mongo shell will prompt the user to "Type it" to continue iterating the next 20 results.

The following table provides some common read operations in the mongo shell:

|Read Operations|Description|
|---|---|
|`db.collection.find(<query>)`|Find the documents matching the <query> criteria in the collection. If the <query> criteria is not specified or is empty (i.e {} ), the read operation selects all documents in the collection.|
|`db.collection.find().sort(<sort order>)`|Return results in the specified <sort order>.|
|`db.collection.find(<query>).sort(<sort order>)`|Return the documents matching the <query> criteria in the specified <sort order>.|
|`db.collection.find( ... ).limit( <n> )`|Limit result to <n> rows. Highly recommended if you need only a certain number of rows for best performance.|
|`db.collection.find( ... ).skip( <n> )`| Skip <n> results.|
|`db.collection.count()`| Returns total number of documents in the collection.|
|`db.collection.find(<query>).count()`| Returns the total number of documents that match the query. The count() ignores limit() and skip(). For example, if 100 records match but the limit is 10, count() will return 100. This will be faster than iterating yourself, but still take time.|
|`db.collection.findOne(<query>)`|Find and return a single document. Returns null if not found.|

## **Administrative Command Helpers**

The following table lists some common methods to support database administration:

|JavaScript Database Administration Methods|Description|
|---|---|
|`db.fromColl.renameCollection(<toColl>)`|Rename collection from fromColl to <toColl>. See Naming Restrictions.|
|`db.getCollectionNames()`|Get the list of all collections in the current database.|
|`db.dropDatabase()`|Drops the current database.|

## **Opening Additional Connections**
You can create new connections within the mongo shell.

The following table displays the methods to create the connections:
|JavaScript Connection Create Methods|Description|
|---|---|
|`db = connect("<host><:port>/<dbname>")`|Open a new database connection.|
|`conn = new Mongo()` |Open a connection to a new server using `new Mongo()`.|
`db = conn.getDB("dbname")`|Use `getDB()` method of the connection to select a database.|