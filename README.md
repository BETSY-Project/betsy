# Git Submodules: Update and Push (client, server, clm...)

## Option 1: Fetch Latest Changes from Submodules

1.  **Update all submodules:**
    ```bash
    git submodule update --remote --merge
    ```
2.  **Commit and push changes in the main project:**
    ```bash
    git add client clm server # or git add .
    git commit -m "Update submodules client, clm, server"
    git push
    ```

## Option 2: Push Changes Made WITHIN a Submodule

If you have modified code *directly within* `clm` or `server` (or `client`):

1.  **For each modified submodule (e.g., `clm`):**
    ```bash
    cd clm # or cd server, or cd client
    git add .
    git commit -m "Changes in clm" # Adapt the message and submodule name
    git push
    cd ..
    ```
2.  **Once all modified submodules are pushed, in the main project:**
    ```bash
    git add client clm server # Add all submodules that were individually modified and pushed
    git commit -m "Update submodule pointers (client, clm, server)" # Adapt if needed
    git push
    ```

**Note:** The commands above include `client` as a potential submodule, in addition to `clm` and `server`. Adapt the submodule names in the `add` commands and commit messages according to the submodules actually modified.
