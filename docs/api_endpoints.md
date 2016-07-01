# API Endpoints


Web browser <--> Front-end <--> **api.py <--> connector.py**

## api.py
RESTful service for vote saving

Resource | HTTP Method | URL and arguments | Returns
----|-----|----- |-----|
Vote saving | POST | <host:port>/send-vote?proposal=<string> | JSON object with confirmation, vote and the wallet's address that stores our votes
Vote status | GET | <host:port>/vote-count | Total number of votes on each option for the proposal



## connector.py
21.co server for operations over micropayments (One satoshi per operation)

Resource | HTTP Method | URL and arguments | Returns
----|-----|-----|-----|
Vote accounting to the Blockchain | POST |  <host:port>/write-vote?proposal=<string> | Wallet address
Votes on each proposal | GET | <host:port>/count | Total votes for the proposal
