# Functional 

- tasks can only be TEXT
- users should be able to READ all of their items
- users should be able to CREATE a new todo item
- users should be able to UPDATE an existing todo items
- user should be able to COMPLETE (update the status) 
- user should be able to DELETE the todo
- user should be able to ORDER the todo based on their priority

- user should be able to CREATE A LIST OF TODO ITEMS (TASK), edit the list
filter, sort list, delete the list

- maybe share the list with someone?  
- create and login with email and password?

## A to-do list application is typically read-heavy. 
Although users may add or check off tasks periodically, they spend most of their time looking at their list and figuring out the next item. Users fetch all tasks every single time they open the list, making reads more frequent than writes.


## Understanding whether an application is read-heavy or write-heavy helps determine the most important aspects of the system architecture and influences design decisions. 

Different optimization strategies and infrastructure choices are needed depending on whether the system primarily handles reads or writes, which affects performance, scaling, and database design.

