# PostgreSQL Data Layer

## Overview

PostgreSQL was used as the database layer for the Sales Dashboard project.

The database stores the sales data that serves as the foundation for the analysis and visualization developed in Power BI.

The project uses a dimensional data model composed of a central fact table and supporting dimension tables.

---

## Data Model

The main tables used in the project are:

### `fact_sales`

The central fact table containing sales records and performance metrics.

Main fields:

- `id_sale` — Unique identifier for each sale
- `sale_date` — Date associated with the sale
- `id_product` — Product identifier
- `id_region` — Region identifier
- `sales_target` — Sales target
- `sales_value` — Actual sales value

### `dim_product`

Dimension table containing product information.

Main fields:

- `id_product` — Unique product identifier
- `product_name` — Product name

### `dim_region`

Dimension table containing regional information.

Main fields:

- `id_region` — Unique region identifier
- `region_name` — Region name

---

## Data Relationships

The `fact_sales` table is connected to the dimension tables through their respective identifiers.

The main relationships are:

```text
dim_product
     │
     │ id_product
     ▼
fact_sales
     ▲
     │ id_region
     │
dim_region
