# Database Drill: Exporting and Dumping Data 
 
## Summary 
We're going to look at a couple approaches for sharing the data in our database.  We'll start by exporting data into another format (e.g., CSV), and we'll finish by dumping our data into another file so that we can recreate our data in another database.


## Releases
### Release 0:  Exporting Data to a File
Sometimes we want to share data from a database without giving access to the database itself.  Perhaps our database contains sensitive information like hospital patient records that we cannot legally share.  Or, we might need to share data with someone unfamiliar with SQL or who wants to work with the data in spreadsheet software like Microsoft Excel.  What can we do?  

Fortunately, most databases offer utilities for exporting data to other formats.  In the [command line shell for SQLite][SQLite] we can do this by configuring (1) the `.mode`, the output format of our queries, and (2) the `.output`, where we want to write the output (e.g., a specific file).

We've received a request to provide student demographic data from our student records database (`student_records.db`).  We need to provide only the gender and birthday of all students with phone numbers from area code 419 ordered from youngest to oldest.  Furthermore, we need to provide the data in a CSV file and formatted as CSV.

*Note:* See the file `example_results/students_in_area_code_419.csv` for expected output.


### Release 1: Dumping Data
Now let's do a database dump for a backup and so you can more easily import this into other datase systems.  Open up sqlite again, and set the output file to `students_sqlite3.dump`.  Now use the `.dump` command.
If you quit out of Sqlite again and mate the `students_sqlite3.dump` file, you'll see that it includes the create table and about 1000 insert statements.  This can recreate the students database!

So let's do it!  Go back into sqlite, but this time without loading a database - just type `sqlite3`.  Then type `.read students_sqlite3.dump`.  View the schema.  View all the database entries.    Voila!

Quit out of sqlite, do `subl sql_history.txt`, and paste the history of all your SQL commands into the source file `sqlite_shell_2.md`

<!-- ##Optimize Your Learning  -->

##Resources

[SQLite]: https://www.sqlite.org/cli.html