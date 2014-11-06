FEEDBACK DATABASE DOCUMENTATION
-------------------------------
NOTE: Still editing.

Convention:
1. Word in capital letter is entity.
2. // is used for comments.

BUSINESS RULES
--------------

* The persons which are filling feedback form are STUDENT.
Adding the supplementary table for feedback but are main table for other modules.

Tables :
Course
Subject
Batch
Time Table

Course :
Course_id        // the unique course id 
Course_name        // The course name (MCA, MTECH MBA, FT, APR )
Stream        // The stream (CS or MGM)
Number_of_sem    // The total number of semester

Subject :
Subject_id        // Unique Subject ID
Course_id        // Course id from above course table
Name of subject    // Name of the subject 
Semester        // The semester in which it is taught
Credits            // The credits of that particular subjects


Batch :
S.No            // The serial number unique 
Batch_id        // The batch id of the batch like (IC-2K9, IM-2K7)
Course_id        //  The course Id from the course table
Year            //  The year of the bactch like (2009, 2007 )
Section        //   The section values (A, B, C, Nil)

Time Table :
Course_id        // The course id from the course table to know the course name
Subject_id        // The subject id from subject table to know subject name
Faculty_id        // The faculty_id from user master table to know name
Semester        // The semester in which the subject is taught.
Year            // The year in which the subject is being taught
Section        // Sections value (A, B ,C Nil ) 
Day            // The day of the week 
Time_from        // The starting time of class
Time_to        // The ending time of class
Room Number     // The room number of the class


* Since STUDENT can be from different course, batch and section, STUDENT has the following attributes:

- student_id // primary key
- course_id // specifies particular student belongs to which course. e.g IC, IT
- batch // specifies student belongs to which batch. e.g 2011, 2012 etc.
- semester
- section

* Each student is assigned to a single COURSE. COURSE has following attributes:
- course_id // primary key
- course_name
- no_of_sem // Specifies particular course has how many semester.
- discipline // specifies course is form which domain e.g management, technical etc.

* Each COURSE has different SUBJECT. SUBJECT has following attributes:
- sub_id // primary key e.g. IC-701
- sub_name
- sub_credits // how much the particular subject is contributing in semester. e.g. 5, 6 etc.
- semester
** course id**

* The person who is teaching the subject is called FACULTY. FACULTY has following attributes:
- faculty_id // primary key
- faculty_name
** subject id for current year **

** we don't need this block right now since no info for form filler is to be saved. **


* FILLED_INFO is used to keep track that which student has filled the form. It contains following attribute:
- student_id // primary key
- semester
- session // current year
- filled // boolean variable yes or no.

** end of block which is not needed **


* FEEDBACK_FORM contains the data filled by STUDENT. It has following attributes:
- s_no // auto_increment & primary key
- batch // year in which student get admission
- course_id
- session // current year
- semester
- sub_id
- section
- faculty_id
- conceptual_clearity // specifies teacher's ability to bring conceptual clearity
- sub_knowledge // specifies teacher's subject knowledge
- practicl_eg // specifies teacher's compliments theory with practical example
- handling_capability // specifies teacher's capability of handling cases/ assignment/ exercises/ activities
- motivation // specifies motivation provided by teacher
- control_ability // specifies teacher's ability to control the teacher
- completion_course // specifies completion & coverage of course
- communication_skill // specifies teacher's communication skill
- Regularity_punctuality // specifies teacher's regularity & punctuality
- guidance_outside // specifies teacher's guidance & interaction outside the classroom
- syllabus_industry_relevance // specifies relevance of syllabus as per industry requirement
- sufficiency_of_course // specifies sufficiency of course content
- book_availability // specifies availability of books in library
- basic_requirements // specifies requirements like chalk, duster
- technological_support // specifies supports like OHP/LCD etc
- study_material // specifies availability of material like photocopy etc
- resourse_availability // specifies availability of resources like internet, computers, softwares, database etc
- cleaniliness_of_class


