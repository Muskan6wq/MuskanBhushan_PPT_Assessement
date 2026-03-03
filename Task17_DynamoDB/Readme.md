
Objective:
Understand NoSQL database using DynamoDB.

Description:
A DynamoDB table was created with partition key and sort key. Items were inserted and verified.


Table Name: Task-17-DynamoDB
Partition Key: UID (Number)
Sort Key: OID (Number)

Objective:
To create a DynamoDB table with partition key and sort key and insert multiple items with attributes.

What I did step by step:

1. I went to AWS Console → DynamoDB.
2. I clicked on Create table.
3. I gave table name:
   Task-17-DynamoDB
4. I added Partition key:
   UID (Number)
5. I added Sort key:
   OID (Number)
6. I kept capacity mode as On-demand.
7. I clicked Create table.
8. I waited until table status became Active.

After table creation, I inserted items:

First Item:
UID : 101
OID : 100
Attributes:
item1 : French Fries
item2 : Coke

Second Item:
UID : 2
OID : 101
Attributes:
item1 : Cheesy-Farmhouse

9. I went to Explore table items.
10. I clicked Create item.
11. I added above values in JSON format.
12. I saved the items.
13. I clicked Scan to verify the inserted data.
14. Both items were successfully displayed.

Result:
The DynamoDB table was successfully created.
Partition key and sort key were configured properly.
Multiple items were inserted successfully.
Data is stored in NoSQL format (JSON-based structure).

Services Used:
- Amazon DynamoDB

Proof:
- Screenshot of table status (Active)
- Screenshot of inserted items after scan
Result:
NoSQL data stored and accessed successfully.
