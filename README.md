# FxDealsAnalyzer

Clustered Data Warehouse

Import deals details from files into DB. Knowing that each 5 seconds around 100000 deal took place and stored in a file shared via a shared folder, the requested performance is to be able to import the file in less than 5 seconds.


Request logic as following :

File format is CSV contains the following fields (Deal Unique Id, From Currency ISO Code "Ordering Currency", To Currency ISO Code, Deal timestamp, Deal Amount in ordering currency).
Validate row structure.
Valid rows should be stored in table/document, with reference to source file name .
Invalid rows should be stored into another table/document, with reference to source file name.
The DB contains another table to maintain accumulative count of deals per Ordering Currency "Columns : Currency ISO Code, CountOfDeals ", so upon completion of importing process the system should increase count of deals per currency.
System should not import same file twice.
No rollback allowed, what every rows imported should be saved in DB.

Technical Specs :

Access to DB should be through JPA.
For DB type, you can select between (MySql or MongoDB)
Provide a web interface for uploading files and inquire about results "using filename" following web applications 3 tier architecture. Spring Batch is not allowed.

Deliverables should be ready to work including :

Workable deployment including sample file.
Deployment steps including sample data of 100K records, contains all invalid/valid records that the system handles.
Maven or Gradle project is required for full source code.
Proper error/exception handling.
Proper Logging.
It is essential to follow TDD and include unit testing of your code and provide it as part of the assignment, noting that this will be one of the major assessment points, minimum code coverage should be 70%.
It is preferred to deliver via github or bitbucket repository.
Provide deployment as a Vagrant or Docker is a plus.
