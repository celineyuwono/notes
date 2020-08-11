## Adding branch name to your commit messages

### Result
```
git commit -m "Test Commit."
// Before
Commit Message: Test Commit.
// After
Commit Message: [branch-name] Test Commit.
```

### Steps
1. Create prepare-commit-msg file in your git repository
```
cd .git/hooks/
sudo vim prepare-commit-msg
```
2. Paste this and `:wq`.
```
NAME=$(git branch | grep '*' | sed 's/* //')  
DESCRIPTION=$(git config branch."$NAME".description)
echo ["$NAME"'] '$(cat "$1") > "$1"  
if [ -n "$DESCRIPTION" ]  
then  
   echo "" >> "$1"  
   echo $DESCRIPTION >> "$1"  
fi
```
3. Set file to executable
```
chmod +x prepare-commit-msg
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk0MjY3Nzk3MSwtOTY5NzIyMTc3XX0=
-->