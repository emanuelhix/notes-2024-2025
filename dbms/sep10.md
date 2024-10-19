problem 1: a company database (slide 64) 
we use real world assumptions here.
we notice the action verb "controls"
employees have a name, social security number, and address. we create an **entity set** for **employee**.
employee = {name, SSN, address}
we create a department entity set, department = {number, name}. 
there is a relationship between employee and department, because employees "manage" (another action verb) the department.

so, employee <----> department <-- controls -- project
this means two things, since the arrow is double sided:
1. employees are only managed under one dept
2. a single employee only manages one dept

we notice "assigned to"  for employees and projects, so we add another relationship
* === is double lines, meaning employees can have multiple projects

weak entity set:  
    if an entity cannot be identified without using some info from some other table, then its a weak entity set.
    in other words, its existence depends on on or more other entity sets.

