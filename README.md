# ipl_matches-Analytics

## Introduction
As a data analysis intern, you have to analyse sports data for a client. You are given two datasets related to IPL (Indian Premier League) cricket matches. One dataset contains ball-by-ball data and the other contains match-wise data. You have to import the datasets into an SQL database and perform the tasks given in this assignment to find important insights from this dataset.


## About the data

The "IPL_Ball.csv" file is for ball-by-ball data and it has information of all the 19,3468 balls bowled between the years 2008 and 2020. It has 17 columns.
The "IPL_matches.csv" file contains match-wise data and has data of 816 IPL matches. This table has 17 columns.


## Project
#### Some queries you can run for Practies.

Import table in sql devloper using given steps in Way_to_imort_csv file in sql devloper.pdf

##### 1.Select the top 20 rows of the deliveries table.
select *from match where rownum<=20;




##### 2.Select the top 20 rows of the matches table.
 select *from deliveries where rownum<=20;
 
 
 
 
##### 3. Fetch data of all the matches played on 2nd May 2013.
select *from match where a_date='02-05-2013';




##### 4.Fetch data of all the matches where the margin of victory is more than 100 runs.
select *from match where result_margin>100;




##### 5.Fetch data of all the matches where the final scores of both teams tied and order it in
select *from match where result='tie' order by a_date DESC; 




##### 6.Get the count of cities that have hosted an IPL match.
select count(distinct city)from match;


##### 7. Find name of stadiums that are named under associations and rename it (column name) as Stadium. Find which cities these stadiums are located.
SELECT DISTINCT venue AS  Stadium, city FROM matches
WHERE venue LIKE '%Association%';




##### 8.Create a database comprising of id, player of match, batsman and bowler usingleft join of 10 rows.
SELECT matches.id, matches.player_of_match, deliveries.batsman, deliveries.bowler
FROM matches
INNER JOIN deliveries
ON matches.id = deliveries.id
LIMIT 10;




##### 9.Find average  of result margins when Chennai Super Kings is winner.
SELECT AVG(result_margin) FROM matches
WHERE winner = 'Chennai Super Kings';




##### 10.Find  sum of result margins when Chennai Super Kings is winner.
SELECT SUM(result_margin) FROM matches
WHERE winner = 'Chennai Super Kings';
