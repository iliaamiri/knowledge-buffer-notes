To update the local list of remote branches:
```bash
git remote update origin --prune
```

## Remove cached git files/folders
A folder:

```bash
git rm --cached .idea -rf
```

A file:
```bash
git rm --cached .env
```
