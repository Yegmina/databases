# Week 5

## Assignment 1

### Question 1

SELECT elevation_ft 
AS 'max(elevation_ft)' 
FROM airport 
WHERE elevation_ft in( 
                        SELECT max(elevation_ft)
                        FROM airport
                            );


![screenshot](w5a1q1.png)

### Question 2

SELECT continent, count(*) 
FROM country 
GROUP BY continent;

![screenshot](w5a1q2.png)

### Question 3

SELECT screen_name, count(*) 
FROM game, goal_reached 
WHERE game.id = game_id 
GROUP BY screen_name;

![screenshot](w5a1q3.png)

### Question 4

SELECT screen_name 
FROM game 
WHERE co2_consumed in
    ( 
        SELECT min(co2_consumed)
        FROM game
    );

![screenshot](w5a1q4.png)

### Question 5

	
select country.name, count(*)
from airport, country
where airport.iso_country = country.iso_country
group by country.iso_country
order by count(*) desc
limit 50;

![screenshot](w5a1q5.png)

### Question 6

SELECT country.name 
FROM airport, country 
WHERE country.iso_country = airport.iso_country 
GROUP BY country.iso_country HAVING count(*) > 1000;

![screenshot](w5a1q6.png)

### Question 7

SELECT name 
FROM airport 
WHERE elevation_ft in
    ( 
        SELECT max(elevation_ft)
        FROM airport
    );

![screenshot](w5a1q7.png)


### Question 8

SELECT country.name 
FROM airport,country 
WHERE 
    country.iso_country = airport.iso_country 
        AND
    elevation_ft in
                    ( 
                        SELECT max(elevation_ft) 
                        FROM airport
                    );

![screenshot](w5a1q8.png)

### Question 9

SELECT count(*) 
FROM goal_reached, game 
WHERE game.id = game_id 
        AND 
      screen_name = "Vesa";

![screenshot](w5a1q9.png)

### Question 10

SELECT name 
FROM airport 
WHERE latitude_deg in
    ( 
        SELECT min( latitude_deg ) 
        FROM airport
    );

![screenshot](w5a1q10.png)
