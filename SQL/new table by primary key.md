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



1. Make new table 'Students_Scores' by using table 1 and table 2  

```sql

create talbe 'Students_Scores' as select s.*, m.*
  from (select * from Student_List) s
, from (select * from Midterm_exam) m
 where s.name  = m.name
   and s.grade = m.grade
   and s.class = m.class

```


