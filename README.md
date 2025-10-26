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
