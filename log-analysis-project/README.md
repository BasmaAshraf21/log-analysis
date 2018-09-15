-Log Analysis Project BY BASMA ASHRAF

-create a reporting tool prints out report (in plain text) based on the data in the database. 
 This reporting tool is a Python program using the psycopg2 module to connect to the database.

           ----------------------------------------------------------------------------------------

The Folder contains 
	* analysis.py ( python file )
	* newsdata.sql ( database file )
   
-This Project answered the three Questions:

   1- What are the most popular three articles of all time?
   2- Who are the most popular article authors of all time?
   3- On which days did more than 1% of requests lead to errors?
   
            ---------------------------------------------------------------------------------------
            
-How to run the project :-  

  - Install Python 2 or 3 onto your computer.

  - Install Vagrant     -> https://www.vagrantup.com/downloads.html

  - Install VirtualBox  -> https://www.virtualbox.org/wiki/Downloads

  - Download the VM configuration
        "https://github.com/udacity/fullstack-nanodegree-vm".

  - From the bash git, run the "vagrant up" ( sometimes you will need to run also " vagrant provision " ) then run the " vagrant ssh " to log in.

  - Extract compressed file 'log-analysis-project'.

  - Then cd into the vagrant directory and then cd to 'log analysis project' file 

  - Setup  the Database
    - use the following command 'psql -d news -f newsdata.sql'
    - Make Views by running the two queries below.
		* create view ALL_Status as select time::date as day , count(*) from log group by day;
	
		* create view Logs as select time::date as day , count(*) as errors 
      		  from log where status = '404 NOT FOUND' group by day;

    - Run this command 'python analysis.py'
    

            ----------------------------------------------------------------------------------