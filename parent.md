Here is a complete, pocket-sized guide to the Git submodule lifecycle, organized by where you need to run each command.

1. Setup & Cloning (Parent Folder)

• Add a new submodule: Run git submodule add <REPO_URL> inside the parent repo, then git commit and git push so GitHub saves the link.
• Clone a repo with submodules: Run git clone --recursive <PARENT_REPO_URL> to download the parent and all submodules at once.
• Initialize missing submodules: If you cloned without --recursive, run git submodule update --init --recursive inside the parent folder.

2. Pulling Remote Changes (Parent Folder)

• Fetch latest submodule updates: Run git submodule update --remote in the parent folder to pull the newest commits from every submodule's remote repo.
• Save the new versions: Run git add ., git commit -m "Update submodules", and git push in the parent folder so the parent locks in the latest commit hashes.

3. Editing & Pushing Code (Inside Submodule Folder)

• Avoid detached HEAD: Navigate into the submodule (cd module-A) and run git checkout main before editing so your commits attach to the real branch.
• Push submodule changes: Make your edits, then run git add ., git commit -m "Your changes", and git push inside the submodule folder.

4. Syncing the Parent Pointer (Back to Parent Folder)

• Update the parent's reference: Step back out to the parent folder (cd ..) after pushing your submodule changes.
• Commit the pointer: Run git add <SUBMODULE_NAME>, git commit -m "Point to latest submodule commit", and git push so the parent repo points to your new work.
If you want to save typing, I can show you how to set up a Git alias that updates and syncs everything with a single short command!
