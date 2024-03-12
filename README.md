# Second_Challenge
classDiagram
    Bank --* Client: has
    Bank --* Account: has
    Client --* Transaction: performs
    Bank --* ATM: has
    Client --* ATM: uses
    class Bank {
        + str name
        + str address
        + str phone
        + str email
        + list[Client] clients
        + list[Account] accounts
        + list[ATM] ATMs
    }
    
    class Client {
        + str name
        + str address
        + str phone
        + str email
        + list[Account] accounts
    }

    class Account {
        + str number
        + float balance
        + str type
        + float interest_rate
        + list[Transaction] Tratransactions
    }

    class Transaction {
        + datetime date
        + float amount
        + str type
        + Account from_account
        + Account to_account
    }

    class ATM {
        + str location
        + str serial_number
        + str status
        + float cash_available
    }
