CREATE TABLE ORDERS (ID int,Products jsonb);

INSERT INTO ORDERS(ID, products) VALUES (1,'{"name": ["YourName"], "number": ["YourNumber"]}'::json);

UPDATE ORDERS
SET products = jsonb_insert(
    products,
    '{name, -1}',
    '"hari"'::jsonb
)
WHERE ID = 1;

