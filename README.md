# Lab 8

## Student information

* Full name: Mehar Singh
* E-mail: msing043@ucr.edu
* UCR NetID: msing043
* Student ID: 862108533

## Answers

* (Q1) What is the result?

[
        5
]

* (Q2) Which query did you use and what is the answer?
query:


USE chicago_crimes_sample;
select DISTINCT(primary_type) 
FROM ChicagoCrimes 
WHERE location_description ="GAS STATION";

answer:

[
        {
                "primary_type": "DECEPTIVE PRACTICE"
        },
        {
                "primary_type": "ROBBERY"
        },
        {
                "primary_type": "THEFT"
        },
        {
                "primary_type": "BATTERY"
        },
        {
                "primary_type": "MOTOR VEHICLE THEFT"
        }
]

* (Q3) Include the query in your README file

USE chicago_crimes_sample;
SELECT year, count(*) AS count FROM (
  SELECT print_datetime(parse_datetime(date_value, "MM/DD/YYYY hh:mm:ss a"), "YYYY") AS year
  FROM ChicagoCrimes
) AS year
GROUP BY year
ORDER BY count DESC;

* (Q4) Which `district` has the most number of crimes? Include the query and the answer in the README file.

query:

USE chicago_crimes_sample;
FROM ChicagoCrimes 
SELECT district
ORDER BY count
LIMIT 1;
 
answer:

district": 18


* (Q5) Include the query in your submission.
USE chicago_crimes_sample;
SELECT year_month,count(year_month) AS count FROM (
  SELECT print_datetime(parse_datetime(date_value, "MM/DD/YYYY hh:mm:ss a"), "YYYY/MM") AS year_month
  FROM ChicagoCrimes
) AS tmp
GROUP BY year_month
ORDER BY year_month

* (Q6) What is the total number of results produced by this query (not only the shown ones)?
232 results
