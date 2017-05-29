# sample1
hive---------------------
create table ss(sep Stringmword array<String>)
row format delimited fields terminated by ','
collection items terminated by '#';

load data local inpath '/home/acadgild/hiveudf' into table ss;

create table pp1(a string,b string) partitioned by (b int ,c string) clustered by (a) sorted by (a) into 2 buckets
row format delimited fields terminated by ',';

insert overwrite local directory '/home/acadgild/hiveopt' row format delimited fields terminated by ',';

pig---------------------
c = foreach A generate name,Todate($2,'dd-MM-YYYY');
f =filter c by $1=ToDate('11-09-1994','dd-MM-YYYY');

store a into '/home/acadgild/pig.json' using JsonStorage();
a =load '/jho' using JsonLoader('f1' l) as

start commands--------
sudo service mysqld start
