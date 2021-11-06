## 13 Advanced Git Commands

1. `git commit -am "that was easy!"` - Don't need to write `git add .` anymore.
2. `git config --global alias.ac "commit -am"` - Create alias command for `git commit -am`, so now we just need to write `git ac "message"`.
3. 1. `git commit --amend -m "new message"` - Change the message of last commit.
4. 2. `git commit --amend --no-edit` - If we forgot to include some files in the commit, use `git add somefile` then use this command to include it in the commit, with --no-edit in the commit message.
5. `git push origin master --force` - Overwrite history on remote (e.g. Github). NOTE: if there's a branch in the remote repository that is not in the local machine, it will be gone forever.
6. `git revert commitid` - Undo a commit with a NEW commit. use `git log --oneline` to get commitid.
7. `git stash` - Remove changes from current branch and save it for later. Use `git pop` to retrieve the stashed changes.
8. 1. `git stash save stashname` - Name our stash.
9. 2. `git stash list` - Get a list of our stashes.
10. 3. `git stash apply stashindex` - retrieve stash, refer by stashindex i.e. 0, 1, etc.
11. `git branch -M newname` - Rename the current branch to newname, e.g. renaming default `master` branch to `main`.
12. `git log --graph --oneline --decorate` - Pretty git log.
13. `git bisect start` - Go to a known working commit, and then walk through commit by commit to locate a bug.
14. 1. `git bisect bad` - To indicate that the commit has bugs.
15. 2. `git bisect good` - To indicate that the commit has no bugs.
16. Fixup/ Squash commit messages: Fixup is to have only one commit message, Squash is to have only one commit message that combines all the commit messages before it. When committing a branch, use `git commit --fixup` or `git commit --squash`, then use `git rebase -i --autosquash`.
17. Hooks - Run codes before or after a commit is executed. For JavaScript, we can create custom git hooks with the help of npm package `husky`.
18. `git fetch origin` && `git reset --hard origin/main` - Restore local repository to match that in the remote repository. The local changes will be lost forever
19. 1. `git clean -df` - Clean up untracked files/ build artifacts in local repository.
20. `git checkout -` - Go to the previously visited branch.
