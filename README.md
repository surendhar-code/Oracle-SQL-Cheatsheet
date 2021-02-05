# Oracle SQL Cheatsheet

This Repository contains the basics of oracle sql for quick references

**Basic create, Insert and Display**

```sql
/* Create Table students */
CREATE TABLE students( name VARCHAR2(30), email VARCHAR2(50), dob DATE, branch VARCHAR2(10));

/* Insert values into table */
INSERT INTO students(name,email,dob,branch) VALUES('ashwin prasad','ashwinprasad202@gmail.com','09-Mar-2002','csbs');

/* Insert multiple rows */
INSERT ALL
INTO students(name,email,dob,branch) VALUES('johndoe','johndoe@gmail.com','01-Nov-2001','cse')
INTO students(name,email,dob,branch) VALUES('janedoe','janedoe@gmail.com','05-Dec-2000','csbs')
INTO students(name,email,dob,branch) VALUES('Luffy','luffy@gmail.com','21-Feb-2005','mech')
SELECT 1 FROM dual;

/* display all students from table */
SELECT * FROM students;

/* delete table */
DROP TABLE students;
```

**Altering Table and Columns**

```sql
/* add a new column */
ALTER TABLE students ADD(location VARCHAR2(30));

/* make email id primary key*/
ALTER TABLE students ADD CONSTRAINT empk PRIMARY KEY(email);

/* modify a particular column */
ALTER TABLE students MODIFY(branch VARCHAR2(5));
```

**Updating values in a Table**

```sql
/* update the location of a student */
UPDATE students SET location='nanganllur' WHERE email='luffy@gmail.com';
```

**Filtering**

```sql
/* filtering students based on branch */
SELECT * FROM students WHERE branch='csbs';

/*(selection and projection) */
SELECT name from students WHERE branch='csbs';

/* selecting multiple columns as a single column */
SELECT name||' - '||email FROM students;

/* using alias to change column title */
SELECT name||' - '||email AS "Basic Student Info" FROM students;
```
