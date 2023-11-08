

## Retrieve all the customers' names and addresses who live in the United States

=>SELECT name FROM customers WHERE country = 'United States'

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Retrieve all the customers in ascending name sequence

=>SELECT name FROM customers ORDER BY name

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Retrieve all the products whose name contains the word socks

=> SELECT * FROM products WHERE product_name ILIKE '%socks%'

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Retrieve all the products which cost more than 100 showing product id, name, unit price and supplier id.

=>SELECT
    p.id AS product_id,
    p.product_name AS product_name,
    pa.unit_price AS unit_price,
    pa.supp_id AS supp_id
FROM
    products p
JOIN
    product_availability pa
ON
    p.id = pa.prod_id
WHERE
    pa.unit_price > 100;

////////////////////////////////////////////////////////////////////////////////////////////////////////////
    
## Retrieve the 5 most expensive products

=>SELECT * FROM product_availability ORDER BY unit_price DESC LIMIT 5;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Retrieve all the products with their corresponding suppliers. The result should only contain the columns product_name, unit_price and supplier_name

=>SELECT 
pa.product_name AS new_name, 
pb.unit_price AS new_price, 
pc.supplier_name AS new_supplier

FROM 
products AS pa JOIN product_availability AS pb 
ON pa.id = pb.prod_id 
JOIN suppliers AS pc ON 
pb.supp_id = pc.id;

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Retrieve all the products sold by suppliers based in the United Kingdom. The result should only contain the columns product_name and supplier_name.

=>SELECT
    p.product_name AS new_name,  //  OR p.product_name to retain old name
    s.supplier_name AS new_supp  // OR s.supplier_name to retain old name
FROM
    products AS p // OR products p
JOIN
    product_availability AS pa // OR product_availability pa
ON
    p.id = pa.prod_id 
JOIN
    suppliers AS s // OR suppliers s
ON
    pa.supp_id = s.id
WHERE
    s.country = 'United Kingdom';

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Retrieve all orders, including order items, from customer ID 1. Include order id, reference, date and total cost (calculated as quantity * unit price).

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Retrieve all orders, including order items, from customer named Hope Crosby

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Retrieve all the products in the order ORD006. The result should only contain the columns product_name, unit_price and quantity.

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Retrieve all the products with their supplier for all orders of all customers. 
## The result should only contain the columns name (from customer), order_reference, order_date, product_name, supplier_name and quantity.

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## Retrieve the names of all customers who bought a product from a supplier based in China.

////////////////////////////////////////////////////////////////////////////////////////////////////////////

## List all orders giving customer name, order reference, order date and order total amount (quantity * unit price) in descending order of total.

////////////////////////////////////////////////////////////////////////////////////////////////////////////



