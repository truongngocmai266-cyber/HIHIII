### ERD Diagram

```mermaid
flowchart LR
    USERS["USERS\nid (PK)\nusername\nfull_name\nrole"]
    ORDERS["ORDERS\nid (PK)\nuser_id (FK)\ntotal_amount\nstatus"]
    ORDER_ITEMS["ORDER_ITEMS\norder_item_id (PK)\norder_id (FK)\nproduct_id (FK)\nquantity\nprice_per_unit"]
    PRODUCTS["PRODUCTS\nid (PK)\nsku\nname\nprice\nstock_quantity"]

    USERS -->|places| ORDERS
    ORDERS -->|contains| ORDER_ITEMS
    PRODUCTS -->|included in| ORDER_ITEMS
