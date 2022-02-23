# Databases

[Database](https://www.codecademy.com/article/wix-what-is-a-database) - the definition.

[Quick SQL Course](https://www.codecademy.com/learn/learn-sql)- Learn to communicate with databases using SQL, the standard data management language.

## Types of Databases
The two most common types of databases are:
- relational - often tabular which suits itself to identifying and accessing data in relation to another piece of data
- non-relational - commonly referred to as NoSql, stores unstructured data and typically scales better

Read more on [types of databases](https://www.codecademy.com/article/what-is-a-database-codepedia).

### Relational Databases
A [relational database](https://www.codecademy.com/article/what-is-rdbms-sql) typically stores data in tables made of rows. A relational database management system RDBMS) is a program that allows you to administer a relational database and typically uses SQL to access the database. 

Popular relational database management systems include:
- [MySQL](https://www.mysql.com/)
- [PostgreSQL](https://www.postgresql.org/)
- [Oracle DB](https://www.oracle.com/database/)
- [SQL Server (Microsoft)](https://www.microsoft.com/en-us/sql-server/sql-server-2017)
- [SQLite](https://www.sqlite.org/) 

### Non-Relational Databases
A non-relational or NoSQL database has a flexible schema and can take a variety of forms. A key-value store is the simplest type where all of the data is in a single table and contains a unique key and a value. A document database stores the data in some form of document like JSON or XML and particular elements can be indexed for faster querying. A column-based or column-oriented database is one where the data becomes the main key rather than an id. A graph databases focuses on the relationship between data elements where each element is stored as a node and connected to other nodes via links.

Popular non-relational databases include:
- [Redis](https://redis.io/) - a key-value store
- [MongoDB](https://www.mongodb.com/) - uses a document data model
- [Cassandra](https://cassandra.apache.org/) - column-based database
- [Neo4J](https://neo4j.com/) - a graph database

### Which type of database do I use?
This question has no simple answer. But here are some aspects to consider when making a decision:
- Language: Relational databases almost always speak SQL where as NoSQL does not. 
- Scalability: NoSQL is typically better suited for large datasets and analyics. SQL databases typically vertically scale meaning that the load is all on one server. NoSQL databases are horizontally salable meaning that you can add more servers by sharding or breaking apart the data.
- Schema design: NoSQL databases have a flexible schema where as SQL databases have a schema which is defined and more difficult to change. SQL's schema allows for multi-row transactions.
- Community: There are different communities around SQL and NoSQL because SQL has existed for so much longer. There are also communities around specific tools and the difference between proprietary products versus open-source products that one might want to consider.

## Assessment Questions

1. What is SQL?
2. What is NoSQL?
