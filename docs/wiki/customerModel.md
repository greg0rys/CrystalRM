```mermaid
erDiagram
    CUSTOMER ||--o{ PROJECT : "has many"
    CUSTOMER ||--o{ PURCHASE : "has many"
    PROJECT ||--o{ PURCHASE : "has many"

    CUSTOMER {
        bigint id PK
        string name
        datetime created_at
        datetime updated_at
    }

    PROJECT {
        bigint id PK
        bigint customer_id FK
        string name
        datetime created_at
        datetime updated_at
    }

    PURCHASE {
        bigint id PK
        bigint customer_id FK
        bigint project_id FK
        decimal amount
        datetime created_at
        datetime updated_at
    }
