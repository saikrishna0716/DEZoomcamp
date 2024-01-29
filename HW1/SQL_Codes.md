# HW1 SQL Queries

## Q3
SELECT count(*) \
FROM yellow_taxi_trips \
WHERE DATE (tpep_pickup_datetime) = '2019-09-18'
	AND DATE (tpep_dropoff_datetime) = '2019-09-18';

## Q4
SELECT DATE (tpep_pickup_datetime)
	,max(trip_distance) \
FROM yellow_taxi_trips \
WHERE DATE (tpep_pickup_datetime) IN (
		'2019-09-16'
		,'2019-09-18'
		,'2019-09-21'
		,'2019-09-26'
		) \
GROUP BY DATE (tpep_pickup_datetime)
ORDER BY 2 DESC

## Q5
SELECT b."Borough"
	,sum(total_amount)
FROM yellow_taxi_trips a
	,zones b
WHERE a."PULocationID" = b."LocationID"
	AND DATE (tpep_pickup_datetime) = '2021-01-01'
GROUP BY b."Borough"
HAVING sum(total_amount) > 50000
ORDER BY 2 DESC limit 3;

## Q6
SELECT c."Borough"
     ,tip_amount
 FROM yellow_taxi_trips a
     ,zones b
     ,zones c
 WHERE a."PULocationID" = b."LocationID"
     AND a."DOLocationID" = c."LocationID"
     AND b."Zone" = 'Astoria'
     AND date_part('year', tpep_pickup_datetime) = 2019
     AND date_part('month', tpep_pickup_datetime) = 9
 ORDER BY 2 DESC limit 1;


