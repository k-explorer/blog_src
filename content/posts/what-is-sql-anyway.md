---
title: "What Is SQL Anyway?"
date: 2021-04-26T08:48:10-07:00
draft: false
---

Structured Query Language, or SQL, is a language used for the manipulation and querying of databases. Let’s have an example:

{{< highlight sql>}}
SELECT *
FROM Lemurs
WHERE Name = "Blue-eyed Black Lemur"
{{< / highlight >}}


SQL is not like HTML. You can’t open an SQL file in a browser and see a pretty-printed table as a result. It just doesn’t work that way. Here is some reasoning:

  1. How is the browser going to know which database to query?
      * OK. I admit that it’s possible to specify that information in the SQL file.
  2. Is it possible to get around the embedded language problem?
      * This needs some explanation: to run HTML in a browser, an HTML interpreter has to come packaged with the browser. However, HTML is not a particularly complex language, so this is alright. An SQL interpreter, however, will make things _very_ slow if packaged with an application. Handle all browser redirects, HTML, JavaScript, as well as SQL wouldn’t work easily. But, again, JavaScript libraries that send off SQL queries (I mean [IndexedDB][1] and [SQL.JS][2]) are well supported in browsers.

Why doesn’t SQL run in a browser? Here is a revelation. SQL _does_ run in a browser, and effectively. All [SQL libraries][3] (except [SQLite][4]) use a web server. Every website is a web server of some kind. If you’ve installed an SQL library on your system, this web server will be “http://localhost", a colon, and then a numerical server port. For example, when I run a web server, I like to use <http://localhost:31845>. Let me backtrack and explain **ports**. Any web server can have a port. Usually, a web server that isn’t a website, that is, a web server that isn’t displaying info but running a background server process (like SQL), will have port numbers to organize processes. Even regular websites have ports, but they're not used at all. For example, <https://www.google.com:31845>, is an existing port, but if you try to visit it, the browser will load never-endingly because nothing is there, not even a process. Back to SQL. Like I said (or typed), all [SQL libraries][3] (except [SQLite][4]) use a web server. They process queries via the web server, and display the result in an application on your computer, or a command line utility.

## SQL Libraries {#sql-libraries}

Multiple libraries used to run SQL exist. The following list will briefly acquaint you with the most commonly used ones. 

  1. SQLite
      * SQLite is my preferred library, as it it small, fast, and does _not_ require a web server or complicated configuration. It is used to store information such as user profiles in many apps, and is preinstalled on Mac, Windows, and Linux machines. It is useful in production and in development.
  2. MySQL
      * Uses a web server. MySQL started out as a community project, but was acquired by Oracle Corporation. It has stayed open-source, and is a popular option for production. 
  3. PostgreSQL, or Postgres
      * The name comes from the fact that Postgres is the successor to the Ingres database, which was developed at the University of California, Berkeley. Postgres is very similar to MySQL and is equally popular for production.
  4. MariaDB
      * MariaDB is extremely similar to MySQL. It was forked from the original project when MySQL was acquired by Oracle. MySQL's creator, Michael Widenius, thought that Oracle's owning MySQL would be problematic, as Oracle already had their own library, Oracle DB, and might not give MySQL any attention. MariaDB and MySQL are few differences, except that 
          * MariaDB has stayed a community project
          * MariaDB is _slightly_ less used.
          * The list of languages that can be used to connect to either of the databases is different, though not significantly.
      * The two databases are so similar that the MariaDB [ODBC][5] can be used to connect to MySQL!
  5. Apache Spark
      * Spark, built by the Apache Software Foundation, is not exactly an SQL library, but a Java based program for data manipulation similar to SQL. However, it does include an SQL component, Spark SQL, which makes it worth including on this list. 

## ODBC {#odbc}

An **O**pen **D**atabase **C**onnectivity, or ODBC, is an interface between the SQL library and the application. For example, LibreOffice Base, a popular database editor, uses ODBC to establish a connection between it and any of the SQL libraries it supports. JDBC (**J**ava **D**atabase **C**onnectivity) is also used for the same purpose, but only in applications made with Java.

## Syntax

Finally we arrive at SQL syntax. SQL's classic syntax is unique. It uses English words (see table below) to tell the library or ODBC connected application what to do.


| Statement | Description | Parameters|
| --------- | ----------- | --------- |
| SELECT    | Specify columns to display | Column names, separated by commas, or '\*' for 'all'|
| WHERE     | Narrow down results | Expression, e.g. 'Year > 2000' |
| UPDATE    | Change all values returned by a WHERE clause to a specific value | SET statement, e.g. "SET Name = 'Bushbaby'", and WHERE clause, e.g. "WHERE ID = 1" |
| ALTER     | ALTER metadata. Substatements include ALTER TABLE and ALTER COLUMN | ADD substatement or TO substatement. E.g. "ALTER TABLE ADD COLUMN Username" |
| DELETE    | Deletes values returned by a WHERE clause. Exactly like UPDATE. | See UPDATE. |


Of course there are some substatements, but these are the main ones. All in all, SQL is a complete data manipulation language.

Now you know what SQL is, so when you see an article on this website about it, you won't be scratching your head.

 [1]: https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API
 [2]: https://sql.js.org
 [3]: #sql-libraries
 [4]: https://sqlite.org
 [5]: #odbc
