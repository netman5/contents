# Transaction In Relational Database Management Systems
![[DBMS-Transaction-Processing.jpg.jpeg]]
Image courtesy of educba

## What is Database Transaction? 

Well as the name suggest, it is performing an operation either by adding, updating or removing from a database. Take for example, a transaction occurring from your bank account 😉️, it is either you perform a credit transaction where you add or receive money into your account or you make a debit transaction which result in updating the current balance.

If you understand the above explanation then it would be easy to grab what DB transaction is.

Database Transaction can be defined as sets or units of tasks performed at a single point in time against a database which is independent of other transaction. In a nutshell database transaction is any change in the database. Click [here](https://www.guru99.com/dbms-transaction-management.html) to read more

It is said that all transaction or database access which start with the word **Begin** and **End** transaction statement are considered a single logical transaction in DBMS.

A transaction may or may not change the state of a database, a successful transaction may change the the current state of the database from a consistent state to another. In the situation of a fail transaction the state of the database remain the same. That is it makes no changes to the state of the database.

In a situation where the transaction does not update the state of the database, for instance when retrieving data, this type of transaction is referred to as a read-only transaction.

For example when querying to list all records from a table

`SELECT * FROM tablename;`

## The acronym ACID
The above acronym was formed purposely for conformity and maintaining of data & database integrity during & after transaction process. According to [database guide](https://database.guide/sql-transactions-tutorial/)it refers to it as set of properties that guarantee database transactions are processed reliably. ACID also concerned with how a database recovers from any failure that might occur during transactions.

Let us look into the meaning of each letter of the ACID

### Atomicity
This guarantee that either all the transactions succeed or none of it does. What this is saying in essence is that if a part of the transaction fails the whole transactions fails. You don't get some of part of transaction succeed and others parts fail. Atomicity cares about either success or nothing.

### Consistency
A transaction can only change the state of the database from a valid one to another valid state maintaining the predefined rules which includes Constraint, Cascade etc. that has been applied on the database. Consistency guarantees that all data will be consistent.

### Isolation
This guarantees that all transactions exist in their own world, that is, each transaction are in complete isolation of others. No two transaction taking place at the same time will ever see the change of the other one. A transaction cannot read data from any other transaction that is yet to be completed.

### Durability
This guarantees the reliability of the data once a successful transaction has taken place. It means once a transaction is committed, it persisted on the system or server whichever one even in the wake of a hardware failure or system crash. A successful transaction or changes must be recoverable and stored permanently in the system.

Let us quickly see a transaction in effect, I'll be using PostgreSQL to demonstrate how a transaction is performed.

Since I started with an example of bank transaction, we might as well just stick to it for the practical example.

We will:
- START TRANSACTION
- Debit account 2
- Credit account 1
- COMMIT TRANSACTION

First lets create the account table

```
DROP TABLE IF EXISTS accounts;
CREATE TABLE accounts (
    id INT GENERATED BY DEFAULT AS IDENTITY,
    name VARCHAR(100) NOT NULL,
    balance DEC(15,2) NOT NULL,
    PRIMARY KEY(id)
);
```


We can start a transaction by inserting data into our account table using `BEGIN TRANSACTION;` or `BEGIN WORK` or just `BEGIN` keyword and commit the transaction by using either `COMMIT TRANSACTION;` or `COMMIT WORK;` or my favorite `COMMIT` command.

Lets insert into table the internet most famous duo

```
-- start a transaction
BEGIN;

-- insert a new row into the accounts table
INSERT INTO accounts(name,balance)
VALUES('Jane Doe',10000);

INSERT INTO accounts(name,balance)
VALUES('John Doe',30000);

-- commit the change (or roll it back later)
COMMIT;
```

Let check the accounts table for the new entries `SELECT * FROM accounts;`
![[account_details.png]]
Then let's transfer $5000 from John's account to Jane but we will be performing the transactions using two sessions

```
BEGIN;

UPDATE accounts 
SET balance = balance - 5000
WHERE id = 2;
```

Let's check both account balance

```
SELECT 
    id,
    name,
    balance
FROM 
    accounts;
```

As we can see from the screenshot below that John account has been debited 
![[balance.png]]

Let's credit lucky Jane and commit
```
UPDATE accounts
SET balance = balance + 5000
WHERE id = 1; 
```

```
COMMIT
```

![[balance_after.png]]
Putting it all together
```
-- start a transaction
BEGIN;

-- deduct 5000 from account 2
UPDATE accounts 
SET balance = balance - 5000
WHERE id = 2;

-- add 5000 to account 1
UPDATE accounts
SET balance = balance + 5000
WHERE id = 1; 

-- select the data from accounts
SELECT id, name, balance
FROM accounts;

-- commit the transaction
COMMIT;
```

A transaction can be rollback using `ROLLBACK`.


And there you have it, I hope I have succeeded in confusing you the more (Joking). If you like my  content you can connect with me here on [LinkedIn](https://www.linkedin.com/in/ola-ishola/) and [Twitter](https://twitter.com/Orlaish)


Thanks for reading.