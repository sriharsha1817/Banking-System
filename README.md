# Banking System Project

This project is a simple Banking System that allows the user to create accounts, deposit and withdraw funds, view account balance, close accounts, and display all existing accounts. It is built using C++ and utilizes file handling to store account data persistently.

## Features

- **Open an Account**: Create a new account with an initial balance.
- **Balance Enquiry**: Check the details of an account by account number.
- **Deposit**: Deposit money into an account.
- **Withdraw**: Withdraw money from an account (with an exception for insufficient funds).
- **Close Account**: Delete an account.
- **Show All Accounts**: Display details of all existing accounts.

## Requirements

- C++ Compiler (e.g., GCC, MSVC)
- Basic understanding of C++ programming

## How to Run

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/banking-system.git
    cd banking-system
    ```

2. Compile the C++ code:
    ```bash
    g++ -o banking_system main.cpp
    ```

3. Run the compiled program:
    ```bash
    ./banking_system
    ```

4. Follow the on-screen prompts to interact with the system.

## File Structure

- **main.cpp**: Contains the main program and all logic for the banking system (class definitions, member functions, etc.).
- **Bank.data**: A data file where account information is stored and retrieved. This file is updated each time an account is opened, closed, or modified.

## Classes

### `Account`
- **Attributes**:
  - `accountNumber`: Unique ID for each account.
  - `firstName`: Account holder's first name.
  - `lastName`: Account holder's last name.
  - `balance`: Current balance of the account.

- **Methods**:
  - `Deposit(float amount)`: Deposit money into the account.
  - `Withdraw(float amount)`: Withdraw money from the account (throws `InsufficientFunds` exception if balance goes below minimum).
  - `getAccNo()`, `getFirstName()`, `getLastName()`, `getBalance()`: Get the respective account details.

### `Bank`
- **Attributes**:
  - `accounts`: A map containing all accounts indexed by their account numbers.

- **Methods**:
  - `OpenAccount(string fname, string lname, float balance)`: Create a new account and store it in the `accounts` map.
  - `BalanceEnquiry(long accountNumber)`: Retrieve account details by account number.
  - `Deposit(long accountNumber, float amount)`: Deposit funds into an account.
  - `Withdraw(long accountNumber, float amount)`: Withdraw funds from an account.
  - `CloseAccount(long accountNumber)`: Close an account.
  - `ShowAllAccounts()`: Display all accounts.

## Exceptions

- **InsufficientFunds**: This exception is thrown if an account's balance goes below the minimum required balance (defined as `MIN_BALANCE`).

## Example Usage

Once the program is running, you will be presented with a menu of options to interact with the banking system. The options include:

1. **Open an Account**: Create a new account with a first name, last name, and initial balance.
2. **Balance Enquiry**: Check the details of an existing account by providing the account number.
3. **Deposit**: Deposit an amount into an existing account.
4. **Withdraw**: Withdraw an amount from an existing account.
5. **Close an Account**: Close an account by providing the account number.
6. **Show All Accounts**: Display a list of all accounts and their details.
7. **Quit**: Exit the program.

## Notes

- Account details are saved to a file called `Bank.data`. Make sure this file is accessible and writable.
- The program uses static account numbers, which are incremented automatically with each new account creation.
