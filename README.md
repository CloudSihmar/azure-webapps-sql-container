Run this application as a container

1. If you are running mysql as PAAS

   Add the schema and items to it like below

   CREATE TABLE Products
(
     ProductID int,
     ProductName varchar(1000),
     Quantity int
)


INSERT INTO Products(ProductID,ProductName,Quantity) VALUES (1,'Mobile',100)

INSERT INTO Products(ProductID,ProductName,Quantity) VALUES (2,'Laptop',200)

INSERT INTO Products(ProductID,ProductName,Quantity) VALUES (3,'Tabs',300)

SELECT * FROM Products
     	


2. If you are running it as a container then run it using the below command

   docker run -dt --name product-database -p 3306:3306 --restart on-failure -e MYSQL_ROOT_PASSWORD=Admin123 mysql

   docker exec -it product-database mysql -uroot -p
   create database appdata;
   use appdata;


   CREATE TABLE Products
(
     ProductID int,
     ProductName varchar(1000),
     Quantity int
);


INSERT INTO Products(ProductID,ProductName,Quantity) VALUES (1,'Mobile',100);

INSERT INTO Products(ProductID,ProductName,Quantity) VALUES (2,'Laptop',200);

INSERT INTO Products(ProductID,ProductName,Quantity) VALUES (3,'Tabs',300);

SELECT * FROM Products;


   
