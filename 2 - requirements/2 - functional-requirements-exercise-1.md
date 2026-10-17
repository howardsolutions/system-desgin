# EXERCISE: FUNCTIONAL REQUIREMENTS 

You're desigining a MOBILE banking application that allows users to manage a SINGLE bank account.

What are the questions you migh ask?

What are examples of functional requirements?

# Questions? 

- what types of transations should the app support (deposit, withdrawls, transfer)?

- how far back does the user could see all of their transactions history?
How long should the data be stored?

- what level of details does the transaction need to have (avoid fraud transactions)? -- build the schema of transaction in our head

- what level of security that we need to have?
- how do we invalidate sessions/log a user out?

- is there compliance we need to adhere to?
- what are the performance requirements?

- how do we display transaction status?

- what type of notifications do we need to show / send the user? (only balance update, or even when their account in danger of hack?)

- what is the primary device type for users? 

- do we have to support mobile wallets?


## FUNCTIONAL?

- users should be able to login to their account with username / password.
- users should be able to view their current balance, view / search / filter transactions history. 
- user should be able to export transaction data for the past 12 months?
- users should be able to deposit, withdrawls, transfer and receive money to others accounts
- users are required to setup MFA?
- user should be able to categorize transactions for budgeting?
- USD is the only currency we supported
- user CAN'T send if their balance is below 0
- users are located in the US

=> Transaction is the most important here in the system. it make up most of the details