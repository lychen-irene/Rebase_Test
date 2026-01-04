# Rebase_Test

I really want to add readme while creating new repo on github, so I try so hard to resolve the conflicts when I push local files.

Steps:

### At local

1. As always, create initial git repo first.

```
$ git init
```

2. Second, add all changing file into index

```
$ git add .
```

3. Third, record your change by commit message

```
$ git commit -m "feat: git init"
```

4. Fourth, remote your local project to GitHub reop so that your project is tracked and managed.

```
$ git remote add origin <ssh-url>
```

5. Fifth, because there is a readme.md on GitHub (but not in local), and there are two commit message, combine them.

```
$ git pull --rebase
```

Git document said that you can also directly run git rebase, it means the same thing.

```
$ git rebase
```

6. Error message will ask you to specify the branch or track local branch instead. Here I choose track local branch.

```
$ git branch --set-upstream-to=origin/main main
```

7. Seventh, local branch 'main' should successfully set up to track 'origin/main', so that we can successfully rebase afterwards.

```
$ git pull --rebase
```

8. Eighth, rebase should work successfully and updated refs/heads/main, so we can finally push our local project onto GitHub. Note that add option [-u | --set-upstream] for set up tracking info so that you can successfully pull again without specify branches.

```
$ git push -u origin main
```

9. Last but not least, you should see two commit records (1st commit by GitHub default, 2nd commit by user) and all branch is up to date with 'origin/main' by

```
$ git status
```
