# Transactions

Use the Transactions page to review the history of all transactions made in your account.  Token additions will have a _Type_ of "credit" and API calls will have a _Type_ of "debit".

#### Transaction History

For each transaction made in your account, you will see:

* Date (the date/time of this transaction in PST)
* Type (Debit or Credit depending upon the type of transaction)
* Start Token Balance (the token balance on this account _prior_ to this transaction)
* Amount (the number of tokens debited/credited from/to the account)
* End Token Balance (the token balance on this account _after_ this transaction)
* Resource URI (the target URI sent - this is for API requests only)

#### Transaction Details

For API calls made, you can see more details about the request.  Expand the dropdown panel, and you will see:

* Request UUID (the unique universal ID of this request)
* Resource Method (the HTTP method used in the API request, such as GET, POST, DELETE, etc.)
* User (the name of the user (based on the API Key that made the API request)
* IP Address (the source IP Address that made the API request)
