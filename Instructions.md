The Extracurricular Activity system is developed using the oracle 9i form builder and sqlplus. In this system, a person can checkout a student's extracurricular activity by entering his roll no. and update his/her detail.

This is the Homepage of the system

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/form1_mainform.PNG)

This is "student list" form where you will get the entire list of students with the related information stored in the database.

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/form2_student_list.PNG)

This one is "student profile" form where you will get the detailed info. about the student.

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/form3_student_profile.PNG)

The "Insert and Delete Entry" form is used to insert and delete a student's information into/from the database.

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/form4_insert_delete.PNG)

The "Update table" form has two sub-forms to update the Programme information and Department information.

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/form5_update_table.PNG)
![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/form6_update_program.PNG)
![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/form7_update_department.PNG)


How to proceed : (please let me know if there is any correction)

First, make the ER model for the system which will be as follows:

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/1.jpg)

Then, make relational model from the ER model which will look as follows:

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/2.jpg)

Then, check the functional dependency for each entity:

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/3.jpg)
![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Form%20images/4.jpg)


After all this, install the oracle 9i or 10g developer software from the official site 
http://www.oracle.com/technetwork/database/enterprise-edition/downloads/index-092322.html

Now, open the sqlplus software and:

First, make the department table as follows, making the DCODE as primary key

CREATE TABLE DEPARTMENT(DCODE VARCHAR(10), DNAME VARCHAR(40), PRIMARY KEY (DCODE));

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Table%20description/desc%20p_department.PNG)

then, make the programme table as follows, making the PCODE and DCODE as primary key and DCODE as foreign key

CREATE TABLE PROGRAMME(PCODE VARCHAR(10), PNAME VARCHAR(50), DCODE VARCHAR(10), PRIMARY KEY (PCODE, DCODE), FOREIGN KEY(DCODE) REFERENCES DEPARTMENT);

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Table%20description/desc%20p_program.PNG)

then, make the student table as follows, making the ROLL as the primary key and PCODE, DCODE as foreign key

CREATE TABLE STUDENT(ROLL VARCHAR(10), FNAME VARCHAR(20), LNAME VARCHAR(20), DOB VARCHAR(10), PCODE VARCHAR(10), DCODE VARCHAR(10), PRIMARY KEY (ROLL), FOREIGN KEY (PCODE) REFERENCES PROGRAMME, FOREIGN KEY (DCODE) REFERENCES DEPARTMENT);

![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Table%20description/desc%20p_student.PNG)

 then, make the contact table. We have to make a separate table because CONTACT is a multivalued attribute
 
 CREATE TABLE CONTACT(ROLL VARCHAR(10), MOBILE INT, PRIMARY KEY (ROLL, MOBILE), FOREIGN KEY (ROLL) REFERENCES STUDENT);
 
 ![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Table%20description/desc%20p_contact.PNG)
 
 then, make the activity table, this is also having a multivalued attribute
 
 CREATE TABLE ACTIVITY(ROLL VARCHAR(10), CATEGORY VARCHAR(20), TITLE VARCHAR(20), PRIMARY KEY (ROLL, CATEGORY, TITLE), FOREIGN KEY (ROLL) REFERENCES STUDENT);
 
![alt text](https://github.com/rajatsharma369007/DBMS-assignment/blob/master/Extracurricular%20system/Table%20description/desc%20p_extracurricular.PNG)
 
Now, we have the structure of our System, so we have to prepare the frontend of the system.
Here, we will be using the form builder to prepare the form.

Go through the tutorial to build the frontend.
https://www.youtube.com/watch?v=hs8jpRklez4

Thank you for visiting here,  
Rajat sharma  
Bachelor in technology  
Computer Science and Engineering  
Tezpur University  

Feel free to contact me  
Email: rajatsharma369007@gmail.com
