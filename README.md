
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

![image](https://github.com/user-attachments/assets/6daedc7c-532e-4363-a237-6df8beeeeb38)




## Data Dictionary
![image](https://github.com/user-attachments/assets/6897fef7-9703-4ad2-a4f2-2d6fed6c55c6)
![image](https://github.com/user-attachments/assets/2d270a6a-04cf-41e1-b4fb-6674b90bfcf1)
![image](https://github.com/user-attachments/assets/71f60b33-f392-47d3-8fa7-51b57a48a963)
![image](https://github.com/user-attachments/assets/7066f4d0-8ca7-4cc8-adc7-3c95671ba91d)
![image](https://github.com/user-attachments/assets/8228a22f-3b35-4370-9e18-54bc95d78069)
![image](https://github.com/user-attachments/assets/bd1e5702-3241-4641-a38b-9aa3c3132d93)
![image](https://github.com/user-attachments/assets/751478c1-a769-4683-b9c9-423ef6150ee3)
![image](https://github.com/user-attachments/assets/40ef9f3f-e78c-499b-9699-a00dafbc8c50)
![image](https://github.com/user-attachments/assets/cc049267-7118-4891-8927-18084de19c78)
![image](https://github.com/user-attachments/assets/e615272a-d79f-4da2-a273-955f24cbb4ad)
![image](https://github.com/user-attachments/assets/6f257712-9658-4408-9a14-c638fd2a9c59)
![image](https://github.com/user-attachments/assets/c8af37c8-f1f3-4af9-9606-02a2a031558f)








## Queries
### 1) Description
Query 1 lists each customer who has placed more than one order and shows the total number of orders placed by each customer. The query combines the customer's first and last name for readability and orders the results by the number of orders.

![image](https://github.com/user-attachments/assets/53191766-ac22-450a-8903-f22d3ad9849b)

### Justification
Query 1 allows managers to identify repeat customers who are consistently making purchases. These customers are essential to LensCrafters' long-term revenue because retaining repeat customers is more cost-effective than acquiring new ones. Recognizing these loyal customers allows managers to design targeted loyalty programs, personalized marketing offers, or exclusive promotions to foster customer retention and maximize sales. 

### 2) Description
Query 2 calculates the average payment amount for each payment type (e.g., Credit Card, Cash, Debit Card). It groups payments by payment type and orders the results by average amount in descending order.

![image](https://github.com/user-attachments/assets/d65d2aef-1c28-42fe-8eed-a6e790a0086d)

### Justification
Query 2 allows managers to analyze which payment methods tend to generate higher transaction amounts. This insight is valuable for understanding customer payment preferences and tailoring incentives (such as discounts for certain payment types) to encourage customers to use more profitable payment methods.

### 3) Description
Query 3 lists all Frames that have never been ordered by any customer. It uses a NOT EXISTS subquery to check if there is no entry in the OrderDetails table referencing the specific FrameID.

![image](https://github.com/user-attachments/assets/7a735104-97a4-4bc9-a6d4-6ff530386494)

### Justification
This query is useful for managers to identify slow-moving or unsold inventory. Frames that have never been ordered may indicate poor customer demand, unappealing styles, or pricing issues. Managers can use this information to make decisions about running targeted promotions or discounts to move this stock or discontinuing underperforming products

### 4) Description
Query 4 lists all orders that include Complete Pair products. It retrieves the Order ID, Customer Name, and Product Type for orders where the product type is specifically labeled as 'Complete Pair'.

![image](https://github.com/user-attachments/assets/d9a3988e-23bd-4631-964b-5df97f6fa9b1)

### Justification
Managers would want to know how many customers are opting to buy both frames and lenses together as a Complete Pair. This insight is useful because Complete Pair sales typically generate more revenue per order and It helps track customer preference trends. Managers can use this data to promote bundle deals and understand how successful current bundling strategies are.

### 5) Description
Query 5 lists each Product Line's brand name along with the total revenue generated from frames and lenses sold under that product line. It joins the ProductLines table with Frames, Lenses, OrderDetails, and Orders to calculate total revenue per product line, including only those frames and lenses actually sold.

![image](https://github.com/user-attachments/assets/ba938457-fb10-4081-b702-234105917eca)

### Justification
This query allows managers to identify which product lines contribute the most to total sales revenue. By knowing which brands perform well, managers can adjust inventory levels to stock more of high-performing product lines and negotiate better deals with suppliers.

### 6) Description
Query 6 allows the managers to highlight high volume customers. Having access to your important customers allows the store to engage and create lasting relationships with returning customers, while also being able to notice if there are patterns between frequent and infrequent customers. 

![query6](https://github.com/user-attachments/assets/03042cd5-15ce-415a-8436-71baf6510fe8)

This query allows managers to pinpoint their most active, engaged customers—those who consistently return to make purchases more frequently than the average customer. Recognizing these customers is important because they are more likely to be loyal customers, contributing significantly to long-term revenue. Additionally, they are ideal targets for exclusive promotions, personalized offers, or loyalty rewards.

 ### 7) Description
 Query 7 retrieves the customer ID, first name, last name, and prescription date for customers with a progressive prescription. The results are sorted in ascending order to display the oldest prescriptions first.
 
 ![q7 final](https://github.com/user-attachments/assets/8f9ff385-93fa-4bc6-af0f-e5b0b3404477)
 ### Justification
 This query allows the manager to keep track of the oldest given prescriptions for customers with progressive prescriptions. Because progressive prescriptions tend to change faster than bifocal or single vision prescriptions, being able to track the oldest progressive prescriptions allows managers to be weary of which prescriptions may need updating soon, allowing them to anticipate and reach out to customers with potentially changing prescriptions.

## Database Information
