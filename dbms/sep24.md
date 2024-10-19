cartesian product *
	select * 
	generates every possible pair of every column, indicated by the wild cad *
	simply compiles a tuple. does not care about the filter condition. that comes after
	thus, this is considered the most expensive operation possible in a db.
	not useful on its own-- essentially just a display statement.. better with WHERE clause.

join operation
	first, the dbms had to do a cartesian product from two tables
	then, after we join them. it checks the WHERE condition.
	
