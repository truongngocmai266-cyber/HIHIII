```mermaid
erDiagram
    USERS {
        int id PK
        string username
        string full_name
        string role
    }

    ORDERS {
        int id PK
        int user_id FK
        decimal total_amount
        string status
    }

    ORDER_ITEMS {
        int order_item_id PK
        int order_id FK
        int product_id FK
        int quantity
        decimal price_per_unit
    }

    PRODUCTS {
        int id PK
        string sku
        string name
        decimal price
        int stock_quantity
    }

    USERS ||--o{ ORDERS : "places"
    ORDERS ||--o{ ORDER_ITEMS : "contains"
    PRODUCTS ||--o{ ORDER_ITEMS : "included in"
```mermaid
flowchart LR
    %% Đặt hướng từ trái sang phải
    USERS[USERS<br/>id (PK)<br/>username<br/>full_name<br/>role]
    ORDERS[ORDERS<br/>id (PK)<br/>user_id (FK)<br/>total_amount<br/>status]
    ORDER_ITEMS[ORDER_ITEMS<br/>order_item_id (PK)<br/>order_id (FK)<br/>product_id (FK)<br/>quantity<br/>price_per_unit]
    PRODUCTS[PRODUCTS<br/>id (PK)<br/>sku<br/>name<br/>price<br/>stock_quantity]

    %% Liên kết giữa các bảng
    USERS -->|places| ORDERS
    ORDERS -->|contains| ORDER_ITEMS
    PRODUCTS -->|included in| ORDER_ITEMS

