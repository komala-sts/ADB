# MSc Data Science Coursework on Advanced DataBase using MS SQL Server 2019. 
<h3>There are two Tasks. Implement your solution to each problem based on tasks’ description.</h3><br />
<h4>Task 1 (65 marks)</h4><br />
<p align='justify'>Imagine you are employed as a database developer consultant for a library. They are currently in the process of developing a new database system which they require for storing information on their members, their library catalogue, loan history and overdue fine repayments. In your initial consultation with the library, you have gathered the information below. Please read the below carefully and continue to the task description.</p>
<b>Client Requirements</b><br />
<p align='justify'>When a member joins the library, they need to provide their full name, address, date of birth and they must create a username and password to allow them to sign into the member portal. Optionally, they can also provide an email address and telephone number. Members are charged a fine if they have overdue books and the library has to keep track of the total overdue fines owed by an individual, how much they have repaid and the outstanding balance. When a member leaves, the library wants to retain their information on the system so they can continue marketing to them, but they should keep a record of the date the membership ended. Members can sign up and login online.
When a member has overdue fines, they can repay some or all the overdue fines. Each repayment needs to be recorded, along with the date / time of the repayment, the amount repaid and the repayment method (cash or card).</p>
<p align='justify'>The library has a catalogue of items. For each they have an item title, item type (which is classified as either a Book, Journal, DVD or Other Media), author, year of publication, date the item was added to the collection and current status (which is either On Loan, Overdue, Available or Lost/Removed). If the item is identified as being lost or removed from the collection, the library will record the date this was identified. If the item is a book, they will also record the ISBN.<br />
The library wants to also keep a record of all current and past loans. Each loan should specify the member, the item, the date the item was taken out, the date the item is due back and the date the item was actually returned (this will be NULL if the item is still out). If the item is overdue, an overdue fee needs to be calculated at a rate of 10p per day.</p>
The library processes hundreds of loans a day and details of the items on loan are business critical for them, so they need to avoid data loss if their systems go down. However, if their systems are down for a couple of hours, they think this isn’t too much of an issue for them.<br /><br />
<b>Task Details</b><br />
<p align='justify'>As the database consultant, you are required to design the database system based on the information provided above, along with a number of associated database objects, such as stored procedures, user-defined functions, views and triggers. Your submission will take the form of working T-SQL statements required for the steps outlined below, a backup of the database created, and a report explaining and justifying your design decisions, and the process you followed to complete the tasks. You should include screenshots and the T-SQL statements within the report itself.</p>
<p align='justify'>1. You should design and normalise your proposed database into 3NF, fully explaining and justifying your database design decisions and documenting the process you have gone through to implement this design using T-SQL statements in Microsoft SQL Server Management Studio, using screenshots to support your explanation. All tables and views must be created using T-SQL statements, which should be included in your report. Clearly highlight which column(s) are primary keys or foreign keys. You should also explain the data type used for each column and justify the reason for choosing this. You should also consider using constraints when creating your database to help ensure data integrity. You must include a database diagram as part of your submission. If you have made any additional assumptions aside from the information above when designing your database, you should clearly state these.</p>
<p align='justify'>2. The library also requires stored procedures or user-defined functions to do the following things:
a) Search the catalogue for matching character strings by title. Results should be sorted with most recent publication date first. This will allow them to query the catalogue looking for a specific item.</br>
b) Return a full list of all items currently on loan which have a due date of less than five days from the current date (i.e., the system date when the query is run)</br>
c) Insert a new member into the database</br>
d) Update the details for an existing member</p>
<p align='justify'>
3. The library wants be able to view the loan history, showing all previous and current loans, and including details of the item borrowed, borrowed date, due date and any associated fines for each loan. You should create a view containing all the required information.</p>
<p align='justify'>4. Create a trigger so that the current status of an item automatically updates to Available when the book is returned.</p>
<p align='justify'>5. You should provide a function, view, or SELECT query which allows the library to identify the total number of loans made on a specified date.</p>
<p align='justify'>6. So that you can demonstrate the database to the client you should insert some records into each of the tables (you only need to add a small number of rows to each, however, you should also ensure the data you input allows you to adequately test that all SELECT queries, user-defined functions, stored procedures, and triggers are working as you expect).</p>
<p align='justify'>
7. If there are any other database objects such as views, stored procedures, user-defined functions, or triggers which you think would be relevant to the library given the brief above, you will obtain higher marks for providing these along with an explanation of their functionality.
Within your report, you will also need to provide your client with advice and guidance on:</br>
• Data integrity and concurrency </br>
• Database security</p>

