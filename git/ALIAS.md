# Alias 

Alias allow as to reduces are git commands and customize them as we want.

@[:arrow_left: Go back to Git](./GIT.md)@

Following are some alias that you can use, this configurations can be place in global git config file or wherever you want.
```
	a = add -A
	av = add -A -v
	s = status -sb
	st = status
	ci = commit
	cimd = commit -a --amend --no-edit
	ci-feat = "!feat() { git commit -m "\":sparkles: feat: $@"\" ; }; feat"
	cia-feat = "!feat() { git commit -am "\":sparkles: feat: $@"\" ; }; feat"
	ci-fix = "!fix() { git commit -m "\":bug: fix: $@"\" ; }; fix"
	cia-fix = "!fix() { git commit -am "\":bug: fix: $@"\" ; }; fix"
	ci-docs = "!docs() { git commit -m "\":memo: docs: $@"\" ; }; docs"
	cia-docs = "!docs() { git commit -am "\":memo: docs: $@"\" ; }; docs"
	acm = !git add -A && git commit -m 
	co = checkout
	cob = checkout -b	
	br = branch
	p = push  
	pu = push -u
	pl = pull
	dfc = !git diff $1^- 
	last = log -1 HEAD --stat
	rs = restore
	rss = restore -S
	lg = log
	lgs = log --oneline --stat
	lgg = log --graph --oneline
	lggs = lgg --stat
``` 