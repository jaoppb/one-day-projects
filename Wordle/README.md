# Wordle

A clone of the popular word guessing game. The challenge is implementing the "Mastermind" logic (Green/Yellow/Gray feedback) and managing the daily word cycle.

## Functional Requirements (FR):

-   **FR01 (Daily Word)**: The system must select a 5-letter word for the day (or per game session).
-   **FR02 (Guess)**: Users submit a 5-letter word.
-   **FR03 (Feedback)**: The system returns the status of each letter:
    -   **Green**: Correct letter, correct position.
    -   **Yellow**: Correct letter, wrong position.
    -   **Gray**: Letter not in word.
-   **FR04 (Dictionary Check)**: The system must reject guesses that are not valid words in the target language (Portuguese, as per original request, or English).

## Non-Functional Requirements (NFR):

-   **NFR01 (Validation)**: Ensure the feedback logic correctly handles double letters (e.g., if the target is "SPEED" and user guesses "EERIE", the coloring logic must be precise).
-   **NFR02 (Limit)**: Max 6 guesses per game.
-   **NFR03 (Localization)**: The word list should be localized (pt-BR per original request, but configurable).
