# Git (Version Control System)

A basic implementation of the core plumbing commands of Git. This challenges your understanding of hashing, trees, and blobs.

## Functional Requirements (FR):

-   **FR01 (Init)**: Initialize a repository (create `.git` folder structure).
-   **FR02 (Add)**: Hash a file and store it in the object database (blob), adding it to the staging area (index).
-   **FR03 (Commit)**: Create a tree object from the index and a commit object pointing to that tree (with parent reference, author, message).
-   **FR04 (Log)**: Traverse the commit history and print it.

## Non-Functional Requirements (NFR):

-   **NFR01 (Compatibility)**: (Optional but recommended) The internal object format (zlib compressed, SHA-1 hash) should ideally be compatible with real Git, allowing `git cat-file` to read your objects.
-   **NFR02 (No Libraries)**: You cannot use `libgit2` or execute `git` commands. You must manipulate the bytes and file system manually.
-   **NFR03 (CLI)**: This project is primarily a CLI tool, not a REST API.

## Improvements

-   **FR05 (Branches)**: Ability to create and switch between branches (managing `.git/refs/heads`).
-   **FR06 (Merge)**: Ability to merge two branches.
    -   *Simple Strategy*: Fast-forward if possible.
    -   *Complex Strategy*: Create a merge commit if history has diverged (3-way merge).