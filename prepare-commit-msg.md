Create prepare-commit-msg file in your git repository

    cd .git/hooks/
    sudo vim prepare-commit-msg
  

```
NAME=$(git branch | grep '*' | sed 's/* //')  
DESCRIPTION=$(git config branch."$NAME".description)echo ["$NAME"'] '$(cat "$1") > "$1"  
if [ -n "$DESCRIPTION" ]  
then  
   echo "" >> "$1"  
   echo $DESCRIPTION >> "$1"  
fi
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkwMjQyODA5XX0=
-->