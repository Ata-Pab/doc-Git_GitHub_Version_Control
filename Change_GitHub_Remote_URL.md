# Change Remote URL of a GitHub Repository

To change the remote URL of a GitHub repository, you can use the `git remote set-url` command. This is useful if the URL of your repository has changed, or if you want to switch from HTTPS to SSH (or vice versa). You may want to add a remote project which you have worked on to your GitHub account from another location with all its history.

## Check the remotes
First, check the current remote URLs associated with your repository by running:

```bash
git remote -v
```

## Update the remote URL
To change the remote URL, use the following command:

```bash
git remote set-url origin new_url_here
```

## Verify the change
After updating the URL, verify that the change was successful by running:

```bash
git remote -v
```

## Push changes/history to the new remote
If you want to push your local repository's history to the new remote, use:

```bash
git push -u origin --all
```

## Push tags to the new remote
If you have tags that you want to push to the new remote, use:

```bash
git push --tags
```
