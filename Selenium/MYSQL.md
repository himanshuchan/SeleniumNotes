- mySQL is a relational database. It is not case sensitive.
- Create database mydb;//create new database named mydb.
- Use mydb;//select this database for the use.
- Alter database read only =1;//makes database to read only.
- Drop database mydb;//drops or delete database. It will fails if database is in read only mode.
- alter database mydb read only=0;//make table writable
- create table employees(￼adhar_no int primary key,

employee_id int ==unique==, //unique constraint- now there cannot be two employee_id with same value  
first_name varchar(50),  
last_name varchar(50),  
hourly_pay decimal(5,2), //eg 50000.23  
hire_date date //date is a format  
Rent int default 0); //==default constraint== with value is 0

- rename table employees to workers;//renames the table.
- alter table employees

modify column email varchar(10);//modify datatype of email coumn

- Alter table employees￼drop column email;//drops or delete the column
- set autocommit =off;//turns off autocommit
- Rollback;//rollbacks the changes which you have done
- create table datetimetable(

my_date date,  
my_time time,  
my_both datetime);

- insert into datetimetable

values(current_date(),current_time(),now());

- Alter table products￼add constraint￼unique(product_name);//unique_constraint is added in product_name column in products table
- alter table products

modify price int not null;//added not null constraint for column named price

- alter table employees

add constraint chk_constraint check(hourly_pay\>12.00);//adding a ==check constraint== where we have added a condition.

- Alter table employees￼drop check chk_constraint;//to drop the check constraint
- Alter table products￼alter price set default 0;//adding a default constraint on already created table
- Primary key is a unique identifier. It can't be null.￼alter table transactions￼add constraint￼primary key (transaction_id);//adding primary key constraint into already created column
- select max(amount) as maximum_amount from transactions;//using alias
- select * from

transactions as tr right join products as pr  
on tr.transaction_id=pr.transaction_id;

-