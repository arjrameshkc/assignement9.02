# assignement9.02

 student = LOAD 'Student.txt' USING PigStorage(',') AS (name:chararray, col_under:chararray,    dob:chararray,stream:chararray,grade:float,state:chararray,city:chararray);
  filter_grade = FILTER student by grade < 5;
  dump filter_grade;
  
 
2. filter_name = FILTER student by state matches 'alaska';
   grp2 = FOREACH filter_name GENERATE name;
   dump grp2;

3. filter_state = FILTER student by state matches 'alabama'; 
   filter_col  =  FILTER student by col_under matches 'government';
   grp3 = FOREACH filter_col GENERATE group,COUNT(*) ;
   dump grp3;

4.filter_student = FILTER student by state matches 'oregon';
  filter_col  =  FILTER filter_student by stream matches 'BE';
  dump filter_col;
