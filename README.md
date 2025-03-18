
# MIST 4610 Group Project
This project involves the development and population of a comprehensive relational database system for LensCrafters, designed to efficiently manage the company’s business operations. The database model includes key entities such as Customers, Employees, Locations, Suppliers, ProductLines, Frames, Lenses, Orders, OrderDetails, Payments, Optometrists, and Prescriptions. The populated data model allows LensCrafters' management to perform advanced SQL queries and analytics for decision-making, customer behavior analysis, sales tracking, inventory control, and overall business efficiency.


## Group Members
##### Nabeel Sadiq
##### Josh Libatique
##### Anthony Lopez
##### Ethan Payne
##### Claire Stockman
## Data Model
Our model is based on the structure of a optical retail business, like LensCrafters. The Location entity represents the physical store locations across different regions. Each location can have multiple employees working within it, which is reflected by the one-to-many relationship between the Locations and Employees entities.

The Employees table stores the details of all employees, including their assigned store location. Employees play a critical role in customer service and sales, and each employee may assist multiple customers. Therefore, we have a one-to-many relationship between the Employees entity and the Customers entity, as each customer is linked to an employee for service purposes.

Each customer has their personal and contact information stored in the Customers entity. Customers place various orders, and the Orders entity captures order-specific details. The one-to-many relationship between Customers and Orders reflects that a single customer may place multiple orders over time.

To process payments for these orders, we have a Payments entity. Each payment is linked to a specific customer, forming another one-to-many relationship from Customers to Payments. Payment information includes payment type, amount, and date, providing complete visibility into financial transactions.

On the product side, Suppliers provide materials for LensCrafters' products. Each supplier offers various product lines, represented by the one-to-many relationship between the Suppliers and ProductLines entities. Each product line contains both frames and lenses.

Frames and lenses are maintained in the Frames and Lenses entities, both connected to ProductLines through one-to-many relationships. The Frames entity includes details such as width, height, type, material, and price, while the Lenses entity records material, coating type, and price.

Orders include specific products, so the OrderDetails entity serves as an associative entity connecting Orders, Frames, and Lenses. It records which frames and lenses are included in each order, along with quantity, price, and product type.

In addition, the optical service aspect is covered through the Optometrists entity, which stores details of optometrists affiliated with each store. Each optometrist may issue multiple prescriptions to customers, represented by the one-to-many relationship between Optometrists and Prescriptions. The Prescriptions entity contains important vision data, including sphere, cylinder, axis values, and prescription type for both eyes, linking each prescription to a specific customer and optometrist.

This data model captures the entire customer journey, from initial consultation to product purchase and prescription management, providing LensCrafters with a robust foundation for business operations and data-driven decision-making.


## Data Dictionary
## Queries
## Database Information