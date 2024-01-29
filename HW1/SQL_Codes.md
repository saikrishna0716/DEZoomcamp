## Q3
### select count(*) 
from yellow_taxi_trips 
where date(tpep_pickup_datetime) = '2019-09-18' and date(tpep_dropoff_datetime) = '2019-09-18';
