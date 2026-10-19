<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Query Data with DynamoDB

**Project Link:** [View Project](https://nextwork.ai/projects/0001cf4c-8256-52ae-b09c-6e99ed36462f)

**Author:** Ahmed Umar Rehman  
**Email:** ahmedumar475@gmail.com

---

![Image](https://nextwork.ai/calm_indigo_beautiful_lizard/uploads/0001cf4c-8256-52ae-b09c-6e99ed36462f_733d9399)

## Introducing Today's Project!

### What is Amazon DynamoDB?

Amazon DynamoDB is a non-relational (NoSQL) database that stores data in tables, items, and attributes.
It is useful because it provides:
- Flexibility — each item can have its own set of attributes.
- Fast data access — partition keys help DynamoDB quickly find items.
- Scalability — it can handle large amounts of data and requests.
- Efficient queries — partition and sort keys help retrieve specific data

### How I used Amazon DynamoDB in this project

In today's project, I used Amazon DynamoDB to create tables, load data into them using AWS CloudShell, query the data, and update related tables using transactions.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is how important data modelling is for DynamoDB queries, especially the need to use the partition key when querying data.

### This project took me...

This project took me 40 mins

## Querying DynamoDB Tables

A partition key is a key used to identify and locate items in a DynamoDB table.

A sort key is an optional key used to organize and sort items with the same partition key, allowing you to find related data more precisely.

![Image](https://nextwork.ai/calm_indigo_beautiful_lizard/uploads/0001cf4c-8256-52ae-b09c-6e99ed36462f_d105b0b0)

## Limits of Using DynamoDB

I ran into an error when I queried for AbdurRehman. This was because I tried to query using an attribute that was not the table's partition key.

Insights we could extract from our Comment table include the comments associated with a specific post and the users who posted those comments.

![Image](https://nextwork.ai/calm_indigo_beautiful_lizard/uploads/0001cf4c-8256-52ae-b09c-6e99ed36462f_cb3e260c)

## Running Queries with CLI

This query will retrieve the item with Id = 101 from the ContentCatalog table and return only its Title, ContentType, and Services attributes, while using a strongly consistent read and showing the consumed capacity.

Query options I could add to my query are --consistent-read, --projection-expression, and --return-consumed-capacity to control read consistency, select specific attributes, and check the capacity consumed by the request.

![Image](https://nextwork.ai/calm_indigo_beautiful_lizard/uploads/0001cf4c-8256-52ae-b09c-6e99ed36462f_733d9399)

## Transactions

A transaction is a group of operations that must all succeed; if one operation fails, none of the changes are applied.  

I ran a transaction using the `transact-write-items` AWS CLI command. This transaction did two things: added a new comment to the `Comment` table and increased the `Comments` count in the related `Forum` table by 1.

![Image](https://nextwork.ai/calm_indigo_beautiful_lizard/uploads/0001cf4c-8256-52ae-b09c-6e99ed36462f_2f65f83e)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/0001cf4c-8256-52ae-b09c-6e99ed36462f)*
