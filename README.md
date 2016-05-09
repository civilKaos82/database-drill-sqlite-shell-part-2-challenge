# Database Drill: Exporting and Dumping Data 
 
## Summary 
We're going to look at a couple approaches for sharing the data in our database.  We'll start by exporting data into another format (e.g., CSV), and we'll finish by dumping our data into another file so that we can recreate our data in another database.


## Releases
### Release 0:  Exporting Data to CSV

Nice work!  It's time to export the whole database into a CSV file so it can be imported easily into Excel.  Use the `.help` command to figure out how to do this.  You'll need to set up the output and the mode!  Export the whole database into the file `students.csv`.  Quit out of Sqlite and view the file.  Cool?


### Release 1: Dumping Data
Now let's do a database dump for a backup and so you can more easily import this into other datase systems.  Open up sqlite again, and set the output file to `students_sqlite3.dump`.  Now use the `.dump` command.
If you quit out of Sqlite again and mate the `students_sqlite3.dump` file, you'll see that it includes the create table and about 1000 insert statements.  This can recreate the students database!

So let's do it!  Go back into sqlite, but this time without loading a database - just type `sqlite3`.  Then type `.read students_sqlite3.dump`.  View the schema.  View all the database entries.    Voila!

Quit out of sqlite, do `subl sql_history.txt`, and paste the history of all your SQL commands into the source file `sqlite_shell_2.md`

<!-- ##Optimize Your Learning  -->

##Resources