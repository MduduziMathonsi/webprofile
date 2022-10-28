
Table : Customers
Schema: public 
Table responsibility : Stores customers details

| Column      | Datatype       | Description                        |
| ----------- | ---------------|------------------------------------|
| CustomerID  |  INT           | PRIMARY KEY for customers table    |
| FirstName   | VARCHAR(50)    | Customer's first name              |
| LastName    | VARCHAR(50)    | Customer's last name               |
| Gender      | VARCHAR        | Customer's gender Male/Female      |
| Address     | VARCHAR(200)   | Customer's residentail address     |
| Phone       | VARCHAR(20)    | Customer's contact number          |
| Email       | VARCHAR(100)   | Customer's email address           |
| City        | VARCHAR(20)    | Customer's city of residence       |
| Country     | VARCHAR(50)    | Customer's country of residence    |

Table : Employees
Schema: public
Table responsibility : Stores Employees details


| Column     | Datatype     | Description                         |
| -----------|--------------|-------------------------------------|
| EmployeeID |  INT         | PRIMARY KEY for Employees table     |
| FirstName  | VARCHAR(50)  | Employee first name                 |
| LastName   | VARCHAR(50)  | Employee last name                  |
| Email      | VARCHAR(100) | Employee gender Male/Female         |
| JobTitle   | VARCHAR(20)  | Employee job title                  |

Table : Payments
Schema: public
Table responsibility : Stores customers payments details

| Column      | Datatype       | Description                                             |
|-----------  |----------------|---------------------------------------------------------|
| CustomerID  |  INT           | FOREIGN KEY  REFERENCES CustomerID in Customer table    |                                                                             
| PaymentID   |  INT           | PRIMARY KEY for payments table                          |
| PaymentDate | DATE           | date of payment                                         |
| Amount      | DECIMAL        | Amount paid by the customer                             |


Table : Products
Schema: public
Table responsibility : Stores products details

| Column       | Datatype     | Description                                                      |
| -------------|--------------|------------------------------------------------------------------|
| ProductId    |  INT         | PRIMARY KEY for product table                                    |                                                                  
| ProductName  | VARCHAR(100) | product name                                                     |
| Description  | VARCHAR(300) | product description                                              |
| BuyPrice     | DECIMAL      | product price                                                    |


Table : Orders
Schema: public
Table responsibility : Stores order detail

| Column                | Datatype       | Description                                          |
| --------------------  |----------------|------------------------------------------------------|
| OrderId               |  INT           | PRIMARY KEY for order table                          |
| ProductID             |  INT           | FOREIGN KEY REFERENCES ProductID in Product table    |
| PaymentID             |  INT           | FOREIGN KEY REFERENCES PaymentID in Payment table    |                                                                      
| FulfilledByEmployeeID |  INT           | FOREIGN KEY REFERENCES EmployeeID in Employees table |                                                                       
| DateRequired          | DATE           | Order required date                                  |
| DateShipped           | DATE           | Order shipped date                                   |
| Status                |VARCHAR(20)     | Order status                                         |

