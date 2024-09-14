
Replace all commit author
```shell
git filter-branch -f --env-filter "
    GIT_AUTHOR_NAME='0r4nd'
    GIT_AUTHOR_EMAIL='103434548+0r4nd@users.noreply.github.com'
    GIT_COMMITTER_NAME='0r4nd'
    GIT_COMMITTER_EMAIL='103434548+0r4nd@users.noreply.github.com'
  " HEAD
```
```shell
git push --force --tags origin 'refs/heads/main'
```
