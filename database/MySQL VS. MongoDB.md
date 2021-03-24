# MySQL vs. MongoDB

- [Reference](https://www.guru99.com/mongodb-vs-mysql.html)
- Mysql: Database --> Schema --> Table
- MongoDB: Database --> Collection --> Document

|                         **MongoDB**                          |                          **MYSQL**                           |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|        MongoDB represents data as **JSON documents**.        |        MySQL represents data in **tables** and rows.         |
| In MongoDB, you **don't need to define the schema**. Instead, you **just drop in documents** don't even need to have the same fields. | MySQL requires you to **define your tables and columns** before you can store anything, and every row in a table must have the same columns. |
| MongoDB has a pre-defined structure that can be defined and adhered to, but also, if you need different documents in a collection, **it can have different structures.** | MySQL uses Structured Query Language (SQL) for database access. **You can't change the schema.** |
| MongoDB supports built-in replication, sharding, and auto-elections. | MySQL supports master-slave replication and master replication. |
| If most of your services are cloud based MongoDB is the best suited for you. | If data security is your priority then MYSQL is the best option for you. |
|     MongoDB places **no restrictions on schema design**.     | MySQL requires you to **define your tables and columns before you can store anything.** Every row in a table must have the same columns. |
|          MongoDB uses JavaScript as query language.          |       MySQL uses the Structured Query Language (SQL).        |
|                MongoDB doesn't support JOIN.                 |               MySQL supports JOIN operations.                |
|   It has the ability to handle **large unstructured data**   | MySQL is quite **slow** in comparison to MongoDB **while dealing with large databases.** |
| **Real-time analytics, content management, internet of things, mobile apps** |              Structured data with clear schema               |
| No schema definition required so lesser risk of attack due to design |                Risk of SQL injection attacks                 |
| An ideal choice if you have unstructured and/or structured data with the potential for rapid growth. | A great choice if you have structured data and need a traditional relational database. |