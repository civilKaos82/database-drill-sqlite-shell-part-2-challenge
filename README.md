# Database Drill: Exporting and Dumping Data 
 
## Summary 
We're going to look at a couple approaches for sharing the data in our database.  We'll start by exporting data into another format (e.g., CSV), and we'll finish by dumping our data into another file so that we can recreate our data in another database.


## Releases
### Release 0:  Exporting Data to a File
Sometimes we want to share data from a database without giving access to the database itself.  Perhaps our database contains sensitive information like hospital patient records that we cannot legally share.  Or, we might need to share data with someone unfamiliar with SQL or who wants to work with the data in spreadsheet software like Microsoft Excel.  What can we do?  

Fortunately, most databases offer utilities for exporting data to other formats.  In the [command line shell for SQLite][SQLite] we can do this by configuring (1) the `.mode`, the output format of our queries, and (2) the `.output`, where we want to write the output (e.g., a specific file).

We've received a request to provide student demographic data from our student records database (`student_records.db`).  We need to provide only the gender and birthday of all students with phone numbers from area code 419 ordered from youngest to oldest.  Furthermore, we need to provide the data in a CSV file and formatted as CSV.

*Note:* See the file `example_results/students_in_area_code_419.csv` for expected output.


### Release 1:  Dumping Data
Databases also provide methods for *dumping* their data: the database can output a series of SQL queries that could be used to recreate the database.  The output can be used as a backup or as a way of importing data into another database.

We're going to create a dump of our database and then read it into a new database.  To begin, open the SQLite command line shell connected to our student records database.  Set up the `.output` to write to a file (e.g., `student_records.dump`) and then use the `.dump` command to create the database dump.  Close the SQLite command line shell and take a look at the output file.

The output file now contains a series of SQL statements that will recreate the students table and the data in the table.  So, let's recreate it!  Reopen the SQLite command line shell, but this time without specifying a database - just type `sqlite3`.  Then use the `.read` command to execute the SQL in our output file.  View the schema and the entries in the recreated `students` table.  Voila!  Our data has been moved from one database to another.


## Conclusion
Moving data from one database to another database or converting it to another format isn't something that we'll do everyday at Dev Bootcamp, but we should be aware of the possibility and understand conceptually what is happening.


[SQLite]: https://www.sqlite.org/cli.html