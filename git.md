
**GIT**

```sh
git config user.name "Shahid Salim"
git config user.email "shahid.salim@hansemerkur.de"
```

```sh
git reset
```

```sh
git reset --soft HEAD~
```

```sh
git reset $(git merge-base master RIP-7606-hcp-overview-dashboard)
git add .
git commit -m "Adding Overview Dashboard"
git push --force
```
