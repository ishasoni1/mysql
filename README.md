create database db1;
use db1;
create table users1(
user_ID int primary key,
name varchar(20)not null,
 mail varchar(50)unique not null,
 phone_no varchar(11) unique not null,
DOB date,
city char(20),
marital_status varchar(25) check(marital_status in
("married","single","divorced")),
gender char(15) check(gender in ("male","female","others"))default
("male"));
create table inventory(
product_id int primary key,
 name varchar(15) unique not null,
 Quantity int check(quantity>0),
 category varchar(24),
marked_price decimal(10,2),
discounted_price decimal(10,2),
date_of_man date,
exprire_date date);

create table transactions(
transaction_id int primary key,
product_id int,
user_ID int,
amount decimal(10,2),
mode_of_payment varchar(40) check(mode_of_payment in("cash","cheque","upi","credit","debit")),
tran_date date,
foreign key(product_id)references inventory(product_id) ,
foreign key(user_ID)references users1(user_ID)
);
select*from users1;
select*from inventory;
select*from transactions;
-- add column
Alter table users1 
add column column1 int;
-- modify column

Alter table users1
modify column1 char(20);
Alter table users1
modify user_ID int  primary key auto_increment;

-- rename column
Alter table users1 rename column column1 to column2;
-- drop column
Alter table users1 drop column column2;

-- inserting values in the table
insert into users1(user_ID,name,mail,phone_no,DOB,city,marital_status,gender) 
values(102,"isha","ish@gmail.com",98456889,"2004-09-23","rajori","single","female");
select* from users1;
insert into users1(user_ID,name,mail,phone_no,DOB,city,marital_status,gender) 
values(103,"nitu","nituh@gmail.com",98676889,"2004-09-10","saritavihar","single","male");
insert into users1(user_ID,name,mail,phone_no,DOB,city,marital_status,gender) 
values(104,"sneha","sneha@gmail.com",984500789,"2014-09-03","chandigarh","married","female");
insert into users1(user_ID,name,mail,phone_no,DOB,city,marital_status,gender) 
values(105,"raju","raj@gmail.com",91126889,"2012-03-05","jaipur","married","male");

insert into users1(user_ID,name,mail,phone_no,city) 
values(106,"priya","priya@gmail.com",88766889,"delhi");
select * from users1;
update users1 set name="nikita" where user_ID=102;
update users1 set name="kki" where city="rajori";
 -- inserting value in inventory 
 -- INSERT Query 1
 
INSERT INTO inventory (product_id, name, Quantity, category, marked_price, discounted_price, date_of_man, exprire_date)
VALUES
(101, 'Laptop Pro X', 50, 'Electronics', 1200.0, 999.99, '2023-01-15', '2023-02-20'),
 (102, 'Wireless Mouse', 200, 'Electronics', 25.0, 19.99, '2023-02-01', '2025-01-31'),
(103, 'Mechanical Keyboard', 150, 'Electronics', 80.0, 69.99, '2023-01-20', '2026-01-19'),
(104, 'Smartphone Model A', 100, 'Electronics', 700.0, 649.99, '2023-03-10', '2024-09-07'),
(105, 'Bluetooth Speaker', 180, 'Electronics', 50.0, 39.99, '2023-02-20', '2025-02-19'),
(106, 'LED Monitor 27"', 75, 'Electronics', 300.0, 259.99, '2023-04-05', '2026-04-04'),
(107, 'External SSD 1TB', 120, 'Electronics', 150.0, 129.99, '2023-03-25', '2027-03-24'),
(108, 'Gaming Headset', 90, 'Electronics', 70.0, 59.99, '2023-01-05', '2025-01-04'),
(109, 'Smartwatch Series 5', 110, 'Wearables', 250.0, 219.99, '2023-02-15', '2024-08-15'),
(110, 'Fitness Tracker', 220, 'Wearables', 60.0, 49.99, '2023-03-01', '2024-02-29'),
(111, 'Running Shoes Pro', 300, 'Footwear', 90.0, 75.0, '2023-04-10', '2025-04-09'),
(112, 'Casual Sneakers', 450, 'Footwear', 65.0, 55.0, '2023-03-18', '2025-03-17'),
(113, 'Men''s T-Shirt', 500, 'Apparel', 20.0, 15.0, '2023-01-25', '2023-07-24'),
(114, 'Women''s Jeans', 350, 'Apparel', 45.0, 38.0, '2023-02-08', '2023-08-07'),
(115, 'Kids Backpack', 280, 'Bags', 30.0, 24.99, '2023-03-05', '2024-03-04'),
(116, 'Leather Wallet', 170, 'Accessories', 40.0, 32.0, '2023-01-01', '2025-12-31'),
(117, 'Sunglasses Aviator', 130, 'Accessories', 55.0, 45.0, '2023-02-28', '2025-02-27'),
(118, 'Coffee Maker', 60, 'Home Appliances', 120.0, 99.0, '2023-04-15', '2026-04-14'),
(119, 'Toaster Oven', 80, 'Home Appliances', 70.0, 59.0, '2023-03-20', '2025-03-19'),
(120, 'Blender High-Speed', 70, 'Home Appliances', 95.0, 79.0, '2023-01-10', '2026-01-09');

select * from inventory;




