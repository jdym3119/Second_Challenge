# Second_Challenge
classDiagram
  Bank --* Client: has
  Bank --* Account: has
  Client --* Transaction: performs
  Bank --* ATM: has
  Client --* ATM: uses

  class Bank {
    + name: str
    + address: str
    + phone: str
    + email: str
    + clients: list[Client]
    + accounts: list[Account]
    + ATMs: list[ATM]
  }

  class Client {
    + name: str
    + address: str
    + phone: str
    + email: str
    + accounts: list[Account]
  }

  class Account {
    + number: str
    + balance: float
    + type: str  # Checking, Savings, etc.
    + interest_rate: float
    + transactions: list[Transaction]
  }

  class Transaction {
    + date: datetime
    + amount: float
    + type: str  # Deposit, Withdrawal, Transfer
    + from_account: Account
    + to_account: Account
  }

  class ATM {
    + location: str
    + serial_number: str
    + status: str  # Online, Offline, Maintenance
    + cash_available: float
  }
