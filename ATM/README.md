# ATM (Automated Teller Machine)

A simulation of an ATM system focusing on transaction logic, currency denomination algorithms, and concurrency safety.

## Functional Requirements (FR):

-   **FR01 (Auth)**: Users must authenticate (e.g., Card ID + PIN) to access their account.
-   **FR02 (Deposit)**: Users can deposit a specific amount of money into their account.
-   **FR03 (Withdraw)**: Users can withdraw money.
    -   *Constraint*: The system must calculate the optimal number of bills/notes to dispense (e.g., Greedy algorithm for change making).
    -   *Constraint*: Verify sufficient balance before dispensing.
-   **FR04 (Balance)**: Users can check their current account balance.
-   **FR05 (Statement)**: Users can see a history of their recent transactions.

## Non-Functional Requirements (NFR):

-   **NFR01 (Concurrency)**: Prevent race conditions. If a user tries to withdraw from two locations simultaneously, the balance must remain consistent (ACID transactions).
-   **NFR02 (Algorithm)**: The withdrawal logic must implement a specific algorithm to determine which bills to give (e.g., if user asks for 130, give 100 + 20 + 10).
-   **NFR03 (Security)**: PINs should not be stored in plain text.
