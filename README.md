# GerDB
Gerador de Banco de Dados
Gerenciador de Banco de Dados Sql Server Compact

Some of the functions you can perform in a SQL Server Compact database include the following:

------ Creating, deleting, and editing tables and the associated data.

------ Creating, maintaining, and deleting indexes.

------ Examining information schema views and data types.

Limitations

Storage
 Column name
 128 characters
 
  
 Columns in a table
 1024
 

 Row size
 8060 bytes
 
  
 Database password
 40 characters
 
  
 Database size
 4 GB 1 
 
  
 Database size increase
 1-page or 16-page increments, depending on table size
 
  
 Page size
 4 KB
 
  
 Sessions
 256
 
  
 Size of BLOB (ntext and image) column
 2 GB
 
  
 Table name
 128 characters
 
  
 Table size
 Unlimited
 
SQL Server Compact 4.0 supports the following data types.

Data Type
 Description 
 
bigint
 Integer (whole number) data from –2^63 (–9,223,372,036,854,775,808) through 2^63–1 (9,223,372,036,854,775,807). Storage size is 8 bytes.
 
integer
 Integer (whole number) data from –2^31 (–2,147,483,648) through 2^31–1 (2,147,483,647).

Storage size is 4 bytes.
 
smallint
 Integer data from –32,768 to 32,767. Storage size is 2 bytes.
 
tinyint
 Integer data from 0 to 255. Storage size is 1 byte.
 
bit
 Integer data with a value of either 1 or 0.

Storage size is 1 bit.
 
numeric (p, s)

Synonyms:

decimal(p,s) and dec (p,s)
 Fixed-precision and scale-numeric data from –10^38+1 through 10^38–1. The p variable specifies precision and can vary between 1 and 38. The s variable specifies scale and can vary between 0 and p.

Storage size is 19 bytes.
 
money
 Monetary data values from (–2^63/10000) (–922,337,203,685,477.5808) through 2^63–1 (922,337,203,685,477.5807), with accuracy to a ten-thousandth of a monetary unit. Storage size is 8 bytes.
 
float
 Floating point number data from –1.79E +308 through 1.79E+308

Storage size is 8 bytes.
 
real
 Floating precision number data from –3.40E+38 through 3.40E+38.

Storage size is 4 bytes.
 
datetime
 Date and time data from January 1, 1753, to December 31, 9999, with an accuracy of one three-hundredth second, or 3.33 milliseconds. Values are rounded to increments of .000, .003, or .007 milliseconds.

Stored as two 4-byte integers. The first 4 bytes store the number of days before or after the base date, January 1, 1900. The base date is the system's reference date. Values for datetime earlier than January 1, 1753, are not permitted. The other 4 bytes store the time of day represented as the number of milliseconds after midnight. Seconds have a valid range of 0–59.

Format
 Example
 
yyyy/mm/dd hh:mm:ss
 1947/08/15 03:33:20
 
mm/dd/yyyy hh:mm:ss
 04/15/1947 03:33:20
 
dd mmm yyyy hh:mm:ss
 15 Jan 1947 03:33:20
 
dd mmmm yyyy h:mm:ss
 15 January 1947 03:33:20
 

 
national character(n)

Synonym:nchar(n)
 Fixed-length Unicode data with a maximum length of 4000 characters. Default length = 1. Storage size, in bytes, is two times the number of characters entered.
 
national character varying(n)

Synonym:nvarchar(n)
 Variable-length Unicode data with a length of 1 to 4000 characters. Default length = 1. Storage size, in bytes, is two times the number of characters entered.
 
ntext¹
 Variable-length Unicode data with a maximum length of (2^30–2)/2 (536,870,911) characters. Storage size, in bytes, is two times the number of characters entered.

NoteNote 
ntext is no longer supported in string functions.
 

 
nchar
 Fixed-length Unicode character data of n characters. n must be a value from 1 through 4,000. The storage size is two times n bytes.
 
binary(n)
 Fixed-length binary data with a maximum length of 8000 bytes. Default length = 1.

Storage size is fixed, which is the length in bytes declared in the type.
 
varbinary(n)
 Variable-length binary data with a maximum length of 8000 bytes. Default length = 1.

Storage size varies. It is the length of the value in bytes.
 
image¹
 Variable-length binary data with a maximum length of 2^30–1 (1,073,741,823) bytes.

Storage is the length of the value in bytes.
 
uniqueidentifier
 A globally unique identifier (GUID). Storage size is 16 bytes.
 
IDENTITY [(s, i)]
 This is a property of a data column, not a distinct data type.

Only data columns of the integer data types can be used for identity columns. A table can have only one identity column. A seed and increment can be specified and the column cannot be updated.

s (seed) = starting value

i(increment) = increment value
 
ROWGUIDCOL
 This is a property of a data column, not a distinct data type. It is a column in a table that is defined by using the uniqueidentifier data type. A table can have only one ROWGUIDCOL column.
 
Timestamp/rowversion
 This is an automatically generated unique binary number.

Storage size is 8 bytes.
 

CREATE DATABASE databaseName 
   [DATABASEPASSWORD '<enterStrongDatabasePasswordHere>' 
      
   ]
   [COLLATE collationName comparisonStyle] 
database password ::= identifier


CREATE DATABASE "SpanishDB.sdf" DATABASEPASSWORD '<enterStrongPasswordHere>' COLLATE Traditional_Spanish_CI_AS