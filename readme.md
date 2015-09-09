#SQL homework

##Normal Mode
1. How many users are there?
    SELECT * FROM users => 50

2. What are the 5 most expensive items?
  SELECT * FROM items ORDER BY price

  60|Ergonomic Steel Car
  40|Sleek Wooden Hat
  100|Awesome Granite Pants
  83|Small Wooden Computer
  25|Small Cotton Gloves

3. What’s the cheapest book? (Does that change for “category is exactly ‘book’” versus “category contains ‘book’”?)
  SELECT * FROM items WHERE category LIKE "%books%" ORDER BY price
Cheapest book in all book categories is Ergonomic  GRanite Chair, 1496
Yes

4. Who lives at “6439 Zetta Hills, Willmouth, WY”? Do they have another address?
SELECT user_id FROM addresses WHERE street LIKE "%6439 Zetta%"
User ID 40
SELECT * FROM users
Corrine Little
Yes, two addresses



5. Correct Virginie Mitchell’s address to “New York, NY, 10108”.
SELECT * FROM users WHERE first_name = "Virginie"
SELECT street, city, state, zip FROM addresses WHERE user_id = 39;




6. How much would it cost to buy one of each tool?
SELECT SUM(price) FROM items WHERE category LIKE "%tool%";
46477


7. How many total items did we sell?
SELECT SUM(quantity) FROM orders
2125


8. How much was spent on books?
SELECT SUM(price) FROM items NATURAL JOIN orders WHERE category LIKE "%book%";
SUM(price)
59241

(to check for duplicate values): SELECT price, title FROM items NATURAL JOIN orders ORDER BY title ASC


9. Simulate buying an item by inserting a User for yourself and an Order for that User.
INSERT INTO users (id, first_name, last_name, email) VALUES (9088, "Michelle", "Dotzenrod", "dotzenrods@gmail.com");

INSERT INTO orders (id, user_id, item_id, quantity, created_at)
VALUES (10000, 9088, 68, 23, 2015-09-08 00:40:30.457689);
*syntax error on time 00

##Hard Mode
What item was ordered most often? Grossed the most money?
item_id 66

What user spent the most?
SELECT MAX(price) FROM items NATURAL JOIN orders WHERE = (SELECT first_name, last_name FROM users);

What were the top 3 highest grossing categories?

