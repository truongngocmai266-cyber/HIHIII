### ERD Diagram

```mermaid
flowchart LR
    USERS[USERS<br/>id (PK)<br/>username<br/>full_name<br/>role]
    ORDERS[ORDERS<br/>id (PK)<br/>user_id (FK)<br/>total_amount<br/>status]
    ORDER_ITEMS[ORDER_ITEMS<br/>order_item_id (PK)<br/>order_id (FK)<br/>product_id (FK)<br/>quantity<br/>price_per_unit]
    PRODUCTS[PRODUCTS<br/>id (PK)<br/>sku<br/>name<br/>price<br/>stock_quantity]

    USERS -->|places| ORDERS
    ORDERS -->|contains| ORDER_ITEMS
    PRODUCTS -->|included in| ORDER_ITEMS
