# Dictionary (Tree Optimization)

A service that returns the meaning of words. The core challenge is the "Tree Optimization" requirement, implying the use of a Trie (Prefix Tree) or a similar data structure for efficient lookups and autocomplete suggestions.

## Functional Requirements (FR):

-   **FR01 (Search)**: A user can submit a word and receive its definition.
-   **FR02 (Autocomplete)**: As the user types, the system returns a list of valid words starting with that prefix.
    *   **Constraint**: This feature must be implemented over **WebSockets** to provide real-time, low-latency feedback as the user types.
-   **FR03 (Insert)**: (Administrative) An endpoint to add new words and definitions to the dictionary.

## Non-Functional Requirements (NFR):

-   **NFR01 (Data Structure)**: You must implement a **Trie (Prefix Tree)** or a highly optimized search tree structure to store the dictionary index in memory.
-   **NFR02 (Performance)**: Lookups should be O(L) where L is the length of the word, independent of the total dictionary size.
-   **NFR03 (Pre-loading)**: On startup, the system should load a large dataset of words (e.g., from a standard unix dictionary file) into the Trie.
