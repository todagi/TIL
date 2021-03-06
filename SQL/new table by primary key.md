Virtual Tables for SQL
===============================================

### table 1 : "Student_List"

![studentlist](https://user-images.githubusercontent.com/33271520/44142112-286a2b2a-a0ba-11e8-97f2-d511711cade4.jpg)


### table 2 : "Midterm_exam"

![midterm](https://user-images.githubusercontent.com/33271520/44142109-28124824-a0ba-11e8-8d48-90cfab0bf852.jpg)


### table 3 : "Supplementary_Learning"

![supplementary](https://user-images.githubusercontent.com/33271520/44142113-2894685e-a0ba-11e8-8581-a5d334040838.jpg)


### table 4 : "Address Code Conversion"

![address](https://user-images.githubusercontent.com/33271520/44142107-27e752ae-a0ba-11e8-8df1-d940eed6ee51.jpg)


### table 5 : "Regional_Index_about_education"

![region_index](https://user-images.githubusercontent.com/33271520/44142111-283b34a0-a0ba-11e8-980e-bb9721721324.jpg)

<br>
<br>
<br>

1. Make new table 'Students_Scores' by using table 1 and table 2  

```sql

create talbe Students_Scores as select s.*, m.*
  from (select * from Student_List) s
, from (select * from Midterm_exam) m
 where s.name  = m.name
   and s.grade = m.grade
   and s.class = m.class

```

2. Make new table 'Major_Subjects_Score' by using table 2 and table 3 : table_1 + table 2('Korean' 'English' 'Math')

```sql

create table Major_subjects_Score as s*
     , m.Korean
     , m.English
     , m.Math
  from  (select * from Student_List) s
  ,     (select b.name
              ,  b.grade
              ,  b.class
              ,  b.Korean
              ,  b.English
              ,  b.Math
           from  Midterm_exam b) m
 where s.name  = m.name
   and s.grade = m.grade
   and s.class = m.class
```

3. See data about scores of 'Midterm_exam' & name and subject of 'Supplementary_Learning'

```sql

select *
  from (select  b.name
              , b.Korean
              , b.Math
              , b.English
              , b.Science
              , b.Society
              , b.history
          from  Midterm_exam b) s
     , (select  d.name
              , d.subject
          from  Supplementary_Learning d) m
 where s.name = m.name   
 ```
 
 4. make table 'Student_Education_Environmnet' by using "Student_List", "Address Code Conversion" and "Regional_Index_about_education"  
    
    columns : 'student_code', 'name', 'grade', 'class', 'AddressCode', 'Average_Income', 'Private_Schools', 'Libraries'
    
```sql
create table Student_Education_Environmnet as 
     , s.student_code
     , s.name
     , s.grade
     , s.class
     , m.AddressCode
     , m.Average_Income
     , m.Private_Schools
     , m.Libraries
 from (select * from Student_List) s
    , (select * from AddressCodeConversion) k  
    , (select * from Regional_Index_about_education) m
where s.address     = m.Address    
      k.AddressCode = m.Address_code

```
    
5. See data about scores above 80 of Korean and English with student_code, name, grade and class

```sql
select *
  from (select a.student_code
             , a.name
             , a.grade
             , a.class
          from Student_List a) k
     , (select b.name
             , b.grade
             , b.class
             , b.Korean
             , b.English
          from Midterm_exam b) j
 where k.name  = j.name
   and k.grade = k.grade
   adn k.class = k.class
   
```
