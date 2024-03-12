# Second_Challenge
---
Bank
---

The depicted diagram addresses the management of a bank, aiming to represent fundamental relationships and structures within the system. The diagram reflects aspects such as bank information, clients and their accounts, financial transactions, and the presence of ATMs. This representation is crucial for understanding how these entities interact in a financial environment. In summary, the class diagram provides an organized and structured view of key entities and their relationships in a banking context, aiding in system comprehension and design.


```mermaid
classDiagram
    direction RL    
    Bank --* Client: has
    Bank --* Account: has
    Client --* Transaction: performs
    Bank --* ATM: has
    Client --* ATM: uses
    
    class Bank {
        +str name
        +str address
        +str phone
        +str email
        +list[Client] clients
        +list[Account] accounts
        +list[ATM] ATMs
    }
    class Client {
        +str name
        +str address
        +str phone
        +str email
        +list[Account] accounts
    }
    class Account {
        +str number
        +float balance
        +str type
        +float interest_rate
        +list[Transaction] Tratransactions
    }
    class Transaction {
        +datetime date
        +float amount
        +str type
        +Account from_account
        +Account to_account
    }
    class ATM {
        +str location
        +str serial_number
        +str status
        +float cash_available
    }
