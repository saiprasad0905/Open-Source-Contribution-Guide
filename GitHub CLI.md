# First Contributions

| <img alt="GitHub Desktop" src="https://cdn.icon-icons.com/icons2/2157/PNG/512/github_git_hub_logo_icon_132878.png" width="200"> | GitHub Command Line Interface (CLI) |
| ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------- |



The first requisite is to have:

- Git installed (how to install [git](https://git-scm.com/downloads))
- Github account

Now we need to install the `github-cli` tool in our system by following the [official documentation](https://github.com/cli/cli#installation)

After that, we need to login in the CLI, so enter this command:

```bash
gh auth login
```

Follow the instructions and we are ready!

# Fork this repository

It's just as easy as running this command:

```bash
gh repo fork firstcontributions/first-contributions
```

**Important: It will prompt you if you want to clone it as well, select the "yes" option**

# Create your branch

We will do this step with git, so enter this command replacing the name with your name, for example:

```bash
git switch -c add-john-doe
```

# Make necessary changes and commit those changes

Now you can open `Contributors.md` file in a text editor and add your name to it. Put your name anywhere between the beginning and the end, then save the file.

In the project directory execute `git status` and you will see the changes.
<img align="right" width="450" src="https://firstcontributions.github.io/assets/Readme/git-status.png" alt="git status" />

Add those changes to the branch you just created using the `git add` command:
`git add Contributors.md`

Now commit those changes using the `git commit` command:
`git commit -m "Add your-name to Contributors list"`
replacing `your-name` with your name.

# Push changes to github

Push your changes using the command `git push`:

```
git push origin -u your-branch-name
```

replacing `your-branch-name` with the name of the branch you created earlier.

<details>
<summary> <strong>If you get any errors while pushing, click here:</strong> </summary>

- ### Authentication Error
     <pre>remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
  remote: Please see https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ for more information.
  fatal: Authentication failed for 'https://github.com/<your-username>/first-contributions.git/'</pre>
  Go to [GitHub's tutorial](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) on generating and configuring an SSH key to your account.

</details>

# Submit your changes for review

Now running this command in our repo's directory will let us create a pull request for review:

```bash
gh pr create --repo firstcontributions/first-contributions
```

After that submit the pull request.

You can use the command `gh status` to see your mentioned pull request in action.


