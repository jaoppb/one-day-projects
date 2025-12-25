# Word Searcher (Large File Processing)

This project focuses on efficient file processing and memory management. The challenge is to read a "HUGE" file (potentially larger than available RAM) and count word frequencies.

## Functional Requirements (FR)

- **FR01 (Input)**: The system must accept a large text file (or a path to one).
- **FR02 (Processing)**: The system must parse the file and count the occurrences of every distinct word.
- **FR03 (Output)**: The system should allow querying the count of a specific word or exporting the top N most frequent words.
- **FR04 (Pagination)**: The system should allow reading the file in chunks or "pages" if the user wants to inspect the raw content without loading everything.

## Non-Functional Requirements (NFR)

- **NFR01 (Streams/Buffering)**: You cannot load the entire file into memory at once. You must use streams or read the file line-by-line/chunk-by-chunk.
- **NFR02 (Performance)**: The counting algorithm should be efficient (e.g., using HashMaps/Dictionaries).
- **NFR03 (Generator)**: Include a script or function to generate a dummy "huge" file (e.g., 1GB of random text) for testing purposes.
