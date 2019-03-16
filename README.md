# Commit logger
Collects all commits from all projects to one place.

I have to report to my master what have been done during day, sometimes i forget to write raport, someites ithappens for whole week, then its realy hard to track what have been done on particular days, so this small hook, will collect the commints in one place and devide commits by days, so it will be much easer to look at particular days commits.

So what it does. After commit it logs the commit's project path, time and commit comment to the log file. Log file is named by date, so each day will have all the commits in that day, for all projects at that day.

!!! Notice, the hook will be added only to new projects, to old one, have to add it by hand

# Adding/linking template dir, so that all next/new projects would have this hook in place
1. Cloning project to a local dir
```bash
git clone https://github.com/lauzis/commit-logger.git ~/.git-templates
```

2. Allow to execute shell script
```bash
chmod a+x ~/.git/hooks/post-commit
```


2. Adding dir for commit logs
```bash
mkdir ~/git_commit_logs
```

3. Link git to local templates
```bash
git config --global init.templatedir '~/.git-templates'
#source https://coderwall.com/p/jp7d5q/create-a-global-git-commit-hook
```



# Copy hook to existing projects
go to project root dir, where .git directory resides
```bash
cp ~/.git-templates/hooks/post-commit ./.git/hooks/
```
