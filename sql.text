
create database MySQL_Assignment;
use MySQL_Assignment;

--creating salesPeople table
create table SalesPeople(
Snum int,
primary key(Snum),
Sname varchar(50) unique,
City varchar(50),
Comm int
);

insert into SalesPeople values(1001, 'Peel', 'London', 12);
insert into SalesPeople values(1002 , 'Serres', 'Sanjose', 13);
insert into SalesPeople values(1004 ,'Motika' ,'London' ,11);
insert into SalesPeople values(1007 ,'Rifkin' ,'Barcelona' ,15);
insert into SalesPeople values(1003 ,'Axelrod' ,'Newyork' ,10);

--creating customer table
create table Customers(
Cnum int,
primary key(Cnum),
Cname varchar(50),
City varchar(50) not null,
Snum int,
foreign key (Snum)
references SalesPeople(Snum)
);

insert into Customers values(2001 , 'Hoffman', 'London' ,1001);
insert into Customers values(2002  ,'Giovanni', 'Rome' ,1003);
insert into Customers values(2003  ,'Liu' ,'Sanjose' ,1002);
insert into Customers values(2004  ,'Grass', 'Berlin' ,1002);
insert into Customers values(2006 ,'Clemens' ,'London' ,1001);
insert into Customers values(2008 ,'Cisneros' ,'Sanjose' ,1007);
insert into Customers values(2007, 'Pereira' ,'Rome' ,1004);

--CREATING ORDERS TABLE 
create table Orders(
Onum int,
primary key(Onum),
Amt int,
Odate varchar(50) not null,
Cnum int,
foreign key (Cnum)
references Customers(Cnum),
Snum int,
foreign key (Snum)
references SalesPeople(Snum)
);
--INSERTING VALUES INTO TABLE
insert into Orders values(3001 ,18.69 ,'3-10-1990' ,2008 ,1007);
insert into Orders values(3003 ,767.19 ,'3-10-1990' ,2001 ,1001);
insert into Orders values(3002 ,1900.10 ,'3-10-1990' ,2007 ,1004);
insert into Orders values(3005,  5160.45, '3-10-1990' ,2003 ,1002);
insert into Orders values(3006 , 1098.16 ,'3-10-1990' ,2008 ,1007);
insert into Orders values(3009 ,1713.23 , '4-10-1990', 2002, 1003);
insert into Orders values(3007 , 75.75, '4-10-1990', 2004 ,1002);
insert into Orders values(3008 , 4273.00 ,'5-10-1990', 2006 ,1001);
insert into Orders values(3010 , 1309.95, '6-10-1990' ,2004 ,1002);
insert into Orders values(3011 , 9891.88 ,'6-10-1990', 2006, 1001);


-- DISPLAYING TABLE VALUES 
select * from orders;
select * from Customers;
select * from SalesPeople;


--ANSWERS FOR QUERIES

-- Q1.Ans

select count(Sname) as count from SalesPeople where Sname like 'a%' or Sname like 'A%';


-- Q2.Ans

select * from SalesPeople where Snum in (select Snum  from orders group by Snum having sum(Amt) > 2000);


-- Q3.Ans

select count(Sname) as count1 from SalesPeople where City='Newyork';


-- Q4.Ans

select count(Sname) as count2  from SalesPeople where City='London' or City='Paris';


-- Q5.Ans

select sn.Sname,sn.City, count( os.Onum) as Total_Orders,os.Odate from SalesPeople sn join orders os on sn.Snum=os.Snum group by sn.Snum;