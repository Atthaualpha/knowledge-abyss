# Alias 

Alias allow as to reduces are git commands and customize them as we want.

*[:arrow_left: Go back to Git](./GIT.md)*

Following are some alias that you can use, this configurations can be place in global git config file or wherever you want.
```
	a = add -A
	av = add -A -v
	s = status -sb
	sl = status
	c = commit
	cam = commit -am
	caa = commit -a --amend --no-edit
	cm = commit -m
	cm-feat = "!git commit -m \"\":sparkles: feat:\"$1\" -m \"$2\" "
	cm-fix = "!git commit -m \"\":bug: fix:\"$1\" -m \"$2\" "
	cm-docs = "!git commit -m \"\":memo: docs:\"$1\" -m \"$2\" "
	acm = !git add -A && git commit -m
	co = checkout
	cob = checkout -b
	b = branch
	p = push 
	pu = push -u
	pl = pull
	difcl = "!git diff \"$1\"^- "
	last = log -1 HEAD --stat
	rs = restore
	rss = restore -S
	lg = log
	lgs = log --oneline --stat
	lgg = log --graph --oneline
	lggs = log --graph --oneline --stat
```