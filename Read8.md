# A Primer on SQL

SQL is a language for interacting with databases. It consists of a number of commands with further
options to allow you to carry out your operations with a database. While DBMS’s differ in the
command subset they provide, usually you would find the classifications below.


Data Definition Language (DDL) : `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE `etc.

Data Manipulation Language (DML) : `INSERT`, `UPDATE`, `DELETE`

Data Query Language (DQL) : `SELECT`

Data Control Language (DCL) : `GRANT`, `REVOKE` etc.

Transaction Control Commands : `COMMIT`, `ROLLBACK` etc.

Besides these, your database management system may give you other sets of commands to work
more efficiently or to provide extra features. But it is safe to say that the ones above would be
present in almost all DBMS’s you encounter.

## Explaining Tables

A table in a relational database is nothing but a matrix of data where the columns describe the type
of data and the row contains the actual data to be stored. Have a look at the figure below to get a
sense of the visualization of a table in a database.

Just like programming languages, SQL also has data types to define the kind of data that will be
stored in its fields. In the table given above, we can see that the fields language and author must
store English language characters. Thus their data type during table creation should be specified as
varchar which stands for variable number of characters.


* Fixed length characters char
* Integer values int
* Decimal numbers decimal
* Date data type date

## Getting your database ready

### Using Ingres

The best way to learn SQL is to practice writing commands on a real relational database. In this book
SQL is taught using a product called Ingres. The reasons for choosing Ingres are simple - it comes
in a free and open source edition, it’s available on most major platforms and it’s a full-fledged
enterprise class database with many features. However, any relational database product that you
can get your hands on should serve you just fine. There might be minor incompatibilities between
different vendors, so if you choose something else to practice on while reading this book, it would
be a good idea to keep the database vendor’s user manual handy.
Since this text deals largely with teaching SQL in a product independent manner, rather than the
teaching of Ingres per se, details with respect to installation and specific operations of the product
will be kept to a minimum. Emphasis is instead placed on a few specific steps that will help you to
get working on Ingres as fast as possible.
The current version of Ingres during the writing of the book was 10.1 and the Community Edition
has been used on a Windows box for the chapters to follow. The installation itself is straightforward
like any other Windows software. However if you are unsure on any option, ask your DBA (database
administrator, in case one is available) or if you are practicing on a home box - select the ‘Traditional
Ingres’ mode and install the Demo database when it asks you these questions. Feel free to refer to
the Ingres installation guide that is available on the web at the following location. Ingres Installation
Guide¹
If your installation is successful, you should be able to start the Ingres Visual DBA from the Start
Menu. This utility is a graphical user interface to manage your Ingres databases, but we will
keep the usage of this to a minimum since our interest lies in learning SQL rather than database
administration.
