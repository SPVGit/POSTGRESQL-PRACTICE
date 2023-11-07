## DISPLAY NAME, PHONE AND COUNTRY FROM CUSTOMERS TABLE - SINGLE LINE

SELECT name, phone, country FROM customers;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## DISPLAY NAME, PHONE AND COUNTRY FROM CUSTOMERS TABLE - MULTI LINE

SELECT name,
       phone,
       country
  FROM
       customers;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## SHOW ALL DATA FROM ROOMS TABLE

SELECT * FROM rooms;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## LIST NAME, PHONE AND EMAIL OF ALL CUSTOMERS:

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## LIST ALL THE DETAILS FROM CUSTOMERS TABLE

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## LIST THE CUSTOMER ID, CHECK IN DATE AND NUMBER OF GUESTS FROM RESERVATIONS 

////////////////////////////////////////////////////////////////////////////////////////////////////////////

# SHOW ROOM NUMBER AND 85% OF THE RATE FROM ROOMS TABLE

SELECT room_no, rate * 0.85 FROM rooms;
+---------+-------------+
| room_no | rate * 0.85 |
+---------+-------------+
|     101 |     72.2500 |
|     102 |     72.2500 |
|     103 |     72.2500 |

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## SHOW ROOM NUMBER AND 85% OF RATE BUT WITH A NEW HEADING (COLUMN ALIAS)

  SELECT room_no,
       rate * 0.85 AS discounted_rate //column alias
    FROM rooms;
+---------+-----------------+
| room_no | discounted_rate |
+---------+-----------------+
|     101 |         72.2500 |
|     102 |         72.2500 |
|     103 |         72.2500 |

////////////////////////////////////////////////////////////////////////////////////////////////////////////

For example, to display the weekly rate for a room (with 10% weekly discount)

SELECT room_no, room_type, rate * 7 * 0.90 from rooms;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

You can change the column heading using a column alias:
SELECT room_no, room_type, rate * 7 * 0.90 as weekly_rate from rooms;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

Use string concatenation to glue character data together:
SELECT 'Customer name = ' || name FROM customers;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT id, name, phone, email, country
  FROM customers
  WHERE country = 'France';

 id  |        name        |      phone       |            email            | country
-----+--------------------+------------------+-----------------------------+---------
 9   | Laurence Lebihan   | 91.24.4555       | laurence.lebihan@xmzx.net   | France
 12  | Carine Schmitt     | 40.32.2555       | carine.schmitt@dftu.net     | France
 15  | Janine Labrune     | 40.67.8555       | janine.labrune@dlsh.net     | France
 25  | Mary Saveley       | 78.32.5555       | mary.saveley@yppl.net       | France
 34  | Martine Rancé      | 20.16.1555       | martine.rancé@xeqs.net      | France
 35  | Marie Bertrand     | (1) 42.34.2555   | marie.bertrand@glut.net     | France
 49  | Frédérique Citeaux | 88.60.1555       | frédérique.citeaux@vekn.net | France
 59  | Annette Roulet     | 61.77.6555       | annette.roulet@lgha.net     | France
 62  | Daniel Da Silva    | +33 1 46 62 7555 | daniel.da.silva@hijy.net    | France
 63  | Daniel Tonini      | 30.59.8555       | daniel.tonini@mxvw.net      | France
 91  | Laurence Lebihan   | 91.24.4555       | laurence.lebihan@xmzx.net   | France
 92  | Paul Henriot       | 26.47.1555       | paul.henriot@uwua.net       | France
 106 | Dominique Perrier  | (1) 47.55.6555   | dominique.perrier@bdim.net  | France
(13 rows)

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT * FROM reservations
   WHERE room_no >= 200
     AND room_no < 300
     AND checkin_date >= '2018-01-01';

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT * FROM rooms
   WHERE room_type = 'PREMIER'
      OR rate < 100.00
     AND room_no < 300;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT rate + 20 * 0.85 from rooms;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT (rate + 20) * 0.85 from rooms;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT * FROM rooms
   WHERE (room_type = 'PREMIER'
      OR rate < 100.00)
     AND room_no < 300;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT ... WHERE price BETWEEN 100 AND 250 ...

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT ... WHERE room_no IN (201, 202, 204, 206) ...

////////////////////////////////////////////////////////////////////////////////////////////////////////////

  ... a NOT BETWEEN b AND c ...

////////////////////////////////////////////////////////////////////////////////////////////////////////////

  ... a NOT IN (b, c, d, ...)

////////////////////////////////////////////////////////////////////////////////////////////////////////////

Which customers are from Norway?

////////////////////////////////////////////////////////////////////////////////////////////////////////////

Which rooms can accommodate more than two people?

////////////////////////////////////////////////////////////////////////////////////////////////////////////

Which invoices are dated after one month ago?

////////////////////////////////////////////////////////////////////////////////////////////////////////////

How would last month's invoices change if we gave a discount of 15%

////////////////////////////////////////////////////////////////////////////////////////////////////////////

List all customers whose second name starts with 'M' (hint: there's a space before the second name)

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT name, length(name) AS namelen, upper(email)
  FROM customers;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

  SELECT * FROM customers
   WHERE lower(country) = 'uk'
     AND city = 'Manchester';

////////////////////////////////////////////////////////////////////////////////////////////////////////////

     SELECT room_no, room_type, rate AS old_rate,
       round(rate * 100/120 * 123.5/100) AS new_rate
   FROM rooms;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

   SELECT cust_id, room_no, checkin_date,
       checkout_date - checkin_date AS nights
   FROM reservations
   WHERE checkout_date = current_date + 1;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

   Write a query to check that all booking dates are before their checkin dates
We plan to offer a discount of 10% on all Premier and Premier Plus rooms next month. How much would we gain on each room if occupancy rose by 5 nights over the month.
List all reservations for this month and the number of nights booked.

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT country FROM customers;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT DISTINCT country FROM customers;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT id, name, phone, email, country
    FROM customers
    ORDER BY country, name;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT id, name, country, city
    FROM customers
    ORDER BY country DESC, city;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

SELECT id, name, phone, email, country
  FROM customers
  ORDER BY country, name
  LIMIT 20;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

  List the different room types and rates for all rooms avoiding duplicates.

////////////////////////////////////////////////////////////////////////////////////////////////////////////

List customers' names addresses and phone numbers in alphabetic order of names.

////////////////////////////////////////////////////////////////////////////////////////////////////////////

List customers' names, addresses, city and country in ascending order of country then reverse order of city within country.

////////////////////////////////////////////////////////////////////////////////////////////////////////////

List the room number, type and the cost of staying 5 nights in each of the top 15 most expensive rooms.

////////////////////////////////////////////////////////////////////////////////////////////////////////////
