# LogsAnalysisProject
Fullstack Web Development Nanodegree Program

## PROMPT
Your task is to create a reporting tool that prints out reports (in plain text) based on the data in the database. This reporting tool is a Python program using the psycopg2 module to connect to the database.

## SETTING UP THE ENVIRONMENT
To help with the setup of this project, you are provided with a vagrantfile
and two SQL scripts to set up the environment as intended for this project.  

Follow these steps to get started:

1. Download [Vagrant](https://www.vagrantup.com/) and [Virtual Box](https://www.virtualbox.org/) and install.
2. Clone this repository to a directory of your choice.

   Now that you have everything in place, it's time to set up your virtual environment.
   
3. `cd` into `<FolderName>`:
   ```sh
   $ cd <FolderName>
   ```

4. Setting up Vagrant:
   ```sh
   $ vagrant up
   ```
   Once `vagrant up` has finished, you will see your shell prompt.

5. Log in to the virtual machine:
   ```sh
   $ vagrant ssh
   ```
   
6. Once logged in, navigate to the shared directory:
   ```sh
   cd /vagrant
   ```

7. Extract the newsdata SQL script and use it to populate the database with test data:
   ```sh
   $ unzip newsdata.zip
   $ psql -d news -f newsdata.sql
   ```

8. Set up the views needed to query the database:
   ```sh
   $ psql -d news -f createviews.sql
   ```
9. Lastly, run logs.py:
   ```sh
   $ python3 logs.py
   ```


## EXPECTED OUTPUT
````

                TOP 3 ARTICLES OF ALL TIME

 "Candidate is jerk, alleges rival" -- 338647 views
 "Bears love berries, alleges bear" -- 253801 views
 "Bad things gone, say good people" -- 170098 views

                TOP AUTHORS OF ALL TIME

 Ursula La Multa -- 507594 views
 Rudolf von Treppenwitz -- 423457 views
 Anonymous Contributor -- 170098 views
 Markoff Chaney -- 84557 views

                DAYS WITH GREATER THAN 1% 404 REQUESTS

 July 17, 2016 -- 2.26 % errors
````

## PROJECT PURPOSE
This project was designed to answer 3 questions about a fictional news website's traffic:

1. What are the most popular three articles of all time?
2. Who are the most popular article authors of all time?
3. On which days did more than 1% of requests lead to errors?
