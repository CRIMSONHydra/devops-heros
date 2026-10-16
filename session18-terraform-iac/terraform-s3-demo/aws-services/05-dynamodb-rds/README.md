# DynamoDB & RDS - Database Services

# DynamoDB

## NoSQL
NoSQL means the database does not use fixed tables with rows and joins like SQL. DynamoDB is a key-value and document database. It is fast and scales easily.

## Tables
A table is where DynamoDB stores your data. Unlike SQL, you only need to define the key, not all columns. AWS fully manages the servers for you (serverless).

## Items
An item is one record in a table, like a row in SQL. Each item must have the primary key. Items can have different attributes from each other.

## Attributes
Attributes are the pieces of data inside an item, like `name` or `age`. They are like columns in SQL, but each item can have different ones. Values can be strings, numbers, lists, maps, and more.

## Partition key
The partition key is the main key that decides where the item is stored. DynamoDB hashes it to pick a partition. Choose a key with many different values so the load spreads evenly.

## Sort key
The sort key is an optional second key. Together with the partition key it makes a unique key. It keeps items with the same partition key in order, so you can query ranges, like orders by date.

## Use cases
- Shopping carts and user sessions.
- Gaming leaderboards.
- IoT and real-time data.
- Apps that need very fast reads and writes at any scale.

---

# RDS

## Relational database
A relational database stores data in tables with rows and columns and uses SQL. Tables can be linked with relationships and joins. It is good for structured data that needs strong consistency.

## Supported engines
RDS supports MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Amazon Aurora. You pick the one your app needs. Aurora is AWS's own faster, cloud-built option.

## DB instances
A DB instance is the database server that RDS runs for you. You pick its size (CPU and memory) and storage. AWS handles patching, setup, and hardware, and you do not get OS access.

## Security
Put the database in a private subnet and control access with security groups. Use encryption at rest (KMS) and in transit (SSL/TLS). Use IAM and strong passwords, and never make the database public unless needed.

## Backups
RDS takes automatic daily backups and keeps transaction logs, so you can restore to any point in time. You can also take manual snapshots that stay until you delete them. Backups are kept for 1 to 35 days.

## Multi-AZ
Multi-AZ keeps a standby copy of your database in a different Availability Zone. If the main one fails, RDS switches to the standby automatically. This is for high availability, not for extra speed.

## Read replicas
A read replica is a copy of the database used only for reading. It helps handle more read traffic and lowers the load on the main database. It can be in another region and can be promoted to a standalone database.

## Use cases
- Business apps, ERP, and CRM.
- E-commerce with orders and payments.
- Web apps that need SQL, joins, and transactions.
- Moving an existing on-premises SQL database to the cloud.
