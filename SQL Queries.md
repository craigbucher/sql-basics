<!-- Select all rows from the classes table. -->

    select * from classes;

<!-- Select the name and credits from the classes table where the number of credits is greater than 3. -->

    select * from classes where credits > 3;

<!-- All rows from the classes table where credits is an even number. -->

    select * from classes where mod(credits,2) = 0;

<!-- All of Tianna's enrollments that she hasn't yet received a grade for. -->

    select * from enrollments left join students on enrollments.student_id=students.id where grade is NULL and student_id = 1;

<!-- All of Tianna's enrollments that she hasn't yet received a grade for, selected by her first name, not her student.id -->

    select * from enrollments left join students on enrollments.student_id=students.id where grade is NULL and students.first_name = 'Tianna';

All of Tianna's enrollments that she hasn't yet received a grade for, selected by her first name, not her student.id, with the class name included in the result set.

<!-- All students born before 1986 who have a 't' in their first or last name. -->

    select * from students where first_name like '%T%' or first_name like '%t%' or last_name like '%T%' or last_name like '%t%' and birthdate < '1986/01/01';

<!-- The average age of all the students. -->

    select AVG(AGE(birthdate)) from students;

<!-- Addresses that have a space in their city name. -->

    select * from addresses where city like '% %';

<!-- Students & their addresses that live in a city with more than one word in the city name. -->

    select * from addresses where city like '% %';

    or

    select * from addresses where LENGTH(city) - LENGTH(REPLACE(city, ' ', '')) = 1;

<!-- The average number of credits for classes offered at the school. -->

    select ROUND(AVG(credits), 2) from classes;

<!-- The first and last name of all students who have received an 'A'. -->

Each student's first name and the total credits they've enrolled in

The total number of credits each student has received a grade for.

<!-- All enrollments, including the class name. -->

    select * from enrollments left join classes on enrollments.class_id=classes.id;

    better?: select * from enrollments left join classes on enrollments.class_id=classes.id join students on enrollments.student_id=students.id;

<!-- Students born between 1982-1985 (inclusive). -->

    select * from students where birthdate > '12/31/1981' and birthdate < '01/01/1986';

Insert a new enrollment recording that Andre Rohan took PHYS 218 and got an A.
