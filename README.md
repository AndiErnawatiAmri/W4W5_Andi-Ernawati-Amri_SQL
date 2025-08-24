# W4W5_Andi-Ernawati-Amri_SQL
Query of Revou assignment 

SELECT
date_trunc(start_date, month) as month,
round(avg(duration_sec)/60,2) as mean
FROM (
  select distinct trip_id, end_date, start_date, duration_sec
FROM `bigquery-public-data.san_francisco_bikeshare.bikeshare_trips`) as trips
where date(start_date) between '2014-01-01' and '2017-12-31'
group by month
order by month desc
