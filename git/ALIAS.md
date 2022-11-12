# Alias 

Alias allow as to reduces are git commands and customize them as we want.

@[:arrow_left: Go back to Git](./GIT.md)@

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
	lg = log
	lgl = log --oneline
	lgs = log --oneline --stat
	lgg = log --graph --oneline
	lggs = lgg --graph --oneline --stat
	sth = stash
	sth-a = stash apply
	sth-d = stash drop
	sth-dn = !sh -c 'git stash drop stash@{$0}'
	sth-p = stash pop
	sth-pn = !sh -c 'git stash pop stash@{$0}'
	sth-an = !sh -c 'git stash apply stash@{$0}'
	sth-l = stash list
	sth-ai = stash apply --index
	mg = merge
	mg-a = merge --abort
	repo = "!start `git remote get-url origin | sed -Ee 's#(git@|git://)#http://#' -e 's@com:@com/@'`| head -n1"
	gcfg = !start $HOME/.gitconfig
	back = checkout -q -
``` 

### Useful Resources
- [Alias wiki (useful to search commands)](https://git.wiki.kernel.org/index.php/Aliases#Aliases)