# Alias 

Alias allow as to reduces are git commands and customize them as we want.

[:arrow_left: Go back to Git](./GIT.md)

## Adding alias

You can add alias to your git config using

> `git config --global alias.<name> <value>`

Following are some alias that you can use, this configurations can be place in global git config file or wherever you want.
```
    a = add -A -v
	s = status -sb
	st = status
	ci = commit
	cimd = commit --amend --no-edit
	ciamd = commit -a --amend --no-edit
	ci-feat = "!feat() { git commit -m "\":sparkles: feat: $@"\" ; }; feat"
	cia-feat = "!feat() { git commit -am "\":sparkles: feat: $@"\" ; }; feat"
	aci-feat = !git a && git cia-feat
	ci-fix = "!fix() { git commit -m "\":bug: fix: $@"\" ; }; fix"
	cia-fix = "!fix() { git commit -am "\":bug: fix: $@"\" ; }; fix"
	aci-fix = !git a && git cia-fix
	ci-docs = "!docs() { git commit -m "\":memo: docs: $@"\" ; };  docs "
	cia-docs = "!docs() { git commit -am "\":memo: docs: $@"\" ; }; docs"
	aci-docs = !git a && git cia-docs
	aci = !git add -A && git commit
	co = checkout
	cob = checkout -b
	cob-feat =!sh -c 'git checkout -b feature/$0'
	cob-fix =!sh -c 'git checkout -b fix/$0'
	cob-hot =!sh -c 'git checkout -b hotfix/$0'
	co-ours = checkout --ours
	co-theirs = checkout --theirs
	co-base = checkout --merge
	br = branch
	br-erase = !sh -c 'git branch -d $0 && git push -d origin $0'
	track = !git br -vv --list "$(git rev-parse --abbrev-ref HEAD)"
	p = push 
	pu = !git push -u origin "$(git rev-parse --abbrev-ref HEAD)"
	pl = pull
	df = diff
	dfc = !git diff $1^- 
	last = log -1 HEAD --oneline --stat
	rt = restore
	rt-s = restore -S .
    rt-w = restore -W .
	rt-all = !git rt-s && git rt-w
	rs = reset
	rs-s = reset --soft
	rs-h = reset --hard
	rs-last = reset --soft HEAD~
	rs-last-h = reset --hard HEAD~
	rb = rebase
	rb-last = rebase HEAD~
	rb-c = rebase --continue
	rb-a = rebase --abort
	lg = log --pretty='%C(magenta) %h %C(auto)%d %C(yellow)%s %C(cyan)%ah'
	lgr = lg --reverse
	lgs = lg --stat
	lgg = lg --graph
	lggs = lg --graph --stat
	sth = stash
	sth-a = stash apply
	sth-d = stash drop
	sth-dn = !sh -c 'git stash drop stash@{$0}'
	sth-p = stash pop
	sth-pn = !sh -c 'git stash pop stash@{$0}'
	sth-an = !sh -c 'git stash apply stash@{$0}'
	sth-l = stash list --oneline
	sth-ai = stash apply --index
	mg = merge
	mg-a = merge --abort
	mg-s = merge --squash
	repo = "!start `git remote get-url origin | sed -Ee 's#(git@|git://)#http://#' -e 's@com:@com/@'`"
	repo-pr = "!start $(echo `git remote get-url origin | sed -Ee 's#(git@|git://)#http://#' -e 's@com:@com/@'`/compare/master..`git rev-parse --abbrev-ref HEAD` | sed 's/s.git/s/') "
	open-config = !start $HOME/.gitconfig
	bl = blame --date=short
	bis = bisect
	bis-s = bisect start
	bis-g = bisect good
	bis-b = bisect bad
	bis-rs = bisect reset
	bis-l = bisect log
	loose = fsck --unreachable
	config-get = config --get-regexp
	ftr = fetch
	ft = !git fetch origin "$(git rev-parse --abbrev-ref HEAD)"
``` 

### Useful Resources
- [Alias wiki (useful to search commands)](https://git.wiki.kernel.org/index.php/Aliases#Aliases)