<h1>Investigating Intrusive Activities: Probing Suspicious Logins Using SQL Analysis</h1>

 

<h2>Project Description</h2>
 In my role as security analyst, it is my responsibility to investigate security issues, thereby assisting my organization in maintaining system security. Furthermore, I am tasked with ensuring that machines are regularly updated as required. Notably, we have recently identified unusual login attempts occuring after business hours. To address the incident, I am using SQL filters to retrieve the records and conduct an in-depth investigation into this security concern.

<br />


<h2>Languages and Utilities Used</h2>

- <b>MariaDB Shell</b> 
  
<h2>Project walk-through:</h2>

<h3>Retrieve after hours failed login attempts</h3>
<p>
To begin with, I am going to identify all unsuccessful attempts after working hours which will help me through my investigation into the issue. The following code demonstrates how I created a SQL query to retrieve all unsuccessful attempts after 18:00.

<br/>
<br/>
<img src="https://i.imgur.com/9tDTQcY.png" height="80%" width="80%" alt="Unsuccesful login attempts"/>
<br />
<br />
 The screenshot is divided into two parts, the first part displays the query I used, and the second part showcases the output. This query retrieves the unsuccessful login attempts after 18:00, Initially, I am selecting all columns from log_in_attempts table. Then, I apply a filter using the WHERE keyword to extract only the unsuccessful attempts after bussiness hours.
<br/>
</p>
<h3>Retrieve login attempts on specific dates</h3>
<p>
  A suspicious event occured on '2022-05-09', any login activity that occured on this day or the day before needs to be investigated. The code below illustrates how I used a SQL filter to look up records on specific dates. 
<br />
<br />
<img src="https://i.imgur.com/5e2nm1M.png" height="80%" width="80%" alt="Login Attempts on Specific Dates"/>
<br />
<br />
  As demonstrated above, the query I employed extracts records from the day of the event and the preceding day. Initially, I select all data from the 'log_in_attempts' table. Next, I utilize the WHERE keyword along with the OR operator to filter the extracted data, exclusively retrieving results from the two specified days.
<br/>
</p>
<h3>Retrieve login attempts outside of Mexico</h3>
<p>
 It has been determined that the suspicious activity did not originate from Mexico. Hence, we will employ a query to exclude Mexico from the filtering process. The code below showcases the query and result obtained. 
<br />
<br />
<img src="https://i.imgur.com/Hc8b9to.png" height="80%" width="80%" alt="Excluding Mexico"/>
<br />
<br/>
 This query is returning all login attempts from the log_in_attempts table. Afterwards, using The WHERE clause along with the NOT operator for countries outside of mexico. Then,I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE.
</p>
<h3>Retrieve employees in Marketing</h3>
<p>
  A mandatory part of my role is to update employees machines. Therefore we need to obtain the information about employees in the Marketing department who are located in all offices in the East building. The screenhot below displays the query that I used.
<br/>
<br/>
<img src="https://i.imgur.com/h4hCISI.png" height="80%" width="80%" alt="Marketing employees"/>
<br />
<br />
 This query is returning all the records from the employees table. I used the WHERE clause to specify the department I am looking for and the LIKE operator with 'EAST%' as the pattern to locate all the employees in the east building.   
<br/>
</p>
<h3>Retrieve employees in Finance or Sales</h3>
<p>
  Now, we need to perform a different update to the computers of all employees in the Finance or the Sales departments, and we need to locate information on these employees. As demonstrated in the code below.
<br/>
<br/> 
<img src="https://i.imgur.com/YUEtY3X.png" height="80%" width="80%" alt="DFinance and Sales department"/>
<br/>
<br/>
The Query I utilized above is returning all employees in the sales and finance departments. I used the WHERE clause along with the OR operator to retrieve employees from both departments.
</p>
<h3>Retrieve all employees not in IT</h3>
<p>
  My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.
The following demonstrates how I created a SQL query to filter for employee machines from employees not in the Information Technology department.
<br/>  
<br/>
<img src="https://i.imgur.com/sC0T0Ei.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with NOT to filter for employees not in this department. 
<br/>
<h3>Summary</h3>
I applied filters to SQL queries to get specific information on login attempts and employee machines. I used two different tables, log_in_attempts and employees. I used the AND, OR, and NOT operators to filter for the specific information needed for each task. I also used LIKE and the percentage sign (%) wildcard to filter for patterns.
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
