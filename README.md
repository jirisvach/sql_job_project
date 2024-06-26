# sql_job_project
In this project I wanted to demonstrate my skills in using SQL and find out some interesting facts about the job market for Data Analyst position.
<br>I used only PostgeSQL in Visual Studio Code.

## Main questions:
**1) What are the top 10 paying companies and Data Analyst roles?[Query_1]** <br>
**2) What are the top 10 paying skills?[Query_2]** <br>
**3) What are the most frequent skills and their average salary?[Query_3]** <br>
**4) Compare different Meta Data Analyst roles salary with average salary[Query_4]** <br>

### Query_0 <br>
Step zero is to set up a new connection between VS Code and the PG Admin server, create a new database, create tables and import all data from csv files into the tables.
<br>
![01](https://github.com/jirisvach/sql_job_project/assets/74241688/44ea3e4d-aaa7-47c5-9766-24b145a0458b)<br>
<br>
The connection test was successful, let´s check the PG Admin server and connect the new sql_job_project database.
<br>
![02](https://github.com/jirisvach/sql_job_project/assets/74241688/b7be19a1-0432-4390-bf33-7e73b24c5b54)<br>
<br>
The database is running successfully, the next step is to create new tables. The tables columns need to be  the same as in the csv files.
<br>
**NOTE:** I´ve used several data types:
  - TEXT and VARCHAR(255) - VARCHAR for columns where I don´t expect a length of more than 255 characters
  - INT and NUMERIC - INT for id´s and NUMERIC for any values lenghth
  - BOOLEAN - for TRUE/FALSE values
  - TIMESTAMP - date time values
<br>![03](https://github.com/jirisvach/sql_job_project/assets/74241688/71d8f9f8-d915-4290-96a7-eb567aaabfe4)

<br> Last step is to copy the data from cvs into the tables.
<br>![04](https://github.com/jirisvach/sql_job_project/assets/74241688/1bf2f45b-4ab7-47d7-868d-a28f67db2fcb)

<br>

### Query_1 <br>
I´m interested in salary_year_avg column and Data Analyst roles. After filtering out the Data Analyst roles I noticed the salary column has some null values. After filtering out null values I used count function to verify the proper analysis can be made. The table has over 5.000 entries which is enough for this project. Then I used join function to connect job postings fact table with the company dim table to be able to see the company's names. The final step was to sort the data by the highest year average salary.
<br>
![05](https://github.com/jirisvach/sql_job_project/assets/74241688/70b0a61f-dd1e-4ae1-85fd-c470e0d90b41)
<br>
And here is the result
![06](https://github.com/jirisvach/sql_job_project/assets/74241688/57f9efe7-5e6d-48f5-8333-4f166645d4d7)
<br>

### Query_2 <br>
To identify top 10 paying skills I used the previous code as a CTE and joined it with skills_dim and skills_job_dim to be able to see skills for each position. I set the number of jobs to top 100 and then I used count to count the frequency of each skill.
<br>
![07](https://github.com/jirisvach/sql_job_project/assets/74241688/5148cefe-3c2a-41d4-9c96-d4cff7a56b05)
<br>
The result showed that SQL and Python are the most valuable skills and are required in half of the top 100 paid jobs
![077](https://github.com/jirisvach/sql_job_project/assets/74241688/539c2a10-698f-4d2d-9863-ff89d7e98309)
<br>

### Query_3 <br>
This query is a combination of two queries - the most frequent skills and the highest paid skills. 
<br>
![08](https://github.com/jirisvach/sql_job_project/assets/74241688/2ee9c952-ded8-4dea-a744-50dc62ae6f52)
<br>
The result showed that Excel is in the top 3 frequent skills but its average salary is second lowest in those top 10 skills
<br>
![09](https://github.com/jirisvach/sql_job_project/assets/74241688/7a0463cd-8cd3-4737-87ad-1c3ef32beb5e)

<br>

### Query_4 <br>
I used the window function to create the extra column showing the global average salary for the Data Analyst role which helps to compare different Meta job roles salaries with the global average salary. 
<br>
![10](https://github.com/jirisvach/sql_job_project/assets/74241688/8d5199fc-1c30-4593-9af9-0d305fdc6219)

<br>
The result showed that only top 3 Data Analyst positions are above the global year salary average. 
<br>
![11](https://github.com/jirisvach/sql_job_project/assets/74241688/809a8ddf-39eb-4d1f-9881-996da4604bc2)


<br>

### Conclusion <br>
In this project, I used basic and some more advanced techniques. As I´ve learned SQL is still one of the most valuable skills to know as a Data Analyst. 
