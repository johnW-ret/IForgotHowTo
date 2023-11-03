# Git

## Rewrite history from HEAD
Example: `HEAD~1`
```
git reset HEAD~1 # defaults to --mixed, leaves last commit changes staged
# ...
git commit # ...
git push --force
```

## Rename last commit
```
git commit --amend -m "commit message"
git push --force
```

## Rewrite root
```
git rebase -i --root
```

To exit interactive editor and save edits:
```
:wq
```

```
git push --force
```