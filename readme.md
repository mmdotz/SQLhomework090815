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




6. How much would it cost to buy one of each tool?


7. How many total items did we sell?


8. How much was spent on books?


9. Simulate buying an item by inserting a User for yourself and an Order for that User.

##Hard Mode
What item was ordered most often? Grossed the most money?


What user spent the most?


What were the top 3 highest grossing categories?

