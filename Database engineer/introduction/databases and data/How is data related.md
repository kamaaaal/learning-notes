data stored in database cannot be in isolation it should be related so we can process it to be a meaningful data.

in the below example. the orders table is related to customers table by having the same customer id

![](Pasted%20image%2020240220072814.png)
	in these table -
		customer id , firstname etc are fields.
		 and the values / rows are records.


#### Primary keys :
every record or row should be uniquely identifiable. eg. even if the first name and last name of a customer exist already, so we always have a **Primary key field** (`CustomerID` in this case) in a table which uniquely identifies a row.

#### Foreign Keys :

Order id in the order table is the primary key of Order table. `Customer ID` in orders table is what establishes the relation between Customer and Order Table.  which is Foreign Key field. Foreign key connects to the primary key (Customer ID) of another table (Customer table in this case) 