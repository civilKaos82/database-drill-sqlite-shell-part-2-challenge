# Database Drill: Exporting and Dumping Data 
 
##Summary 

 For this challenge we will continue using the students database and learn how to modify the data.  [Download the 'students.db' file](https://github.com/downloads/dbc-challenges/binary_store/DB02_SQL_students.db).

Load up the DB file into sqlite3 - `sqlite3 students.db`.  You should now be in SQLite shell.

Orient yourself by typing `.schema`.  Notice all the columns that are available to query!  See if there are other database tables by typing `.tables`.  See all the database files open by typing `.databases`.

##Releases

###Release 0 : Update and Insert

Update the entry that has ID number '855' with a new email address.  It should now be jared.smith@hulu.com.  Then update Valentine Hackett's phone number to 415-346-4497.  Remember the `UPDATE` function?

View the entry with ID of 855 to make sure the email address has been updated.  Check to make sure Valentine's phone number has been changed too.

Now let's add a new student.  Her name is Julie Kravinski, born October 27th 1971, email julie@giants.com, phone number 415-399-5599.


#### SQL Shortcuts and Intricacies 

Chances are you wrote out a pretty long SQL statement to do that last `INSERT` statement to add Julie.  How could you shorten it?  Careful!  SQLite, just like PostgreSQL and MySQL, have subtle and annoying differences to the standard SQL language.  Make sure you use SQLite syntax for this!

Write out the traditional SQL shortcut way of inserting into a table along with your SQLite version.  What is the subtle difference between the two?

#### Delete in SQLite

Elvis Schuppe has decided to stay in the plumbing business.  Please delete him from the database.  Then delete the first 20 people in the database. Do it with ID numbers.

Some databases are different when selecting or deleting by ID numbers.  Some include the start/end numbers, others don't include the end number.  How does SQLite deal with ranges?

###Release 1 : Exporting and Dumping

Nice work!  It's time to export the whole database into a CSV file so it can be imported easily into Excel.  Use the `.help` command to figure out how to do this.  You'll need to set up the output and the mode!  Export the whole database into the file `students.csv`.  Quit out of Sqlite and view the file.  Cool?

Now let's do a database dump for a backup and so you can more easily import this into other datase systems.  Open up sqlite again, and set the output file to `students_sqlite3.dump`.  Now use the `.dump` command.
If you quit out of Sqlite again and mate the `students_sqlite3.dump` file, you'll see that it includes the create table and about 1000 insert statements.  This can recreate the students database!

So let's do it!  Go back into sqlite, but this time without loading a database - just type `sqlite3`.  Then type `.read students_sqlite3.dump`.  View the schema.  View all the database entries.    Voila!

Quit out of sqlite, do `subl sql_history.txt`, and paste the history of all your SQL commands into the source file `sqlite_shell_2.md`

<!-- ##Optimize Your Learning  -->

##Resources