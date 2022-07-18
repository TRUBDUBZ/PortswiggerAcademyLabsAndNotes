# SQL Injections

- using SQL search queries to uncover sensitive data ie paswd/creds

## Example

  `https://insecure-website.com/products?category=Gifts`

- This Url causes the app to make an SQL query to retrieve details
  
  `SELECT * FROM products WHERE category = 'Gifts' AND released = 1`
  
  - This SQL query asks the database to return:
    - all details ( * )
    - from the products table
    - where the category is Gifts
    - and released is 1.

- The restriction released = 1 is being used to hide products that are not released. For unreleased products, presumably released = 0

- The application doesnt implement any defenses against SQL injection attacks, so an attacker can construct an attack like:

  `SELECT * FROM products WHERE caategory = 'Gifts'--' AND released = 1`

- The key thing here is that the double-dash sequence -- is a comment indicator in SQL, and means that the rest of the query is interpreted as a comment.
- This effectively removes the remainder of the query, so it no longer includes AND released = 1. This means that all products are displayed, including unreleased products.

- Going further, an attacker can cause the application to display all the products in any category, including categories that they don't know about:
  
  `https://insecure-website.com/products?category=Gifts'+OR+1=1--`

- This results in the SQL query:

  `SELECT * FROM products WHERE category = 'Gifts' OR 1=1--' AND released = 1`

- The modified query will return all items where either the category is 'Gifts', or 1 is equal to 1. 

- Since 1=1 is always true, the query will return all items.

