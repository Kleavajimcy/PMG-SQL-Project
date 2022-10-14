# PMG-SQL-Project
SQL Assessment Challenges

SQL Challenge

The database contains two tables, store_revenue and marketing_data. Refer to the two CSV files, store_revenue and marketing_data to understand how these tables have been created.

store_revenue contains revenue by date, brand ID, and location:

    create table store_revenue ( id int not null primary key auto_increment, date datetime, brand_id int, store_location varchar(250), revenue float
    );

marketing_data contains ad impression and click data by date and location:

    create table marketing_data ( id int not null primary key auto_increment, date datetime, geo varchar(2), impressions float, clicks float );

Please provide a SQL statement under each question.

    Question #0 (Already done for you as an example) Select the first 2 rows from the marketing data ​
    select * from marketing_data limit 2; ​

    Question #1 Generate a query to get the sum of the clicks of the marketing data ​
    select sum(clicks) from dbo.marketing_data;
    
    Question #2 Generate a query to gather the sum of revenue by store_location from the store_revenue table ​
    select store_location, sum(revenue) from dbo.store_revenue
    group by store_location;
    
    Question #3 Merge these two datasets so we can see impressions, clicks, and revenue together by date and geo. Please ensure all records from each table are accounted for. ​
    select sl.date, , impression as 'Impression', clicks as 'Clicks', revenue as 'Revenue' from dbo.marketing_data mr
    left join dbo.store_revenue sl on mr.date = sl.date
    
    Question #4 In your opinion, what is the most efficient store and why? ​
    
    Question #5 (Challenge) Generate a query to rank in order the top 10 revenue producing states ​
    select top 10 store_location, sum(revenue) as 'Revenue' from dbo.store_revenue
    group by store_location
    order by Revenue desc

