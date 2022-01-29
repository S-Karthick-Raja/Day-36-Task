# Day-36-Task


--The Following are the tables has to be in your database & model deisgn:
[users, codekata, attendance, topics, tasks, company_drives, mentors, students_activated_courses, courses]

--The following are the queries need to be executed

1. Create tables for the above list given

--ANSWER:
    CREATE TABLE ZenDataBase(
    Users varchar(45),
    Codekata integer,
    Attendance integer,
    Topics integer,
    Tasks integer,
    Company_drives integer,
    Mentors varchar(45),
    Students_activated_courses integer,
    Courses varchar(45)
)

2. insert at least 5 rows of values in each table

--ANSWER:
INSERT INTO ZenDataBase(
    Users,
    Codekata,
    Attendance,
    Topics,
    Tasks,
    Company_drives,
    Mentors,
    Students_activated_courses,
    Courses
) VALUES
    ("Sathish.K", 56, 90, 40, 14, 0, "Divya", 1, "Fullstack Developer"),
    ("Santhosh.S", 60, 90, 40, 95, 0, "Yokesh", 1, "Fullstack Developer"),
    ("Ragav.P", 134, 80, 90, 65, 0, "Ragavkumar", 1, "DataScientist"),
    ("Yokesh.C", 190, 37, 36, 75, 0, "Kingston", 1, "Fullstack Developer"),
    ("Sivamani.R", 170, 20, 90, 25, 0, "Rajesh", 1, "Ethical Hacking")

3. get number problems solved in codekata by combining the users

--ANSWER:
SELECT sum(Codekata) 
as Total_solved_codekata 
FROM ZenDataBase

4. display the no of company drives attended by a user

--ANSWER:
SELECT Users, Company_drives 
FROM ZenDataBase

5. combine and display students_activated_courses and courses for a specific user groping them based on the course

--ANSWER:
SELECT Courses,count(Courses) 
as 
Users,Students_activated_courses 
FROM 
ZenDataBase 
GROUP BY Courses 
ORDER BY Courses desc

6. list all the mentors

--ANSWER:
SELECT Mentors FROM ZenDataBase

7. list the number of students that are assigned for a mentor

--ANSWER:
SELECT Mentors,
count(Users) as Students 
FROM ZenDataBase 
GROUP BY Mentors
ORDER BY Students 
