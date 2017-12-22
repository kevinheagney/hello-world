
mysql -uroot -p
mysql> CREATE database Traffic;
mysql> use Traffic;
mysql> CREATE TABLE accidenttable (Accident_Index varchar, Accident_Severity int, Number_of_Casualties int, Speed_limit int)
mysql> LOAD DATA INFILE ‘accidenttable' INTO TABLE traffic.accidenttable


Then use Hive to analyse the data and write the results to HDFS. Then use Tableau to visualize the results.
Hive> CREATE TABLE accidentdata (accidentindex string, accidentseverity int, numbercasualties int, speedlimit int)
Hive> SELECT * FROM accidentdata;
Hive> SELECT speedlimit, AVG(accidentseverity) FROM accidentdata GROUP BY speedlimit;
Hive> SELECT speedlimit, AVG(numbercasualities) FROM accidentdata GROUP BY speedlimit;
