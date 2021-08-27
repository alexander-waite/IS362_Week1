#part1

#Q1
SELECT COUNT(*) FROM planes WHERE speed > 0;
SELECT MIN(speed) FROM planes;
SELECT MAX(speed) FROM planes;

#Q2
SELECT SUM(distance) from flights where (year = 2013 AND month = 1);
SELECT SUM(distance) from flights where (year = 2013 AND month = 1 AND tailnum = '');

#Q3
SELECT planes.manufacturer, SUM(distance) from flights 
inner join planes on flights.tailnum = planes.tailnum where (flights.year = 2013 AND flights.month = 7 AND flights.day = 5)
group by manufacturer;
SELECT planes.manufacturer, SUM(distance) from flights 
left outer join planes on flights.tailnum = planes.tailnum where (flights.year = 2013 AND flights.month = 7 AND flights.day = 5)
group by manufacturer;

#Q4 - which airplane and airport flies the most
select MAX(flights.tailnum), COUNT(flights.tailnum) from flights
