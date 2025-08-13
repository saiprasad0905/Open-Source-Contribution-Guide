Amending a commit is a way to modify the most recent commit you have made in your current branch. This can be helpful if you need to edit the commit message or if you forgot to include changes in the commit. You can continue to amend a commit until you push it to the remote repository.
> Use this when you need to adjust a commit you made.

# Amending a Commit

Amending a commit means making changes to your most recent commit. This is useful if you forgot to add something, made a mistake in your commit message, or want to combine small changes into one commit. You can amend a commit as long as you haven't pushed it to GitHub yet, but you can also amend after pushing (with extra care).

---

## Why Amend a Commit?

- You forgot to include a file or change in your last commit.
- You want to fix a typo or mistake in your last commit message.
- You want to keep your commit history clean by combining small changes.

---

## How to Change the Last Commit Message

If you just want to change the message of your most recent commit:

```bash
git commit --amend -m "Your new commit message"
git push origin <branch-name>
```

- If you already pushed the commit to GitHub, you may need to force push (see below).
- If you run `git commit --amend` without `-m`, your text editor will open so you can edit the message.

---

## How to Add a Missed Change to the Last Commit

Imagine you made a commit, but forgot to add a small change to a file. Here’s what you can do:

### Example commit history:
```
g56123f create file botfile
a2235d updated contributor.md
a5da0d modified botfile
```
Suppose you forgot to add a word to `botfile` in commit `a5da0d`.

### Two ways to fix this:
1. **Make a new commit** for the missed change (your history will look like this):
    ```
    g56123f create file botfile
    a2235d updated contributor.md
    a5da0d modified botfile
    b0ca8f added single word to botfile
    ```
2. **Amend the previous commit** so both changes are in one commit (recommended for small fixes):

#### Steps to amend:
- Edit the file and save your changes.
- Add the file to staging:
  ```bash
  git add <filename>
  ```
- Instead of making a new commit, run:
  ```bash
  git commit --amend
  ```
  - This opens your text editor to edit the commit message. You can keep it the same or update it.
- Save and close the editor.
- Push your changes:
  ```bash
  git push origin <branch-name>
  ```

---

## If You Already Pushed the Commit to GitHub

If you already pushed the commit and then amend it, your local history will be different from GitHub. You need to force push:

```bash
git add <your changed files>
git commit --amend -m "Your new commit message"
git push --force
```

> **Tip:**  
> Use `git push --force-with-lease` instead of `--force` for safety. This helps avoid overwriting other people's changes.

---

## ⚠️ Warning About Force Push

Force pushing will overwrite the commit history on GitHub for your branch. If others are working on the same branch, their changes might be lost. Only force push if you are sure it’s safe.

---

**In summary:**  
- Use `git commit --amend` to fix your last commit.
- Force push only if you already pushed the commit to GitHub.
- Amending is great for small fixes and keeping your history clean!
