# git pull cannot lock ref 에러

원격 브랜치와 싱크를 맞추기 위해서 git pull을 했는데 
> error: cannot lock ref 'refs/remotes/origin/{branch_name}': 'refs/remotes/origin/{branch_prefix}' exists; cannot create 'refs/remotes/origin/{branch_name}'

라는 에러가 떴다.


```
$ git gc --prune=now
$ git remote prune origin
```
명령어로 해결할 수 있다.



https://stackoverflow.com/questions/2998832/git-pull-fails-unable-to-resolve-reference-unable-to-update-local-ref
