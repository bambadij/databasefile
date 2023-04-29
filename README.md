# databasefile

DATABASES 

 

In this project you are going to use SQL to answer questions about a money transfer business operated by a company called Wave. The schema below is a slightly simplified glimpse of some tables from Wave’s actual PostgreSQL schema. It includes everything you’ll need to answer the questions. 

For each question, please write a SQL query that would answer it. And if you’d like, feel free to also include any notes or comments you have about the question if it would help us understand your thought process! 

Graphical user interface, application Description automatically generated 

The provided project files contain SQL queries to create the tables for different database management systems as well as data for each table. Create a database with the files provided and answer the question provided.

Questions 

1. How many users does Wave have? 

2. How many transfers have been sent in the currency CFA?  

A transfer in Wave is when a user (denoted by their user id in the u_id column) sends money from their Wave account (often to another Wave user, but the recipient might also be a mobile number that hasn’t signed up for an account yet, or the sender of the transfer could be making a bill payment, or a few other possibilities; the `kind` column stores which possibility). 

3. How many different users have sent a transfer in CFA? 

4. How many agent_transactions did we have in the months of 2022 (broken down by month)?  

An agent transaction (often abbreviated atx) is when someone deposits or withdraws money from a Wave agent, and an agent is a person or business that is contracted to facilitate transactions for users. The most important of these are cash-in and cash-out (i.e. loading value into the mobile money system, and then converting it back out again). A typical example: a Wave user deposits some cash into their Wave account with their local agent (an agent transaction), then transfers that money to another Wave user, who in turn withdraws it via another agent transaction at their own local agent. 

5. Over the course of the first half of 2022, how many Wave agents were “net depositors” vs. “net withdrawers”?  

A net depositor is an agent who received more deposit volume than withdrawal volume over some given time frame (and vice versa for a net withdrawer). Whether an agent transaction is a deposit or a withdrawal is determined by the sign of its amount: a negative amount is a deposit, and a positive amount is a withdrawal; zero amounts aren’t allowed. 

6. Build an “atx volume city summary” table: find the volume of agent transactions created in the first half of 2022, grouped by city. You can determine the city where the agent transaction took place from the agent’s city field. 

7. Now separate the atx volume by country as well (so your columns should be country, city, volume). 

8. Build a “send volume by country and kind” table: find the total volume of transfers (by send_amount_scalar) sent in the first half of 2022, grouped by country and transfer kind.  

There are a few different kinds of Wave transfers, e.g. a ‘P2P’ transfer between a Wave user and a mobile number, or a payment from a Wave user to a merchant. The country a transfer was sent from isn’t stored on the transfers table itself, but rather on the wallet table’s ledger_location field (and each transfer has a source_wallet_id). Your columns should be country, transfer kind, and volume. 

9. Then add columns for transaction count and number of unique senders (still broken down by country and transfer kind). 

10. Finally, which wallets sent more than 1,000,000 CFA in transfers in the first quarter (as identified by the source_wallet_id column on the transfers table), and how much did they send? 