• Database backup and recovery
Generic information on these topics, which is not applied to the given scenario, is likely to score poorly.

To get more than a satisfactory mark, you must use all of the below at least once in your database:<br/>
• Views<br/>
• Stored procedures<br/>
• System functions and user defined functions<br/>
• Triggers<br/>
• SELECT queries which make use of joins and sub-queries<br/>


<h4>Task 2 (35 marks)</h4><br />
<p align='justify'>For the second task, you should use the three csv files provided for you on Blackboard. These files are an excerpt from a larger file which is a real-world dataset released every month by the National Health Service (NHS) in England. The file provides a information on prescriptions which have been issued in England, although the extract we have provided focusses specifically on Bolton.</p>
The data includes three related tables, which are provided in three csv files:<br/>
• The Medical_Practice.csv file has 60 records and provides the names and addresses of the medical practices which have prescribed medication within Bolton. The PRACTICE_CODE column provides a unique identifier for each practice.<br/>
• The Drugs.csv file provides details of the different drugs that can be prescribed. This includes the chemical substance, and the product description. The BNF_CHAPTER_PLUS_CODE column provides a way of categorising the drugs based on the British National Formulatory (BNF) Chapter that includes the prescribed product. For example, an antibiotic such as Amoxicillin is categorised under ‘05: Infections’. TheBNF_CODE column provides a unique identifier for each drug.<br/>
• The Prescriptions.csv file provides a breakdown of each prescription. Each row corresponds to an individual prescription, and each prescription is linked to a practice via the PRACTICE_CODE and the drug via the BNF_CODE. It also specifies the quantity (the number of items in a pack) and the items (the number of packs). The PRESCRIPTION_CODE column provides a unique identifier for each prescription.<br/>
<p align='justify'>For this task, imagine you work as a database consultant for a pharmaceutical company. They want to analyse the prescribing data to understand more about the types of medication being prescribed, the organisations doing the prescribing, and the quantities prescribed.</p>
<p align='justify'>1. The first stage of your task is to create a database and import the three tables from the csv file. You should also add the necessary primary and foreign key constraints to the tables and provide a database diagram in your report which shows the three tables and their relationships. You should create the database with the name PrescriptionsDB and the tables with the following names:</p>
a. Medical_Practice<br/>
b. Drugs<br/>
c. Prescriptions<br/>
You should also leave the column names as they appear in the csv file. This is so we can re-run your code.<br/></br>
<p align='justify'>
 2. Write a query that returns details of all drugs which are in the form of tablets or capsules. You can assume that all drugs in this form will have one of these words in the BNF_DESCRIPTION column.</p>
<p align='justify'>
 3. Write a query that returns the total quantity for each of prescriptions – this is given by the number of items multiplied by the quantity. Some of the quantities are not integer values and your client has asked you to round the result to the nearest integer value.</p>
<p align='justify'>4. Write a query that returns a list of the distinct chemical substances which appear in the Drugs table (the chemical substance is listed in the CHEMICAL_SUBSTANCE_BNF_DESCR column)</p>
<p align='justify'>5. Write a query that returns the number of prescriptions for each BNF_CHAPTER_PLUS_CODE, along with the average cost for that chapter code, and the minimum and maximum prescription costs for that chapter code.</p>
<p align='justify'>6. Write a query that returns the most expensive prescription prescribed by each practice, sorted in descending order by prescription cost (the ACTUAL_COST column in the prescription table.) Return only those rows where the most expensive prescription is more than £4000. You should include the practice name in your result.</p>
<p align='justify'>7. You should also write at least five queries of your own and provide a brief explanation
of the results which each query returns. You should make use of all of the following at least once:</p>
o Nested query including use of EXISTS or IN<br/>
o Joins<br/>
o System functions<br/>
o Use of GROUP BY, HAVING and ORDER BY clauses<br/>
 
